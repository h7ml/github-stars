---
project: formula
stars: 45
description: Formula language for JavaScript
url: https://github.com/formula/formula
---

Best function and expression library for JSON.

Install
-------

npm install --save formula

General Usage
-------------

import { run } from "formula";

// jsonpath + spreadsheet-like expression system eats json for lunch.
run("$.a.b = 1", '{ "a": { "b": 1 } }')

// sum, vlookup, hlookup and friends.
run("sum(a, b, c) = 1+2+3", { a: 1, b: 2, c: 3 });

Browser ready
-------------

Add to the browser with:

<script type\="text/javascript" src\="https://unpkg.com/formula@3.16.0/lib/formula.min.js"
