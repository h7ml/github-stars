---
project: cloudbase-framework
stars: 1980
description:  腾讯云开发云原生一体化部署工具 🚀  CloudBase Framework：一键部署，不限框架语言，云端一体化开发，基于Serverless 架构
url: https://github.com/Tencent/cloudbase-framework
---

Tip

想要更智能的开发体验？试试 CloudBase AI ToolKit - 用自然语言描述需求，AI 帮你生成代码并自动部署到云端。 快速上手

云开发 CloudBase Framework
=======================

🚀 CloudBase Framework 是云开发官方出品的前后端一体化部署工具 🔥

**无需改动代码，前后端一键托管部署，基于Serverless架构，加速访问，弹性免运维。**

更多特性和优势

Table of Contents
-----------------

-   Table of Contents
-   快速开始
-   项目示例
-   插件
    -   自动检测生成插件配置流程
    -   目前支持的插件列表
-   配置示例
-   Changelog
-   License
-   优秀应用案例
-   在线交流群
-   CloudBase Framework 资讯
    -   技术文章
    -   演讲
    -   新闻
-   Contributors ✨
-   贡献指南

快速开始
----

1.  **安装 CLI**

npm install -g @cloudbase/cli@latest

1.  **初始化一个应用**

cloudbase init

1.  **部署应用**

cloudbase framework deploy

一键部署一个 Vue CLI 创建的 项目

项目示例
----

下面的快速开始部分可以帮助您更快地体验 CloudBase Framework 的能力，以便尽快开始将自己的项目部署起来。

查看项目示例

每一个例子都提供了一个 **部署按钮**，可以点击之后在云端一键部署，将应用安装在您的腾讯云开发环境中。同时我们也提供了对应的源代码，可以查看源代码，Clone 或者下载项目到本地进行修改，在本地通过 CloudBase CLI 进行一键部署。

  
**Daruk 应用**  

Daruk 是一款基于 Koa2，使用 Typescript 开发的轻量级 web 框架 ，使用云函数云资源

  
**ThinkJS 应用**  

ThinkJS 是一款可以使用ES6/7 特性开发项目的Node.js 框架，支持TypeScript。 ，使用云函数云资源

  
**Jenkins**  

Jenkins 是一个独立的开源软件项目，是基于 Java 开发的一种持续集成工具，用于监控持续重复的工作，旨在提供一个开放易用的软件平台，使软件的持续集成变成可能。 ，使用云托管,CFS云资源

  
**Go 云函数**  

快速搭建一个基于 GO 语言的简单、可靠、高效的应用 ，使用云函数云资源

  
**Java 云函数示例**  

快速构建开放、极简 Java 应用框架 ，使用云函数云资源

  
**PHP 云函数示例**  

快速构建灵活、高效的 PHP 应用框架 ，使用云函数云资源

  
**Omi 应用**  

快速构建一个跨框架的 Omi 应用 ，使用云函数, 静态托管云资源

  
**Aqueduct (Dart Server) 云托管**  

快速构建一个包含多线程 HTTP 服务器框架的 Aqueduct 云托管实例 ，使用云数据库, 云托管云资源

  
**Nextcloud**  

Nextcloud 是一套个人云存储解决方案，内置了图片相册、日历联系人、文件管理、RSS 阅读等丰富的应用。 ，使用云托管,CynosDB,CFS云资源

  
**VuePress 网站应用**  

快速构建基于 VuePress 的网站应用 ，使用静态托管云资源

  
**Nest 应用**  

快速构建一种渐进式的 Node.js 框架，用于构建高效、可靠、可扩展的服务器端应用 ，使用云函数云资源

  
**Egg 应用**  

快速构建基于 Node.js 和 Koa 的 Egg 企业框架及应用 ，使用云函数云资源

  
**Next SSR 应用**  

快速构建一个简单、智能、静态和服务器混合渲染的应用框架 ，使用云函数, 静态托管云资源

  
**Bitwarden**  

Bitwarden 是一款自由且开源的密码管理服务，用户可在加密的保管库中存储敏感信息（例如网站登录凭据）。Bitwarden 平台提供有多种客户端应用程序，包括网页用户界面、桌面应用，浏览器扩展、移动应用以及命令行界面。 ，使用云托管,CFS云资源

点击进入应用中心查看更多应用

插件
--

云开发 CloudBase Framework 支持插件机制，提供了多种应用框架和云资源的插件，只需要很少的配置甚至 0 配置就可以现有应用和云开发 CloudBase Framework 框架进行集成。

查看插件说明插件可以处理应用中的一些独立单元的构建、部署、开发、调试等流程。例如 website 插件可以处理静态网站等单元，node 插件可以处理 koa 、express 等 node 应用。插件可以组合使用。

插件的配置写在 cloudbaserc 文件中，目前仅支持 JSON 文件，后续会支持 YAML。

请参考完整的插件文档

插件的配置可以手动填写，也可以自动生成，目前针对前端框架支持自动识别填写插件。

### 自动检测生成插件配置流程

可以在项目目录下直接运行 `cloudbase` 命令进行自动检测生成插件配置文件并部署

```
cloudbase


✔ 是否使用云开发部署当前项目 <Projects/test/test-vue> ？ (Y/n) · true
✔ 选择关联环境 · webpage - [webpage:按量计费]
   ______ __                   __ ____
  / ____// /____   __  __ ____/ // __ ) ____ _ _____ ___
 / /    / // __ \ / / / // __  // __  |/ __ `// ___// _ \
/ /___ / // /_/ // /_/ // /_/ // /_/ // /_/ /(__  )/  __/
\_________\____/ \__,_/ \__,_//_____/ \__,_//____/ \___/       __
   / ____/_____ ____ _ ____ ___   ___  _      __ ____   _____ / /__
  / /_   / ___// __ `// __ `__ \ / _ \| | /| / // __ \ / ___// //_/
 / __/  / /   / /_/ // / / / / //  __/| |/ |/ // /_/ // /   / ,<
/_/    /_/    \__,_//_/ /_/ /_/ \___/ |__/|__/ \____//_/   /_/|_|


 CloudBase Framework  info     Version v1.2.10
 CloudBase Framework  info     Github: https://github.com/Tencent/cloudbase-framework

 CloudBase Framework  info     EnvId webpage
? 检测到当前项目包含 Vue.js 项目

  🔨 构建脚本 `npm run build`
  📦 本地静态文件目录 `dist`

  是否需要修改默认配置 No
? 请输入应用唯一标识(支持大小写字母数字及连字符, 同一账号下不能相同) test-vue
? 是否需要保存当前项目配置，保存配置之后下次不会再次询问 Yes
 CloudBase Framework  info     📦 install plugins
```

### 目前支持的插件列表

插件链接

插件

最新版本

插件介绍

@cloudbase/framework-plugin-website

一键部署网站应用

@cloudbase/framework-plugin-node

一键部署 Node 应用（支持底层部署为函数或者 云托管）

@cloudbase/framework-plugin-nuxt

一键部署 Nuxt SSR 应用

@cloudbase/framework-plugin-function

一键部署函数资源

@cloudbase/framework-plugin-container

一键部署云托管容器服务

@cloudbase/framework-plugin-dart

一键部署 Dart 应用

@cloudbase/framework-plugin-database

一键声明式部署云开发 NoSQL 云数据库

@cloudbase/framework-plugin-deno

一键部署 Deno 应用

@cloudbase/framework-plugin-next

一键部署 Next SSR 应用

@cloudbase/framework-plugin-mp

一键部署微信小程序应用

@cloudbase/framework-plugin-auth

一键设置登录配置

配置示例
----

例如一个 Vue 的全栈项目，包含网站前端和云函数

查看 Vue 全栈项目的配置示例

可以在在项目下手动创建一个 `cloudbaserc.json`，填写如下配置文件，调用 `cloudbase framework deploy` 进行部署

或者直接运行 `cloudbase` 来进行自动检测并部署

{
  "envId": "{{env}}",
  "framework": {
    "plugins": {
      "client": {
        "use": "@cloudbase/framework-plugin-website",
        "inputs": {
          "buildCommand": "npm run build",
          "outputPath": "dist"
        }
      },
      "server": {
        "use": "@cloudbase/framework-plugin-function",
        "inputs": {
          "functionRootPath": "cloudfunctions",
          "functions": \[
            {
              "name": "helloworld",
              "config": {
                "timeout": 5,
                "envVariables": {},
                "runtime": "Nodejs10.15",
                "memorySize": 128
              }
            }
          \]
        }
      }
    }
  }
}

更多配置详细参数说明，可以查看配置说明文档，点击查看配置文档

Changelog
---------

CloudBase Framework 的版本变更日志请参阅 changelog 文件

License
-------

开源协议文档请参阅 Apache License 2.0

优秀应用案例
------

  
**企业微信**  
🌐

  
**腾讯直播**  
🌐

  
**腾讯云微搭低代码平台**  
🌐

  
**腾讯云开源应用中心**  
🌐

  
**心悦俱乐部**  
🌐

  
**健康码**  
🌐

  
**CloudBase CMS**  
🌐

  
**Hi头像**  
🌐

  
**CloudBase TodoList**  
🌐

  
**ShowMess实时弹幕**  
🌐

  
**校拍**  
🌐

  
**Pagic**  
🌐

  
**衣科官网**  
🌐

  
**Twikoo 评论**  
🌐

  
**实时地震**  
🌐

  
**可道云网盘**  
🌐

  
**NiceUp**  
🌐

  
**道德文章**  
🌐

  
**OneDrive 图床**  
🌐

  
**Waline 评论系统**  
🌐

  
**编程主页**  
🌐

  
**全球空气质量监测可视化**  
🌐

  
**cloudbase-access**  
🌐

  
**腾讯教育官网**  
🌐

  
**巨应壁纸**  
🌐

  
**Halo**  
🌐

  
**兰空图床**  
🌐

持续征集优秀应用案例

在线交流群
-----

如果在使用、安装过程中有任何问题，或者建议，欢迎加群讨论、反馈问题

CloudBase Framework 资讯
----------------------

### 技术文章

-   一键部署！这样搭建一个文档网站真的很简单！
-   云开发 Action，赋予 GitHub 云上超能力
-   实战 | 全栈开发一款团购小程序应用
-   开源一个辅助 B 站 UP 办抽奖活动的工具
-   如何在持续集成（CI）环境中使用 CloudBase Framework
-   实战丨借助云开发 Framework 快速部署 Kodexplorer
-   腾讯 CloudBase ，开启一键部署
-   长文攻略| 快速打造一键部署云开发应用
-   如何将开源容器应用快速打造为云开发应用
-   云开发还可以这么玩系列之二----小手一点，一键部署！
-   如何更快打造云原生应用：CloudBase Framework 云原生一体化实践
-   CloudBase FrameWork 如何进行云托管部署
-   云开发外卖优惠券小程序之 CLI 一键部署
-   小程序·云开发地表最强 CI 利器来了
-   基于云开发 CloudBase 搭建在线视频会议应用
-   基于 ThinkJS 的云开发体验
-   如何把 Flutter 云端一体化做到极致？
-   如何用云开发快速搭建实时 Todo List 应用
-   如何用 Cloudbase Framework 部署一个 Vue 项目
-   第一个 Deno 部署工具是如何打造的？
-   云开发推出「前后端一体化部署工具」CloudBase Framework

✍️ 欢迎提交技术文章

### 演讲

-   云原生一体化部署工具 CloudBase Framework 开源探索
-   如何更快打造云原生应用：CloudBase Framework 云原生一体化实践
-   TLC 大会讲师专访：聊聊云开发 CloudBase 的设计与实践

### 新闻

-   云开应用征集应用评选：他 们 真 的 有 点 极 客
-   3 分钟上线一款应用，我是怎么做到的？
-   向 100 万云开发者“秀肌肉”的机会来了
-   国内首发，这款 Serverless 云原生一体化部署工具正式开源！
-   腾讯云十年新风向：云原生与开源的未来
-   腾讯云首次公布云原生全系产品矩阵，提供国内最完善产品矩阵
-   这个小小小小小变化，你发现了没？
-   【年度回顾】2020，云开发的 20 个重大更新
-   凤凰网：腾讯开源 Serverless 云原生一体化部署工具
-   腾讯科技：国内首发！腾讯云原生一体化部署工具宣布开源
-   腾讯开源：【开源公告】云原生一体化部署工具 CloudBaseFramework 开源啦

Contributors ✨
--------------

Thanks goes to these wonderful people (emoji key):

  
**Booker Zhao**  
🚇 ⚠️ 💻 🔌

  
**Weijia Wang**  
💻

  
**hengechang**  
💻 🚇

  
**Zijie Zhou**  
💻 🔌 📢

  
**erikqin**  
💻 🚧 💡

  
**Hanqin**  
🐛 💡

  
**Zem**  
💻

  
**magenta**  
📝 💻

  
**TIANXIANG LAN**  
🖋

  
**liyuanfeng**  
💻

  
**白宦成**  
💻

  
**易良**  
💻

  
**Sherry Zhang**  
💻 📝

  
**RealyBig**  
💻

  
**Saiya**  
📢 🐛 📝

  
**mirageql**  
💻 📝 💡

  
**Tab Liang**  
💻

  
**juukee**  
🐛

  
**Albert Liu**  
💻

  
**SearchFan**  
🐛

  
**Zira**  
💡 📝

  
**代码抄写狮**  
🐛

  
**lichaochao**  
💡

  
**MrZhaoCn**  
💻 💡

  
**xcatliu**  
💡

  
**唐羲**  
🐛

  
**Life**  
🐛

  
**Austin Lee**  
💻 💡

  
**iMaeGoo**  
💡

  
**Doggy**  
💡

  
**nasa.wang**  
💡

  
**pandagis**  
💡

  
**beet**  
💡 💻 📝

  
**程序员鱼皮**  
💡

  
**LanHao**  
💡

  
**manfwh**  
💻

  
**H**  
💡

  
**二鸟**  
💡

  
**Ryan Wang**  
💡

  
**UCToo**  
📝

  
**心谭**  
💻

  
**LRCong**  
💻

  
**Rin Hoshizora**  
📖

  
**justyouhappy**  
💻

  
**yuwuwu**  
📝

This project follows the all-contributors specification. Contributions of any kind welcome!

贡献指南
----

欢迎大家参与到 CloudBase Framework 的开发工作，贡献一份力量

您可以选择如下的贡献方式：

-   贡献一篇技术文章
-   贡献应用模板
-   提交一个应用案例
-   贡献代码，提交 Pull Request
-   反馈 bug，提交 Issue
-   在技术会议上发表技术演讲

我们会将您加入 我们的贡献者名单

贡献方式请参考 贡献指南 文档
