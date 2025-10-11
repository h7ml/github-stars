---
project: lodash
stars: 61253
description: A modern JavaScript utility library delivering modularity, performance, & extras.
url: https://github.com/lodash/lodash
---

lodash v4.17.21
===============

Site | Docs | FP Guide | Contributing | Wiki | Code of Conduct | Twitter | Chat

The Lodash library exported as a UMD module.

Generated using lodash-cli:

$ npm run build
$ lodash -o ./dist/lodash.js
$ lodash core -o ./dist/lodash.core.js

Download
--------

-   Core build (~4 kB gzipped)
-   Full build (~24 kB gzipped)
-   CDN copies

Lodash is released under the MIT license & supports modern environments.  
Review the build differences & pick one that’s right for you.

Installation
------------

In a browser:

<script src\="lodash.js"\></script\>

Using npm:

$ npm i -g npm
$ npm i --save lodash

In Node.js:

// Load the full build.
var \_ \= require('lodash');
// Load the core build.
var \_ \= require('lodash/core');
// Load the FP build for immutable auto-curried iteratee-first data-last methods.
var fp \= require('lodash/fp');

// Load method categories.
var array \= require('lodash/array');
var object \= require('lodash/fp/object');

// Cherry-pick methods for smaller browserify/rollup/webpack bundles.
var at \= require('lodash/at');
var curryN \= require('lodash/fp/curryN');

**Note:**  
Install n\_ for Lodash use in the Node.js < 6 REPL.

Why Lodash?
-----------

Lodash makes JavaScript easier by taking the hassle out of working with arrays,  
numbers, objects, strings, etc. Lodash’s modular methods are great for:

-   Iterating arrays, objects, & strings
-   Manipulating & testing values
-   Creating composite functions

Module Formats
--------------

Lodash is available in a variety of builds & module formats.

-   lodash & per method packages
-   lodash-es, babel-plugin-lodash, & lodash-webpack-plugin
-   lodash/fp
-   lodash-amd
