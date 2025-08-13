---
project: sailor
stars: 21
description: "水手"低码开发平台，向研发提效迈一大步！（调研demo)
url: https://github.com/giscafer/sailor
---

Sailor
======

水手低码平台（Sailor Low-Code Platform）。

使用文档说明：document.md

技术栈：

-   服务端：Koa + MongoDB
-   前端：React + Amis

本地运行
----

> 注意：需要使用 `Node14+` 版本；

1.  根目录 `npm i` 安装前端项目依赖
2.  `cd sailor-server` 进入服务端目录

-   `npm i` 安装服务端依赖
-   将根目录文件`package.json`的`scripts.dev`的`MONGODB_USER`和`MONGODB_PASSWORD`修改为为本地 mongodb 的用户名和密码（db sailor）
-   `npm run dev` 开发启动后端

1.  根目录 `npm run fis3:release` 编译前端代码
2.  根目录 `npm run client:start` 启动前端，成功后访问：http://localhost:8082/

TODO List
---------

### V1.0

-   用户登录
-   项目列表
-   项目新增、删除、查询
-   项目编辑
-   新增页面、删除页面
-   页面预览
-   amis-editor 编辑后保存页面
-   项目下载
-   下载的项目本地运行正常

TODO List:

-   页面重命名
-   项目重命名
-   页面缓存清除（保存退出、删除之后）
-   统计图渲染问题

简要截图
----

使用协议
----

MIT
