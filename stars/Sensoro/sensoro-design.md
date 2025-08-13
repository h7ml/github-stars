---
project: sensoro-design
stars: 9
description: 申哲科技 React 组件库
url: https://github.com/Sensoro/sensoro-design
---

Sensoro Design
==============

✨ 特性
----

-   🚀 TypeScript: 使用 TypeScript 编写，提供完整的类型定义。
-   💎 优雅美观: 基于 Ant Design。
-   🎉 开箱即用: 高质量的 React 组件。
-   ⚡️ 按需加载: 支持按需加载，具体请查看babel-plugin-import

📦 安装
-----

```
// npm
npm install @sensoro/sensoro-design --save

// yarn
yarn add @sensoro/sensoro-design

// pnpm
pnpm install @sensoro/sensoro-design
```

⌨️ 本地开发
-------

本仓库使用 pnpm 进行依赖管理，开发前请保证已安装

# 克隆项目到本地
git clone git@github.com:sensoro-design/sensoro-design.git

# 安装依赖
yarn

# 启动服务
yarn start

在其他项目联调
-------

# 执行编译
pnpm build:lib

# 在组件库项目目录执行
pnpm link --global

# 在需要调试的项目执行
pnpm link --global @sensoro/sensoro-design

打开浏览器访问 http://localhost:8888
