---
project: txiki.js
stars: 2796
description: A tiny JavaScript runtime
url: https://github.com/saghul/txiki.js
---

txiki.js — The tiny JavaScript runtime
======================================

Overview
--------

> **txikia** (basque): small, tiny.

_txiki.js_ is a small and powerful JavaScript runtime. It targets state-of-the-art ECMAScript and aims to be WinterCG compliant.

It's built on the shoulders of giants: it uses QuickJS-ng as its JavaScript engine and libuv as the platform layer.

See it in action here:

Getting started
---------------

First head over to building and build the runtime.

$ ./build/tjs eval "console.log('hello world')"
hello world
$

If you want to run a script you can use `tjs run`:

$ ./build/tjs run examples/hello\_world.js
hello world
$

Explore all the options:

$ ./build/tjs --help

For TS support see @txikijs/types.

Features
--------

Support for the ES2023 specification (almost complete).

### WinterCG

_txiki.js_ aims to be WinterCG compliant, you can track the progress here.

### Web Platform APIs

-   alert, confirm, prompt (1)
-   Console
-   Crypto (2)
-   Encoding API
-   EventTarget
-   fetch
-   JSON modules
-   Performance
-   setTimeout, setInterval
-   Storage API
-   Streams API
-   URL
-   URLPattern
-   URLSearchParams
-   WebAssembly (3)
-   WebSocket
-   Web Workers API

(1): All of them are async.

(2): No subtle support.

(3): No tables, globals or memory support.

### Runtime features

-   Standalone executables
-   TCP and UDP sockets
-   Unix sockets / named pipes
-   Signal handling
-   File operations
-   Child processes
-   WASI
-   ...

See the full API documentation.

Other extras:

-   Import directly from HTTP(S) URLs
-   Import JSON files
-   Builtin test runner

### Standard library

The following modules compose the standard library:

-   `tjs:assert`
-   `tjs:ffi`
-   `tjs:getopts`
-   `tjs:hashing`
-   `tjs:ipaddr`
-   `tjs:path`
-   `tjs:sqlite`
-   `tjs:uuid`

Supported platforms
-------------------

-   GNU/Linux
-   macOS
-   Windows (beta)
-   Other Unixes (please test!)

Building
--------

CMake is necessary.

_NOTE:_ The txiki.js build depends on a number of git submodules (libffi, libuv and wasm3). If you didn't already clone this repository recursively, make sure you initialize these submodules with `git submodule update --init` before proceeding to the build.

### GNU/Linux

Install dependencies (`libcurl`, `build-essential`, `cmake`, `autoreconf`, `libtool`, `libltdl-dev`):

# On Debian / Ubuntu
sudo apt install libcurl4-openssl-dev build-essential cmake autoconf texinfo libtool libltdl-dev

### macOS

Install dependencies (`cmake`, `autoconf`):

brew install cmake autoconf automake libtool texinfo

### Unix systems

# Get the code
git clone --recursive https://github.com/saghul/txiki.js --shallow-submodules && cd txiki.js
# Compile it!
make
# Run the REPL
./build/tjs

### Windows (beta)

Windows support it's currently considered beta. Tests do pass, but building it is not as easy as it should be.

Building has only been tested in 64bit Windows.

#### Prerequisites

First make sure you have MSYS2 installed. The `mingw64` and `clang64` environments are currently tested.

Then install the required dependencies:

pacman -S git make pactoys
pacboy -S curl-winssl:p toolchain:p cmake:p ninja:p

#### Build

These commands must be run in a MinGW64 or clang64 shell.

make

This will build the executable just like on Unix. Note that at this point there are a number of dynamically linked libraries, so if you want to use the executable on a different system you'll need to copy those too. Check the list with `ldd build/tjs.exe`.

#### Running the tests

Make sure these commands are run from Windows Terminal (mintty, what MSYS2 provides is not supported).

make test

### Customizing the build

If you are making a custom build and are modifying any of the JS files that are part of the runtime, you'll need to regenerate the C code for them, so your changes become part of the build.

# First install the JS dependencies
npm install
# Now bundle the code and compile it into C source files
make js

`tjs compile` - creating standalone executables
-----------------------------------------------

Creating standalone executables is possible with `tjs compile`. The resulting executable will bundle the given code and the txiki.js runtime. No compiler is needed.

**NOTE:** The resulting executable will have the same runtime dependencies as the `tjs` executable.

Assuming a `bundle.js` file with some JS code, the following command will create a standalone executable with it:

tjs compile bundle.js

The new executable will be called `bundle` on Unix platforms and `bundle.exe` on Windows. The output name can be customized by passing a second option:

tjs compile bundle.js myexe

The `tjs compile` command doesn't do any code bundling. If you need to bundle your app into a single JS file for use with `tjs compile`, esbuild can be a good option. Here is how to bundle an app into a single `bundle.js` file:

npx esbuild my-app/index.js \\
    --bundle \\
    --outfile=bundle.js \\
    --external:tjs:\* \\
    --minify \\
    --target=es2023 \\
    --platform=neutral \\
    --format=esm \\
    --main-fields=main,module

Versioning
----------

txiki.js uses calendar versioning with the form YY.MM.MICRO.

  
  

Built with ❤️ by saghul and these awesome contributors.
