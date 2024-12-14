---
project: pythonx
stars: 42
description: Python Interpreter in Elixir
url: https://github.com/cocoa-xu/pythonx
---

Pythonx
=======

Python Interpreter in Elixir

Important

Pythonx is still very much a work in progress and is mainly intended for some proof of concept at current stage.

Proof of Concept
----------------

### Low-Level

iex\> alias Pythonx.C
iex\> alias Pythonx.C.PyDict
iex\> alias Pythonx.C.PyLong
iex\> alias Pythonx.C.PyRun
iex\> alias Pythonx.C.PyUnicode
iex\> Pythonx.initialize\_once()
iex\> globals \= PyDict.new()
#Reference<0.1798353731.1418330114.239105>
iex\> locals \= PyDict.new()
#Reference<0.1798353731.1418330114.239123>
iex\> a \= PyLong.from\_long(1)
#Reference<0.1798353731.1418330114.239141>
iex\> b \= PyLong.from\_long(2)
#Reference<0.1798353731.1418330114.239155>
iex\> PyDict.set\_item\_string(locals, "a", a)
true
iex\> PyDict.set\_item\_string(locals, "b", b)
true
iex\> PyRun.string("c = a + b", C.py\_file\_input(), globals, locals)
#Reference<0.1798353731.1418330117.241204>
iex\> c \= PyUnicode.from\_string("c")
#Reference<0.1798353731.1418330117.241222>
iex\> val\_c \= PyDict.get\_item\_with\_error(locals, c)
#Reference<0.1798353731.1418330117.241236>
iex\> PyLong.as\_long(val\_c)
3

### BEAM Level

iex\> Pythonx.initialize\_once()
iex\> globals \= Pythonx.Beam.encode(%{})
#PyObject<
  type: "dict",
  repr: "{}"
\>
iex\> locals \= Pythonx.Beam.encode(\[a: 1, b: 2\])
#PyObject<
  type: "dict",
  repr: "{'a': 1, 'b': 2}"
\>
iex\> Pythonx.Beam.PyRun.string("c = a + b", Pythonx.Beam.py\_file\_input(), globals, locals)
#PyObject<
  type: "NoneType",
  repr: "None"
\>
iex\> locals
#PyObject<
  type: "dict",
  repr: "{'a': 1, 'b': 2, 'c': 3}"
\>

### High-Level

iex\> Pythonx.initialize\_once()
iex\> state \= Pythonx.State.new(locals: \[a: 1, b: 2\])
%Pythonx.State{globals: %{}, locals: \[a: 1, b: 2\]}
iex\> {result, state} \= Pythonx.PyRun.string("c = a + b", Pythonx.py\_file\_input(), state)
iex\> state.locals
%{"a" \=> 1, "b" \=> 2, "c" \=> 3}

### Very High Level

#### Python Code Evaluation

defmodule MyModule do
  import Pythonx

  def do\_stuff\_in\_python do
    a \= 1
    b \= 2
    pyinline("c = a + b",
      return: \[:c\]
    )
    dbg(c)
  end
end

Or in IEx

iex\> Pythonx.initialize\_once()
iex\> import Pythonx
iex\> a \= 1
1
iex\> b \= 2
2
iex\> pyinline("c = a + b", return: \[:c\])
iex\> c
3

#### Executes a command with the embedded python3 executable

iex\> import Pythonx
iex\> python3! "path/to/script.py"
iex\> python3! \["path/to/script.py", "arg1", "arg2"\]

#### Executes a command with the embedded pip module

iex\> import Pythonx
iex\> pip! \["install", "-U", "numpy"\]
iex\> pip! \["install", "-U", "yt-dlp"\]

#### Use an external python library

iex\> import Pythonx
iex\> video\_id \= "dQw4w9WgXcQ"
iex\> pyeval(
...\>   """
...>   from yt\_dlp import YoutubeDL
...>   import json
...>   with YoutubeDL(params={'quiet': True}) as ytb\_dl:
...>     info = ytb\_dl.extract\_info('https://www.youtube.com/watch?v=#{video\_id}', download=False)
...>     info = json.dumps(info, indent=2)
...>   """,
...>   return: \[:info\]
...> )
\[youtube\] Extracting URL: https://www.youtube.com/watch?v=dQw4w9WgXcQ
\[youtube\] dQw4w9WgXcQ: Downloading webpage
\[youtube\] dQw4w9WgXcQ: Downloading ios player API JSON
\[youtube\] dQw4w9WgXcQ: Downloading player a95aa57a
\[youtube\] dQw4w9WgXcQ: Downloading m3u8 information
iex> IO.puts(info)

Installation
------------

If available in Hex, the package can be installed by adding `pythonx` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:pythonx, "~> 0.1.0"}
  \]
end

Documentation can be generated with ExDoc and published on HexDocs. Once published, the docs can be found at https://hexdocs.pm/pythonx.
