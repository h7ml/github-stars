---
project: grpc
stars: 43601
description: C++ based gRPC (C++, Python, Ruby, Objective-C, PHP, C#)
url: https://github.com/grpc/grpc
---

gRPC – An RPC library and framework
===================================

gRPC is a modern, open source, high-performance remote procedure call (RPC) framework that can run anywhere. gRPC enables client and server applications to communicate transparently, and simplifies the building of connected systems.

**Homepage:**

grpc.io

**Mailing List:**

grpc-io@googlegroups.com

To start using gRPC
-------------------

To maximize usability, gRPC supports the standard method for adding dependencies to a user's chosen language (if there is one). In most languages, the gRPC runtime comes as a package available in a user's language package manager.

For instructions on how to use the language-specific gRPC runtime for a project, please refer to these documents

-   C++: follow the instructions under the `src/cpp` directory
-   C#/.NET: NuGet packages `Grpc.Net.Client`, `Grpc.AspNetCore.Server`
-   Dart: pub package `grpc`
-   Go: `go get google.golang.org/grpc`
-   Java: Use JARs from Maven Central Repository
-   Kotlin: Use JARs from Maven Central Repository
-   Node: `npm install @grpc/grpc-js`
-   Objective-C: Add `gRPC-ProtoRPC` dependency to podspec
-   PHP: `pecl install grpc`
-   Python: `pip install grpcio`
-   Ruby: `gem install grpc`
-   WebJS: follow the grpc-web instructions

Per-language quickstart guides and tutorials can be found in the documentation section on the grpc.io website. Code examples are available in the examples directory.

Precompiled bleeding-edge package builds of gRPC `master` branch's `HEAD` are uploaded daily to packages.grpc.io.

To start developing gRPC
------------------------

Contributions are welcome!

Please read How to contribute which will guide you through the entire workflow of how to build the source code, how to run the tests, and how to contribute changes to the gRPC codebase. The "How to contribute" document also contains info on how the contribution process works and contains best practices for creating contributions.

Troubleshooting
---------------

Sometimes things go wrong. Please check out the Troubleshooting guide if you are experiencing issues with gRPC.

Performance
-----------

See the Performance dashboard for performance numbers of master branch daily builds.

Concepts
--------

See gRPC Concepts

About This Repository
---------------------

This repository contains source code for gRPC libraries implemented in multiple languages written on top of a shared C++ core library src/core.

Libraries in different languages may be in various states of development. We are seeking contributions for all of these libraries:

Language

Source

Shared C++ \[core library\]

src/core

C++

src/cpp

Ruby

src/ruby

Python

src/python

PHP

src/php

C# (core library based)

src/csharp

Objective-C

src/objective-c

Language

Source repo

Java

grpc-java

Kotlin

grpc-kotlin

Go

grpc-go

NodeJS

grpc-node

WebJS

grpc-web

Dart

grpc-dart

.NET (pure C# impl.)

grpc-dotnet

Swift

grpc-swift
