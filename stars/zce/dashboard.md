---
project: dashboard
stars: 560
description: A dashboard scaffolding based on Vue.js 3.0 created by Vite.
url: https://github.com/zce/dashboard
---

dashboard
=========

> A dashboard scaffolding based on Vue.js 3.0 & Vite.

🎉 New dashboard scaffolding
----------------------------

https://github.com/zce/fearless

### Features

-   Modern Vue.js Ecosystem
    -   vue 3.x
    -   vuex 4.x
    -   vue-router 4.x
-   Fully strongly typed
    -   typescript 4.x
-   Next generation frontend tooling
    -   vite 2.x
-   HTTP request based on Fetch API
    -   ky 0.x (not axios)
-   Customizable UI Library
    -   naive-ui 2.x
-   Complete engineering workflow
    -   eslint 7.x
    -   husky 7.x
    -   lint-staged 11.x
    -   commitlint 13.x
-   Locally mocked API server
    -   express 4.x
-   Authorization
    -   Access token
    -   Refresh token
    -   Auth refresh token
    -   Role based authorization
-   Modern application deployment
    -   GitHub Actions
    -   Vercel (with Serverless functions)

### TODOs

-   Vite
-   Migration deps to 3.0
-   Basic API usage
-   Compatibility issues
-   Composition APIs

### Features

-   Type annotation enhancement by JSDoc
-   Access control by route interception
-   Vuex (modules, plugins)
-   API Services
-   I18n support
-   Element UI custom theme
-   Travis CI & GitHub Actions
-   etc.

### Preview

### Online demo

https://dashboard.zce.me

> -   username: zce
> -   password: wanglei

> P.S. For Chinese: https://zce.gitee.io/vue-admin

Getting Started
---------------

### Prerequisites

-   Node.js (>= 10.12, 12.10 preferred)
-   npm (>= 6.x) or yarn (>= 1.20)
-   Git (>= 2.20)

### Clone & Install

# clone repo
$ git clone https://github.com/zce/dashboard.git
$ cd dashboard
# install dependencies
$ npm install # or yarn

### Scaffolding tools

Create an application by zce/caz

# create vue.js apps through this
$ npx caz vue dashboard
# enter generated directory
$ cd dashboard

### Available Scripts

# dev with hot reload at http://localhost:3000
$ npm run dev # or yarn dev

# build for production with minification
$ npm run build # or yarn build

Fake API Server
---------------

Online service by Vercel: https://dashboard-server.now.sh

> Source: zce/dashboard-server

### Usage

# clone api server
$ git clone https://github.com/zce/dashboard-server.git

$ cd dashboard-server

# install deps
$ npm install # or yarn

# run api server
$ npm start # or yarn start

# => api server run @ http://localhost:2080

Then modify `VUE_APP_API_BASE` in `.env.development` or `.env.prodution`:

\- VUE\_APP\_API\_BASE=https://dashboard-server.now.sh
+ VUE\_APP\_API\_BASE=http://localhost:3000

License
-------

MIT © 汪磊 & WEDN.NET
