---
project: primjs
stars: 1012
description: JavaScript Engine Optimized for Lynx
url: https://github.com/lynx-family/primjs
---

PrimJS is a lightweight, high-performance JavaScript engine designed specifically for the Lynx cross-platform framework. Fully supporting ES2019, PrimJS is built on top of QuickJS and delivers superior performance and a better development experience compared to QuickJS.

Key features include:
---------------------

-   **Optimized Interpreter:** PrimJS introduces a template interpreter leveraging stack caching and register optimizations, significantly enhancing performance.
-   **Seamless Object Model Integration:** The engine's object model integrates efficiently with the Lynx object model, reducing data communication overhead and improving rendering performance.
-   **Advanced Memory Management:** Utilizing a Garbage Collector (GC) instead of QuickJS's Reference Counting, PrimJS offers better performance, improved memory analyzability, and reduced risk of memory leaks.
-   **Comprehensive Debugging Support:** Full implementation of the Chrome DevTools Protocol (CDP) enables seamless integration with Chrome Debugger for enhanced debugging capabilities.

Performance
-----------

For detailed performance benchmarks, please refer to performance comparison document. The benchmark results show that PrimJS outperforms QuickJS by approximately 28% in overall score (3735 vs 2904) on the Octane Benchmark suite. We are continuously working on performance optimizations.

Quick Start
-----------

### Dependencies

1.  **Clone the repository:**
    
    git clone git@github.com:lynx-family/primjs.git
    
2.  **Install dependencies:**
    
    cd primjs
    source tools/envsetup.sh
    hab sync .
    

### Building on Linux and macOS

PrimJS uses `gn` and `ninja` for building. Follow these steps to generate the `qjs` binary:

gn gen out/Default
ninja -C out/Default qjs\_exe

To enable the template interpreter and garbage collector, use the following `gn` arguments (for example, on the arm64 platform, these arguments configure the build system to target ARM64 architecture while enabling the bytecode-based template interpreter and automatic memory management):

gn gen out/Default --args= '
    target\_cpu="arm64" 
    enable\_primjs\_snapshot = true
    enable\_compatible\_mm = true
    enable\_tracing\_gc = true'
ninja -C out/Default -j32 qjs\_exe

### Release Build

For a release build, set the `is_debug = false` argument during configuration.

### Running PrimJS

The primary binary is `qjs`, located at `out/Default/qjs`. Use it to run JavaScript files:

./out/Default/qjs test.js

### Running Tests

Run the following steps from the root directory to build and execute unit tests:

#### Build Unit Tests

python3 tools/ci/check\_test\_build.py

#### Run Unit Tests

python3 tools/ci/check\_test\_run.py

How to Contribute
-----------------

### Code of Conduct

We are devoted to ensuring a positive, inclusive, and safe environment for all contributors. Please find our Code of Conduct for detailed information.

### Contributing Guide

We welcome you to join and become a member of Lynx Authors. It's people like you that make this project great.

Please refer to lynx contributing guide for details.

### Open Source Roadmap

Discussions
-----------

Large discussions and proposals are discussed in Github Discussions

License
-------

PrimJS is Apache licensed, as found in the LICENSE file.
