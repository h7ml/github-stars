---
project: vm.js
stars: 441
description: Javascript 解释器. Javascript Interpreter
url: https://github.com/axetroy/vm.js
---

vm.js
=====

Run Javascript code in ECMAScript, without eval(), new Function(), setTimeout()...

It base on https://github.com/bramblex/jsjs

Try it out

Usage
-----

import vm from "@axetroy/vm";

const sanbox \= { console: console };

const context \= vm.createContext(sanbox);

try {
  vm.runInContext(\`console.log("Hello world");\`, context);
} catch (err) {
  console.error(err);
}

Support
-------

-   ECMA5
-   ES2015
    -   Let and const
    -   Block scoping
    -   ES modules
    -   Arrow functions
    -   Class
    -   Computed properties
    -   Destructuring
    -   For of
    -   Function/Class name
    -   Literals
    -   Object super
    -   Default and rest parameters
    -   Shorthand properties
    -   Spread
    -   Template literals
    -   Lifting template literal restriction
    -   Unicode-regex
    -   Generator function
-   ES2016
    -   Exponentiation operator
-   ES2017
    -   Trailing commas in function parameter lists and calls
    -   Async functions
    -   Shared memory and atomics
-   ES2018
    -   Asynchronous iteration
    -   Promise.prototype.finally()
    -   s (dotAll) flag for regular expressions
    -   RegExp named capture groups
    -   RegExp Unicode Property Escapes
-   Experimental
    -   Object rest spread
    -   Class property
    -   Do expressions
    -   Optional catch binding
    -   Decorators
    -   Global

Test
----

I have written a lot of test case for this, look at here

Now it still in development, got a lot of work to do and more detail to resolve.

I will release the first stable version of write 500 test case.

If you want to join it. welcome to PR.

### How to run a single test

npx tsc && npx ava ./build/test/ecma5/array/

### How to run the whole test

npm run test

### Related

bramblex/jsjs

jkeylu/evil-eval

License
-------

The MIT License
