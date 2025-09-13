---
project: remote-cache
stars: 186
description: The Vercel Remote Cache SDK
url: https://github.com/vercel/remote-cache
---

Vercel Remote Cache SDK
=======================

An SDK for Remote Caching on Vercel.

Tip

Vercel Remote Cache is now free for all plans. Get started today at vercel.com.

Table of Contents
-----------------

-   Summary
-   Examples
-   Packages
-   Contributing

Summary
-------

Remote Computation Caching (or just Remote Caching) is a feature of advanced build tools like Turborepo, Bazel, and Buck to cache compiled computations and code artifacts in the cloud with the hope of recycling them across machines to reduce overall build/computation time. The key idea is that you "never recompute work that’s already been done before."

> Through Vercel's Remote Caching API, teams can leverage this advanced primitive without needing to think about hosting, infrastructure, or maintenance.

This repository holds the source code to the Vercel Remote Caching SDK as well as examples of build systems that leverage it. For those looking to integrate their build systems with Vercel Remote Caching, you've come to the right place. The @vercel/remote SDK is a thin layer over our existing REST API. We've provided packages that implement this SDK for Nx and Rush build tools. See our examples list of build systems using the Vercel Remote Cache.

Examples
--------

Build systems and tools that integrate with Vercel Remote Caching.

-   Turborepo
-   Rush
-   Nx

Packages
--------

Name

Description

Package

@vercel/remote

An SDK for remote artifact caching on Vercel

@vercel/remote-nx

Remote caching plugin for Nx using Vercel Remote Cache

@vercel/remote-rush

Remote caching plugin for Rush using Vercel Remote Cache

Contributing
------------

To develop on this package see the CONTRIBUTING.md.
