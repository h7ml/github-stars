---
project: got
stars: 14760
description: 🌐 Human-friendly and powerful HTTP request library for Node.js
url: https://github.com/sindresorhus/got
---

  
  
  
  
  
  

* * *

Sindre's open source work is supported by the community.  
Special thanks to:

  
  
  

* * *

  
  
  
  
  
  
  

> Human-friendly and powerful HTTP request library for Node.js

See how Got compares to other HTTP libraries

* * *

**You probably want Ky instead, by the same people. It's smaller, works in the browser too, and is more stable since it's built on `Fetch`. Or fetch-extras for simple needs.**

* * *

**Support questions should be asked here.**

Install
-------

npm install got

**Warning:** This package is native ESM and no longer provides a CommonJS export. If your project uses CommonJS, you will have to convert to ESM. Please don't open issues for questions regarding CommonJS / ESM.

**Got v11 is no longer maintained and we will not accept any backport requests.**

Take a peek
-----------

**A quick start guide is available.**

### JSON mode

Got has a dedicated option for handling JSON payload.  
Furthermore, the promise exposes a `.json<T>()` function that returns `Promise<T>`.

import got from 'got';

const {data} \= await got.post('https://httpbin.org/anything', {
	json: {
		hello: 'world'
	}
}).json();

console.log(data);
//=> {"hello": "world"}

For advanced JSON usage, check out the `parseJson` and `stringifyJson` options.

**For more useful tips like this, visit the Tips page.**

Highlights
----------

-   Used by 10K+ packages and 5M+ repos
-   Actively maintained
-   Trusted by many companies

Documentation
-------------

By default, Got will retry on failure. To disable this option, set `options.retry.limit` to 0.

#### Main API

-   Promise API
-   Options
-   Stream API
-   Pagination API
-   Advanced HTTPS API
-   HTTP/2 support
-   `Response` class

#### Timeouts and retries

-   Advanced timeout handling
-   Retries on failure
-   Errors with metadata

#### Advanced creation

-   Hooks
-   Instances
-   Progress events & other events
-   Plugins
-   Compose

#### Cache, Proxy and UNIX sockets

-   RFC compliant caching
-   Proxy support
-   Unix Domain Sockets

#### Integration

-   Diagnostics Channel
-   TypeScript support
-   AWS
-   Testing

* * *

### Migration guides

-   Request migration guide
    -   _(Note that Request is unmaintained)_
-   Axios
-   Node.js

Got plugins
-----------

-   `got4aws` - Got convenience wrapper to interact with AWS v4 signed APIs
-   `gh-got` - Got convenience wrapper to interact with the GitHub API
-   `gl-got` - Got convenience wrapper to interact with the GitLab API
-   `gotql` - Got convenience wrapper to interact with GraphQL using JSON-parsed queries instead of strings
-   `got-fetch` - Got with a `fetch` interface
-   `got-scraping` - Got wrapper specifically designed for web scraping purposes
-   `got-ssrf` - Got wrapper to protect server-side requests against SSRF attacks

Comparison
----------

`got`

`node-fetch`

`ky`

`axios`

`superagent`

HTTP/2 support

✔️¹

❌

✔️

❌

✔️\*\*

Browser support

❌

✔️\*

✔️

✔️

✔️

Promise API

✔️

✔️

✔️

✔️

✔️

Stream API

✔️

Node.js only

❌

❌

✔️

Pagination API

✔️

❌

❌

❌

❌

Request cancelation

✔️

✔️

✔️

✔️

✔️

RFC compliant caching

✔️

❌

❌

❌

❌

Cookies (out-of-the-box)

✔️

❌

❌

❌

❌

Follows redirects

✔️

✔️

✔️

✔️

✔️

Retries on failure

✔️

❌

✔️

❌

✔️

Progress events

✔️

❌

✔️

Browser only

✔️

Handles gzip/deflate

✔️

✔️

✔️

✔️

✔️

Advanced timeouts

✔️

❌

❌

❌

❌

Timings

✔️

❌

❌

❌

❌

Errors with metadata

✔️

❌

✔️

✔️

❌

JSON mode

✔️

✔️

✔️

✔️

✔️

Custom defaults

✔️

❌

✔️

✔️

❌

Composable

✔️

❌

❌

❌

✔️

Hooks

✔️

❌

✔️

✔️

❌

Issues open

Issues closed

Downloads

Coverage

TBD

Build

Bugs

Dependents

Install size

GitHub stars

TypeScript support

Last commit

\* It's almost API compatible with the browser `fetch` API.  
\*\* Need to switch the protocol manually. Doesn't accept PUSH streams and doesn't reuse HTTP/2 sessions.  
¹ Requires Node.js 15.10.0 or above.  
❇️ Almost-stable feature, but the API may change. Don't hesitate to try it out!  
❔ Feature in early stage of development. Very experimental.

Click here to see the install size of the Got dependencies.

Maintainers
-----------

Sindre Sorhus

Szymon Marczak

These amazing companies are using Got
-------------------------------------

  

> Segment is a happy user of Got! Got powers the main backend API that our app talks to. It's used by our in-house RPC client that we use to communicate with all microservices.
> 
> — Vadim Demedes

> Antora, a static site generator for creating documentation sites, uses Got to download the UI bundle. In Antora, the UI bundle (aka theme) is maintained as a separate project. That project exports the UI as a zip file we call the UI bundle. The main site generator downloads that UI from a URL using Got and streams it to vinyl-zip to extract the files. Those files go on to be used to create the HTML pages and supporting assets.
> 
> — Dan Allen

> GetVoIP is happily using Got in production. One of the unique capabilities of Got is the ability to handle Unix sockets which enables us to build a full control interfaces for our docker stack.
> 
> — Daniel Kalen

> We're using Got inside of Exoframe to handle all the communication between CLI and server. Exoframe is a self-hosted tool that allows simple one-command deployments using Docker.
> 
> — Tim Ermilov

> Karaoke Mugen uses Got to fetch content updates from its online server.
> 
> — Axel Terizaki

> Renovate uses Got, gh-got and gl-got to send millions of queries per day to GitHub, GitLab, npmjs, PyPi, Packagist, Docker Hub, Terraform, CircleCI, and more.
> 
> — Rhys Arkins

> Resistbot uses Got to communicate from the API frontend where all correspondence ingresses to the officials lookup database in back.
> 
> — Chris Erickson

> Natural Cycles is using Got to communicate with all kinds of 3rd-party REST APIs (over 9000!).
> 
> — Kirill Groshkov

> Microlink is a cloud browser as an API service that uses Got widely as the main HTTP client, serving ~22M requests a month, every time a network call needs to be performed.
> 
> — Kiko Beats

> We’re using Got at Radity. Thanks for such an amazing work!
> 
> — Mirzayev Farid
