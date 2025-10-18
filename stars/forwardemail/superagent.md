---
project: superagent
stars: 16641
description: Ajax for Node.js and browsers (JS HTTP client). Maintained for @forwardemail, @ladjs, @spamscanner, @breejs, @cabinjs, and @lassjs.
url: https://github.com/forwardemail/superagent
---

superagent
==========

> Small progressive client-side HTTP request library, and Node.js module with the same API, supporting many high-level HTTP client features. Maintained for Forward Email and Lad.

Table of Contents
-----------------

-   Install
-   Usage
    -   Node
    -   Browser
-   Supported Platforms
    -   Required Browser Features
-   Plugins
-   Upgrading from previous versions
-   Contributors
-   License

Install
-------

npm:

npm install superagent

yarn:

yarn add superagent

Usage
-----

### Node

const superagent \= require('superagent');

// callback
superagent
  .post('/api/pet')
  .send({ name: 'Manny', species: 'cat' }) // sends a JSON post body
  .set('X-API-Key', 'foobar')
  .set('accept', 'json')
  .end((err, res) \=> {
    // Calling the end function will send the request
  });

// promise with then/catch
superagent.post('/api/pet').then(console.log).catch(console.error);

// promise with async/await
(async () \=> {
  try {
    const res \= await superagent.post('/api/pet');
    console.log(res);
  } catch (err) {
    console.error(err);
  }
})();

### Browser

**The browser-ready, minified version of `superagent` is only 50 KB (minified and gzipped).**

Browser-ready versions of this module are available via jsdelivr, unpkg, and also in the `node_modules/superagent/dist` folder in downloads of the `superagent` package.

> Note that we also provide unminified versions with `.js` instead of `.min.js` file extensions.

#### VanillaJS

This is the solution for you if you're just using `<script>` tags everywhere!

<script src\="https://cdnjs.cloudflare.com/polyfill/v3/polyfill.min.js?features=WeakRef,BigInt"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/superagent"\></script\>
<!-- if you wish to use unpkg.com instead: -->
<!-- <script src="https://unpkg.com/superagent"></script> -->
<script type\="text/javascript"\>
  (function() {
    // superagent is exposed as \`window.superagent\`
    // if you wish to use "request" instead please
    // uncomment the following line of code:
    // \`window.request = superagent;\`
    superagent
      .post('/api/pet')
      .send({ name: 'Manny', species: 'cat' }) // sends a JSON post body
      .set('X-API-Key', 'foobar')
      .set('accept', 'json')
      .end(function (err, res) {
        // Calling the end function will send the request
      });
  })();
</script\>

#### Bundler

If you are using browserify, webpack, rollup, or another bundler, then you can follow the same usage as Node above.

Supported Platforms
-------------------

-   Node: v14.18.0+
    
-   Browsers (see .browserslistrc):
    
    npx browserslist
    
    and\_chr 102
    and\_ff 101
    and\_qq 10.4
    and\_uc 12.12
    android 101
    chrome 103
    chrome 102
    chrome 101
    chrome 100
    edge 103
    edge 102
    edge 101
    firefox 101
    firefox 100
    firefox 91
    ios\_saf 15.5
    ios\_saf 15.4
    ios\_saf 15.2-15.3
    ios\_saf 15.0-15.1
    ios\_saf 14.5-14.8
    ios\_saf 14.0-14.4
    ios\_saf 12.2-12.5
    kaios 2.5
    op\_mini all
    op\_mob 64
    opera 86
    opera 85
    safari 15.5
    safari 15.4
    samsung 17.0
    samsung 16.0
    

### Required Browser Features

We recommend using https://cdnjs.cloudflare.com/polyfill/ (specifically with the bundle mentioned in VanillaJS above):

<script src\="https://cdnjs.cloudflare.com/polyfill/v3/polyfill.min.js?features=WeakRef,BigInt"\></script\>

-   WeakRef is not supported in Opera 85, iOS Safari 12.2-12.5
-   BigInt is not supported in iOS Safari 12.2-12.5

Plugins
-------

SuperAgent is easily extended via plugins.

const nocache \= require('superagent-no-cache');
const superagent \= require('superagent');
const prefix \= require('superagent-prefix')('/static');

superagent
  .get('/some-url')
  .query({ action: 'edit', city: 'London' }) // query string
  .use(prefix) // Prefixes \*only\* this request
  .use(nocache) // Prevents caching of \*only\* this request
  .end((err, res) \=> {
    // Do something
  });

Existing plugins:

-   superagent-no-cache - prevents caching by including Cache-Control header
-   superagent-prefix - prefixes absolute URLs (useful in test environment)
-   superagent-suffix - suffix URLs with a given path
-   superagent-mock - simulate HTTP calls by returning data fixtures based on the requested URL
-   superagent-mocker — simulate REST API
-   superagent-cache - A global SuperAgent patch with built-in, flexible caching
-   superagent-cache-plugin - A SuperAgent plugin with built-in, flexible caching
-   superagent-jsonapify - A lightweight json-api client addon for superagent
-   superagent-serializer - Converts server payload into different cases
-   superagent-httpbackend - stub out requests using AngularJS' $httpBackend syntax
-   superagent-throttle - queues and intelligently throttles requests
-   superagent-charset - add charset support for node's SuperAgent
-   superagent-verbose-errors - include response body in error messages for failed requests
-   superagent-declare - A simple declarative API for SuperAgent
-   superagent-node-http-timings - measure http timings in node.js
-   superagent-cheerio - add cheerio to your response content automatically. Adds `res.$` for HTML and XML response bodies.
-   @certible/superagent-aws-sign - Sign AWS endpoint requests, it uses the aws4 to authenticate the SuperAgent requests

Please prefix your plugin with `superagent-*` so that it can easily be found by others.

For SuperAgent extensions such as couchdb and oauth visit the wiki.

Upgrading from previous versions
--------------------------------

Please see GitHub releases page for the current changelog.

Our breaking changes are mostly in rarely used functionality and from stricter error handling.

-   6.0 to 6.1
    -   Browser behaviour changed to match Node when serializing `application/x-www-form-urlencoded`, using `arrayFormat: 'indices'` semantics of `qs` library. (See: https://www.npmjs.com/package/qs#stringifying)
-   5.x to 6.x:
    -   Retry behavior is still opt-in, however we now have a more fine-grained list of status codes and error codes that we retry against (see updated docs)
    -   A specific issue with Content-Type matching not being case-insensitive is fixed
    -   Set is now required for IE 9, see Required Browser Features for more insight
-   4.x to 5.x:
    -   We've implemented the build setup of Lass to simplify our stack and linting
    -   Unminified browserified build size has been reduced from 48KB to 20KB (via `tinyify` and the latest version of Babel using `@babel/preset-env` and `.browserslistrc`)
    -   Linting support has been added using `caniuse-lite` and `eslint-plugin-compat`
    -   We can now target what versions of Node we wish to support more easily using `.babelrc`
-   3.x to 4.x:
    -   Ensure you're running Node 6 or later. We've dropped support for Node 4.
    -   We've started using ES6 and for compatibility with Internet Explorer you may need to use Babel.
    -   We suggest migrating from `.end()` callbacks to `.then()` or `await`.
-   2.x to 3.x:
    -   Ensure you're running Node 4 or later. We've dropped support for Node 0.x.
    -   Test code that calls `.send()` multiple times. Invalid calls to `.send()` will now throw instead of sending garbage.
-   1.x to 2.x:
    -   If you use `.parse()` in the _browser_ version, rename it to `.serialize()`.
    -   If you rely on `undefined` in query-string values being sent literally as the text "undefined", switch to checking for missing value instead. `?key=undefined` is now `?key` (without a value).
    -   If you use `.then()` in Internet Explorer, ensure that you have a polyfill that adds a global `Promise` object.
-   0.x to 1.x:
    -   Instead of 1-argument callback `.end(function(res){})` use `.then(res => {})`.

Contributors
------------

Name

**Kornel Lesiński**

**Peter Lyons**

**Hunter Loftis**

**Nick Baugh**

License
-------

MIT © TJ Holowaychuk
