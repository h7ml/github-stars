---
project: vite-config
stars: 51
description: Vite的常用配置vite.config.js
url: https://github.com/staven630/vite-config
---

vite-config 全面配置(持续更新)
======================

  细致全面的 vitejs 配置信息。涵盖了使用 vitejs 开发过程中大部分配置需求。

  不建议直接拉取此项目作为模板，希望能按照此教程按需配置，或者复制 vite.config.js 增删配置,并自行安装所需依赖。

  vue-cli4 配置见 vue-cli4-config。

目录

-   √ 定义全局变量
-   √ 配置路径别名 alias
-   √ 配置代理 Proxy
-   √ 使用 TSX/JSX
-   √ SFC 支持 name 属性
-   √ ESlint 错误显示在浏览器中
-   √ 提供 externals
-   √ 提供全局 less、scss 变量
-   √ 按需加载 ElementPlus、Ant Design Vue
-   √ 生成雪碧图
-   √ CDN 加载类库
-   √ 打包分析
-   √ esbuild error

### ✅ 定义全局变量

##### 使用 define 定义全局变量

  通常情况下，在页面中会用到一些常量，而这些常量可能后期又会发生变更，那么这类常量就不能在代码中使用硬编码处理。

  最基础的做法是在构建时生成全局常量，使用时引用全局常量。

> vite.config.ts

export default defineConfig({
  define: {
    INITIAL\_COUNT: 10,
  },
})

  在代码中使用：

const count = ref(INITIAL\_COUNT);

##### 使用 env 文件定义环境变量

  Vite 使用dotenv可以加载自定义的环境变量。

  以下开发的 dev、stage、prod 三种环境为例。将新建四种 env 文件

.env         # 存放不同环境共用的环境变量，定义的变量将被各环境共享
.env.dev     # 开发环境
.env.stage   # 测试环境
.env.prod    # 正式环境

> .env

```
VITE_TOKEN_NAME = 'token'
```

> .env.dev

```
NODE_ENV = development

VITE_BASE_URL = http://wwww.demo.com/api

VITE_BASE_PATH = /
```

> .env.stage

NODE\_ENV = production

VITE\_BASE\_URL = http://wwww.stage.com/api

VITE\_BASE\_PATH = /stage

> .env.prod

NODE\_ENV = production

VITE\_BASE\_URL = http://wwww.prod.com/api

VITE\_BASE\_PATH = /prod

  vite 的--mode 选项，会读取指定的值匹配的环境变量，如运行 vite --mode dev 时，.env 和.env.dev 两个环境变量文件将被加载。

> package.json

"scripts": {
  "dev": "vite --mode dev",
  "stage": "vue-tsc --noEmit && vite build --mode stage",
  "prod": "vue-tsc --noEmit && vite build --mode prod",
},

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import vue from '@vitejs/plugin-vue'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[vue()\]

  return {
    plugins,
  }
}

  在 vite.config.ts 中可以使用 process.env 上挂载的变量。项目中，Vite 会在一个特殊的 import.meta.env 对象上暴露环境变量。默认以"VITE\_"开头的变量，将被挂载在 import.meta.env 对象上。

  在 src/env.d.ts 中添加以下信息,可实现环境变量代码自动提示：

interface ImportMetaEnv {
  VITE\_BASE\_URL: string
}

interface ImportMeta {
  readonly env: ImportMetaEnv
}

▲ 回顶部

### ✅ 配置路径别名 alias

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import path from 'path'

const nodeResolve \= (dir) \=> path.resolve(\_\_dirname, '.', dir)

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const resolve \= {
    alias: {
      '@': nodeResolve('src'),
      '~': nodeResolve('public'),
    },
  }

  return {
    resolve,
  }
}

  使用 typescript 开发，如果出现找不到模块“path”或其相应的类型声明。则需要安装@types/node

npx pnpm i -D @types/node

  修改 tsconfig.json 配置：

{
  "compilerOptions": {
    "baseUrl": ".",
    "importHelpers": true,
    "skipLibCheck": true,
    "allowSyntheticDefaultImports": true,
    "paths": {
      "@/\*": \["src/\*"\]
    }
  }
}

  这样就可以使用'@'来替代相对路径对组件进行引用：

<script lang\="ts"\>import HelloWorld from '@/components/HelloWorld.vue'</script\>

  也可以使用以下方式配置 alias：

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import path from 'path'

const nodeResolve \= (dir) \=> path.resolve(\_\_dirname, '.', dir)

export default ({ mode }: ConfigEnv): UserConfig \=> {
  return {
    resolve: {
      alias: \[
        {
          find: /@\\//,
          replacement: \`${nodeResolve('src')}/\`,
        },
        {
          find: /@comps\\//,
          replacement: \`${nodeResolve('src/components')}/\`,
        },
      \],
    },
  }
}

▲ 回顶部

### ✅ 配置代理 Proxy

  Vitejs 的开发服务器选项https://cn.vitejs.dev/config/#server-host

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const server \= {
    host: '0.0.0.0',
    port: 3000,
    proxy: {
      '/api': {
        target: 'http://192.168.1.163:8081/',
        changeOrigin: true,
        rewrite: (url) \=> url.replace(/^\\/api/, ''),
      },
    },
  }

  return {
    server,
  }
}

-   target

  实际的后端 api 地址。如请求/api/getUserInfo 会转发到http://192.168.1.163:8081/api/getUserInfo。

-   changeOrigin

  是否改写 origin。设为 true，则请求 header 中 origin 将会与 target 配置项的域名一致。

-   rewrite

  重写转发的请求链接。

▲ 回顶部

### ✅ 使用 TSX/JSX

  @vitejs/plugin-vue-jsx通过 HMR 提供 Vue 3 JSX 和 TSX 支持。

npx pnpm i @vitejs/plugin-vue-jsx

> vite.config.ts

import vueJsx from '@vitejs/plugin-vue-jsx'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[vueJsx()\]

  return {
    plugins,
  }
}

  修改 tsconfig.json 配置，使.tsx 中支持 JSX

{
  "compilerOptions": {
    "jsx": "preserve" // .tsx中支持JSX
  }
}

▲ 回顶部

### ✅ SFC 支持 name 属性

  vite-plugin-vue-setup-extend支持<script setup>新增 name 属性

npx pnpm i -D vite-plugin-vue-setup-extend

> vite.config.ts

import vueSetupExtend from 'vite-plugin-vue-setup-extend'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[vueSetupExtend()\]

  return {
    plugins,
  }
}

▲ 回顶部

### ✅ ESlint 错误显示在浏览器中

  vite-plugin-eslint

npx pnpm i -D vite-plugin-eslint

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import eslintPlugin from 'vite-plugin-eslint'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const IS\_PROD \= \['prod', 'production'\].includes(mode)

  let plugins \= \[\]

  if (!IS\_PROD) {
    plugins \= \[
      ...plugins,
      eslintPlugin({
        cache: false,
        include: \['src/\*\*/\*.vue', 'src/\*\*/\*.ts', 'src/\*\*/\*.tsx'\],
      }),
    \]
  }

  return {
    plugins,
  }
}

▲ 回顶部

### ✅ 提供 externals

  vite-plugin-externals:为 Vite 提供 commonjs 外部支持

npx pnpm i -D vite-plugin-externals

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import { viteExternalsPlugin } from 'vite-plugin-externals'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const IS\_PROD \= \['prod', 'production'\].includes(mode)

  let plugins \= \[\]

  if (IS\_PROD) {
    plugins \= \[
      ...plugins,
      viteExternalsPlugin({
        vue: 'Vue',
        react: 'React',
        'react-dom': 'ReactDOM',
        // value support chain, tranform to window\['React'\]\['lazy'\]
        lazy: \['React', 'lazy'\],
      }),
    \]
  }

  return {
    plugins,
  }
}

▲ 回顶部

### ✅ 提供全局 less、scss 变量

##### 提供全局 less 变量

-   直接提供变量

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const css \= {
    preprocessorOptions: {
      less: {
        additionalData: \`@injectedColor: red;\`,
        javascriptEnabled: true,
      },
    },
  }
  return {
    css,
  }
}

-   通过导入 less 文件提供变量

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const css \= {
    preprocessorOptions: {
      less: {
        additionalData: '@import "@/assets/less/variables.less";',
        javascriptEnabled: true,
      },
    },
  }

  return {
    css,
  }
}

##### 提供全局 scss 变量

-   直接提供变量

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const css \= {
    preprocessorOptions: {
      less: {
        additionalData: \`$injectedColor: orange;\`,
        javascriptEnabled: true,
      },
    },
  }
  return {
    css,
  }
}

-   通过导入 scss 文件提供变量

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const css \= {
    preprocessorOptions: {
      scss: {
        additionalData: \`@import "@/assets/scss/variables.scss";\`,
        javascriptEnabled: true,
      },
    },
  }

  return {
    css,
  }
}

▲ 回顶部

### ✅ 按需加载 ElementPlus、Ant Design Vue

  unplugin-vue-components

##### 按需引入 ElementPlus

  unplugin-element-plus为 Element Plus 按需引入样式。

npx pnpm i -D unplugin-vue-components unplugin-element-plus

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'

import Components from 'unplugin-vue-components/vite'
import { ElementPlusResolver } from 'unplugin-vue-components/resolvers'
import ElementPlus from 'unplugin-element-plus/vite'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[
    Components({
      resolvers: \[ElementPlusResolver()\],
    }),
    ElementPlus({}),
  \]

  return {
    plugins,
  }
}

##### 按需引入 Ant Design Vue

npx pnpm i -D unplugin-vue-components

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'

import Components from 'unplugin-vue-components/vite'
import { AntDesignVueResolver } from 'unplugin-vue-components/resolvers'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[
    Components({
      resolvers: \[AntDesignVueResolver()\],
    }),
  \]
  return {
    plugins,
  }
}

▲ 回顶部

### ✅ 生成雪碧图

  vite-plugin-svg-icons

npx pnpm i -D vite-plugin-svg-icons

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import viteSvgIcons from 'vite-plugin-svg-icons'

import path from 'path'

const nodeResolve \= (dir) \=> path.resolve(\_\_dirname, dir)

export default ({ mode }: ConfigEnv): UserConfig \=> {
  let plugins \= \[
    viteSvgIcons({
      // 指定需要缓存的图标文件夹
      iconDirs: \[nodeResolve('icons')\],
      // 指定symbolId格式
      symbolId: 'icon-\[dir\]-\[name\]',
      // 是否压缩
      svgoOptions: true,
    }),
  \]

  return {
    plugins,
  }
}

  使用方式见https://github.com/anncwb/vite-plugin-svg-icons/blob/main/README.zh\_CN.md

▲ 回顶部

### ✅ CDN 加载类库

  vite-plugin-cdn-import

npx pnpm i -D vite-plugin-cdn-import

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import importToCDN from 'vite-plugin-cdn-import'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const IS\_PROD \= \['prod', 'production'\].includes(mode)

  let plugins \= \[\]

  if (IS\_PROD) {
    plugins \= \[
      ...plugins,
      importToCDN({
        modules: \[
          {
            name: 'cesium',
            var: 'Cesium',
            path: \`https://cesium.com/downloads/cesiumjs/releases/1.88/Build/Cesium/Cesium.js\`,
          },
          {
            name: 'widgets',
            path: \`https://cesium.com/downloads/cesiumjs/releases/1.88/Build/Cesium/Widgets/widgets.css\`,
          },
        \],
      }),
    \]
  }

  return {
    plugins,
  }
}

▲ 回顶部

### ✅ 打包分析

  rollup-plugin-visualizer

npx pnpm i -D rollup-plugin-visualizer

> vite.config.ts

import { UserConfig, ConfigEnv, loadEnv } from 'vite'
import { visualizer } from 'rollup-plugin-visualizer'

export default ({ mode }: ConfigEnv): UserConfig \=> {
  const IS\_PROD \= \['prod', 'production'\].includes(mode)

  let plugins \= \[\]

  if (IS\_PROD) {
    plugins \= \[...plugins, visualizer()\]
  }

  return {
    plugins,
  }
}

▲ 回顶部

### ✅ esbuild error

Error: spawn D:\\github\\vite-config\\node\_modules\\esbuild\\esbuild.exe ENOENT
    at Process.ChildProcess.\_handle.onexit (node:internal/child\_process:282:19)
    at onErrorNT (node:internal/child\_process:480:16)
    at processTicksAndRejections (node:internal/process/task\_queues:83:21)
Emitted 'error' event on ChildProcess instance at:
    at Process.ChildProcess.\_handle.onexit (node:internal/child\_process:288:12)
    at onErrorNT (node:internal/child\_process:480:16)
    at processTicksAndRejections (node:internal/process/task\_queues:83:21) {

node ./node\_modules/esbuild/install.js

▲ 回顶部
