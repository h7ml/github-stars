---
project: vite-plugin-tauri
stars: 193
description: Integrate Tauri in a Vite project to build cross-platform apps.
url: https://github.com/amrbashir/vite-plugin-tauri
---

vite-plugin-tauri
=================

Integrate Tauri in a Vite project to build cross-platform apps

Install
-------

> Make sure to setup your environment for Tauri development.

# pnpm
pnpm add -D vite-plugin-tauri @tauri-apps/cli
# yarn
yarn add -D vite-plugin-tauri @tauri-apps/cli
# npm
npm i -D vite-plugin-tauri @tauri-apps/cli

Usage
-----

// vite.config.js
import { defineConfig } from "vite";
import tauri from "vite-plugin-tauri"; // 1. import the plugin

export default defineConfig({
  plugins: \[
    tauri(), // 2. add it to the plugins list
  \],

  // 3. optional but recommended
  clearScreen: false,
  server: {
    open: false,
  },
});

Tauri CLI arguments
-------------------

You can pass arguments to the tauri CLI by prefixing the args with `-- -t/--tauri`, for example:

pnpm dev -- -t --verbose --release

The `--` is necessary, otherwise `vite` will crash with unkown CLI argument and `-t` or `--tauri` marks the start of the tauri arguments.

Advanced Usage
--------------

### Using a separate config for Tauri

You can also use a separate config file to add the `vite-plugin-tauri` plugin which allows you to define a separate script in `package.json` to develop your tauri app that won't conflict with your normal vite web development flow.

1.  Create a `vite.config.tauri.js` with the following content
    
    import { defineConfig, mergeConfig } from "vite";
    import baseViteConfig from "./vite.config";
    import tauri from "vite-plugin-tauri";
    
    export default defineConfig(
      mergeConfig(baseViteConfig, {
        plugins: \[tauri()\],
    
        // optional but recommended
        clearScreen: false,
        server: {
          open: false,
        },
      }),
    );
    
2.  Modify `package.json`:
    
    // package.json
    {
      ..
      "scripts": {
        "dev": "vite",
        "build": "vite build",
    +   "dev:tauri": "vite --config vite.config.tauri.js",
    +   "build:tauri": "vite build --config vite.config.tauri.js",
        "preview": "vite preview"
      },
      ..
    }
    

License
-------

MIT © Amr Bashir
