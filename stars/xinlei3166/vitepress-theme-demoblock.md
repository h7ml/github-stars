---
project: vitepress-theme-demoblock
stars: 226
description: 一个基于 Vitepress 的主题插件，它可以帮助你在编写文档的时候增加 Vue 示例。
url: https://github.com/xinlei3166/vitepress-theme-demoblock
---

vitepress-theme-demoblock
=========================

> 这是 3.x 版本的文档，已经采用 TypeScript 和 ESM 规范重写，2.x 版本文档请看v2文档，1.x 版本文档请看v1文档。

简介
--

`vitepress-theme-demoblock` 是一个基于 `Vitepress` 的主题插件，它可以帮助你在编写文档的时候增加 `Vue` 示例，它的诞生初衷是为了降低编写组件文档时增加一些相关示例的难度。

使用 `Vitepress` 编写组件示例有以下不足之处：

-   1.组件示例和示例代码本质上一样，却需要写两遍。
-   2.`Vitepress` 无法渲染 `Markdown` 中的代码块。

查看Demo

提示
--

由于 `Vitepress` 版本更新频繁，目前支持版本为 `1.0.1`。

`Vue` 支持版本为 `3.4.21`。

安装
--

npm install -D vitepress-theme-demoblock
yarn add -D vitepress-theme-demoblock
pnpm add -D vitepress-theme-demoblock

快速上手
----

`.vitepress/config.js` 文件中使用 `demoblockPlugin` 和 `demoblockVitePlugin` 插件

import { demoblockPlugin, demoblockVitePlugin } from 'vitepress-theme-demoblock'

markdown: {
  config: (md) \=> {
    md.use(demoblockPlugin)
  }
},
vite: {
  plugins: \[demoblockVitePlugin()\]
}

`.vitepress/theme/index.js` 中使用 `vitepress-theme-demoblock` 主题，并注册组件(包含主题中默认的组件)。

import DefaultTheme from 'vitepress/theme'
import 'vitepress-theme-demoblock/dist/theme/styles/index.css'
import { useComponents } from './useComponents'

export default {
  ...DefaultTheme,
  enhanceApp(ctx) {
    DefaultTheme.enhanceApp(ctx)
    useComponents(ctx.app)
  }
}

`package.json` 配置命令 `scripts`，`vitepress-rc` 用来注册组件(`--docsDir` 指定docs目录，`--componentsDir` 指定组件注册目录)， 如果 `.vitepress` 目录和 `package.json` 同级，--docsDir 设置为 `.`。

"scripts": {
  "docs:dev": "yarn run register:components && vitepress dev docs",
  "docs:build": "yarn run register:components && vitepress build docs",
  "docs:serve": "vitepress serve docs",
  "register:components": "vitepress-rc"
}

更多用法
----

`.md` 文件中 使用 `style` 和 `script`，参考下面例子：

\# code snippet ...

<style\>
body { color: red; }
</style\>

<script setup\>
console.log('vitepress-theme-demoblock setup')
</script\>

<script\>
console.log('vitepress-theme-demoblock')
</script\>

从 v2 迁移
-------

`v3` 在使用插件时需要使用一个 `Vite` 插件。

vite: {
  plugins: \[demoblockVitePlugin()\]
}

`v3` 不支持 `:::demo` 后面的描述。

v2 :::demo 使用 \`type\`、\`plain\`、\`round\` 和 \`circle\` 属性来定义 Button 的样式。
v3 :::demo

因使用了 `Vite` 插件，`Vue` 组件经过 `@vitejs/plugin-vue-jsx` 插件编译， 很多用法已经支持， 例如：setup、jsx、tsx、css v-bind 等等。插件之前的一些属性和方法都已删除，目前只保留了 `customClass` 属性。

多语言
---

`.vitepress/config.js` 文件中增加 `demoblock` 字段来支持多语言 (默认中文)

themeConfig: {
  // demoblock locales
  demoblock: {
    'root': {
      'view-source': 'View source',
        'hide-source': 'Hide source',
        'edit-in-editor': 'Edit in Playground',
        'edit-on-github': 'Edit on GitHub',
        'copy-code': 'Copy code',
        'copy-success': 'Copy success',
        'copy-error': 'Copy error',
    },
    'zh': {
      'view-source': '查看源代码',
        'hide-source': '隐藏源代码',
        'edit-in-editor': '在 Playground 中编辑',
        'edit-on-github': '在 Github 中编辑',
        'copy-code': '复制代码',
        'copy-success': '复制成功',
        'copy-error': '复制失败'
    }
  }
}

自定义主题
-----

通过配置 `customClass` 类名称，自定义 `demoblock` 样式

markdown: {
  config: (md) \=> {
    md.use(demoblockPlugin, {
      customClass: 'demoblock-custom'
    })
  }
}

通过重写 `css-variables`，自定义 `demoblock` 样式

:root {
  \--demoblock-border: var(\--vp-c-divider);
  \--demoblock-control: #909399;
  \--demoblock-control-bg: var(\--vp-c-bg);
}

html.dark {
  \--demoblock-control: #A3A6AD;
}

配置主题色

:root {
  \--vp-c-brand-1: hsl(237, 100%, 70%);
  \--vp-c-brand-2: hsl(237, 100%, 73%);
  \--vp-c-brand-3: hsl(237, 100%, 70%);
  \--vp-c-brand-soft: hsl(237, 100%, 70%, 14%);
}

使用第三方组件库
--------

这个插件主要是针对自己的组件库来使用的，第三方的组件库直接导入使用即可(例如 `element-plus` )。

在 `.vitepress/theme/index.js` 文件中加入以下代码：

import DefaultTheme from 'vitepress/theme'
import 'element-plus/dist/index.css'
// import ElementPlus from 'element-plus'
// import cn from 'element-plus/lib/locale/lang/zh-cn'

export default {
  ...DefaultTheme,
  enhanceApp(ctx) {
    DefaultTheme.enhanceApp(ctx)
    // ctx.app.use(ElementPlus, { locale: cn })
  }
}

使用的时候，导入 `element-plus` 组件即可：

<template\>
  <div class\="card-wrap"\>
    <div class\="card"\>{{ title }}</div\>
    <el-button type\="primary" @click\="onClick"\>点击</el-button\>
  </div\>
</template\>

<script setup>
import { ref } from 'vue'
import { ElMessage, ElButton } from 'element-plus'
const title \= ref('vitepress-theme-demoblock')
const onClick \= () \=> {
  ElMessage('消息')
}
</script\>

也可以安装 unplugin-auto-import 和 unplugin-vue-components ，配合 `Vite` 实现自动导入。

感谢
--

参考：element-ui, element-plus, vite-plugin-markdown-preview, nova-next
