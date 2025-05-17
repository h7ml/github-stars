---
project: elixir-ls
stars: 1601
description: A frontend-independent IDE "smartness" server for Elixir. Implements the "Language Server Protocol" standard and provides debugger support via the "Debug Adapter Protocol"
url: https://github.com/elixir-lsp/elixir-ls
---

ElixirLS - Elixir Language Server and Debug Adapter
===================================================

ElixirLS is provides two components: a language server driving code intelligence and a debug adapter that allows step through debugging of Elixir projects. Language server adheres to the Language Server Protocol. Debug adapter implements Debug Adapter Protocol.

This is the main elixir-ls repo
-------------------------------

This repo is a community maintained fork. The original repository JakeBecker/elixir-ls has now been deprecated in favor of this one.

Features
--------

-   Debugger support
-   Automatic, incremental Dialyzer analysis
-   Automatic inline suggestion of @specs based on Dialyzer's inferred success typings
-   Inline reporting of build warnings and errors
-   Documentation lookup on hover
-   Go-to-definition
-   Code completion
-   Code formatter
-   Find references to functions and modules (Thanks to @mattbaker)
-   Quick symbol lookup in file (Thanks to @mattbaker)
-   Quick symbol lookup in workspace and stdlib (both Elixir and erlang) (@lukaszsamson)

Note: On its first run, Dialyzer will build a PLT cache. This will take a considerable amount of CPU time (usually 10+ minutes). After that is complete, the CPU usage will go back to normal. Alternatively, instead of waiting you can disable Dialyzer in the settings.

IDE plugins
-----------

IDE

Plugin

Support

BBEdit

bbpackage

Emacs

eglot

Emacs

lsp-mode

Supports debug adapter via dap-mode

Kakoune

kak-lsp

Limitations

Kate

built-in LSP Client plugin

Does not support debug adapter

Neovim

coc.nvim

Does not support debug adapter

Neovim

nvim-dap

Supports debug adapter only

Neovim

nvim-lspconfig

Does not support debug adapter

Nova

nova-elixir-ls

Sublime Text

LSP-elixir

Does not support debug adapter

Vim/Neovim

ALE

Does not support debug adapter or @spec suggestions

Vim/Neovim

elixir-lsp/coc-elixir

Does not support debug adapter

Vim/Neovim

vim-lsp

Does not support debug adapter

VS Code

elixir-lsp/vscode-elixir-ls

Supports all ElixirLS features

Helix

elixir-lsp

Supports all ElixirLS features

Zed

elixir language support

Supports all ElixirLS features

Please feel free to create and publish your own client packages and add them to this list!

Detailed Installation Instructions
----------------------------------

The installation process for ElixirLS depends on your editor.

VSCode

Please install the extension via the following link: https://marketplace.visualstudio.com/items?itemName=JakeBecker.elixir-ls

Emacs Installation Instructions

Download the latest release and unzip it into a directory. (This is the directory referred to as the `"path-to-elixir-ls/release"`, below.)

If you will be using `lsp-mode`, add this configuration:

  (use-package lsp-mode
    :commands lsp
    :ensure t
    :diminish lsp-mode
    :hook
    (elixir-mode . lsp)
    :init
    (add-to-list 'exec-path "path-to-elixir-ls/release"))

For `eglot`, use:

(require 'eglot)

;; This is optional. It automatically runs \`M-x eglot\` for you whenever you are in \`elixir-mode\`:
(add-hook 'elixir-mode-hook 'eglot-ensure)

;; Be sure to edit the path appropriately; use the \`.bat\` script instead for Windows:
(add-to-list 'eglot-server-programs '(elixir-mode "path-to-elixir-ls/release/language\_server.sh"))

If you access any projects via symlinks, and the lsp crashes immediately on startup in those projects, you might need this:

(setq find-file-visit-truename t)

Supported Elixir and OTP versions
---------------------------------

Elixir itself supports the last five released versions with security updates: https://hexdocs.pm/elixir/compatibility-and-deprecations.html#content

OTP supports the last three versions with security updates: https://github.com/erlang/otp/blob/master/SECURITY.md#supported-versions https://www.erlang.org/doc/system/misc.html#supported-releases

ElixirLS generally aims to support all supported versions of Elixir on all compatible versions of OTP. However this is not a hard and fast rule and may change in the future.

### Support matrix

OTP Versions

Elixir Versions

Supports ElixirLS

Issue(s)

any

<= 1.13

No

Broken, no support for required APIs

22

1.13

?

Erlang docs not working (requires EIP 48), May still work but no longer supported

23

1.13

?

May still work but no longer supported

24

1.13

?

May still work but no longer supported

25

1.13.4

?

May still work but no longer supported

23

1.14

Yes

None

24

1.14 - 1.16

Yes

None

25

1.14 - 1.18

Yes

None

26.0.0 - 26.0.1

any

No

#886

26.0.2 - 26.1.2

1.14.5 - 1.18

\*nix only

#927, #1023

\>= 26.2.0

1.14.5 - 1.18

Yes

None

any

1.15.5

Yes

Broken formatter #975

27

1.17 - 1.18

Yes

None

### Version management

It is generally recommended to install Elixir and Erlang via a version manager so that you can have different projects using different versions of Elixir without having to change your system-installed version. Supported managers include:

-   asdf
-   mise
-   vfox

ElixirLS launch script will attempt to activate found version manager.

#### Windows

Version managers are currently not supported on Windows. mise and vfox may work if activated.

Debugger support
----------------

ElixirLS provides debug adapter support adhering to the Debug Adapter Protocol, which is closely related to the Language Server Protocol.

When debugging in Elixir or Erlang, only modules that have been "interpreted" (using `:int.ni/1` or `:int.i/1`) will accept breakpoints or show up in stack traces. The debugger in ElixirLS automatically interprets all modules in the Mix project and its dependencies before launching the Mix task. Therefore, you can set breakpoints anywhere in your project or dependency modules.

Please note that there is currently a limit of 100 breakpoints.

To debug modules in `.exs` files (such as tests), they must be specified under `requireFiles` in your launch configuration so that they can be loaded and interpreted before running the task. For example, the default launch configuration for `mix test` in the VSCode plugin is shown below:

{
  "type": "mix\_task",
  "name": "mix test",
  "request": "launch",
  "task": "test",
  "taskArgs": \["\--trace"\],
  "startApps": true,
  "projectDir": "${workspaceRoot}",
  "requireFiles": \["test/\*\*/test\_helper.exs", "test/\*\*/\*\_test.exs"\]
}

Currently, to debug a single test or a single test file, it is necessary to modify `taskArgs` and ensure that no other tests are required in `requireFiles`.

{
  "type": "mix\_task",
  "name": "mix test",
  "request": "launch",
  "task": "test",
  "taskArgs": \["tests/some\_test.exs:123"\],
  "startApps": true,
  "projectDir": "${workspaceRoot}",
  "requireFiles": \["test/\*\*/test\_helper.exs", "test/some\_test.exs"\]
}

### Debugging Phoenix apps

To debug Phoenix applications using ElixirLS, you can use the following launch configuration:

{
  "type": "mix\_task",
  "name": "phx.server",
  "request": "launch",
  "task": "phx.server",
  "projectDir": "${workspaceRoot}",
  "debugAutoInterpretAllModules": false,
  "debugInterpretModulesPatterns": \["MyApp\*", "MyAppWeb\*"\],
  "exitAfterTaskReturns": false
}

In case of phoenix apps it is generally not advised to interpret all modules. Cowboy and ecto have known performance issues when run in interpreted mode. The example configuration disables auto interpreting and instead makes the DAP interpret only a subset of modules.

Note that `exitAfterTaskReturns` is set to `false`. Otherwise DAP session will end immediately after starting because mix task `phx.server` returns control to the caller.

Please make sure that `startApps` is not set to `true`. To clarify, `startApps` is a configuration option in the ElixirLS debug adapter. It controls whether or not to start the applications in the Mix project before running the task. In the case of Phoenix applications, setting `startApps` to `true` can interfere with the application's normal startup process and cause issues.

If you are running tests in the Phoenix application, you may need to set `startApps` to true. This will ensure that the necessary applications are started before the tests run.

#### Known issues

-   Phoenix live reload and CodeReloader is not compatible with debug adapter. It will purge and recompile beams running in interpreted mode, unset breakpoints and corrupt the debug session phoenix\_live\_reload issue
    
-   When cowboy and/or ecto modules are interpreted the DAP server leaks enormous amount of heap memory on every request. The reason is unknown. GH issue
    

### NIF modules limitation

It's important to note that NIF (Native Implemented Function) modules cannot be interpreted due to limitations in `:int`. Therefore, these modules need to be excluded, using the `excludeModules` option. This option can also be used to disable interpretation for specific modules when it's not desirable, such as when performance is unsatisfactory.

{
  "type": "mix\_task",
  "name": "mix test",
  "request": "launch",
  "task": "test",
  "taskArgs": \["\--trace"\],
  "projectDir": "${workspaceRoot}",
  "requireFiles": \["test/\*\*/test\_helper.exs", "test/\*\*/\*\_test.exs"\],
  "excludeModules": \[":some\_nif", "Some.SlowModule"\]
}

### Function breakpoints

Function breakpoints in ElixirLS allow you to break on the first line of every clause of a specific function. In order to set a function breakpoint, you need to specify the function in the format of MFA (module, function, arity).

For example, to set a function breakpoint on the `foo` function in the `MyModule` module that takes one argument, you would specify it as `MyModule.foo/1`.

Please note that function breakpoints only work for public functions and do not support breaking on private functions.

### Conditional breakpoints

Break conditions allow you to specify an expression that, when evaluated, determines whether the breakpoint should be triggered or not. The expression is evaluated within the context of the breakpoint, which includes all bound variables.

For example, you could set a breakpoint on a line of code that sets a variable `x`, adding a break condition of `x > 10`. This would cause the breakpoint to trigger when that line of code is executed, but only if the value of `x` is greater than `10` when that line of code is executed.

However, it's important to note that the expression evaluator used by ElixirLS has some limitations. For example, it doesn't support some Elixir language features, such as macros and some built-in functions. In addition, the expression evaluator is not as powerful as the one used by the Elixir interpreter, so some expressions that work in the interpreter may not work in ElixirLS.

### Hit conditions

A "hit condition" is an optional parameter that can be set on a breakpoint to control how many times a breakpoint should be hit before stopping the process. It is expressed as an integer and can be used to filter out uninteresting hits, allowing the process to continue until a certain condition is met.

For example, if you have a loop that runs 10 times and you want to stop the process only when the loop reaches the 5th iteration, you can set a breakpoint with a hit condition of five. This will cause the breakpoint to be hit only on the 5th iteration of the loop; the process will continue to run until then.

### Log points

"Log points" are a type of breakpoint that logs a message to the standard output without stopping program execution. When a log point is hit, the message is evaluated and printed to the console. The message can include interpolated expressions enclosed in curly braces `{}`, e.g. `my_var is {inspect(my_var)}`. These expressions will be evaluated in the context of the breakpoint. To escape the curly braces, you can use the escape sequence `\{` and `\}`.

It's important to note that as of version 1.51 of the Debug Adapter Protocol specification, log messages are not supported on function breakpoints.

### Expression evaluator

The debugger's expression evaluator has some limitations due to how the Erlang VM works. Specifically, the evaluator is implemented using `:int`, which works at the level of individual BEAM instructions. As a result, it returns multiple versions of variables in Static Single Assignment form, without indicating which one is valid in the current Elixir scope.

To work around this, the evaluator uses a heuristic to select the highest versions of variables. However this doesn't always behave correctly in all cases. For example, in the following code snippet:

a \= 4
if true do
  a \= 5
end
some

If a breakpoint is set on the line with `some_function()`, the last bound value for `a` seen by the expression breakpoint evaluator will be `5`, even though it should be `4`.

Additionally, although all bound variables are accessible in the expression evaluator, the evaluator doesn't support accessing module attributes (because these are determined at compile time).

### Connecting to debug adapter

It may be useful to connect to a running debug adapter node via OTP distribution. This enables inspecting the running application and remotely triggering debugged functions. In order to do so, set `ELS_ELIXIR_OPTS` environment variable in the launch configuration (VSCode only) or **Local setup script** and pass in the appropriate node `name/sname` and `cookie`.

{
  "env": {
    "ELS\_ELIXIR\_OPTS": "\--name mynode@localhost --cookie secret"
  }
}

### Attaching to remote nodes

ElixirLS debug adapter is capable of remote debugging OTP cluster nodes. This functionality relies on OTP debugger. In order to attach to a remote node `some@host` a special launch config with request `attach` is needed. The launch config must specify `remoteNode`. Remember to provide `ELS_ELIXIR_OPTS` environment variable in the launch configuration (VSCode only) or **Local setup script** with `cookie` and `name` or `sname` for local DAP node.

{
  "type": "mix\_task",
  "name": "attach",
  "request": "attach",
  "projectDir": "${workspaceRoot}",
  "remoteNode": "some@host",
  "debugAutoInterpretAllModules": false,
  "debugInterpretModulesPatterns": \["MyApp.\*"\],
  "env": {
    "ELS\_ELIXIR\_OPTS": "\--sname elixir\_ls\_dap --cookie mysecret"
  }
}

#### Troubleshooting

-   Ensure that the remote node is accessible and accepting connections
-   Ensure that erlang cookie is correct
-   Ensure that OTP `debugger` application is loadable on remote node. This may require including it in `extra_applications`
-   If connecting to an OTP release, ensure that it is built with `strip_beams` set to `false`. Note that it defaults to `true`
-   Ensure that remote node application has not been compiled with `debug_info` set to `false` via `elixirc_options` or `@compile` attribute
-   Ensure that both source files and compiled beams are available in the project directory

#### Limitations

Remote debugger has several limitations compared to local debugger:

-   `dbg` macro breakpoints are not supported
-   conditional breakpoints, hit conditional breakpoints and log points are not supported
-   pausing non interpreted processes is not supported
-   expressions are evaluated on local node

#### Warning

ElixirLS debug adapter interprets modules with `:int.ni/1` on all connected nodes. It attempts to uninterpret all modules on debug session end but that may not be possible due to loss of connectivity. This may affect production workloads. Use remote debugging with caution.

Automatic builds and error reporting
------------------------------------

ElixirLS provides automatic builds and error reporting. By default, builds are triggered automatically when files are saved, but you can also enable "autosave" in your IDE to trigger builds as you type. If you prefer to disable automatic builds, you can set the `elixirLS.autoBuild` configuration option to `false`.

Internally, ElixirLS uses the `mix compile` task to compile Elixir code. When errors or warnings are encountered during compilation, they are returned as LSP diagnostics. Your IDE may display them inline in your code as well as in the "Problems" pane. This allows you to quickly identify and fix errors in your code as you work.

Dialyzer integration
--------------------

Dialyzer is a static analysis tool used to identify type discrepancies, unused code, unreachable code, and other warnings in Erlang and Elixir code. ElixirLS provides automatic integration with Dialyzer to help catch issues early on in the development process.

After each successful build, ElixirLS automatically analyzes the project with Dialyzer and maintains a "manifest" file in .elixir\_ls/dialyzer\_manifest to store the results of the analysis. The initial analysis of a project can take a few minutes, but subsequent analyses are usually very fast, often taking less than a second. ElixirLS also looks at your modules' abstract code to determine whether they reference any modules that haven't been analyzed and includes them automatically.

You can control which warnings are shown by using the `elixirLS.dialyzerWarnOpts` setting in your project or IDE's `settings.json`. You can find available options in dialyzer documentation, under the section "Warning options".

To disable Dialyzer completely, set `elixirLS.dialyzerEnabled` to false.

If Dialyzer gets stuck and emits incorrect or outdated warnings, it's best to restart the language server.

Code completion
---------------

ElixirLS provides an advanced code completion provider. This provider uses two main mechanisms to provide suggestions to the user.

The first mechanism is reflection, which involves getting information about compiled modules from the Erlang and Elixir APIs. This mechanism provides precise results, but it is not well suited for on-demand completion of symbols from the currently edited file. The compiled version of the code may be outdated or the file may not even compile, which can lead to inaccurate results.

The second mechanism used by the code completion provider is AST analysis of the current text buffer. This mechanism helps in cases where reflection is not accurate enough (e.g., completing symbols from the currently edited file). However, it also has its limitations. Due to the metaprogramming-heavy nature of Elixir, it is infeasible to be 100% accurate with AST analysis.

The completions include:

-   keywords
-   special form snippets
-   functions
-   macros
-   modules
-   variables
-   sigils
-   struct fields (only if the struct type is explicitly stated or can be inferred from the variable binding)
-   atom map keys (if map keys can be inferred from variable binding)
-   attributes
-   binary modifiers
-   types (in typespecs)
-   behaviour callbacks (inside the body of implementing module)
-   protocol functions (inside the body of implementing module)
-   keys in keyword functions arguments (if defined in spec)
-   function returns (if defined in spec)

Workspace Symbols
-----------------

With Dialyzer integration enabled, ElixirLS will build an index of symbols (modules, functions, types, and callbacks). The symbols are taken from the current workspace, all dependencies, and stdlib (Elixir and Erlang). This feature enables quick navigation to symbol definitions.

ElixirLS configuration settings
-------------------------------

Below is a list of configuration options supported by the ElixirLS language server. Please refer to your editor's documentation to determine how to configure language servers.

elixirLS.autoBuild

Trigger ElixirLS build when code is saved

elixirLS.dialyzerEnabled

Run ElixirLS's rapid Dialyzer when code is saved

elixirLS.incrementalDialyzer

Use OTP incremental dialyzer (available on OTP 26+)

elixirLS.dialyzerWarnOpts

Dialyzer options to enable or disable warnings - See Dialyzer's documentation for options. Note that the `race_conditions` option is unsupported.

elixirLS.dialyzerFormat

Formatter to use for Dialyzer warnings

elixirLS.envVariables

Environment variables to use for compilation

elixirLS.mixEnv

Mix environment to use for compilation

elixirLS.mixTarget

Mix target to use for compilation

elixirLS.projectDir

Subdirectory containing the Mix project, if it is not in the project root

elixirLS.fetchDeps

Automatically fetch project dependencies when compiling.

elixirLS.suggestSpecs

Suggest `@spec` annotations inline, using Dialyzer's inferred success typings (Requires Dialyzer).

elixirLS.trace.server

Traces communication between VS Code and the Elixir language server.

elixirLS.autoInsertRequiredAlias

Enable auto-insert required alias - By default, this option is `true` (enabled).

elixirLS.signatureAfterComplete

Show signature help after confirming autocomplete.

elixirLS.enableTestLenses

Show code lenses to run tests in terminal.

elixirLS.additionalWatchedExtensions

Additional file types capable of triggering a build on change

elixirLS.languageServerOverridePath

Absolute path to an alternative ElixirLS release that will override the packaged release

elixirLS.stdlibSrcDir

Path to Elixir's std lib source code. See \[here\](elixir-lsp/elixir\_sense#277) for more info

Debug Adapter configuration options
-----------------------------------

Below is a list of configuration options supported by the ElixirLS Debug Adapter. Configuration options can be supplied via launch configuration. Please refer to your editor's documentation on how to configure debug adapters.

startApps

Run `mix app.start` before launching the debugger. Some tasks (such as Phoenix tests) expect apps to already be running before the test files are required. Defaults to `false`.

task

Mix task to run with debugger - Defaults to task set under `:default_task` key in mixfile.

taskArgs

A list of arguments to mix task

debugAutoInterpretAllModules

Auto interpret all modules from project build path. Defaults to `true`.

env

An object with environment variables - To set Object keys, specify environment variables; values should be strings.

stackTraceMode

Option passed to `:int.stack_trace/1`. See :int.stack\_trace/1 for details. Allowed values are `all`, `no_tail`, and `false`.

requireFiles

A list of additional files that should be required and interpreted - This is especially useful for debugging tests.

debugInterpretModulesPatterns

A list of globs specifying modules that should be interpreted

projectDir

An absolute path to the directory where \`mix.exs\` is located - In VSCode, `${workspaceRoot}` can be used.

excludeModules

A list of modules that should not be interpreted

exitAfterTaskReturns

Should the debug session stop when mix task returns. Tasks that return early while the code continues running asynchronously require `false` setting. Defaults to `true`.

noDebug

Run mix task without debugging. Defaults to `false`.

breakOnDbg

Should the debugger break on Kernel.dbg/2 macro. Defaults to `true`.

Troubleshooting
---------------

Basic troubleshooting steps:

-   Make sure you have `hex` and `git` installed.
-   Make sure `github.com` and `hex.pm` are accessible. You may need to configure an HTTPS proxy. If your setup uses TLS man-in-the-middle inspection, you may need to set `HEX_UNSAFE_HTTPS=1`.
-   If ElixirLS fails to start, you can try cleaning the `Mix.install` directory (location on your system can be obtained by calling `Path.join(Mix.Utils.mix_cache(), "installs")` from `iex` session)
-   Restart ElixirLS with the custom command `restart`.
-   Run `mix clean` or `mix clean --deps` in ElixirLS with the custom command `mixClean`.
-   Restart your editor (which will restart ElixirLS).
-   After stopping your editor, remove the entire `.elixir_ls` directory, then restart your editor.
    -   NOTE: This will cause you to have to re-run the entire dialyzer build.

You may need to set `elixirLS.mixEnv`, `elixirLS.mixTarget`, and `elixirLS.projectDir` if your project requires this. By default, ElixirLS compiles code with `MIX_ENV=test` and `MIX_TARGET=host`; it assumes that `mix.exs` is located in the workspace root directory.

If you get an error like the following immediately on startup:

```
[Warn  - 1:56:04 PM] ** (exit) exited in: GenServer.call(ElixirLS.LanguageServer.JsonRpc, {:packet, %{...snip...}}, 5000)
    ** (EXIT) no process: the process is not alive or there's no process currently associated with the given name, possibly because its application isn't started
```

and you installed Elixir and Erlang from the Erlang Solutions repository, you may not have a full installation of Erlang. This can be solved with `sudo apt-get install esl-erlang`. (This was originally reported in #208).

On Fedora Linux, if you only install the Elixir package you will not have a full Erlang installation. This can be fixed by running `sudo dnf install erlang` (This was reported in #231).

Known Issues/Limitations
------------------------

-   `.exs` files don't return compilation errors.
-   "Fetching n dependencies" sometimes get stuck (remove the `.elixir_ls` directory to fix).
-   "Go to definition" does not work within the `scope` of a Phoenix router.
-   On first launch, Dialyzer will cause high CPU usage for a considerable time.
-   Dialyzer does not pick up changes involving remote types (#502)

Building and running
--------------------

There are two ways of building the release: `Mix.install` based (recommended) and `.ez` archives (deprecated).

### `Mix.install` based release

mix deps.get
MIX\_ENV=prod mix compile
MIX\_ENV=prod mix elixir\_ls.release2 -o <release\_dir\>

This copies language server and debugger adapter launch scripts to the `<release_dir>` and includes a `VERSION` manifest file. The launch scripts install a release specified by the version manifest via `Mix.install` and then launch it. This ensures that ElixirLS is built with the correct combination of Elixir and OTP.

### Local setup

This section provides additional information on how to set up the ElixirLS locally.

When launching ElixirLS from an IDE that is itself launched from a graphical shell, the environment may not be complete enough to find or run the correct Elixir/OTP version. To address this on Unix or Linux, the ElixirLS wrapper scripts try to configure ASDF (a version manager for Elixir and other languages), but that may not always be what is needed.

To ensure that the correct environment is set up, you can create a setup script. The setup script location varies based on platform and shell:

-   Unix-based systems using bash or zsh: `$XDG_CONFIG_HOME/elixir_ls/setup.sh` (by default `~/.config/elixir_ls/setup.sh`)
-   Unix-based systems using fish: `$XDG_CONFIG_HOME/elixir_ls/setup.fish` (by default `~/.config/elixir_ls/setup.fish`)
-   Windows-based systems `%APPDATA%\elixir_ls\setup.bat`

In the setup script, the environment variable `ELS_MODE` is available and set to either `debug_adapter` or `language_server` to help you decide what to do.

Note: The setup script must not read from `stdin` or write to `stdout`. On Unix, Linux, and macOS this might be accomplished by adding `>/dev/null` at the end of any line that produces output; for a Windows batch script, you will want to add `@echo off` at the top and use `>nul`.

If you want to debug your setup script you can write to stderr.

### Development

Please refer to DEVELOPMENT.md.

Environment variables
---------------------

ElixirLS supports the following environment variables.

ELS\_INSTALL\_PREFIX

(not supported on Windows) The folder where the language server was installed - If set, this makes maintaining multiple versions/instances on the same host much easier. If it is not set or empty, a heuristic will be used to discover the install location.

ELS\_LOCAL

If set to `1`, this will make ElixirLS run a local release. If this is not set, a published release matching `VERSION` will be used (default).

ELS\_ELIXIR\_OPTS

Optional parameters to pass to elixir CLI - May be used to set a node name and cookie.

ELS\_ERL\_OPTS

Optional parameters to pass to the erl CLI

ASDF\_DIR

(not supported on Windows)(deprecated, not used with asdf v0.16+) If this is set, ElixirLS will look for the asdf script in a directory given by that variable.

Telemetry
---------

ElixirLS language server sends telemetry information to the client via LSP Telemetry notification, DAP Output event and DAP ErrorResponse. Telemetry data include usage, performance, environment info and error reports. Please refer to your client and/or extension documentation on telemetry.

Acknowledgements and related projects
-------------------------------------

ElixirLS incorporates code intelligence providers that were originally developed in Elixir Sense and still uses this library for lower lever operations. Other prior work includes Alchemist Server, Elixir plugin for Atom, VSCode Elixir. Credit for those projects goes to their respective authors.

License
-------

ElixirLS source code is released under Apache License 2.0.

See LICENSE for more information.

ElixirLS includes parts of other projects, please see the respective licenses which apply to them.
