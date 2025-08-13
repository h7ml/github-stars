---
project: wasm3
stars: 7661
description: 🚀 A fast WebAssembly interpreter and the most universal WASM runtime
url: https://github.com/wasm3/wasm3
---

Note

I regret to inform the community that since my house was destroyed by russians who invaded my country, **Wasm3 will enter a minimal maintenance phase**. At this time, I am unable to continue the development of new features. However, I am committed to keeping the project alive and will actively review and merge incoming Pull Requests. I deeply appreciate your understanding and support during this difficult period. **Your contributions to Wasm3 are now more valuable than ever.**

Wasm3
=====

A fast WebAssembly interpreter and the most universal WASM runtime.  
Based on **CoreMark 1.0** and **independent** benchmarks. Your mileage may vary.

Installation
------------

**Please follow the installation instructions.**

Wasm3 can also be used as a library for:

Python3 │ Rust │ C/C++ │ D │ GoLang │ Zig │ Perl  
Swift │ .Net │ Nim │ Arduino, PlatformIO, Particle │ QuickJS

Status
------

`wasm3` passes the WebAssembly spec testsuite and is able to run many `WASI` apps.

Minimum useful system requirements: **~64Kb** for code and **~10Kb** RAM

`wasm3` runs on a wide range of architectures (`x86`, `x86_64`, `ARM`, `RISC-V`, `PowerPC`, `MIPS`, `Xtensa`, `ARC32`, ...) and platforms:

-   Linux, Windows, OS X, FreeBSD, Android, iOS
-   OpenWrt, Yocto, Buildroot (routers, modems, etc.)
-   Raspberry Pi, Orange Pi and other SBCs
-   MCUs: Arduino, ESP8266, ESP32, Particle, ... see full list
-   Browsers. Yes, using WebAssembly itself!
-   `wasm3` can execute `wasm3` (self-hosting)

Features
--------

Webassembly Proposals

Extra

☑ Import/Export of Mutable Globals

☑ Structured execution tracing

☑ Non-trapping float-to-int conversions

☑ Big-Endian systems support

☑ Sign-extension operators

☑ Wasm and WASI self-hosting

☑ Multi-value

☑ Gas metering

☑ Bulk memory operations (partial support)

☑ Linear memory limit (< 64KiB)

☑ Custom page size

⏳ Multiple memories

⏳ Reference types

☐ Tail call optimization

☐ Fixed-width SIMD

☐ Exception handling

☐ Stack Switching

Motivation
----------

**Why use a "slow interpreter" versus a "fast JIT"?**

In many situations, speed is not the main concern. Runtime executable size, memory usage, startup latency can be improved with the interpreter approach. Portability and security are much easier to achieve and maintain. Additionally, development impedance is much lower. A simple library like Wasm3 is easy to compile and integrate into an existing project. (Wasm3 builds in a just few seconds). Finally, on some platforms (i.e. iOS and WebAssembly itself) you can't generate executable code pages in runtime, so JIT is unavailable.

**Why would you want to run WASM on embedded devices?**

Wasm3 started as a research project and remains so by any means. Evaluating the engine in different environments is part of the research. Given that we have `Lua`, `JS`, `Python`, `Lisp`, `...` running on MCUs, `WebAssembly` is a promising alternative. It provides toolchain decoupling as well as a completely sandboxed, well-defined, predictable environment. Among practical use cases we can list `edge computing`, `scripting`, `plugin systems`, running `IoT rules`, `smart contracts`, etc.

Used by
-------

　 　 　 　 　 　 　 　 　 　 　 　

Further Resources
-----------------

Demos  
Installation instructions  
Cookbook  
Troubleshooting  
Build and Development instructions  
Supported Hardware  
Testing & Fuzzing  
Performance  
Interpreter Architecture  
Logging  
Awesome WebAssembly Tools

### License

This project is released under The MIT License (MIT)
