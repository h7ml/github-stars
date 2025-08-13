---
project: unplugin-vue-import-props
stars: 26
description: Add import define props type support for Vue script-setup and lang is typescript 在Vue3中使用此款插件，传递给 defineProps 的泛型参数可以是一个导入的类型
url: https://github.com/liulinboyi/unplugin-vue-import-props
---

unplugin-vue-import-props
=========================

Add import define props type support for Vue script-setup and lang is typescript，now support global types.

在Vue3中使用此款插件，传递给 defineProps 的泛型参数可以是一个导入的类型，现在已支持全局类型。

Usage
-----

### Basic example

app.vue

<script setup lang="ts">
import { Test } from "./app";
defineProps<Test\>();
</script\>

app.ts

export interface Test {
  name: string
}

Output

<script setup lang="ts">
import { } from "./app";
defineProps<{name:string;}>();
</script\>

app.vue

<script setup lang="ts">
import { Foo as Test } from "./app";
defineProps<Test\>();
</script\>

app.ts

export interface Foo {
  name: string
}

Output

<script setup lang="ts">
import { } from "./app";
defineProps<{name:string;}>();
</script\>

Installation
------------

npm i unplugin-vue-import-props -D

If you want use `typeRoot` to set global types path, please add configPath like:

// vite.config.ts
import ImportProps from 'unplugin-vue-import-props/vite'
import Vue from '@vitejs/plugin-vue'
import { resolve } from 'path'

export default defineConfig({
  plugins: \[Vue(), ImportProps({
      configPath: resolve(\_\_dirname, './tsconfig.json')
  })\],
})

now you can use global types.

Vite  

// vite.config.ts
import ImportProps from 'unplugin-vue-import-props/vite'
import Vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: \[Vue(), ImportProps()\],
})

  

Rollup  

// rollup.config.js
import ImportProps from 'unplugin-vue-import-props/rollup'

export default {
  plugins: \[ImportProps()\], // Must be before Vue plugin!
}

  

esbuild  

// esbuild.config.js
import { build } from 'esbuild'

build({
  plugins: \[
    require('unplugin-vue-import-props/esbuild')(), // Must be before Vue plugin!
  \],
})

  

Webpack  

// webpack.config.js
module.exports \= {
  /\* ... \*/
  plugins: \[require('unplugin-vue-import-props/webpack')()\],
}

  

Vue CLI  

// vue.config.js
module.exports \= {
  configureWebpack: {
    plugins: \[require('unplugin-vue-import-props/webpack')()\],
  },
}

  

#### TypeScript Support

// tsconfig.json
{
  "compilerOptions": {
    // ...
    "types": \["unplugin-vue-import-props" /\* ... \*/\]
  }
}

#### Related articles

https://www.yuque.com/docs/share/4bd70f56-a3e2-4296-843c-08550288c70f?#

Plugin Template: unplugin-vue-macros

> With great appreciation to this project unplugin-vue-macros and its owners 三咲智子 and contributors, this project was created using this project as a template
