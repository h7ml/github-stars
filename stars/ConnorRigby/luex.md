---
project: luex
stars: 16
description: Nif for running lua inside erlang
url: https://github.com/ConnorRigby/luex
---

Luex
====

Run lua inside Elixir/Erlang

Installation
------------

If available in Hex, the package can be installed by adding `luex` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:luex, "~> 0.1.0"}
  \]
end

Example Usage
-------------

{:ok, l} \= Luex.init()
Luex.dostring(l, "while(true) do end")

and that's it. Now the vm is stuck forever. Good luck.

Luex.dostring(l, "return 1 + 1")
{:ok, {2.0}}

Luex.dostring(l, "whoops()")
{:error,
 "\[string \\"whoops()\\r...\\"\]:1: attempt to call a nil value (global 'whoops')"}

Luex.dostring(l, "return 1, 2, 3")
{:ok, {1.0, 2.0, 3.0}}

Luex.dostring(l, "return 'abcd'")
{:ok, {"abcd"}}

Luex.dostring(l, "return 'cool string!', 0")
{:ok, {"cool string!", 0.0}}

Luex.dostring(l, "a = 1000")
{:ok, {}}
Luex.dostring(l, "return a")
{:ok, {1000.0}}

iex(7)\> Luex.dostring(l, """
i = 0
wow = coroutine.wrap(function ()
  while true do
   i = i + 1
   coroutine.yield(i)
  end
end)
return wow()
""")
{:ok, {1.0}}
Luex.dostring(l, "return wow()")
{:ok, {2.0}}
Luex.dostring(l, "return wow()")
{:ok, {3.0}}
Luex.dostring(l, "return wow()")
{:ok, {4.0}}
Luex.dostring(l, "return wow()")
{:ok, {5.0}}
