---
project: proposal-change-array-by-copy
stars: 506
description: Provides additional methods on Array.prototype and TypedArray.prototype to enable changes on the array by returning a new copy of it with the change.
url: https://github.com/tc39/proposal-change-array-by-copy
---

> **Note** This proposal is 'finished' and has been merged into the ECMAScript spec. PR

Change Array by copy
====================

Provides additional methods on `Array.prototype` and `TypedArray.prototype` to enable changes on the array by returning a new copy of it with the change.

Status
------

This proposal is currently at Stage 4.

-   Candidate spec text

Champions
---------

-   Robin Ricard (Bloomberg)
-   Ashley Claymore (Bloomberg)

Reviewers
---------

-   Jordan Harband
-   Justin Ridgewell
-   Sergey Rubanov

Overview
--------

This proposal introduces the following function properties to `Array.prototype`:

-   `Array.prototype.toReversed() -> Array`
-   `Array.prototype.toSorted(compareFn) -> Array`
-   `Array.prototype.toSpliced(start, deleteCount, ...items) -> Array`
-   `Array.prototype.with(index, value) -> Array`

All of those methods keep the target Array untouched and returns a copy of it with the change performed instead.

`toReversed`, `toSorted`, and `with` will also be added to TypedArrays:

-   `TypedArray.prototype.toReversed() -> TypedArray`
-   `TypedArray.prototype.toSorted(compareFn) -> TypedArray`
-   `TypedArray.prototype.with(index, value) -> TypedArray`

These methods will then be available on subclasses of `TypedArray`. i.e. the following:

-   `Int8Array`
-   `Uint8Array`
-   `Uint8ClampedArray`
-   `Int16Array`
-   `Uint16Array`
-   `Int32Array`
-   `Uint32Array`
-   `Float32Array`
-   `Float64Array`
-   `BigInt64Array`
-   `BigUint64Array`

### Example

const sequence \= \[1, 2, 3\];
sequence.toReversed(); // => \[3, 2, 1\]
sequence; // => \[1, 2, 3\]

const outOfOrder \= new Uint8Array(\[3, 1, 2\]);
outOfOrder.toSorted(); // => Uint8Array \[1, 2, 3\]
outOfOrder; // => Uint8Array \[3, 1, 2\]

const correctionNeeded \= \[1, 1, 3\];
correctionNeeded.with(1, 2); // => \[1, 2, 3\]
correctionNeeded; // => \[1, 1, 3\]

Motivation
----------

The `Tuple.prototype` introduces these functions as a way to deal with the immutable aspect of the Tuples in Record & Tuple. While Arrays are not immutable by nature, this style of programming can be beneficial to users dealing with frozen arrays for instance.

This proposal notably makes it easier to write code able to deal with Arrays and Tuples interchangeably.

Relationship with Record & Tuple
--------------------------------

While this proposal is derived from Record & Tuple, it should progress independently.

If web compatibility prescribes it, property names defined in this proposal are going to be changed. Those changes should be reflected on `Tuple.prototype`.

Implementations
---------------

-   Firefox/SpiderMonkey, shipping unflagged since Firefox 115
    
-   Safari/JavaScriptCore, shipping unflagged since Safari Tech Preview 146
    
-   Chrome/V8, shipping unflagged since Chrome 110
    
-   Ladybird/LibJS, shipping unflagged
    
-   core-js
    
    -   change-array-by-copy
-   es-shims:
    
    -   `array.prototype.tosorted`
    -   `array.prototype.toreversed`
    -   `array.prototype.tospliced`
    -   `array.prototype.with`
-   ./polyfill.js (minimalist reference implementation)
