---
project: vue-pure-admin
stars: 18969
description: 全面ESM+Vue3+Vite+Element-Plus+TypeScript编写的一款后台管理系统（兼容移动端）
url: https://github.com/pure-admin/vue-pure-admin
---

vue-pure-admin
==============

**中文** | English

简介
--

`vue-pure-admin` 是一款开源免费且开箱即用的中后台管理系统模版。完全采用 `ECMAScript` 模块（`ESM`）规范来编写和组织代码，使用了最新的 `Vue3`、 `Vite`、`Element-Plus`、`TypeScript`、`Pinia`、`Tailwindcss` 等主流技术开发

研发理念
----

稳定中求创新，技术中见未来

精简版本（实际项目开发请用精简版本，提供 `非国际化` 、`国际化` 两个版本选择）
------------------------------------------

精简版本是基于 vue-pure-admin 提炼出的架子，包含主体功能，更适合实际项目开发，打包后的大小在全局引入 element-plus 的情况下仍然低于 `2.3MB`，并且会永久同步完整版的代码。开启 `brotli` 压缩和 `cdn` 替换本地库模式后，打包大小低于 `350kb`

点我查看非国际化精简版本  
点我查看国际化精简版本

配套视频
----

点我查看 UI 设计  
点我查看快速开发教程

配套保姆级文档
-------

点我查看 vue-pure-admin 文档  
点我查看 @pureadmin/utils 文档

高级服务
----

点我查看详情

`Tauri` 版本
----------

点我查看 Tauri 版本

`Electron` 版本
-------------

点我查看 Electron 版本

预览
--

点我查看预览

`PC` 端

  

暗色风格

  

移动端

### 使用 `Gitpod`

在 `Gitpod`（适用于 `GitHub` 的免费在线开发环境）中打开项目，并立即开始编码.

安装使用
----

### 拉取代码

#### 推荐使用 `@pureadmin/cli` 脚手架

  

1.  全局安装

npm install -g @pureadmin/cli

1.  交互式选择模板并创建项目

pure create

点我查看 @pureadmin/cli 脚手架详细用法

#### 从 `GitHub` 上拉取

git clone https://github.com/pure-admin/vue-pure-admin.git

#### 从 `Gitee` 上拉取

git clone https://gitee.com/yiming\_chang/vue-pure-admin.git

### 安装依赖

cd vue-pure-admin

pnpm install

### 启动平台

pnpm dev

### 项目打包

pnpm build

Docker 支持
---------

1.  自定义镜像名为 `vue-pure-admin` 的镜像（请注意下面命令末尾有一个点 `.` 表示使用当前路径下的 `Dockerfile` 文件，可根据实际情况指定路径）

docker build -t vue-pure-admin .

1.  端口映射并启动 `docker` 容器（`8080:80`：表示在容器中使用 `80` 端口，并将该端口转发到主机的 `8080` 端口；`pure-admin`：表示自定义容器名；`vue-pure-admin`：表示自定义镜像名）

docker run -dp 8080:80  --name pure-admin vue-pure-admin

操作完上面两个命令后，在浏览器打开 `http://localhost:8080` 即可预览

当然也可以通过 Docker Desktop 可视化界面去操作 `docker` 项目，如下图

更新日志
----

CHANGELOG

如何贡献
----

非常欢迎您的加入！提一个 Issue 或者提交一个 `Pull Request`

**Pull Request:**

1.  Fork 代码!
2.  创建自己的分支: `git checkout -b feat/xxxx`
3.  提交您的修改: `git commit -am 'feat(function): add xxxxx'`
4.  推送您的分支: `git push origin feat/xxxx`
5.  提交`pull request`

特别代码贡献
------

非常感谢你们能深入了解源码并对 `pure-admin` 组织作出优秀贡献 ❤️

**贡献人**

**具体代码**

hb0730

代码

o-cc

代码

yj-liuzepeng

代码

skyline523

代码

shark-lajiao

代码

WitMiao

代码

QFifteen

代码

edgexie

代码

way-jm

代码

simple-hui

代码

tinysimple

代码

`Git` 贡献提交规范
------------

参考 vue 规范 (Angular)

-   `feat` 增加新功能
-   `fix` 修复问题/BUG
-   `style` 代码风格相关无影响运行结果的
-   `perf` 优化/性能提升
-   `refactor` 重构
-   `revert` 撤销修改
-   `test` 测试相关
-   `docs` 文档/注释
-   `chore` 依赖更新/脚手架配置修改等
-   `workflow` 工作流改进
-   `ci` 持续集成
-   `types` 类型定义文件更改
-   `wip` 开发中

浏览器支持
-----

本地开发推荐使用 `Chrome`、`Edge`、`Firefox` 浏览器，作者常用的是最新版 `Chrome` 浏览器  
实际使用中感觉 `Firefox` 在动画上要比别的浏览器更加丝滑，只是作者用 `Chrome` 已经习惯了，看个人爱好选择吧  
更详细的浏览器兼容性支持请看 Vue 支持哪些浏览器？ 和 Vite 浏览器兼容性

  
IE

  
Edge

  
Firefox

  
Chrome

  
Safari

不支持

最后两个版本

最后两个版本

最后两个版本

最后两个版本

维护者
---

xiaoxian521、Ten-K

许可证
---

完全免费开源

MIT © 2020-present, pure-admin

`Star`
------

非常感谢留下星星的好心人，感谢您的支持 ❤️

`Fork`
------

瞧，那些 `小哥哥` 、`小姐姐` 认真 `学习` 的样子真滴是 `哎呦不错哦` ❤️
