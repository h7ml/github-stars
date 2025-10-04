---
project: electron-vite
stars: 4797
description: Next generation Electron build tooling based on Vite 新一代 Electron 开发构建工具，支持源代码保护
url: https://github.com/alex8088/electron-vite
---

electron-vite
=============

Next generation Electron build tooling based on Vite

Documentation | Getting Started | create-electron

中文文档

  
  

Features
--------

-   ⚡️ Vite powered and use the same way.
-   🛠 Pre-configured for Electron, don't worry about configuration.
-   💡 Optimize asset handling (Node.js addons, WebAssembly, Worker Thread, etc).
-   🚀 Fast HMR for renderer processes.
-   🔥 Hot reloading for main process and preload scripts.
-   🔌 Easy to debug in IDEs like VSCode or WebStorm.
-   🔒 Compile to v8 bytecode to protect source code.
-   🏷️ Support for TypeScript decorators.
-   📦 Out-of-the-box support for TypeScript, Vue, React, Svelte, SolidJS and more.

Usage
-----

### Install

npm i electron-vite -D

### Development & Build

In a project where `electron-vite` is installed, you can use `electron-vite` binary directly with `npx electron-vite` or add the npm scripts to your `package.json` file like this:

{
  "scripts": {
    "start": "electron-vite preview",
    "dev": "electron-vite dev",
    "prebuild": "electron-vite build"
  }
}

### Configuration

When running `electron-vite` from the command line, electron-vite will automatically try to resolve a config file named `electron.vite.config.js` inside project root. The most basic config file looks like this:

// electron.vite.config.js
export default {
  main: {
    // vite config options
  },
  preload: {
    // vite config options
  },
  renderer: {
    // vite config options
  }
}

### Getting Started

Clone the electron-vite-boilerplate or use the create-electron tool to scaffold your project.

npm create @quick-start/electron

Currently supported template presets include:

JavaScript

TypeScript

vanilla

vanilla-ts

vue

vue-ts

react

react-ts

svelte

svelte-ts

solid

solid-ts

Contribution
------------

See Contributing Guide.

License
-------

MIT © alex.wei
