---
project: unstorage
stars: 2331
description:  💾 Unstorage provides an async Key-Value storage API with conventional features like multi driver mounting, watching and working with metadata, dozens of built-in drivers and a tiny core.
url: https://github.com/unjs/unstorage
---

💾 Unstorage
============

Unstorage provides an async Key-Value storage API with conventional features like multi driver mounting, watching and working with metadata, dozens of built-in drivers and a tiny core.

👉 Documentation

Features
--------

-   Designed for all environments: Browser, NodeJS, and Workers
-   Lots of Built-in drivers
-   Asynchronous API
-   Unix-style driver mounting to combine storages
-   Default in-memory storage
-   Tree-shakable utils and tiny core
-   Auto JSON value serialization and deserialization
-   Binary and raw value support
-   State snapshots and hydration
-   Storage watcher
-   HTTP Storage with built-in server

Usage
-----

Install `unstorage` npm package:

# yarn
yarn add unstorage

# npm
npm install unstorage

# pnpm
pnpm add unstorage

import { createStorage } from "unstorage";

const storage \= createStorage(/\* opts \*/);

await storage.getItem("foo:bar"); // or storage.getItem('/foo/bar')

👉 Check out the the documentation for usage information.

Nightly release channel
-----------------------

You can use the nightly release channel to try the latest changes in the `main` branch via `unstorage-nightly`.

If directly using `unstorage` in your project:

{
  "devDependencies": {
    "unstorage": "npm:unstorage-nightly"
  }
}

If using `unstorage` via another tool in your project:

{
  "resolutions": {
    "unstorage": "npm:unstorage-nightly"
  }
}

Contribution
------------

-   Clone repository
-   Install dependencies with `pnpm install`
-   Use `pnpm dev` to start jest watcher verifying changes
-   Use `pnpm test` before pushing to ensure all tests and lint checks passing

License
-------

MIT
