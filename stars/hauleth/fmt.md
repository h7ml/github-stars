---
project: fmt
stars: 7
description: null
url: https://github.com/hauleth/fmt
---

Fmt
===

Formatting sigil for Elixir. Inspired by Rust `format!` macro and Python's `f-strings`

import Fmt
foo \= 1
~F"#{foo :: x}" \== "0x1"

Installation
------------

If available in Hex, the package can be installed by adding `sigil_f` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:fmt, "~> 0.1.0"}
  \]
end

Documentation can be generated with ExDoc and published on HexDocs. Once published, the docs can be found at https://hexdocs.pm/sigil\_f.
