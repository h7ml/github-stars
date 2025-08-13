---
project: unplugin-vue2-script-setup
stars: 608
description: 💡 Bring `<script setup>` to Vue 2.
url: https://github.com/unplugin/unplugin-vue2-script-setup
---

unplugin-vue2-script-setup
==========================

Bring `<script setup>` to Vue 2. Works for Vite, Nuxt, Vue CLI, Webpack, esbuild and more, powered by unplugin.

> ⚠️ With the release of Vue 2.7, which has Composition API and `<script setup>` built-in, **you no longer need this plugin**. Thereby this plugin has entered maintenance mode and will only support Vue 2.6 or earlier. This project will reach End of Life by the end of 2022.

Install
-------

npm i -D unplugin-vue2-script-setup
npm i @vue/composition-api

Install `@vue/composition-api` in your App's entry (it enables the `setup()` hook):

import Vue from 'vue'
import VueCompositionAPI from '@vue/composition-api'

Vue.use(VueCompositionAPI)

Vite  

// vite.config.ts
import { defineConfig } from 'vite'
import { createVuePlugin as Vue2 } from 'vite-plugin-vue2'
import ScriptSetup from 'unplugin-vue2-script-setup/vite'

export default defineConfig({
  plugins: \[
    Vue2(),
    ScriptSetup({ /\* options \*/ }),
  \],
})

Example: `playground/`

  

Nuxt  

> It's built-in in Nuxt Bridge.

Vue CLI  

// vue.config.js
const ScriptSetup \= require('unplugin-vue2-script-setup/webpack').default

module.exports \= {
  parallel: false, // disable thread-loader, which is not compactible with this plugin
  configureWebpack: {
    plugins: \[
      ScriptSetup({ /\* options \*/ }),
    \],
  },
}

Example: `examples/vue-cli`

###### TypeScript

To use TypeScript with Vue CLI, install `@vue/cli-plugin-typescript` but disable the type check:

npm i -D @vue/cli-plugin-typescript vue-tsc

const ScriptSetup \= require('unplugin-vue2-script-setup/webpack').default

module.exports \= {
  parallel: false,
  configureWebpack: {
    plugins: \[
      ScriptSetup({ /\* options \*/ }),
    \],
  },
  chainWebpack(config) {
    // disable type check and let \`vue-tsc\` handles it
    config.plugins.delete('fork-ts-checker')
  },
}

And then use `vue-tsc` to do the type check at build time:

// package.json
{
  "scripts": {
    "dev": "vue-cli-service serve",
    "build": "vue-tsc --noEmit && vue-cli-service build"
  }
}

  

Webpack  

// webpack.config.js
const ScriptSetup \= require('unplugin-vue2-script-setup/webpack').default

module.exports \= {
  /\* ... \*/
  plugins: \[
    ScriptSetup({ /\* options \*/ }),
  \]
}

  

Rollup  

// rollup.config.js
import Vue from 'rollup-plugin-vue'
import ScriptSetup from 'unplugin-vue2-script-setup/rollup'

export default {
  plugins: \[
    Vue(),
    ScriptSetup({ /\* options \*/ }),
  \]
}

  

esbuild  

// esbuild.config.js
import { build } from 'esbuild'
import ScriptSetup from 'unplugin-vue2-script-setup/esbuild'

build({
  /\* ... \*/
  plugins: \[
    ScriptSetup({
      /\* options \*/
    }),
  \],
})

  

Jest  

npm i -D vue-jest

// jest.config.js
module.exports \= {
  transform: {
    '.\*\\\\.(vue)$': 'unplugin-vue2-script-setup/jest',
  },
}

  

JavaScript API  

import { transform } from 'unplugin-vue2-script-setup'

const Vue2SFC \= await transform(\`
<template>
  <!-- ... -->
</template>
<script setup>
  // ...
</script>
\`)

  

IDE
---

We recommend using VS Code with Volar to get the best experience (You might want to disable Vetur if you have it).

When using Volar, you need to install `@vue/runtime-dom` as devDependencies to make it work on Vue 2.

npm i -D @vue/runtime-dom

Learn more

###### Global Types

If the global types are missing for your IDE, update your `tsconfig.json` with:

{
  "compilerOptions": {
    "types": \[
      "unplugin-vue2-script-setup/types"
    \]
  }
}

###### Support Vue 2 template

Volar preferentially supports Vue 3. Vue 3 and Vue 2 template has some different. You need to set the `experimentalCompatMode` option to support Vue 2 template.

{
  "compilerOptions": {
    // ...
  },
  "vueCompilerOptions": {
    "target": 2
  }
}

###### ESLint

If you are using ESLint, you might get `@typescript-eslint/no-unused-vars` warning with `<script setup>`. You can disable it and add `noUnusedLocals: true` in your `tsconfig.json`, Volar will infer the real missing locals correctly for you.

Configurations
--------------

Ref Sugar (take 2)

In v0.5.x, we shipped the **experimental** Ref Sugar (take 2) implementation based on Vue 3's `@vue/reactivity-transform` package. Notice the syntax is not settled yet and might be changed in the future updates. **Use at your own risk!**

To enabled it, pass the option:

ScriptSetup({
  reactivityTransform: true
})

To get TypeScript support, update your `tsconfig.json` with:

{
  "compilerOptions": {
    "types": \[
      "unplugin-vue2-script-setup/types",
      "unplugin-vue2-script-setup/ref-macros"
    \]
  }
}

Recommendations
---------------

If you enjoy using `<script setup>`, you might also want to try `unplugin-auto-import` to improve the DX even further.

Progress
--------

-   PoC
-   Components registration
-   Compile time macros `defineProps` `defineEmits` `withDefaults` `defineExpose`
-   Global types
-   Merge with normal scripts
-   Ref Sugar (take 2)
-   `<template lang="pug">` support
-   Vite plugin
-   Webpack plugin
-   Nuxt module
-   Top-level await (not supported)

How?
----

👀

It's made possible by transforming the `<script setup>` syntax back to normal `<script>` and let the Vue 2 SFC compiler handle the rest.

  

Sponsors
--------

License
-------

MIT License © 2021 Anthony Fu
