---
project: MallChatWeb
stars: 1204
description: mallchat的前端项目，是一个既能购物又能聊天的电商系统。以互联网企业级开发规范的要求来实现它，电商该有的购物车，订单，支付，推荐，搜索，拉新，促活，推送，物流，客服，它都必须有。持续更新ing
url: https://github.com/Evansy/MallChatWeb
---

MallChat-抹茶
===========

**一个既能购物又能即时聊天的电商系统。致力于打造互联网企业级项目的最佳实践。  
电商该有的购物车、订单、支付、推荐、搜索、拉新、促活、推送、物流、客服、它都必须有。_持续更新 ing～_**

  

项目导航
----

1.  **快速体验地址**：抹茶聊天首页
2.  **后端项目仓库**：MallChat
3.  **项目视频记录**：Bilibili 地址 全程分享项目进度，功能选型的思考，同时征集迭代建议。
4.  **项目学习文档**：10w+字，保姆级教学路线，环境搭建、核心功能、基建轮子、接口压测、问题记录、一个不落。可点击抹茶项目文档查看（内含 500 人交流大群）
5.  **项目交流群**：对抹茶感兴趣的，可以加入交流群。你的每一个举动，都会决定项目未来的方向。无论是提意见做产品经理，还是找 bug 做个测试人员，又或者加入开发小模块成为 contributer，都欢迎你的加入。
6.  **码云仓库**：https://gitee.com/Evansy/MallChatWeb （国内访问速度更快）

项目介绍
----

抹茶聊天是一个 IM 项目，通过 netty 实现和前端的 websocket 连接。内含微信扫描登录，成员列表，上下线动画，消息列表，消息互动，还有很多实用的小轮子列如 aop 日志，分布式锁注解，频控注解，ip 解析归属地等，持续更新中。。。

### 项目演示

### 项目启动及部署

-   环境: node 16.18+, 包管理工具 pnpm (安装完 node 执行 `npm i pnpm -g` 即可);
-   安装依赖: clone 工程之后，执行 `pnpm i`
    -   `npm` 安装报错, 命令后加参数 `npm i --ignore-scripts` 忽略 `scripts` 相关依赖即可解决
    -   推荐使用 `pnpm`, 安装依赖不会有 因为网络而失败 的问题
-   启动: 按 `F5` 即可自动执行 `pnpm run dev` 并且打开浏览器
-   部署
    -   部署到本地：执行 `pnpm build` 构建完成后把 `dist` 文件夹 放到服务器，并配置 `nginx` 即可
    -   自动 CI/CD：通过 `github actions` 在代码提交到 GitHub 之后自动构建并部署到服务器, 详细参考可查看 deploy.yml

#### C 端项目

-   前端项目地址：https://github.com/Evansy/MallChatWeb
-   项目演示地址：https://mallchat.cn (记住 抹茶.cn，下次工作摸鱼可直接打开)

### 技术选型

#### 前端技术

技术

说明

官网

Vue3

前端流行开发框架

https://cn.vuejs.org

Pinia

vue3 官方推荐状态管理框架

https://pinia.vuejs.org

vue-router

Vue 的官方路由

https://router.vuejs.org

TypeScript

让 JS 具备类型声明

https://www.typescriptlang.org/

Element Plus

基于 vue3 的组件库

https://element-plus.org/

Alova

轻量级的请求策略库，用起来负担比 axios 小

https://alova.js.org/

vite

极速的前端打包构建工具

https://cn.vitejs.dev

pnpm

速度快、节省磁盘空间的软件包管理器

https://www.pnpm.cn

#### 后端技术

见 MallChat

### 后端环境搭建

在项目目录下的`application.yml`修改自己的启动环境`spring.profiles.active` = `test`然后找到同级文件`application-test.properties`，填写自己的环境配置。星球成员提供一套测试环境配置，可直连

### 项目文档

保姆级教学路线，环境搭建、核心功能、性能优化、埋点上报、问题记录、项目亮点一个不落。点击 项目文档

更多有趣功能在持续更新中。。。

star 趋势图
--------

贡献
--

**贡献之前请先阅读 行为准则 和 贡献指南。感谢所有为 MallChat 做过贡献的人!**

#### 前端:

#### 后端:

#### 优秀贡献者:

类别

用户

贡献模块

前端

图片、语音、文件类型消息收发

消息互动操作(撤回、点赞、删除)

虚拟列表

后端

DFA敏感词检测

OpenAI聊天机器人

Ac自动机敏感词检测

限流编程式

握手认证

公众号
---

微信搜索 **阿斌 Java 之路** 关注我的原创公众号，后台回复「**抹茶**」即可加入抹茶交流群，一些做过公司万人群聊，高并发的小伙伴都在里面讨论方案。公众号也会经常更新项目相关的文档，等你来撩~~
