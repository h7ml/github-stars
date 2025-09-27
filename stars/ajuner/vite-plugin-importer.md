---
project: vite-plugin-importer
stars: 57
description: Integration for babel-plugin-import
url: https://github.com/ajuner/vite-plugin-importer
---

vite-plugin-importer
====================

Integration for babel-plugin-import

use
---

config same as babel-plugin-import

```
npm install vite-plugin-importer --save
yarn add vite-plugin-importer
```

// vite.config.js
import { defineConfig } from "vite";
import usePluginImport from 'vite-plugin-importer'
export default defineConfig({
  plugins: \[
    ... // other plugins
    usePluginImport({
      libraryName: "ant-design-vue",
      libraryDirectory: "es",
      style: true,
    }),
    usePluginImport({
      libraryName: "antd",
      libraryDirectory: "es",
      style: true,
    }),
    usePluginImport({
      libraryName: 'vant',
      libraryDirectory: 'es',
      style: (name) \=> \`${name}/style/less\`,
    }),
    usePluginImport({
      libraryName: 'element-plus',
      customStyleName: (name) \=> {
        return \`element-plus/lib/theme-chalk/${name}.css\`;
      },
    }),
    usePluginImport({
      libraryName: "@arco-design/web-react",
      libraryDirectory: 'es',
      camel2DashComponentName: false,
      style: true,
    })
    // Other configurations welcome PR
  \];
})

LICENSE
-------

MIT
