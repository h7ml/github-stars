---
project: vite-plugin-mock-dev-server
stars: 227
description: 🚀mock-dev-server is injected into the vite development environment to simulate requests and data responses.在vite 开发环境中注入 mock-dev-server, 模拟请求和数据响应
url: https://github.com/pengzhanbo/vite-plugin-mock-dev-server
---

vite-plugin-mock-dev-server
===========================

  
  

**Vite Plugin for API mock dev server.**

  

  

  

English | 简体中文

  
  

Features
--------

-   ⚡️ Lightweight, Flexible, Fast.
-   🧲 Not injection-based, non-intrusive to client code.
-   💡 ESModule/commonjs.
-   🦾 Typescript.
-   🔥 HMR
-   🏷 Support `.[cm]?js` / `.ts` / `.json` / `.json5`.
-   📦 Auto import mock file.
-   🎨 Support any lib, like `mockjs`, or do not use it.
-   📥 Path rule matching, request parameter matching.
-   ⚙️ Support Enabled/Disabled any one of the API mock.
-   📀 Supports response body content type such as `text/json/buffer/stream`.
-   ⚖️ Use `server.proxy`
-   🍕 Support `viteConfig.define` and `env` in the mock file.
-   ⚓️ Support `viteConfig.resolve.alias` in the mock file.
-   🌈 Support `vite preview` mode.
-   📤 Support `multipart` content-type, mock upload file.
-   📥 Support mock download file.
-   ⚜️ Support `WebSocket Mock` and `Server-Sent Events Mock`
-   🗂 Support building small independent deployable mock services.

Documentation
-------------

See the documentation for more details.

Install
-------

# npm
npm i -D vite-plugin-mock-dev-server
# yarn
yarn add vite-plugin-mock-dev-server
# pnpm
pnpm add -D vite-plugin-mock-dev-server

Usage
-----

`vite.config.ts`

import { defineConfig } from 'vite'
import { mockDevServerPlugin } from 'vite-plugin-mock-dev-server'

export default defineConfig({
  plugins: \[
    mockDevServerPlugin(/\* plugin options \*/),
  \],
  // The fields defined here can also be used in mock.
  define: {},
  server: {
    // plugin will read \`server.proxy\`
    proxy: {
      '^/api': { target: 'http://example.com' }
    }
  }
})

The plugin will read the configuration of `server.proxy` or `options.prefix`, and enable mock matching for matched URLs.

The plugin will also read the `define` configuration, which supports direct use in mock files.

Edit Mock File
--------------

By default, write mock data in the `mock` directory of your project's root directory:

`mock/**/*.mock.ts` :

import { defineMock } from 'vite-plugin-mock-dev-server'

export default defineMock({
  url: '/api/test',
  body: { a: 1, b: 2 }
})

Methods
-------

### mockDevServerPlugin(pluginOptions)

vite plugin

`vite.config.ts`

import { defineConfig } from 'vite'
import { mockDevServerPlugin } from 'vite-plugin-mock-dev-server'

export default defineConfig({
  plugins: \[
    mockDevServerPlugin({ /\* plugin options \*/ }),
  \]
})

### defineMock(mockOptions)

Mock Options Type Helper

import { defineMock } from 'vite-plugin-mock-dev-server'

export default defineMock({
  url: '/api/test',
  body: {}
})

### createDefineMock(transformer)

Return a custom defineMock function to support preprocessing of mock config.

import path from 'node:path'
import { createDefineMock } from 'vite-plugin-mock-dev-server'

// Preprocessed mock url
const defineAPIMock \= createDefineMock((mock) \=> {
  mock.url \= path.join('/api', mock.url)
})

export default defineApiMock({
  url: '/test' // Complete as '/api/test'
})

### createSSEStream(req, res)

Create a `Server-sent events` write stream to support mocking `EventSource`.

import { createSSEStream, defineMock } from 'vite-plugin-mock-dev-server'

export default defineMock({
  url: '/api/sse',
  response: (req, res) \=> {
    const sse \= createSSEStream(req, res)
    sse.write({ event: 'message', data: { message: 'hello world' } })
    sse.end()
  }
})

Plugin Options
--------------

### prefix

-   **Type:** `string | string[]`
    
-   **Default:** `[]`
    
-   **Details:**
    
    Configure custom matching rules for the mock server. Any request path starting with the value of `prefix` will be proxied to the corresponding target. If the `prefix` value starts with ^, it will be recognized as a RegExp.
    
    > In general, `server.proxy` is sufficient to meet the needs. Adding this item is for compatibility with certain scenarios.
    

### wsPrefix

-   **Type:** `string | string[]`
    
-   **Default:** `[]`
    
-   **Details:**
    
    Configure the matching rules for the WebSocket service. Any request path starting with the value of `wsPrefix` and using the `ws/wss` protocol will be proxied to the corresponding target.
    
    If the value of `wsPrefix` starts with `^`, it will be recognized as a RegExp.
    
    > Different from using `viteConfig.server.proxy` by default for http mock, `websocket mock` does not use the ws-related configuration in `viteConfig.server.proxy`. Also, rules configured in `wsPrefix` cannot be configured simultaneously in `viteConfig.server.proxy`, as it will cause conflicts when starting the vite server because multiple instances of WebSocketServer cannot be implemented for the same request. This conflict is neither a problem with Vite nor with the plugin; it belongs to a reasonable error type. When switching between WebSocket Mock and WebSocket Proxy, please pay attention to avoid duplicate configurations that may cause conflicts.
    

### cwd

-   **Type:** `string`
    
-   **Default:** `process.cwd()`
    
-   **Details:**
    
    Configure the matching context for `include` and `exclude`.
    

### include

-   **Type:** `string | string[]`
    
-   **Default：** `['mock/**/*.mock.{js,ts,cjs,mjs,json,json5}']` (Relative to the root directory)
    
-   **Details:**
    
    Configure to read mock files, which can be a directory, glob, or an array.
    

### exclude

-   **Type:** `string | string[]`
    
-   **Default：** `['**/node_modules/**','**/.vscode/**','**/.git/**']`
    
-   **Details:**
    
    When reading mock files for configuration, the files that need to be excluded can be a directory, glob, or array.
    

### reload

-   **Type:** `boolean`
    
-   **Default:** `false`
    
-   **Details:**
    
    When the mock resource is hot updated, only the data content is updated, but the page is not refreshed by default. If you want to refresh the page every time you modify the mock file, you can open this option.
    

### cors

-   **Type:** `boolean | CorsOptions`
    
-   **Default:** `true`
    
-   **Details:**
    
    Enable by default.
    
    Configure to `cors`, see cors
    

### log

-   **Type:** `boolean | 'info' | 'warn' | 'error' | 'silent' | 'debug'`
    
-   **Default:** `info`
    
-   **Details:**
    
    Enable log and configure log level.
    

### formidableOptions

-   **Type:** `formidable.Options`
    
-   **Details:**
    
    Configure to `formidable`, see formidable options
    
    example: Configure to file upload dir
    
    MockDevServerPlugin({
      formidableOptions: {
        uploadDir: path.join(process.cwd(), 'uploads'),
      }
    })
    

### cookiesOptions

-   **Type:** `CookiesOptions`
    
-   **Details:**
    
    Configure to `cookies`, see cookies
    

### bodyParserOptions

-   **Type:** `BodyParserOptions`
    
-   **Details:**
    
    Configure to `co-body`, see co-body
    

### build

-   **Type:** `boolean | ServerBuildOptions`
    
-   **Default:** `false`
    
-   **Details:**
    
    The configuration needed to build a small, independently deployable mock service.
    
    interface ServerBuildOptions {
      /\*\*
       \* server port
       \* @default 8080
       \*/
      serverPort?: number
      /\*\*
       \* build output dir
       \* @default 'mockServer'
       \*/
      dist?: string
      /\*\*
       \* log level
       \* @default 'error'
       \*/
      log?: LogLevel
    }
    

### priority

-   **Type:** `MockMatchPriority`
    
-   **Details:**
    
    Custom path matching rule priority。read more
    

Mock Options
------------

**http mock**

import { defineMock } from 'vite-plugin-mock-dev-server'
export default defineMock({
  url: '/api/test',
  body: { message: 'hello world' }
})

**websocket mock**

import { defineMock } from 'vite-plugin-mock-dev-server'
export default defineMock({
  url: '/socket.io',
  ws: true,
  setup(wss) {
    wss.on('connection', (ws, req) \=> {
      console.log('connected')
    })
  }
})

### options.url

-   **Type:** `string`
    
-   **Details:**
    
    The interface address that needs to be mocked, supported by path-to-regexp for path matching.
    

### options.enabled

-   **Type:** `boolean`
    
-   **Default:** `true`
    
-   **Details:**
    
    Whether to enable mock for this interface. In most scenarios, we only need to mock some interfaces instead of all requests that have been configured with mock. Therefore, it is important to be able to configure whether to enable it or not.
    

### options.method

-   **Type:** `Method | Method[]`
    
    type Method \= 'GET' | 'POST' | 'PUT' | 'DELETE' | 'OPTIONS' | 'HEAD' | 'PATCH'
    
-   **Default:** `['GET', 'POST']`
    
-   **Details:**
    
    The interface allows request methods
    

### options.type

-   **Type:** `'text' | 'json' | 'buffer' | string`
    
-   **Details:**
    
    Response body data type. And also support types included in mime-db.
    
    When the response body returns a file and you are not sure which type to use, you can pass the file name as the value. The plugin will internally search for matching `content-type` based on the file name suffix.
    

### options.headers

-   **Type:** `object | (request: MockRequest) => object | Promise<object>`
    
-   **Default:** `{ 'Content-Type': 'application/json' }`
    
-   **Details:**
    
    Configure the response body headers
    

### options.status

-   **Type:** `number`
    
-   **Default:** `200`
    
-   **Details:**
    
    Configure Response Header Status Code
    

### options.statusText

-   **Type:** `string`
    
-   **Default:** `"OK"`
    
-   **Details:**
    
    Configure response header status text
    

### options.delay

-   **Type:** `number | [number, number]`
    
-   **Default:** `0`
    
-   **Details:**
    
    Configure response delay time, If an array is passed in, it represents the range of delay time.
    
    unit: `ms`
    

### options.body

-   **Type:** `Body | (request: MockRequest) => Body | Promise<Body>`
    
    type Body \= string | object | Buffer | Readable
    
-   **Details:**
    
    Configure response body data content. `body` takes precedence over `response`.
    

### options.response

-   **Type:** `(req: MockRequest, res: MockResponse, next: (err?: any) => void) => void | Promise<void>`
    
-   **Details:**
    
    If you need to set complex response content, you can use the response method, which is a middleware. Here, you can get information such as req and res of the http request, and then return response data through res.write() | res.end(). Otherwise, you need to execute next() method. In `req`, you can also get parsed request information such as `query`, `params`, `body` and `refererQuery`.
    

### options.cookies

-   **Type:** `CookiesOptions | (request: MockRequest) => CookiesOptions | Promise<CookiesOptions>`
    
    type CookiesOptions \= Record<string, CookieValue\>
    
    type CookieValue \= string | \[string, SetCookie\]
    
-   **Details:**
    
    Configure response body cookies
    

### options.validator

-   **Type:** `Validator | (request: MockRequest) => boolean`
    
    interface Validator {
      /\*\*
       \* The query string located after \`?\` in the request address has been parsed into JSON.
       \*/
      query: Record<string, any\>
      /\*\*
       \* The queryString located after \`?\` in the referer request has been parsed as JSON.
       \*/
      refererQuery: Record<string, any\>
      /\*\*
       \* Body data in the request
       \*/
      body: Record<string, any\>
      /\*\*
       \* The params parameter parsed from the \`/api/id/:id\` in the request address.
       \*/
      params: Record<string, any\>
      /\*\*
       \* headers data in the request
       \*/
      headers: Headers
    }
    
-   **Details:**
    
    Request Validator
    
    Sometimes, for the same API request, data needs to be returned based on different request parameters.
    
    However, if all of this is written in a single mock's body or response, the content can become cumbersome and difficult to manage. The function of a validator allows you to configure multiple mocks with the same URL simultaneously and determine which mock should be used through validation.
    

### options.ws

-   **Type:** `boolean`
    
-   **Default:** `false`
    
-   **Details:**
    
    Enable WebSocket interface simulation
    

### options.setup

-   **Type:** `(wss: WebSocketServer, ctx: WebSocketSetupContext) => void`
    
-   **Details:**
    
    Configure Websocket Server
    

interface WebSocketSetupContext {
  /\*\*
   \* When defining WSS, you may perform some automatic or looping tasks.
   \* However, when hot updating, the plugin will re-execute \`setup()\`,
   \* which may result in duplicate registration of listening events and looping tasks
   \* such as setTimeout. You can use \`onCleanup()\` to clear these automatic or looping tasks.
   \*/
  onCleanup: (cleanup: () \=> void) \=> void
}

Request/Response Enhance
------------------------

When defining methods using `headers`, `body`, and `response`, the plugin adds new content to the `request` and `response` parameters.

**In Request:**

The original type of `request` is `http.IncomingMessage`. The plugin adds data such as `query`, `params`, `body`, `refererQuery`, and the `getCookie(name)` method for obtaining cookie information on this basis.

type Request \= http.IncomingMessage & {
  query: object
  params: object
  body: any
  refererQuery: object
  getCookie: (name: string, option?: Cookies.GetOption) \=> string | undefined
}

**In Response:**

The original type of `response` is `http.ServerResponse<http.IncomingMessage>`. The plugin adds `setCookie(name, value)` method for configuration cookies on this basis.

type Response \= http.ServerResponse<http.IncomingMessage\> & {
  setCookie: (
    name: string,
    value?: string | null,
    option?: Cookies.SetOption,
  ) \=> void
}

Share Mock Data
---------------

Due to each `mock` file being compiled as a separate entry point, the local files they depend on are also compiled within. Additionally, each mock file has an independent scope. This means that even if multiple mock files collectively depend on a `data.ts` file, they cannot share data. If one mock file modifies the data in `data.ts`, other mock files will not receive the updated data.

To address this, the plugin offers a `defineMockData` function, which allows using `data.ts` as a shared data source within mock files.

type defineMockData<T\> \= (
  key: string, // key
  initialData: T, // initial data
) \=> \[getter, setter\] & { value: T }

### Examples

`data.ts`

import { defineMockData } from 'vite-plugin-mock-dev-server'

export default defineMockData('posts', \[
  { id: '1', title: 'title1', content: 'content1' },
  { id: '2', title: 'title2', content: 'content2' },
\])

`*.mock.ts`

import { defineMock } from 'vite-plugin-mock-dev-server'
import posts from './data'

export default defineMock(\[
  {
    url: '/api/posts',
    body: () \=> posts.value
  },
  {
    url: '/api/posts/delete/:id',
    body: (params) \=> {
      const id \= params.id
      posts.value \= posts.value.filter(post \=> post.id !== id)
      return { success: true }
    }
  }
\])

> **Tips：**
> 
> The `defineMockData` function relies solely on the shared data support provided by `memory`. If persistent mock data is required, it is recommended to use a `nosql` database like `lowdb` or `level`.

Custom-Path-Matching-Priority
-----------------------------

> Custom rules only affect links with dynamic parameters, such as: `/api/user/:id`

The priority of the path matching rules built into the plugin can already meet most needs, but if you need more flexible customization of the matching rule priority, you can use the `priority` parameter.

Exp：

import { defineConfig } from 'vite'
import mockPlugin from 'vite-plugin-mock-dev-server'

export default defineConfig({
  plugins: \[
    mockPlugin({
      priority: {
        // The priority of matching rules is global.
        // The rules declared in this option will take priority over the default rules.
        // The higher the position of the rule in the array, the higher the priority.
        global: \['/api/:a/b/c', '/api/a/:b/c', '/api/a/b/:c'\],
        // For some special cases where the priority of certain rules needs to be adjusted,
        // this option can be used. For example, when a request matches both Rule A and Rule B,
        // and Rule A has a higher priority than Rule B, but it is desired for Rule B to take effect.
        special: {
          // When both A and B or C match, and B or C is at the top of the sort order,
          // insert A into the top position.
          // The \`when\` option is used to further constrain the priority adjustment to
          // be effective only for certain requests.
          '/api/:a/:b/c': {
            rules: \['/api/a/:b/:c', '/api/a/b/:c'\],
            when: \['/api/a/b/c'\]
          },
          // If no \`when\` is specified, it means that all requests matching the rules need to have their priorities adjusted. It can be abbreviated as \`\[key\]: \[...rules\]\`
          '/api/:a/b': \['/api/a/:b'\],
        }
      }
    })
  \]
})

> **Tip:**
> 
> `priority` although it can adjust the priority, most of the time you do not need to do so. For some special requests, you can use static rules instead of `priority`, as static rules always have the highest priority.

Examples
--------

`mock/**/*.mock.{ts,js,mjs,cjs,json,json5}`

See more examples： example

**exp:** Match `/api/test`, And returns a response body content with empty data

export default defineMock({
  url: '/api/test',
})

**exp:** Match `/api/test` , And returns a static content data

export default defineMock({
  url: '/api/test',
  body: { a: 1 },
})

**exp:** Only Support `GET` Method

export default defineMock({
  url: '/api/test',
  method: 'GET'
})

**exp:** In the response header, add a custom header and cookie

export default defineMock({
  url: '/api/test',
  headers: { 'X-Custom': '12345678' },
  cookies: { 'my-cookie': '123456789' },
})

export default defineMock({
  url: '/api/test',
  headers({ query, body, params, headers }) {
    return { 'X-Custom': query.custom }
  },
  cookies() {
    return { 'my-cookie': '123456789' }
  }
})

**exp:** Define multiple mock requests for the same URL and match valid rules with validators

export default defineMock(\[
  // Match /api/test?a=1
  {
    url: '/api/test',
    validator: {
      query: { a: 1 },
    },
    body: { message: 'query.a == 1' },
  },
  // Match /api/test?a=2
  {
    url: '/api/test',
    validator: {
      query: { a: 2 },
    },
    body: { message: 'query.a == 2' },
  },
  {
    // \`?a=3\` will resolve to \`validator.query\`
    url: '/api/test?a=3',
    body: { message: 'query.a == 3' }
  },
  // Hitting the POST /api/test request, and in the request body,
  // field a is an array that contains items with values of 1 and 2.
  {
    url: '/api/test',
    method: \['POST'\],
    validator: { body: { a: \[1, 2\] } }
  }
\])

**exp:** Response Delay

export default defineMock({
  url: '/api/test',
  delay: 6000, // delay 6 seconds
})

**exp:** The interface request failed

export default defineMock({
  url: '/api/test',
  status: 502,
  statusText: 'Bad Gateway'
})

**exp:** Dynamic route matching

export default defineMock({
  url: '/api/user/:userId',
  body({ params }) {
    return { userId: params.userId }
  }
})

The `userId` in the route will be resolved into the `request.params` object.

**exp:** Use the buffer to respond data

import { Buffer } from 'node:buffer'

// Since the default value of type is json,
// although buffer is used for body during transmission,
// the content-type is still json.
export default defineMock({
  url: 'api/buffer',
  body: Buffer.from(JSON.stringify({ a: 1 }))
})

// When the type is buffer, the content-type is application/octet-stream.
// The data passed in through body will be converted to a buffer.
export default defineMock({
  url: 'api/buffer',
  type: 'buffer',
  // Convert using Buffer.from(body) for internal use
  body: { a: 1 }
})

**exp:** Response file type

Simulate file download, and pass in the file reading stream.

import { createReadStream } from 'node:fs'

export default defineMock({
  url: '/api/download',
  // When you are unsure of the type, you can pass in the file name for internal parsing by the plugin.
  type: 'my-app.dmg',
  body: () \=> createReadStream('./my-app.dmg')
})

<a href\="/api/download" download\="my-app.dmg"\>Download File</a\>

**exp:** Use `mockjs`:

import Mock from 'mockjs'

export default defineMock({
  url: '/api/test',
  body: Mock.mock({
    'list|1-10': \[{
      'id|+1': 1
    }\]
  })
})

You need install `mockjs`

**exp:** Use `response` to customize the response

export default defineMock({
  url: '/api/test',
  response(req, res, next) {
    const { query, body, params, headers } \= req
    console.log(query, body, params, headers)

    res.status \= 200
    res.setHeader('Content-Type', 'application/json')
    res.end(JSON.stringify({
      query,
      body,
      params,
    }))
  }
})

**exp:** Use json / json5

{
  "url": "/api/test",
  "body": {
    "a": 1
  }
}

**exp:** multipart, upload files.

use `formidable` to support.

<form action\="/api/upload" method\="post" enctype\="multipart/form-data"\>
  <p\>
    <span\>file: </span\>
    <input type\="file" name\="files" multiple\="multiple"\>
  </p\>
  <p\>
    <span\>name:</span\>
    <input type\="text" name\="name" value\="mark"\>
  </p\>
  <p\>
    <input type\="submit" value\="submit"\>
  </p\>
</form\>

fields `files` mapping to `formidable.File`

export default defineMock({
  url: '/api/upload',
  method: 'POST',
  body(req) {
    const body \= req.body
    return {
      name: body.name,
      files: body.files.map((file: any) \=> file.originalFilename),
    }
  },
})

**exp:** Graphql

import { buildSchema, graphql } from 'graphql'

const schema \= buildSchema(\`
type Query {
  hello: String
}
\`)
const rootValue \= { hello: () \=> 'Hello world!' }

export default defineMock({
  url: '/api/graphql',
  method: 'POST',
  body: async (request) \=> {
    const source \= request.body.source
    const { data } \= await graphql({ schema, rootValue, source })
    return data
  },
})

fetch('/api/graphql', {
  method: 'POST',
  body: JSON.stringify({ source: '{ hello }' })
})

**exp:** WebSocket Mock

// ws.mock.ts
export default defineMock({
  url: '/socket.io',
  ws: true,
  setup(wss, { onCleanup }) {
    const wsMap \= new Map()
    wss.on('connection', (ws, req) \=> {
      const token \= req.getCookie('token')
      wsMap.set(token, ws)
      ws.on('message', (raw) \=> {
        const data \= JSON.parse(String(raw))
        if (data.type \=== 'ping')
          return
        // Broadcast
        for (const \[\_token, \_ws\] of wsMap.entires()) {
          if (\_token !== token)
            \_ws.send(raw)
        }
      })
    })
    wss.on('error', (err) \=> {
      console.error(err)
    })
    onCleanup(() \=> wsMap.clear())
  }
})

// app.ts
const ws \= new WebSocket('ws://localhost:5173/socket.io')
ws.addEventListener('open', () \=> {
  setInterval(() \=> {
    // heartbeat
    ws.send(JSON.stringify({ type: 'ping' }))
  }, 1000)
}, { once: true })
ws.addEventListener('message', (raw) \=> {
  console.log(raw)
})

**exp：** EventSource Mock

// sse.mock.ts
import { createSSEStream, defineMock } from 'vite-plugin-mock-dev-server'

export default defineMock({
  url: '/api/sse',
  response(req, res) {
    const sse \= createSSEStream(req, res)
    let count \= 0
    const timer \= setInterval(() \=> {
      sse.write({
        event: 'count',
        data: { count: ++count },
      })
      if (count \>= 10) {
        sse.end()
        clearInterval(timer)
      }
    }, 1000)
  },
})

// app.js
const es \= new EventSource('/api/sse')

es.addEventListener('count', (e) \=> {
  console.log(e.data)
})

Mock Services
-------------

In some scenarios, it may be necessary to use the data provided by mock services for display purposes, but the project may have already been packaged, built and deployed without support from `Vite` and this plugin's mock service. Since this plugin supports importing various `node` modules in mock files at the design stage, the mock file cannot be inline into client build code.

To meet such scenarios, on one hand, the plugin provides support under `vite preview`, and on the other hand, it also builds a small independent mock service application that can be deployed to relevant environments during `vite build`. This can then be forwarded through other HTTP servers like Nginx to actual ports for mock support.

The default output is built into the directory `dist/mockServer`, generating files as follows:

./mockServer
├── index.js
├── mock-data.js
└── package.json

In this directory, execute `npm install` to install dependencies, and then execute `npm start` to start the mock server.

The default port is `8080`.

You can access related `mock` interfaces through `localhost:8080/`.

Links
-----

-   vite
-   awesome-vite
-   rspack-plugin-mock - **Rspack** and **Rsbuild** plugin for API mock server

Contributors
------------

  
**pengzhanbo**  
📖 🤔 💡 💻

  
**jiadesen**  
🤔 🐛

  
**yogibaba**  
💻

  
**pfdgithub**  
💻 🐛

  
**chuyuan du**  
💻

  
**hlwen**  
🐛 💻

LICENSE
-------

The plugin is licensed under the MIT License
