---
project: lowcode-dashboard
stars: 175
description: 低代码 可视化 拖拽大屏
url: https://github.com/zzcandor/lowcode-dashboard
---

> lowcode-dashboard

> Make data reports by dragging and dropping :)

特性 / Features
-------------

-   通过 Excel 导入数据
-   可视化画布
-   图表、图片、文字、边框支持
-   可拖拽和缩放的组件
-   静态数据、GET接口支持
-   生成公开链接

截图 / Screenshot
---------------

开发 / Develop
------------

### 前端部分：Vue.js

#### Project setup

```
npm install
```

#### Compiles and hot-reloads for development

```
npm run serve
```

#### Compiles and minifies for production

```
npm run build
```

### 后端部分：Node.js + Koa + MongoDB

准备工作：配置并运行 MongoDB 数据库，新建一个空数据库并命名为`低代码大屏`。无需手动配置表结构，它们会被自动创建。

#### Run web-service

```
node ./server/app.js
```

鸣谢 / Thanks
-----------

本项目使用了 Vue.js 及以下第三方库：

-   ElemeFE / element
-   ElemeFE / v-charts
-   josdejong / jsoneditor
-   SortableJS / Vue.Draggable
-   mauricius / vue-draggable-resizable
-   kirillmurashov / vue-drag-resize
-   koajs / koa
-   标尺工具 vue-ruler-tool
-   ChartFun

LICENSE
-------

MIT
