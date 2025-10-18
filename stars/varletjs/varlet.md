---
project: varlet
stars: 5246
description: A Vue3 component library based on Material Design 2 and 3, supporting mobile and desktop.
url: https://github.com/varletjs/varlet
---

VARLET
======

A Vue3 component library based on Material Design 2 and 3, supporting mobile and desktop.

Documentation | 中文介绍

* * *

### Intro

Varlet is a `Vue3` component library based on Material Design 2 and 3, supporting mobile and desktop, developed and maintained by `varletjs` organization.

### Features

-   🚀   Provide 60+ high quality general purpose components
-   🚀   Components are very lightweight
-   💪   Developed by Chinese, complete Chinese and English documentation and logistics support
-   🛠️   Support on-demand introduction
-   🛠️   Support theme customization
-   🌍   Support internationalization
-   💡   Support WebStorm syntax highlighting
-   💪   Support the SSR
-   📦   Support Nuxt Module
-   💡   Support the Typescript
-   💪   Make sure more than 90 percent unit test coverage, providing stability assurance
-   🎨   Supports both Material Design 2 and Material Design 3 design systems
-   🛠️   Support dark mode
-   🔧   Provide official VSCode extension
-   ⌨️   Support Accessibility (still improving)

### Install

### CDN

`varlet.js` contain all the styles and logic of the component library, and you can import them.

<div id\="app"\></div\>
<script src\="https://cdn.jsdelivr.net/npm/vue"\></script\>
 <!-- Desktop Adaptation -->
<script src\="https://cdn.jsdelivr.net/npm/@varlet/touch-emulator/iife.js"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/@varlet/ui/umd/varlet.js"\></script\>
<script\>
  const app \= Vue.createApp({
    template: '<var-button>Button</var-button>'
  })
  app.use(Varlet).mount('#app')
</script\>

### Webpack / Vite

# Install with npm or yarn or pnpm

# npm
npm i @varlet/ui -S

# yarn
yarn add @varlet/ui

# pnpm
pnpm add @varlet/ui

import App from './App.vue'
import Varlet from '@varlet/ui'
import { createApp } from 'vue'
import '@varlet/ui/es/style'

createApp(App).use(Varlet).mount('#app')

### Official Ecosystem

The following projects are maintained by the official team for a long time.

Name

Description

@varlet/cli

`Vue3 component library rapid prototyping tool`

@varlet/touch-emulator

`Desktop adapter, so that the mobile component library can run on the desktop`

@varlet/ui-playground

`Varlet component library online editing tool`

@varlet/import-resolver

`A resolver for` unplugin-vue-components `used to implement Varlet and import it on demand`

@varlet/preset-unocss

UnoCss `presets for varlet`

@varlet/preset-tailwindcss

tailwindcss `presets for varlet`

varlet-theme-builder

`Theme generator for generating theme variables for varlet Material Design 3`

varlet-vscode-extension

`Varlet Component Library VSCode Plugin`

vscode-theme-varlet

`Varlet VSCode Theme`

varlet-app-example

`Varlet component library app template`

varlet-install-example

`Case collection of Varlet component library and various ecosystem integration`

### Community Ecosystem

The following projects are maintained by community personnel, welcome to add.

Name

Description

vue-h5-template

`Vue-based mobile template scaffolding, providing mobile presets for Varlet component library`

create-vite-app

`A desktop template scaffolding based on Vue3, providing desktop presets for Varlet component library`

vscode-common-intellisense

`A VS Code extension that provides better intellisense to Varlet developers`

vue3-varlet-mobile

`A mobile template based on Vue 3 and Varlet Component Library`

### Playground

See Varlet UI Playground.

### Contribution

See Contributing Guide.

### GitCode Repo

See Here.

### Community

We recommend that issue be used for problem feedback, or others:

-   Wechat group

-   Join the Discord

### Thanks to contributors

### Thanks to the following sponsors

### Sponsor this project

Sponsor this project to support our better creation.

#### Wechat / Alipay
