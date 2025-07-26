---
project: walt
stars: 4655
description: :zap: Walt is a JavaScript-like syntax for WebAssembly text format :zap:
url: https://github.com/ballercat/walt
---

  
  
**Walt** | _Alternative Syntax for WebAssembly_ | Demo

⚡ **Walt** is an alternative syntax for WebAssembly text format. It's an experiment for using JavaScript syntax to write to as 'close to the metal' as possible. _It's JavaScript with rules._ `.walt` files compile directly to WebAssembly binary format.

Highlights:

-   Write _"close to the metal"_ JavaScript!
-   **No C/C++ or Rust required**, just _typed_ JavaScript.
-   **NO LLVM/binary toolkits required**, zero dependencies 100% written in JS.
-   Fast compilation, integrates into webpack!

📖 Read the Quick Start Guide

🚀 Try it out in the Walt Explorer.

🙏 Contributions are welcomed! Contributing guide.

🐥 Current status: **Alpha**

### Roadmap

Problem
=======

Writing zero-overhead, optimized WebAssembly is pretty tough to do. The syntax for `.wat` files is terse and difficult to work with directly. If you do not wish to use a systems language like C or Rust, then you're kind of out of luck. Your best bet (currently) is to write very plain C code, compile that to .wast and then optimize that result. Then you're ready to compile that into the final WebAssembly binary. This is an attempt to take C/Rust out of the equation and write 'as close to the metal' as possible without losing readability.

I feel like this is currently a problem. Most Web engineers are not familiar with the C family languages or Rust. It's a barrier for wide spread adoption of WebAssembly. A competent Front-end engineer should be able to edit WebAssembly as easily as any other systems programmer.

Solution
========

Provide a **thin layer** of syntax sugar on top of `.wat` text format. Preferably porting as much of JavaScript syntax to WebAssembly as possible. This improved syntax should give direct control over the WebAssembly output. Meaning there should be minimal to none post optimization to be done to the wast code generated. The re-use of JavaScript semantics is intentional as I do not wish to create a brand new language.

Here is what an example of a `.walt` module which exports a recursive Fibonacci function looks like:

export function fibonacci(n: i32): i32 {
  if (n <= 0) return 0;

  if (n \== 1) return 1;

  return fibonacci(n \- 1) + fibonacci(n \- 2);
}

When this code is ran through the walt compiler you end up with a buffer which can be used to create a WebAssembly module with a `fibonacci` export just as you would expect. All done with familiar JS syntax and without any external binary toolkits! A working demo of this exists in the `fibonacci-spec.js` unit test file.

Project Goals
=============

The ultimate goal of Walt is to make WebAssembly accessible to average JavaScript engineer by providing a subset of JavaScript syntax which compiles to WebAssembly bytecode directly. That WebAssembly should be easy to make use of and simple to integrate into an existing project with the current build tools.

Use cases
---------

Pretty much everyone who wants a quick-start into wasm can use Walt to get there. The use-cases are not specific to this project alone but more to WebAssembly in general. The fact that Walt does not require a stand-alone compiler and can integrate into any(almost?) build tool still makes certain projects better candidates over others.

-   Web/Node libraries, looking to improve performance.
-   Games
-   Projects depending on heavy real-time computation from complex UIs to 3D visualizations
-   Web VR/AR
-   Anyone interested in WebAssembly who is not familiar with system languages.

See Wiki for detailed design decisions etc.

Prior Art
---------

-   wah - A slightly higher level syntax on top of the wasm text format
-   mini-c - Experimental C to WebAssembly compiler

Contributors
------------

ballercat

tbroadley

thomassturm

Baransu

whitecrownclown

balajmarius

hlaaftana

ForsakenHarmony

hamlim

petetnt

novoselrok

Dragas
