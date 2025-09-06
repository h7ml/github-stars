---
project: vue-vine
stars: 1403
description: Another style of writing Vue components.
url: https://github.com/vue-vine/vue-vine
---

  
  

-   Contribution Guide
-   中文 README

Another style of writing Vue components.

-   NPM version:  
-   VSCode extension:  
-   Open VSX extension:  
-   Check more details in Vue Vine docs:  

**Why this ?**  

There are many discussions in community that hopes for a solution that supports writing multiple Vue components in a single file. That's why `Vue Vine` was born.

`Vue Vine` was designed to provide more flexibility of managing Vue components. It is a parallel style to SFC.

Take a quick view:

Try the demo
------------

Use interactive commands(`create-vue-vine`) to create your first project. Look here: Project starter template

Or you can try it online: Vue Vine Playground

Relevant packages
-----------------

Category

Package

Version

Description

@vue-vine/compiler

Compiler

@vue-vine/language-server

Language Server

@vue-vine/language-service

Language Service

@vue-vine/vite-plugin

Vite Plugin

@vue-vine/eslint-parser

ESLint Parser

@vue-vine/eslint-plugin

ESLint Plugin

@vue-vine/eslint-config

ESLint Config

@vue-vine/nuxt

Nuxt Module

vue-vine-tsc

TypeScript CLI checker

create-vue-vine

Project starter CLI

Install
-------

# If you didn't install \`@antfu/ni\` yet, I highly recommend you to install it.
ni vue-vine

Use the plugin in `vite.config.ts`:

import { VineVitePlugin } from 'vue-vine/vite'

export default defineConfig({
  plugins: \[
    // ...Other plugins
    VineVitePlugin()
  \],
})

Then add macro's type definition in `tsconfig.json`:

{
  "compilerOptions": {
    "types": \["vue-vine/macros"\]
  }
}

For ESLint, install our custom ESLint config:

ni -D @vue-vine/eslint-config

You need to load the config into your flat configs.

import antfu from '@antfu/eslint-config'

// \`VueVine()\` returns an ESLint flat config
import VueVine from '@vue-vine/eslint-config'

export default antfu(
  {
    // First option is not Linter.FlatConfig,
    // it's a setting for antfu's config itself
  },
  ...VueVine(),
)

Finally, install the VSCode extension, search `Vue Vine` in the marketplace.
