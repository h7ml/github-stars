---
project: vue-hooks-plus
stars: 1971
description: High performance  & Simplicity  🧲  Vue 3 Hooks library
url: https://github.com/InhiblabCore/vue-hooks-plus
---

VueHooks Plus
=============

English | 简体中文

High performance & Simplicity Vue3 Hooks library

✨ Features
----------

-   🏄🏼‍♂️ Easy to learn and use
-   🔋 Supports SSR
-   🛸 Contains a comprehensive collection of basic Hooks
-   🏟️ A wide range of application scenarios
-   🦾 Preferred useRequest, Powerful request middle tier
-   🎪 Interactive demo, immersive
-   🎯 Written in TypeScript with predictable static types
-   🪄 Support the on-demand load, and reduce the packing volume
-   🤺 Playground, there's ample scope for one's abilities
-   🔐 Perfect test, safe and reliable

📦 Install
----------

npm i vue-hooks-plus

### CDN

<script src\="https://cdn.jsdelivr.net/npm/vue-hooks-plus/dist/js/index.iife.js"\></script\>

It will be exposed to global as `VueHooks_Plus`

🤹‍♀️ Usage
-----------

import { useRequest } from 'vue-hooks-plus'

Introduced on demand

import useRequest from 'vue-hooks-plus/es/useRequest'

Auto Import

Vite  

import AutoImport from 'unplugin-auto-import/vite'
import { VueHooksPlusResolver } from '@vue-hooks-plus/resolvers'

export const AutoImportDeps \= () \=>
  AutoImport({
    imports: \['vue', 'vue-router'\],
    include: \[/\\.\[tj\]sx?$/, /\\.vue$/, /\\.vue\\?vue/, /\\.md$/\],
    dts: 'src/auto-imports.d.ts',
    resolvers: \[VueHooksPlusResolver()\],
  })

  

Webpack  

const { VueHooksPlusResolver } \= require('@vue-hooks-plus/resolvers')
module.exports \= {
  /\* ... \*/
  plugins: \[
    require('unplugin-auto-import/webpack')({
      imports: \['vue', 'vue-router'\],
      include: \[/\\.\[tj\]sx?$/, /\\.vue$/, /\\.vue\\?vue/, /\\.md$/\],
      dts: 'src/auto-imports.d.ts',
      resolvers: \[VueHooksPlusResolver()\],
    }),
  \],
}

  

For other supported tools, please see unplugin-auto-import

### Globalization Documentations

-   English Documentations
-   中文文档

### Example

-   Vue Admin Novel
-   Nuxt 3
-   Vite + Vue 3
-   Webpack + Vue 3

🤩 Awesome
----------

### Template

-   Ray Template

🪴 Project Activity
-------------------

### Contributing

Welcome to join us! You can check out the Contributing Guide to learn how to get started.

### Contributors

Thanks for all their contributions 🐝 !

🌸 Thanks
---------

This project is heavily inspired by the following awesome projects.

-   ahooks
-   @koale/useworker

📄 License
----------

MIT License © 2022-PRESENT YongGit
