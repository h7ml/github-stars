---
project: core
stars: 31
description: 简单零依赖的响应式框架（Simple zero-dependency responsive framework that uses jsx syntactic sugar to describe the UI）
url: https://github.com/gyronorg/core
---

Gyron
=====

`Gyron` 是一款简单零依赖的响应式框架。核心代码大小: 。

它还拥有很好的性能表现，详情可以参见 js-framework-benchmark 提供的结果。

在线体验 https://gyron.970819.xyz/explorer

-   文档
    -   English
    -   官方网站

快速使用
----

我们提供了各个不同构建平台的插件用来解析和优化 `Gyron` 的代码，想要快速使用可以使用@gyron/cli脚手架。下面是一个用 `Gyron` 编写的 TODO 应用。

import { useValue, createGyron, FC } from 'gyron'

export const APP \= FC(() \=> {
  const list \= useValue<number\[\]\>(\[\])
  function add() {
    list.value.push(Date.now())
  }
  function remove(item: number) {
    const index \= list.value.findIndex((value) \=> value \=== item)
    list.value.splice(index, 1)
  }
  return (
    <\>
      <ul\>
        {list.value.map((item) \=> (
          <li\>
            {item} <button onClick\={() \=> remove(item)}\>\-</button\>
          </li\>
        ))}
      </ul\>
      <button onClick\={add} class\="add"\>
        +
      </button\>
    </\>
  )
})

createGyron(<APP />).render('#app')

功能
--

Gyron 已经完成了所有预期之内的功能，可以参考 http://gyron.970819.xyz/ 查看所有功能说明。

如果你想了解这些功能和社区其它框架有什么不同可以打开 Issues 一起沟通学习，或者 clone 代码后查看对应的模块。

### tsc 命令支持

最简单使用方式就是在 tsconfig.json 中加上下面这个配置，然后在每一个文件加上 `import { reactCreateElement as h } from '@gyron/jsx-runtime'` 一串代码。

{
  "compilerOptions": {
    "jsxFactory": "h"
  }
}

或者直接在文件中加入 `/** @jsx h */`。

/\*\* @jsx h \*/
import { h } from '@gyron/jsx-runtime'

const App \= () \=> {
  return <div\>Hello World</div\>
}

### 使用现代的打包工具

-   vite
-   webpack
-   rollup
-   parcel

目前模板就是基于 vite 制作而成，在适配其它平台时可以阅读jsx这篇文档，里面有更新详细的教程。

核心
--

“核心”是指前端项目中可能会用到的周边生态，下面列出的是作者本人维护的。

其中 `router` 和 `redux` 也是运行时的代码，是为了解决复杂项目时，项目的路由和状态管理器。 `dom-client` 和 `dom-server` 分别对应着客户端渲染接口和服务端渲染接口。

名称

版本

描述

babel-plugin-jsx

将 `jsx` 语法转换成可运行的表达式，在开发环境时生成热更新辅助代码

cli

可定制项目的脚手架

dom-client

对接浏览器 `document` 工具，可自定义接入支持 `ecma` 标准的应用程序

dom-server

对接服务端 `node` 工具，用于服务端渲染

redux

全局状态管理器

jsx-runtime

支持 `jsx` 语法的运行时，比如 `babel` 的 `transform-react-jsx` 插件

reactivity

响应式核心（灵感来自于 Vue）

router

路由管理器

runtime

渲染器以及程序入口

shared

公共工具函数

sync

同步第三方数据工具函数，让第三方数据具有反应性

### 脚手架

# 全局安装 CLI
npm install @gyron/cli -g
# 创建项目
gyron create <instance-name\>
# 进入项目
cd <instance-name\>
# 安装依赖
npm install
# 运行
npm run start

### 附加说明

本说明在 MIT 基础之上作为附加说明展示在本文档中展示。

以下为附加说明：

```
任何情况任何人在未经过作者的授权不允许在公司作为 KPI 项目发布或推广，保护开源项目的合法权益。
```

### SSR

完善文档请阅读 SSR

### 更新记录

详情参阅 CHANGELOG.md

### 测试

请 clone 项目后运行`yarn`，然后再执行`yarn test`

想了解更多，请参阅 https://gyron.970819.xyz/。

### 赞赏

如果项目对你有帮助，可以 star 或者微信扫描下方二维码
