---
project: auto-service
stars: 181
description: 【+v:skipper_yqj】点个 Star，手有余香, Swagger or YAPI to TypeScript services and models
url: https://github.com/gogoyqj/auto-service
---

name

route

指南

/

import logo from './public/assets/logo.png'; import swagger from './public/assets/swagger.png';

Autos
=====

介绍
--

Autos（automatic Service），根据 Swagger 或者 YApi 格式的接口文档（JSON）自动生成 TypeScript 的接口调用或者类型代码。

Autos 依赖基于开源项目 Swagger Codegen 定制开发的 Java 生成工具，请确保您的平台已经安装 Java。

特性
--

-   支持 Swagger 和 YApi 两种格式的接口文档
-   支持增量更新接口文档数据
-   支持对接口规范性进行检查
-   支持仅生成 TypeScript 类型代码
-   支持所有 Swagger Codegen 的特性，包括自定义 TypeScript 代码模板
-   支持对接口入参、数据返回进行校验

Autos 是如何工作的？
-------------

<img src={swagger} style={{ width: 800 }} />

命名由来
----

Autos 曾经有一个不那么酷的名字 “sm2tsservice”（Swagger or Mock to TypeScript Service）。

换成 “ Autos”（automatic Service） 从字面上能更好被理解、更容易被记住，logo 则蹭一下变形金刚的名气，采用的是 “Autobot(s)” （博派）的标志。

<img src={logo} style={{ width: 160 }} />
