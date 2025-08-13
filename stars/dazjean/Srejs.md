---
project: Srejs
stars: 24
description: Server rendering engine  缩写为 srejs 即服务器端渲染引擎，为React，Vue提供轻量级封装的服务端渲染骨架。提供了类似模板引擎一样的用法用于在Koa框架中使用。
url: https://github.com/dazjean/Srejs
---

  

**Server rendering engine, abbreviated as srejs, is the server-side rendering engine. It provides the simplest and most flexible react and Vue lightweight server-side rendering skeleton tool for each node development framework, and supports the use in any koa framework.**

  

  

> Server rendering engine 缩写为 Srejs, 即服务器端渲染引擎，为各个node开发框架提供最简单，最灵活的React，Vue轻量级服务端渲染骨架工具，支持在任何koa框架中使用。

Development and debugging
-------------------------

yarn install
#\# debugg React
cd packages/app && npm start  

#\# debugg Vue2.0 
cd packages/app-vue && npm start 

#\# debugg Vue3.0
cd packages/app-vue3 && npm start 

Feature
-------

-   🚀 Support SSR and CSR(支持SSR和CSR)
-   🚀 State management（redux/vuex）
-   🚀 Initialize the component props on the server side(在服务端初始化组件Props)
-   🚀 Nested Route（React-Router/Vue-Router）
-   🚀 Customize HTML and SEO
-   🚀 Support spa and mpa(单页面应用和多页面应用)
-   🚀 Support page level build updates（按需构建指定页面编译）
-   🚀 Support layout(@srejs/react支持)
-   🚀 React16+
-   🚀 Vue2.0
-   🚀 Vue3.0

How to Use
----------

### Develop page components（React/Vue）

//web/pages/index/index.ts
import React from 'react'
export default function (props:any) {
  const { title } \= props
  return <div className\="ts-demo"\>{title}</div\>
}

### Use in koa Middleware

import koa from 'koa';
import srejs from '@srejs/react';
// import srejs from '@srejs/vue'; 

const app \= new koa();
const Sre \= new srejs(app，process.env.NODE\_ENV != 'production',false); 
app.use((ctx,next)\=>{
    Sre.render(ctx,'index',{title:'The page title'})
})
app.listen(8001);

### Production

Page components need to be compiled in advance before deployment in the production environment

Add `scripts` configuration to the `package.json`

"scripts": {
    "build":"npx ssr build",
    "analyzer": "npx ssr analyzer",
},

Quick start
-----------

-   React
-   Vue2.0
-   Vue3.0

Questions
---------

Please open an issue

License
-------

MIT License

Copyright (c) 2021 dazjean
