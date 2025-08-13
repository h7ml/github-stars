---
project: tiny-rendering-engine
stars: 71
description: 从零开始实现一个玩具版浏览器渲染引擎
url: https://github.com/woai3c/tiny-rendering-engine
---

tiny-rendering-engine
=====================

从零开始实现一个玩具版浏览器渲染引擎

功能
--

-   HTML 解析器 - v1 分支
-   CSS 解析器 - v2 分支
-   构建样式树 - v3 分支
-   布局树 - v4 分支
-   绘制 - v5 分支

文档
--

-   从零开始实现一个玩具版浏览器渲染引擎

疑难问题
----

### 安装 canvas 报错

请参考 canvas 安装指引文档：https://github.com/Automattic/node-canvas/wiki

开发
--

安装依赖

pnpm i

开发

```
pnpm dev
```

构建

```
pnpm build
```

测试

```
pnpm test
```

示例
--

所有示例均在 examples 目录下，查看示例前需要先执行构建命令 `pnpm build`。

参考资料
----

-   Let's build a browser engine!
-   robinson
-   渲染页面：浏览器的工作原理
-   关键渲染路径
-   计算机系统要素
