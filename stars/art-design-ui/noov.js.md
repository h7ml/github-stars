---
project: noov.js
stars: 17
description: 📦 noov.js for react ssr solution
url: https://github.com/art-design-ui/noov.js
---

noov.js
=======

> 📦 快速、通用、轻量级的 SSR 解决方案

功能
--

-   📦 支持热更新
-   📱 服务端数据预取
-   💪 支持 redux
-   🧳 自定义 layout 组件
-   ⚡️ 支持自定义 TDK 配置

快速开始
----

npm i
npm run dev

API
---

### asyncData

> 你可能想要在服务器端获取并渲染数据。noov.js 添加了 asyncData 方法使得你能够在渲染组件之前异步获取数据。

-   类型： Function

asyncData 方法会在组件（限于页面组件）每次加载之前被调用。它可以在服务端或路由更新之前被调用。

 Home.asyncData() {
    return { project: 'nuxt' }
  }

> 注意：由于 asyncData 方法是在组件 初始化 前被调用的，所以在方法内是没有办法通过 this 来引用组件的实例对象。

TDK 配置
------

> 你可能想要想要在每个页面都配置不同的 TDK，这里可以在 config 目录进行配置，key 值对应`路由`

export default {
  '/': {
    title: 'home',
    keywords: 'noov.js',
    description: '一套react-ssr解决方案'
  }
}

> 另外也可以通过接口获取 TDK

社区
--
