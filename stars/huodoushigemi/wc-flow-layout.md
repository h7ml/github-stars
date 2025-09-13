---
project: wc-flow-layout
stars: 208
description: High performance waterfall layout written using web components
url: https://github.com/huodoushigemi/wc-flow-layout
---

wc-waterfall
============

The `wc-waterfall` is a high performance waterfall component written using `web-component`

It can support running in various frameworks, such as `React` `Vue` `SolidJs`

🌈 Demo
-------

-   https://huodoushigemi.github.io/wc-flow-layout/
-   codepen — Basic usage
-   codepen — Photo wall
-   Vue SFC Playground
-   SolidJs Playground
-   Animation

⚙️ Installation
---------------

-   ### npm
    

npm i wc-waterfall

-   ### scripts
    

<script src\="https://cdn.jsdelivr.net/npm/wc-waterfall/dist/index.iife.js"\></script\>

🦄 Example
----------

### 🚀 Use in VanillaJS

import 'wc-waterfall'

<wc-waterfall gap\="10" cols\="3"\>
  <div\>01</div\>
  <div\>02</div\>
  <div\>03</div\>
  <div\>04</div\>
  <div\>05</div\>
  <div\>06</div\>
</wc-waterfall\>

### 🚀 Use in React

// App.tsx
import 'wc-waterfall'

export default function MyApp() {
  return (
    <wc-waterfall gap\={10} cols\={3}\>
      <div\>01</div\>
      <div\>02</div\>
      <div\>03</div\>
      <div\>04</div\>
      <div\>05</div\>
      <div\>06</div\>
    </wc-waterfall\>
  )
}

TypeScript support (JSX/TSX)

// shims.d.ts
declare namespace JSX {
  interface IntrinsicElements {
    'wc-waterfall': React.DetailedHTMLProps<React.HTMLAttributes<HTMLElement\> & import('wc-waterfall').WaterfallProps, HTMLElement\>;
  }
}

### 🚀 Use in Vue

// main.ts
import 'wc-waterfall'

<!-- App.vue -->
<template\>
  <wc-waterfall :gap\="10" :cols\="3"\>
    <div\>01</div\>
    <div\>02</div\>
    <div\>03</div\>
    <div\>04</div\>
    <div\>05</div\>
    <div\>06</div\>
  </wc-waterfall\>
</template\>

// vite.config.ts
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: \[
    vue({
      template: {
        compilerOptions: { isCustomElement: (tag) \=> tag.startsWith('wc-') }
      },
    })
  \],
})

🚀 Use in SSR
-------------

\- import 'wc-waterfall'
+ if (typeof document != 'undefined') import('wc-waterfall')

📄 Props
--------

Name

Type

Default

Description

cols

`number`

2

Number of columns

gap

`number | string | [number, number]`

4

Interval between cells. Can be a single number(e.g. 10), space-separated values (e.g. "10 20"), or a numeric tuple (e.g., \[10, 20\])

⭐️ Show Your Support
--------------------

Please give a ⭐️ if this project helped you!

👏 Contributing
---------------

If you have any questions or requests or want to contribute, please write the issue or give me a Pull Request freely.
