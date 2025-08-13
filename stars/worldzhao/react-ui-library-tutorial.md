---
project: react-ui-library-tutorial
stars: 503
description: 📚React组件库搭建指南
url: https://github.com/worldzhao/react-ui-library-tutorial
---

React 组件库搭建指南
-------------

-   React 组件库搭建指南（一）：项目初始化
-   React 组件库搭建指南（二）：开发调试
-   React 组件库搭建指南（三）：编译打包
-   React 组件库搭建指南（四）：单元测试
-   React 组件库搭建指南（五）：标准化发布流程

🚀 在线预览

🚆 本地预览

git clone git@github.com:worldzhao/react-ui-library-tutorial.git
cd react-ui-library-tutorial
pnpm install
pnpm start

按顺序执行完命令后，即可在 localhost:3000 端口看到以下内容：

概览
--

本系列文章主要包含以下内容：

-   项目初始化: 组件库前期开发准备工作。`eslint`/`commit lint`/`typescript`等等；
-   开发阶段: 使用 dumi 进行开发调试以及文档编写；
-   打包阶段: 输出~~`umd`~~/`cjs`/`esm`产物并支持按需加载；
-   组件测试: 使用`@testing-library/react`及其相关生态进行组件测试；
-   发布 npm: 编写脚本完成发布或直接使用 np 发布；
-   部署文档站点: 使用 Github Pages 以及 Github Actions 完成文档站点自动部署。
