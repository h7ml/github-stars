---
project: wean
stars: 399
description: :four_leaf_clover: Super fast miniapp compiler.
url: https://github.com/ctripcorp/wean
---

* * *

**🔥 Note this is early experimental! 实验阶段的主要工作是想办法让整体架构变稳定、简洁，不建议上生产。**

* * *

wean 是一个小程序编译器前端，它负责将标准的微信小程序打包成 fre 代码，这样做有很多好处——

-   **小程序引擎** - 将打包产物跑到 APP webview 上，就可以成为专属小程序，如“携程小程序”
-   **开箱即用** - 更现代的标准，更短的开发链路，从某种程度上缓解微信小程序的历史包袱
-   **跨端** - 以保住微信为前提，一套代码，支持所有小程序端

wean 生成 fre 代码，借助 esbuild 做 js 的打包

### QQ group

### Demo

-   图虫小程序 @ 飘香豆腐
    
-   TodoMVC
    

### Run

$ npm install
$ npm link
$ wean

### Motivation

在 wean 之前，大量小程序工具使用 babel + webpack 进行打包，各种 loader 、plugin 导致整个开发链路变长，O(n^n) 一遍又一遍的 ast 遍历，复杂度指数级增长，编译耗时超级长，调试也超级困难

wean 旨在解决链路问题，它自研编译器和打包器，整体复杂度维持在 O(n)，没有任何 AST 操作，同一个小程序项目，wean 大约比 taro（+webpack）快一百倍

### Package

Package

Description

Version

wean

微信小程序打包器

wean/wxml

wxml 编译器

### Design

#### License

MIT @ctripcorp
