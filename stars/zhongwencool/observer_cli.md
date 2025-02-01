---
project: observer_cli
stars: 1410
description: Visualize Erlang/Elixir Nodes On The Command Line
url: https://github.com/zhongwencool/observer_cli
---

* * *

observer\_cli
=============

Visualize Erlang/Elixir Nodes On The Command Line base on recon. Document in detail.

Goal
----

-   Provide a high-performance tool usable both in development and production settings.
-   Focus on important and detailed information about real-time running system.
-   Keep minimal consumption.

* * *

### Installation

**Erlang**

%% rebar.config
{deps, \[observer\_cli\]}
%% erlang.mk
dep\_observer\_cli \= hex 1.8.1

**Elixir**

\# mix.exs
   def deps do
     \[{:observer\_cli, "~> 1.8"}\]
   end

* * *

### How-To

#### Try in local shell.

%% rebar3 project
rebar3 shell
1\> observer\_cli:start().
%% mix project
iex \-S mix
iex(1)\> :observer\_cli.start

#### Monitor remote node

%% rebar3 project
rebar3 shell \--name 'observer\_cli@127.0.0.1'
1\> observer\_cli:start('target@host', 'magic\_cookie').
%% mix project
iex \--name "observer\_cli@127.0.0.1" \-S mix
iex(1)\> :observer\_cli.start(:'target@host', :'magic\_cookie')

❗ **ensure observer\_cli application been loaded on target node.**

#### Try in Elixir 1.9.x release

%% create elixir release
mix release
%% rpc current node
\_build/dev/rel/example/bin/example rpc ":observer\_cli.start"

❗ **ensure observer\_cli application been loaded on current node.**

#### Escriptize

1.  cd path/to/observer\_cli/
2.  `rebar3 escriptize` to generate an escript executable containing the project's and its dependencies' BEAM files. Place script(`_build/default/bin/observer_cli`) anywhere in your path and use `observer_cli` command.
3.  `observer_cli TARGETNODE [TARGETCOOKIE REFRESHMS]` to monitor remote node.

* * *

### DEMO

### How to write your own plugin?

If you need to customize some of your internal metrics and integrate it into observer\_ci, you only need to write a `observer_cli_plugin` behaviour in a few simple steps to get a nice presentation.

1.  Configure observer\_cli，tell observer\_cli how to find your plugin.

%% module       - Specific module implements plugin behavior. It's mandatory.
%% title        - Menu title. It's mandatory.
%% shortcut     - Switch plugin by shortcut. It's mandatory.
%% interval     - Refresh interval ms. It's optional. default is 1500ms.
%% sort\_column  - Sort the sheet by this index. It's optional default is 2.

{plugins,
  \[
    #{module \=> observer\_cli\_plug\_behaviour\_x, title \=> "XPlug",
      interval \=> 1600, shortcut \=> "X", sort\_column \=> 3},
    #{module \=> observer\_cli\_plug\_behaviour\_y, title \=> "YPlug",
      interval \=>2000, shortcut \=> "Y", sort\_column \=> 3}
  \]
}

The main view is `HOME` by default(`observer_cli:start()`). If you want to plugin view as main view, DO:`your_cli:start().`

% your\_cli.erl
start() \-> observer\_cli:start\_plugin().

1.  Write observer\_cli\_plugin behaviour. observer\_cli\_plugin has 3 callbacks.

2.1 attributes.

\-callback attributes(PrevState) \-> {\[Rows\], NewState} when
    Rows :: #{content \=> string()|integer()|{byte, pos\_integer()},
              width \=> pos\_integer(), color \=> binary()}.

for example:

attributes(PrevState) \->
  Attrs \= \[
    \[
      #{content \=> "XXX Ets Size", width \=> 15},
      #{content \=> 122, width \=> 10},
      #{content \=> "Memory Capcity", width \=> 15},
      #{content \=> {percent, 0.12}, width \=> 16},
      #{content \=> "XYZ1 Process Mem", width \=> 19},
      #{content \=> {byte, 1023 \* 1203}, width \=> 19}
    \],
    \[
      #{content \=> "YYY Ets Size", width \=> 15},
      #{content \=> 43, width \=> 10},
      #{content \=> "Disk Capcity", width \=> 15},
      #{content \=> {percent, 0.23}, width \=> 16},
      #{content \=> "XYZ2 Process Mem", width \=> 19},
      #{content \=> {byte, 2034 \* 220}, width \=> 19}
    \],
    \[
      #{content \=> "ZZZ Ets Size", width \=> 15},
      #{content \=> 108, width \=> 10},
      #{content \=> "Volume Capcity", width \=> 15},
      #{content \=> {percent, 0.101}, width \=> 16},
      #{content \=> "XYZ3 Process Mem", width \=> 19},
      #{content \=> {byte, 12823}, width \=> 19}
    \]
  \],
  NewState \= PrevState,
  {Attrs, NewState}.

|Home(H)|XPlug(X)|YPlug(Y)| | 0Days 3:34:50 |
|XXX Ets Size | 122 | Memory Capcity | 12.00% | XYZ1 Process Mem | 1.1737 MB |
|YYY Ets Size | 43 | Disk Capcity | 23.00% | XYZ2 Process Mem | 436.9922 KB |
|ZZZ Ets Size | 108 | Volume Capcity | 10.10% | XYZ3 Process Mem | 12.5225 KB |

\-callback sheet\_header() \-> \[SheetHeader\] when
    SheetHeader :: #{title \=> string(), width \=> pos\_integer(), shortcut \=> string()}.

for example:

sheet\_header() \->
  \[
    #{title \=> "Pid", width \=> 15},
    #{title \=> "Register", width \=> 20},
    #{title \=> "Memory", width \=> 20, shortcut \=> "S"},
    #{title \=> "Reductions", width \=> 23, shortcut \=> "R"},
    #{title \=> "Message Queue Len", width \=> 23, shortcut \=> "Q"}
  \].

|No |Pid |Register |Memory(S) |Reductions(R) |Message Queue Len(Q) |

\-callback sheet\_body(PrevState) \-> {\[SheetBody\], NewState} when
    PrevState :: any(),
    SheetBody :: list(),
    NewState :: any().

for example:

sheet\_body(PrevState) \->
  Body \= \[
    begin
      Register \=
        case erlang:process\_info(Pid, registered\_name) of
          \[\] -> \[\];
          {\_, Name} -> Name
        end,
      \[
        Pid,
        Register,
        {byte, element(2, erlang:process\_info(Pid, memory))},
        element(2, erlang:process\_info(Pid, reductions)),
        element(2, erlang:process\_info(Pid, message\_queue\_len))
      \]
    end
    || Pid <- erlang:processes()
  \],
  NewState \= PrevState,
  {Body, NewState}.

Support `{byte, 1024*10}` to `10.0000 KB`; `{percent, 0.12}` to `12.00%`.

|No |Pid |Register |Memory(S) |Reductions(R) |Message Queue Len(Q) |
|1 |<0.242.0> | | 4.5020 MB | 26544288 | 0 |
|2 | <0.206.0> | | 1.2824 MB | 13357885 | 0 |
|3 | <0.10.0> | erl\_prim\_loader | 1.0634 MB | 10046775 | 0 |
|4 | <0.434.0> | | 419.1719 KB | 10503690 | 0 |
|5 | <0.44.0> | application\_contro | 416.6250 KB | 153598 | 0 |
|6 | <0.50.0> | code\_server | 416.4219 KB | 301045 | 0 |
|7 | <0.9.0> | rebar\_agent | 136.7031 KB | 1337603 | 0 |
|8 | <0.207.0> | | 99.3125 KB | 9629 | 0 |
|9 | <0.58.0> | file\_server\_2 | 41.3359 KB | 34303 | 0 |
|10 | <0.209.0> | | 27.3438 KB | 31210 | 0 |
|11 | <0.0.0> | init | 25.8516 KB | 8485 | 0 |
|refresh: 1600ms q(quit) Positive Number(set refresh interval time ms) F/B(forward/back) Current pages is 1 |

Support F/B to page up/down.

A more specific plugin can collect linux system information such as kernel vsn, loadavg, disk, memory usage, cpu utilization, IO statistics.

* * *

### Changelog

-   1.8.1
    
    -   Show node name in system pane.
-   1.8.0
    
    -   Support `<Pid` to jump to specific pid.
    -   Show process's label if it's set with proc\_lib:set\_label(Label)
    -   Show The number of bytes in the output distribution queue on System View. This queue sits between the Erlang code and the port driver, using undocumented function`erlang:dist_get_stat/1`.
    -   Fix Doc View not show when otp version = 27
-   1.7.5
    
    -   Fix crash when mnesia table with external copies. Which `mnesia:table_info(TabName, storage_type)` returns tuple `{ext, _, _}`
    -   Correct the order of the application information; the items Memory and Reductions have been switched.
-   1.7.4
    
    -   fix crash when ets:info/1 return undefined.
-   1.7.3
    
    -   fix system pane exception by `ps` command.
-   1.7.2
    
    -   Fix error when inspecting process that monitors via {RegName, Node}.
-   1.7.1
    
    -   application view show starting/loading/startPfalse/loaded/started application.
    -   fixed badarg when staring by rpc and stop by `ctrl+c`.
    -   fixed mix.exe version error
-   1.7.0
    
    -   application view support reductions/memory/process\_count sort
    -   plugin support `{byte, 1024}` to `10.0000 KB`
    -   plugin support `{percent, 0.1234` to `12.34%`
    -   plugin support dig deep process view.
-   1.6.2
    
    -   fixed crash when ps command not found on windows.
-   1.6.1
    
    -   remove precise opt version
-   1.6.0
    
    -   hidden schedule usage default
    -   format by erlformat
    -   add `ps -o pcpu,pmem,rss,vsz` information
    -   remove recon\_alloc:memory/1 from `HOME`(too much cpu usage)
-   1.5.4
    
    -   Bump Recon to 2.5.1 for otp23 alloc compat.
-   1.5.2
    
    -   Use erlang:system\_info(otp\_release) when can't find `OTP_VERSION` file for the full version.
-   1.5.1
    
    -   Hide mnesia tab when it's not started
    -   Show specific erl version such as '22.0.5'
-   1.5.0
    
    -   Bump Recon to 2.5.0
-   1.4.5
    
    -   Include a minimal mix.exs build file
    -   Make sure EXIT message has been clear
-   1.4.4
    
    -   Make sure connection errors can be handled
-   1.4.3
    
    -   Bump Recon to 2.4.0
-   1.4.2
    
    -   Hidden schedule process bar when core > 100.
    -   Allow to compile escript w/ inet6 based distribution.
    -   Rewrite plugin callback, rename kv\_label/0 to attributes/1.
-   1.4.1
    
    -   Fixed ets view memory usage wrong.
    -   mnesia view memory usage According to bytes.
-   1.4.0
    
    -   Support write your own plugin.
-   1.3.4
    
    -   View(ets mnesia) support page down/up; support sort by memory or size.
    -   Fixed pause crash.
    -   Make refresh interval configurable.
-   1.3.3
    
    -   fixed io:format(Format,Args) Format not support iolist OTP R21
-   1.3.2
    
    -   Make sure all observer\_cli process exit when quit.
    -   Upgrade recon to 2.3.6
-   1.3.1
    
    -   Add atom limit/count in home.
    -   Escript support short name and long name.
    -   Fixed store process not exit.
    -   Upgrade recon to 2.3.5
-   1.3.0
    
    -   Rewrite Network/Process view.
    -   Support PageDown/PageUp for top n list.
    -   Escript auto load observer\_cli when it's not load on target node.
-   1.2.2
    
    -   fix schedule number >= 32 display wrong.
    -   improve memory(byte/kilobyte/megabyte/gigabyte) unit.
-   1.2.1
    
    -   fixed autosize not work.
    -   try best to make color adjust all platform.
-   1.2.0
    
    -   add application GUI.
    -   Rearrange GUI and optimize render.
    -   Always automatically adapt to the window size.
-   1.1.0
    
    -   Support escript, `observer_cli <TARGETNODE> <COOKIE>`
-   1.0.9
    
    -   Upgrade rebar3 to 3.3.3 for publish hex repo.

* * *

### Contributors

  
zhongwencool  
💻

  
Dimitrios Zorbas  
💻

  
taotao  
💻

  
Trevor Brown  
💻

  
Zaiming Shi  
💻

* * *

### License

See the LICENSE file for license rights and limitations (MIT).
