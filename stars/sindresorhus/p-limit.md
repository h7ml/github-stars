---
project: p-limit
stars: 2528
description: Run multiple promise-returning & async functions with limited concurrency
url: https://github.com/sindresorhus/p-limit
---

p-limit
=======

> Run multiple promise-returning & async functions with limited concurrency

_Works in Node.js and browsers._

Install
-------

npm install p-limit

Usage
-----

import pLimit from 'p-limit';

const limit \= pLimit(1);

const input \= \[
	limit(() \=> fetchSomething('foo')),
	limit(() \=> fetchSomething('bar')),
	limit(() \=> doSomething())
\];

// Only one promise is run at once
const result \= await Promise.all(input);
console.log(result);

API
---

### pLimit(concurrency) default export

Returns a `limit` function.

#### concurrency

Type: `number`  
Minimum: `1`

Concurrency limit.

### limit(fn, ...args)

Returns the promise returned by calling `fn(...args)`.

#### fn

Type: `Function`

Promise-returning/async function.

#### args

Any arguments to pass through to `fn`.

Support for passing arguments on to the `fn` is provided in order to be able to avoid creating unnecessary closures. You probably don't need this optimization unless you're pushing a _lot_ of functions.

### limit.map(array, mapperFunction)

Process an array of inputs with limited concurrency.

The mapper function receives the item value and its index.

Returns a promise equivalent to `Promise.all(array.map((item, index) => limit(mapperFunction, item, index)))`.

This is a convenience function for processing inputs that arrive in batches. For more complex use cases, see p-map.

### limit.activeCount

The number of promises that are currently running.

### limit.pendingCount

The number of promises that are waiting to run (i.e. their internal `fn` was not called yet).

### limit.clearQueue()

Discard pending promises that are waiting to run.

This might be useful if you want to teardown the queue at the end of your program's lifecycle or discard any function calls referencing an intermediary state of your app.

Note: This does not cancel promises that are already running.

### limit.concurrency

Get or set the concurrency limit.

### limitFunction(fn, options) named export

Returns a function with limited concurrency.

The returned function manages its own concurrent executions, allowing you to call it multiple times without exceeding the specified concurrency limit.

Ideal for scenarios where you need to control the number of simultaneous executions of a single function, rather than managing concurrency across multiple functions.

import {limitFunction} from 'p-limit';

const limitedFunction \= limitFunction(async () \=> {
	return doSomething();
}, {concurrency: 1});

const input \= Array.from({length: 10}, limitedFunction);

// Only one promise is run at once.
await Promise.all(input);

#### fn

Type: `Function`

Promise-returning/async function.

#### options

Type: `object`

#### concurrency

Type: `number`  
Minimum: `1`

Concurrency limit.

FAQ
---

### How is this different from the `p-queue` package?

This package is only about limiting the number of concurrent executions, while `p-queue` is a fully featured queue implementation with lots of different options, introspection, and ability to pause the queue.

Related
-------

-   p-throttle - Throttle promise-returning & async functions
-   p-debounce - Debounce promise-returning & async functions
-   p-map - Run promise-returning & async functions concurrently with different inputs
-   p-all - Run promise-returning & async functions concurrently with optional limited concurrency
-   More…
