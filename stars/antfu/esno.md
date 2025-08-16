---
project: esno
stars: 1609
description: Alias to `tsx`
url: https://github.com/antfu/esno
---

esno
====

Node.js runtime enhanced with esbuild for loading TypeScript & ESM  
  

From v0.15, `esno` is essentially an alias of `tsx`, with automated CJS/ESM mode and caching.

> Issues are disabled in this repo, they should be report in esbuild-kit/tsx instead.

Usage
-----

npx esno hello.ts

#### Install globally

npm i -g esno

esno index.ts

#### Install as dependency

npm i esno

{
  "scripts": {
    "start": "esno index.ts"
  },
  "dependencies": {
    "esno": "\*"
  }
}

Learn more at `tsx`.
