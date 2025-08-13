---
project: vue-components-lib-seed
stars: 214
description: :seedling: a vue3.0 components library template. Vue3.0 组件库的次佳实践.
url: https://github.com/zouhangwithsweet/vue-components-lib-seed
---

A Vue3 UI library template
==========================

中文文档

Help you quickly create a component library.

-   🚀 dev with `Vite`
-   ✈️ build with `esbuild`
-   🚁 generate types with `ts-morph`

Docs
----

power by vitepress

-   doc example

Feature
-------

-   🌈 Speedy dev & build
-   🎆 Customize friendly
-   📝 More beautiful doc, support `Chinese` and `English`. Support `Dark Mode` by vueuse
-   🍭 Rich scripts, inspired by esbuild-plugin-vue & vue-dts-gen
-   😋 Type friendly
-   🚚 `ESM` & `CJS` product

How to use
----------

Generate a repository by vue-components-lib-seed

### Checklist

-   Replace all `my-lib` words with your libary name. Just search `my-lib` and replace them in VScode
    -   `.gitignore`
    -   `package.json`
    -   `vite.config.ts`
    -   `.vitepress`
    -   `scripts` ...

### Install

yarn

### Dev

> Benefited from `vite-plugin-pages`, the `src/pages/index.vue` is the entry page for development. You can visit `/[component-name]/demo` to check component, like `http://localhost:3000/#/button/demo`.

yarn dev

### Build

yarn build

### Test

yarn test

### Generate entry point

> The entry file is the `input` option for rollup.

yarn gen-entry

### Generate Component

> A component's name is required for this command.

yarn gen \[component\\'s name\]

### Generate dts

npx esno ./scripts/gen-dts.ts

### Release

> This command will add git tag、generate changelog. You can test your lib with argument `--dry`

yarn release \[--dry\]

Build Docs
----------

> ❗ Noted: you should run `yarn build:lib` before run this command. Because the docs need the build bundle.

### Docs dev

yarn docs:dev

### Docs build

yarn docs:build

### Docs deploy

Here is a git action. When you push the code to the `master` branch, the document will be automatically deployed on `gh-pages` branch. Then you can set the Github Pages's source on the `gh-pages` branch.

### Use demo code in doc

Take button as an example.

In `button.md`, insert the following code

:::demo  
src/packages/button/demo/demo0.vue  
:::
\- or
:::demo  
src/packages/button/demo/demo\*.vue  
:::

There is a global component `Demos` to display all demos. This is currently the only way to show demo. More info.

### Custom doc style

You can add the `class` in frontmatter, then the `<Content>` would inherit the `class`. Of course, the `unocss` can be used here.

\---
class: 'custom-class'
\---

Recommended IDE Setup
---------------------

VSCode + Volar.

### If Using `<script setup>`

`<script setup>` is a feature that is currently in RFC stage. To get proper IDE support for the syntax, use Volar instead of Vetur (and disable Vetur).

Credits
-------

-   unplugin-vue
-   esbuild-plugin-vue
-   vue-dts-gen
-   vueuse
-   vitepress-for-component
-   unocss
-   Element Plus

Thanks
------

  
eeeeelle  
✍️release-script
