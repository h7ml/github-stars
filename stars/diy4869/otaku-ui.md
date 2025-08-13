---
project: otaku-ui
stars: 86
description: 一个二次元的React组件库
url: https://github.com/diy4869/otaku-ui
---

OTAKU-UI
========

该项目是基于`React Hooks、Typescript、vite`来实现的一个`UI库`，目前依然属于不成熟状态，不适合生产环境。

项目启动
----

### 1.1 全局安装lerna

`npm install -g lerna`

### 1.2 安装依赖

`lerna bootstrap`

### 1.3 启动

`cd packages/my-vue-app`， 执行`npm run dev`即可

otaku-cli
---------

先后执行 `cd packages/otaku-cli`、`npm link` 即可，就可以在命令行使用`otaku-cli`了

### 一些命令

-   create xxx 将会在`packages/otaku-ui/src/lib`目录下创建一个组件
-   publish 用于更新文档网站

Options:
  -V --version            查看当前版本
  -h, --help              查看帮助

Commands:
  create <componentName\>  创建组件
  publish                 更新文档网站

浏览器支持
-----

  
Edge Chromium

  
Firefox

  
Chrome

  
Safari

Edge 86+

last 2 versions

86+

last 2 versions
