---
project: fastglobal
stars: 1150
description: Fast no copy globals for Elixir & Erlang.
url: https://github.com/discord/fastglobal
---

FastGlobal
==========

The Erlang VM is great at many things, but quick access to large shared data is not one of them. Storing data in a single process results in overloading the process, using an ETS table gets more expensive to read as the data gets larger, and both require copying data to the calling process. If you have large infrequently changing data that needs to be accessed by thousands of processes there is a better way.

Erlang has an optimization called constant pools for functions that return static data, you can also compile modules at runtime. This method was originally popularized by mochiglobal. This module is an Elixir version with some optimizations such as generating the atom keys and reusing them.

Performance
-----------

```
benchmark name               iterations   average time
fastglobal get                 10000000   0.33 µs/op
ets get                          500000   7.64 µs/op
agent get                        100000   12.67 µs/op
fastglobal purge perf (100)         500   2846.26 µs/op
fastglobal put (5)                  500   3683.30 µs/op
fastglobal put (10)                 500   6449.98 µs/op
fastglobal put (100)                 50   44543.56 µs/op
```

Caveats
-------

-   Compile times get slower as data size increases.
-   Compile times get slower the more processes are in the system. Erlang talks to each process when purging a module.
-   Getting a key that does not exist is expensive due to try/catch, put at least a `nil` value.
-   Creating atoms from strings is not cheap, use `FastGlobal.new`.

Usage
-----

Add it to `mix.exs`

defp deps do
  \[{:fastglobal, "~> 1.0"}\]
end

And just use it as a global map.

data \= %{
  a: 1,
  b: 2,
  c: \[3, 4\]
}
FastGlobal.put(:data, data)
data \== FastGlobal.get(:data)

License
-------

FastGlobal is released under the MIT License. Check LICENSE file for more information.
