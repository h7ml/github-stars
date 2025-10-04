---
project: fil-c
stars: 1416
description: Fil-C: completely compatible memory safety for C and C++
url: https://github.com/pizlonator/fil-c
---

Fil-C 0.671
===========

Fil-C is a fanatically compatible memory-safe implementation of C and C++. Lots of software compiles and runs with Fil-C with zero or minimal changes. All memory safety errors are caught as Fil-C panics. Fil-C achieves this using a combination of concurrent garbage collection and invisible capabilities (each pointer in memory has a corresponding capability, not visible to the C address space). Every fundamental C operation (as seen in LLVM IR) is checked against the capability. Fil-C has no `unsafe` escape hatch of any kind.

Fil-C is special because:

-   Fil-C achieves full safety with no escape hatches. There is no `unsafe` keyword in Fil-C that could be used to turn off protections. It's not even possible to link to unsafe code.
    
-   Fil-C's capability-based approach achieves a similar level of safety to hardware capabilities like CHERI, except that it runs on stock hardware (X86\_64, currently).
    
-   Fil-C is engineered to prevent memory safety bugs from being used for exploitation rather than just simply flagging them often enough to find bugs. This makes Fil-C different from AddressSanitizer, HWAsan, or MTE, which can all be bypassed by attackers. The key difference that makes this possible is that Fil-C is capability based (so each pointer knows what range of memory it may access, and how it may access it) rather than tag based (where pointer accesses are allowed if they hit valid memory).
    
-   From a language user standpoint, Fil-C is just C and C++ with GCC/clang extensions. It's more likely than not that your favorite C or C++ program or library compiles in Fil-C with zero changes. The Fil-C compiler is based on clang 20.1.8, so it supports C17 and C++20.
    

License
-------

The compiler (clang + LLVM) is covered by LLVM-LICENSE.txt. The runtime is covered by PAS-LICENSE.txt (see libpas/LICENSE.txt in the source distribution). The libc is covered by MUSL-LICENSE.txt (see projects/yolomusl/COPYRIGHT and projects/usermusl/COPYRIGHT in the source distribution). The libc++/libc++abi are covered by LLVM-LICENSE.txt.

You can fetch the compiler, runtime, libc++/libc++abi, and libc (musl) source from https://github.com/pizlonator/fil-c. The source distribution also includes many programs that have been ported to Fil-C in the projects/ directory, and they have a variety of licenses.

Requirements
------------

Fil-C only works on Linux/X86\_64.

Previous versions worked on Darwin/ARM64 and FreeBSD, but now I'm focusing just on Linux/X86\_64 because it allows me to do a more faithful job of implementing libc. There's nothing fundamentally stopping Fil-C from working on ARM or OSes other than Linux.

Getting Started
---------------

If you downloaded Fil-C binaries, run:

```
./setup.sh
```

If you downloaded Fil-C source, run:

```
./build_all_fast.sh
```

Then you'll be able to use Fil-C from within this directory.

The binary distribution of Fil-C comes with musl as the libc. Using `./build_all_fast.sh` in the source distribution also builds Fil-C using musl. If you are using source, then you can also:

-   `./build_all_fast_glibc.sh` - builds a similar setup but with glibc 2.40 as the libc.
    
-   `./build_all.sh` - full musl-based build (also builds lots of software that was ported to Fil-C).
    
-   `./build_all_glibc.sh` - full glibc-based build (builds even more software that was ported to Fil-C).
    

Things That Work
----------------

Lots of software packages work in Fil-C with zero or minimal changes, including big ones like openssl, CPython, SQLite, and many others. Fil-C is powerful enough to support a fully memory safe Linux userland.

Fil-C has full support for C and C++ plus almost all of the extensions that clang 20 supports. Fil-C has excellent support for atomics and SIMD intrinsics, for example.

Fil-C catches all of the stuff that makes memory safety in C hard, like:

-   Out-of-bounds on the heap or stack.
    
-   Use-after free (also heap or stack).
    
-   Type confusion between pointers and non-pointers.
    
-   Type errors arising from linking.
    
-   Type errors arising from misuse of va\_lists.
    
-   Pointer races.
    
-   System calls. All buffers passed to system calls are checked for bounds and type.
    
-   Lots of other stuff.
    

Fil-C comes with a reasonably complete POSIX libc and even supports tricky features like threads, signal handling, `mmap`/`munmap`, `longjmp`/`setjmp`, and C++ exceptions.

Learn More
----------

You can learn more about Fil-C by visiting the website.

You can also e-mail me: pizlo@mac.com

Follow me on Twitter.

File issues at GH.
