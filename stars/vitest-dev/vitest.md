---
project: vitest
stars: 15289
description: Next generation testing framework powered by Vite.
url: https://github.com/vitest-dev/vitest
---

Vitest
======

Next generation testing framework powered by Vite.

**Get involved!**

Documentation | Getting Started | Examples | Why Vitest?

中文文档

  
  

Features
--------

-   Vite's config, transformers, resolvers, and plugins. Use the same setup from your app!
-   Jest Snapshot
-   Chai built-in for assertions, with Jest expect compatible APIs
-   Smart & instant watch mode, like HMR for tests!
-   Native code coverage via `v8` or `istanbul`.
-   Tinyspy built-in for mocking, stubbing, and spies.
-   JSDOM and happy-dom for DOM and browser API mocking
-   Browser Mode for running component tests in the browser
-   Components testing (Vue, React, Svelte, Lit, Marko)
-   Benchmarking support with Tinybench
-   Projects support
-   expect-type for type-level testing
-   ESM first, top level await
-   Out-of-box TypeScript / JSX support
-   Filtering, timeouts, concurrent for suite and tests
-   Sharding support
-   Reporting Uncaught Errors
-   Run your tests in the browser natively

> Vitest requires Vite >=v6.0.0 and Node >=v20.0.0

import { assert, describe, expect, it } from 'vitest'

describe('suite name', () \=> {
  it('foo', () \=> {
    expect(1 + 1).toEqual(2)
    expect(true).to.be.true
  })

  it('bar', () \=> {
    assert.equal(Math.sqrt(4), 2)
  })

  it('snapshot', () \=> {
    expect({ foo: 'bar' }).toMatchSnapshot()
  })
})

$ npx vitest

Sponsors
--------

### Vladimir Sponsors

### Anthony Fu Sponsors

### Patak Sponsors

Credits
-------

Thanks to:

-   The Jest team and community for creating a delightful testing API
-   @lukeed for the work on uvu where we are inspired a lot from.
-   @pi0 for the idea and implementation of using Vite to transform and bundle the server code.
-   The Vite team for brainstorming the initial idea.
-   @patak-dev for the awesome package name!

Contribution
------------

See Contributing Guide.

License
-------

MIT License © 2021-Present VoidZero Inc. and Vitest contributors
