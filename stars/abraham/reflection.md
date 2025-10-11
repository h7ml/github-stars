---
project: reflection
stars: 283
description: Lightweight (3K) ES Module implementation of reflect-metadata
url: https://github.com/abraham/reflection
---

Reflection
==========

Lightweight ES Module implementation of reflect-metadata to work with TypeScript's experimental decorator support.

Why?
----

The main reason for this library is to provide a much smaller implementation that can be included as a module.

-   ES module
    -   `reflection` can be loaded with `<script type="module" src="..."></script>`
-   Size (uncompressed)
    -   `reflect-metadata` is ~50K
    -   `core-js/es7/reflect` is ~80K
    -   `@abraham/reflection` is ~3K

Read about how to drop 20K from your production Angular app by switching to this.

Install
-------

npm install @abraham/reflection

Usage
-----

import '@abraham/reflection';
Reflect.defineMetadata(metadataKey, metadataValue, target);

You can also import `Reflection`:

import { Reflection as Reflect } from '@abraham/reflection';
Reflect.defineMetadata(metadataKey, metadataValue, target);

API
---

Reflection does not currently cover the complete API surface of reflect-metadata. The following methods are available:

Reflect.decorate(...);
Reflect.defineMetadata(...);
Reflect.getMetadata(...);
Reflect.hasMetadata(...);
Reflect.getOwnMetadata(...);
Reflect.hasOwnMetadata(...);
Reflect.metadata(...);
