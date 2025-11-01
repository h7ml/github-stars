---
project: ruabick
stars: 157
description: Dumi like tool based on vitepress.
url: https://github.com/dewfall123/ruabick
---

ruabick
=======

一个 vue 组件库开发工具，类似dumi，基于 VitePress。

English Introduction | 中文介绍

文档
--

详细文档

功能
--

### 1\. 在 markdown 里面使用 demo 组件

<demo src\="../demo.vue" title\="Demo block" desc\="use demo"\></demo\>

也可以这样使用(去掉反斜杠)

\\\`\`\`vue:demo
<script lang\="ts" setup\>
  const number \= 1;
</script\>

<template\>
  <span\>The number is {{number}}</span\>
</template\>
\\\`\`\`

渲染效果

### 2\. 自动生成 API 文档

在 markdown 里面使用`<API>`组件，只需要传入文件路径，自动生成文档。

> 基于`vue-docgen-api`项目, 参考了很多arco-design-vue的代码。

<API src\="./demo.vue" lang\="zh"\></API\>

查看效果

对于 ts 文件，暂时只支持生成 ts 文件里面 interface 文档，而且必须要有 jsDoc 格式的注释。

<API src\="./demo.ts" lang\="zh"\></API\>

### 3\. 文件映射

一般来说，我们使用 VitePress 会单独建一个`docs`目录，把文档集中放在此目录下。但是`Demo`文件放在`docs`目录下面会让`组件源码`和`demo.vue`隔得太远，放到一起更为合理。

所以`ruabick`能把 markdown 写在`src`目录下 main，通过 formatter 指定映射路径，把改文件映射到`docs`目录下面。

更多说明

// src/dir/demo-introduction.md

\---

mapping:
path: /demo

\---

开始使用
----

> 提供了脚手架创建新项目。实际上也可以基于 VirePress 安装`ruabick/*`的一些插件来使用，但是较为繁琐，不推荐。

pnpm create @ruabick/vlib

Packages
--------

> `ruabick`是一个 monorepo 库，包含的一些插件也可以单独使用。

-   @ruabick/md-demo-plugins
-   vitepress-demo-block
-   vite-plugin-gen-api-doc

License
-------

MIT
