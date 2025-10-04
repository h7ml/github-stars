---
project: dynamic-analysis
stars: 1037
description: ⚙️ A curated list of dynamic analysis tools and linters for all programming languages, binaries, and more.
url: https://github.com/analysis-tools-dev/dynamic-analysis
---

This repository lists **dynamic analysis tools** for all programming languages, build tools, config files and more. The focus is on tools which improve code quality such as linters and formatters. The official website, analysis-tools.dev is based on this repository and adds rankings, user comments, and additional resources like videos for each tool.

Sponsors
--------

This project would not be possible without the generous support of our sponsors.

If you also want to support this project, head over to our Github sponsors page.

Meaning of Symbols:
-------------------

-   ©️ stands for proprietary software. All other tools are Open Source.
-   ℹ️ indicates that the community does not recommend to use this tool for new projects anymore. The icon links to the discussion issue.
-   ⚠️ means that this tool was not updated for more than 1 year, or the repo was archived.

Pull requests are very welcome!  
Also check out the sister project, awesome-static-analysis.

Table of Contents
-----------------

#### Programming Languages

Show languages

-   .NET
-   C
-   C++
-   Go
-   Java
-   JavaScript
-   PHP
-   Python
-   Ruby
-   Rust
-   SQL
-   Visual Basic
-   Zig

#### Multiple languages

#### Other

-   API
    
-   Binaries
    
-   Bytecode/IR
    
-   Cloud
    
-   Containers
    
-   Laravel
    
-   Security/DAST
    
-   Web
    
-   WebAssembly
    
-   XML
    

* * *

Programming Languages
---------------------

.NET
----

-   Microsoft IntelliTest — Generate a candidate suite of tests for your .NET code.
    
-   Pex and Moles — Pex automatically generates test suites with high code coverage using automated white box analysis.
    

C
-

-   CHAP — Analyzes un-instrumented ELF core files for leaks, memory growth, and corruption. It helps explain memory growth, can identify some forms of corruption, and supplements a debugger by giving the status of various memory locations.
    
-   KLEE — Symbolic virtual machine built on top of the LLVM compiler infrastructure.
    
-   LDRA ©️ — A tool suite including dynamic analysis and test to various standards can ensure test coverage to 100% op-code, branch & decsion coverage.
    
-   LLVM/Clang Sanitizers —
    
    -   AddressSanitizer - A memory error detector for C/C++
    -   MemorySanitizer - A detector of uninitialized memory reads in C/C++ programs.
    -   ThreadSanitizer - A data race detector for C/C++
    
-   Valgrind — An instrumentation framework for building dynamic analysis tools.
    

C++
---

-   CHAP — Analyzes un-instrumented ELF core files for leaks, memory growth, and corruption. It helps explain memory growth, can identify some forms of corruption, and supplements a debugger by giving the status of various memory locations.
    
-   KLEE — Symbolic virtual machine built on top of the LLVM compiler infrastructure.
    
-   LDRA ©️ — A tool suite including dynamic analysis and test to various standards can ensure test coverage to 100% op-code, branch & decsion coverage.
    
-   LLVM/Clang Sanitizers —
    
    -   AddressSanitizer - A memory error detector for C/C++
    -   MemorySanitizer - A detector of uninitialized memory reads in C/C++ programs.
    -   ThreadSanitizer - A data race detector for C/C++
    
-   Valgrind — An instrumentation framework for building dynamic analysis tools.
    

Go
--

-   statsviz — Instant live visualization of your Go application runtime statistics in the browser. It plots heap usage, MSpans/MCaches, Object counts, Goroutines and GC/CPU fraction.

Java
----

-   Java PathFinder — An extensible software model checking framework for Java bytecode programs.
    
-   Parasoft Jtest ©️ — Jtest is an automated Java software testing and static analysis product that is made by Parasoft. The product includes technology for Data-flow analysis Unit test-case generation and execution, static analysis, regression testing, code coverage, and runtime error detection.
    

JavaScript
----------

-   Iroh.js — A dynamic code analysis tool for JavaScript. Iroh allows to record your code flow in realtime, intercept runtime informations and manipulate program behaviour on the fly.
    
-   Jalangi2 — Jalangi2 is a popular framework for writing dynamic analyses for JavaScript.
    

PHP
---

-   Enlightn — A static and dynamic analysis tool for Laravel applications that provides recommendations to improve the performance, security and code reliability of Laravel apps. Contains 120 automated checks.

Python
------

-   CrossHair — Symbolic execution engine for testing Python contracts.
    
-   DynaPyt — DynaPyt is a framework for writing dynamic analyses for Python. The analyses can also modify runtime values to alter the execution.
    
-   icontract — Design-by-contract library supporting behavioral subtyping There is also a wider tooling around the icontract library such as a linter (pyicontract-lint) and a plug-in for Sphinx (sphinx-icontract).
    
-   Scalene — A high-performance, high-precision CPU and memory profiler for Python
    
-   typo — Runtime Type Checking for Python 3.
    

Ruby
----

-   suture — A Ruby gem that helps you refactor your legacy code by the result of some old behavior with a new version.

Rust
----

-   cargo-careful — Execute Rust code carefully, with extra checking along the way. It builds the standard library with debug assertions. Here are some of the checks this enables:

-   `get_unchecked` in slices performs bounds checks \* `copy`, `copy_nonoverlapping`, and `write_bytes` check that pointers are aligned and non-null and (if applicable) non-overlapping `{NonNull,NonZero*,...}::new_unchecked` check that the value is valid \* plenty of internal consistency checks in the collection types \* mem::zeroed and the deprecated mem::uninitialized panic if the type does not allow that kind of initialization

-   hyperfine — A command-line benchmarking tool It features statistical analysis across multiple runs, support for arbitrary shell commands, constant feedback about the benchmark progress and current estimates, warmup runs, a simple and expressive syntax, and more.
    
-   loom — Concurrency permutation testing tool for Rust. It runs a test many times, permuting the possible concurrent executions of that test.
    
-   MIRI — An interpreter for Rust's mid-level intermediate representation, which can detect certain classes of undefined behavior like out-of-bounds memory accesses and use-after-free.
    
-   puffin — Instrumentation profiler for Rust.
    
-   rust-san — How-to sanitize your Rust code with built-in Rust dynamic analyzers
    
-   stuck — provides a visualization for quickly identifying common bottlenecks in running, asynchronous, and concurrent applications.
    

SQL
---

-   WhiteHat Sentinel Dynamic ©️ — Part of the WhiteHat Application Security Platform. Dynamic application security scanner that covers the OWASP Top 10.

Visual Basic
------------

-   VB Watch ©️ — Profiler, Protector and Debugger for VB6. Profiler measures performance and test coverage. Protector implements robust error handling. Debugger helps monitor your executables.

Zig
---

-   poop — Performance Optimizer Observation Platform This command line tool uses Linux's `perf_event_open` functionality to compare the performance of multiple commands with a colorful terminal user interface. It is similar to `hyperfine`.

Multiple languages
------------------

-   allocscope — allocscope is a tool for tracking down where the most egregiously large allocations are occurring in a C, C++ or Rust codebase. It is particularly intendend to be useful for developers who want to get a handle on excessive allocations and are working in a large codebase with multiple contributors with allocations occuring in many modules or libraries.
    
-   bytehound — A memory profiler for Linux. Can be used to analyze memory leaks, see where exactly the memory is being consumed, identify temporary allocations and investigate excessive memory fragmentation.
    
-   CASR — Crash Analysis and Severity Report.
    
-   Code Pulse — Code Pulse is a free real-time code coverage tool for penetration testing activities by OWASP and Code Dx (GitHub).
    
-   Sydr ©️ — Continuous Hybrid Fuzzing and Dynamic Analysis for Security Development Lifecycle.
    

Other
-----

API
---

-   Smartbear ©️ — Test automation and performance testing platform

Binaries
--------

-   angr — Platform agnostic binary analysis framework from UCSB.
    
-   BOLT — Binary Optimization and Layout Tool - A linux command-line utility used for optimizing performance of binaries with profile guided permutation of linking to improve cache efficiency
    
-   Dr. Memory — Dr. Memory is a memory monitoring tool capable of identifying memory-related programming errors (Github).
    
-   DynamoRIO — Is a runtime code manipulation system that supports code transformations on any part of a program, while it executes.
    
-   llvm-propeller — Profile guided hot/cold function splitting to improve cache efficiency. An alternative to BOLT by Facebook
    
-   Pin Tools — A dynamic binary instrumentation tool and a platform for creating analysis tools.
    
-   TRITON — Dynamic Binary Analysis for x86 binaries.
    

Bytecode/IR
-----------

-   souper — optimize LLVM IR with SMT solvers

Cloud
-----

-   prowler — Prowler is an Open Source security tool to perform AWS and Azure security best practices assessments, audits, incident response, continuous monitoring, hardening and forensics readiness. It contains hundreds of controls covering CIS, PCI-DSS, ISO27001, GDPR, HIPAA, FFIEC, SOC2, AWS FTR, ENS and custom security frameworks.

Containers
----------

-   cadvisor — Analyzes resource usage and performance characteristics of running containers.

Laravel
-------

-   Enlightn — A static and dynamic analysis tool for Laravel applications that provides recommendations to improve the performance, security and code reliability of Laravel apps. Contains 120 automated checks.

Security/DAST
-------------

-   AppScan Standard ©️ — HCL's AppScan is a dynamic application security testing suite (previously by IBM)
    
-   Enlightn — A static and dynamic analysis tool for Laravel applications that provides recommendations to improve the performance, security and code reliability of Laravel apps. Contains 120 automated checks.
    
-   WhiteHat Sentinel Dynamic ©️ — Part of the WhiteHat Application Security Platform. Dynamic application security scanner that covers the OWASP Top 10.
    

Web
---

-   Smartbear ©️ — Test automation and performance testing platform

WebAssembly
-----------

-   Wasabi — Wasabi is a framework for writing dynamic analyses for WebAssembly, written in JavaScript.

XML
---

-   WhiteHat Sentinel Dynamic ©️ — Part of the WhiteHat Application Security Platform. Dynamic application security scanner that covers the OWASP Top 10.

License
-------

To the extent possible under law, Matthias Endler has waived all copyright and related or neighboring rights to this work. The underlying source code used to format and display that content is licensed under the MIT license.

Title image Designed by Freepik.
