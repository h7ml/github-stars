---
project: vite-plugin-env-transformer
stars: 1
description: Convert the configuration in the env file to ES module for use
url: https://github.com/AqingCyan/vite-plugin-env-transformer
---

vite-plugin-env-transformer
===========================

This is a vite plugin. It parses the configuration from your `.env` file into an object and allows you to import it as an ES module in your code.

English | 简体中文

Installation
------------

```
pnpm i -D vite-plugin-env-transformer
```

Usage
-----

Create an envs folder in the root directory, add some `.env.[mode]` files like this:

# envs/.env.dev
VITE\_BASE\_URL\='https://github.com/AqingCyan/vite-plugin-env-transform-module'

SYSTEM\_NAME\='demo project'
SYSTEM\_CONFIG\_ONE\='config one'
SYSTEM\_CONFIG\_TWO\='config two'
SYSTEM\_CONFIT\_THREE\_TEXT\='demo text'

Your `.env.[mode]` file's mode is `dev`.

Your env variable will be read in a tree structure.

const system \= {
  name: 'demo project',
  config: {
    one: 'config one',
    two: 'config two',
    three: {
      text: 'demo text'
    }
  }
}

// vite.config.ts
import { ConfigEnv, defineConfig } from 'vite'
import { envTransformModule } from 'vite-plugin-env-transformer'

const options \= { mode, resolveId: 'demo:siteData', envConstantPrefix: 'SYSTEM' }

export default ({ mode }: ConfigEnv) \=> {
  plugins: \[envTransformModule(options)\]
}

Now when your project compiles, you get a module called `demo:siteData` that contains the configuration you wrote in the `.env.dev` file.

This module is virtual, so we also need to write type.

///<reference types="vite/client" />
interface SiteData {
  readonly system: {
    name: string
    config: {
      one: string
      two: string
      three: {
        text: string
      }
    }
  }
}

declare module 'demo:siteData' {
  const siteData: SiteData
  export default siteData
}

Now you can use it in your project!

// App.tsx
import siteData from 'demo:siteData'

console.log(siteData)

see example

Options
-------

// TODO

TODO
----

// TODO
