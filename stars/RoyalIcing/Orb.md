---
project: Orb
stars: 242
description: Write WebAssembly with Elixir
url: https://github.com/RoyalIcing/Orb
---

Orb: Write WebAssembly with Elixir
==================================

Docs | Examples

Write WebAssembly with the power of Elixir as your compiler:

-   Use Elixir’s **module system** to break problems down and then compose them together.
-   Chain function calls together with the **pipe `|>` operator**.
-   Publish reusable code with the **Hex package manager**.
-   **Write unit tests** using Elixir’s built-in ExUnit.
-   Reduce boilerplate with Elixir’s **powerful macro system**.
-   **Run dynamic Elixir code at compile time** e.g. talk to the rest of your Elixir application, call out to an Elixir library, or make network requests.
-   **Compile modules on-the-fly** e.g. use feature flags to conditionally compile code paths or enable particular WebAssembly instructions, creating a custom “tree shaken” WebAssembly module per user.

Status
------

Orb is alpha in active development. My aim is to refine the current feature set and complete a `.wasm` compiler (current it compiles to WebAssembly’s `.wat` text format) in order to get to beta.

Libraries
---------

-   **Orb** (alpha): Write WebAssembly 1.0 in Elixir.
-   **SilverOrb** (work-in-progress): Batteries-included standard library for Orb.
-   OrbExtismPDK (coming later): Write Extism plugins in Elixir with Orb.

Installation
------------

Add `orb` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:orb, "~> 0.1.1"}
  \]
end

Example
-------

defmodule CalculateMean do
  use Orb

  global do
    @tally 0
    @count 0
  end

  defw insert(n: I32) do
    @tally \= @tally + n
    @count \= @count + 1
  end

  defw calculate\_mean(), I32 do
    @tally / @count
  end
end

This can be converted to WebAssembly text format (wat):

wat \= Orb.to\_wat(CalculateMean)
\# """
\# (module $CalculateMean
\#   (global $count (mut i32) (i32.const 0))
\#   (global $tally (mut i32) (i32.const 0))
\#   (func $insert (export "insert") (param $element i32)
\#     (i32.add (global.get $count) (i32.const 1))
\#     (global.set $count)
\#     (i32.add (global.get $tally) (local.get $element))
\#     (global.set $tally)
\#   )
\#   (func $calculate\_mean (export "calculate\_mean") (result i32)
\#     (i32.div\_s (global.get $tally) (global.get $count))
\#   )
\# )
\# """

Write this out as a `.wat` WebAssembly text file:

File.write!("example.wat", wat)

You can then compile this to a `.wasm` WebAssembly file using wat2wasm from the WebAssembly Binary Toolkit:

wat2wasm example.wat

Or you can execute it directly in Elixir with OrbWasmtime:

alias OrbWasmtime.Instance

\# Run above example
inst \= Instance.run(CalculateMean)
Instance.call(inst, :insert, 4)
Instance.call(inst, :insert, 5)
Instance.call(inst, :insert, 6)
assert Instance.call(inst, :calculate\_mean) \== 5

Note there is another excellent Elixir Wasmtime wrapper out there called Wasmex, you may want to check that out too.

Composing modules
-----------------

You can compose modules together using `Orb.include/1`:

defmodule Math do
  use Orb

  defw square(n: I32), I32 do
    n \* n
  end
end

defmodule SomeOtherModule do
  use Orb

  Orb.include(Math)

  defw magic(), I32 do
    Math.square(3)
  end
end

Use cases
---------

-   Parsers
-   State machines
-   Formatters & string builders
-   HTTP endpoint that can be deployed agnostically to the server or edge.
-   Interactive UI controls
-   Write a HTML component and run it in:
    -   Phoenix LiveView & dead views
    -   In the browser using `<wasm-html>` custom element
-   LiveView and its server rendering is a fantastic default, but the latency can be noticeable for certain UI interactions. With Orb you could use Elixir to write a WebAssembly module that then runs in the user’s browser.
-   Animation that runs fast in the browser and also works on the server
-   Code generators

Why WebAssembly?
----------------

-   It runs on all of today’s major platforms: browser, server, edge, mobile, laptop, tablet, desktop.
-   Universal/isomorphic components (ones that run on the server and browser) are possible in React and Next.js, but they have many different flavours and can get pretty complex for a system that was meant to be declarative.
-   Like HTML and CSS it’s backwards compatible, which means WebAssembly you author today will be guaranteed to still work in a decade or longer.
-   It’s memory-safe and sandboxed. It can’t read memory outside of itself, only what has been explicitly passed into it. It can even be timeboxed to run for a maximum duration.
-   It’s fast.

Why develop Orb in Elixir?
--------------------------

Here are the reasons I chose to write Orb in Elixir.

-   Established language:
    -   Has package manager.
    -   Has composable modules with `alias` & `use`.
    -   Has syntax highlighting in IDEs, GitHub, and in highlighting libraries.
    -   Has language server with autocomplete.
    -   Has documentation system.
    -   Has unit test library.
    -   Has CI integration.
    -   Has linting.
    -   Integrates with native libraries in Rust and Zig.
    -   Has upcoming type system.
-   Established frameworks:
    -   Can integrate with Phoenix LiveView.
    -   Can connect to cloud, databases.
    -   Can integrate with Rust.
-   Community that is friendly and collaborative.
-   Can be extended with additional functions and macros:
    -   Unlike say C’s basic string-inserting preprocessor, Elixir is a full programming language without constraints.
    -   We can read files or the network and then generate code.
    -   You can create your own DSL. Want to enforce immutable-style programming? Want to add pattern matching? Design your own DSL on top of Orb for it.
