---
project: unplugin-unused
stars: 102
description: Check unused dependencies.
url: https://github.com/unplugin/unplugin-unused
---

unplugin-unused
===============

Check unused dependencies.

Installation
------------

npm i -D unplugin-unused

Usage
-----

Unused({
  include: \[/\\.(\[cm\]?\[jt\]sx?|vue)$/\],
  exclude: \[/node\_modules/\],
  level: 'warning', // or 'error'
  /\*\*
   \* Ignore some dependencies.
   \*/
  ignore: {
    peerDependencies: \['vue'\],
  },
  // Or ignore all kinds of dependencies.
  // ignore: \['vue'\],

  /\*\*
   \* Dependency kinds to check.
   \*/
  depKinds: \['dependencies', 'peerDependencies'\],
})

Vite  

// vite.config.ts
import UnpluginUnused from 'unplugin-unused/vite'

export default defineConfig({
  plugins: \[UnpluginUnused()\],
})

  

Rollup  

// rollup.config.js
import UnpluginUnused from 'unplugin-unused/rollup'

export default {
  plugins: \[UnpluginUnused()\],
}

  

Rolldown  

// rolldown.config.js
import UnpluginUnused from 'unplugin-unused/rolldown'

export default {
  plugins: \[UnpluginUnused()\],
}

  

esbuild  

// esbuild.config.js
import { build } from 'esbuild'

build({
  plugins: \[require('unplugin-unused/esbuild')()\],
})

  

Webpack  

// webpack.config.js
module.exports \= {
  /\* ... \*/
  plugins: \[require('unplugin-unused/webpack')()\],
}

  

Sponsors
--------

License
-------

MIT License © 2024-PRESENT Kevin Deng
