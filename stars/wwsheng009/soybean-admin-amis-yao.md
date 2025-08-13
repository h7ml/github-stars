---
project: soybean-admin-amis-yao
stars: 8
description: soybean admin integrated with amis and yao
url: https://github.com/wwsheng009/soybean-admin-amis-yao
---

SoybeanAdmin
============

中文 | English

* * *

Note

如果您觉得 `SoybeanAdmin`对您有所帮助，或者您喜欢我们的项目，请在 GitHub 上给我们一个 ⭐️。您的支持是我们持续改进和增加新功能的动力！感谢您的支持！

简介
--

`SoybeanAdmin` 是一个清新优雅、高颜值且功能强大的后台管理模板，基于最新的前端技术栈，包括 Vue3, Vite6, TypeScript, Pinia 和 UnoCSS。它内置了丰富的主题配置和组件，代码规范严谨，实现了自动化的文件路由系统。此外，它还采用了基于 ApiFox 的在线Mock数据方案。`SoybeanAdmin` 为您提供了一站式的后台管理解决方案，无需额外配置，开箱即用。同样是一个快速学习前沿技术的最佳实践。

特性
--

-   **前沿技术应用**：采用 Vue3, Vite6, TypeScript, Pinia 和 UnoCSS 等最新流行的技术栈。
-   **清晰的项目架构**：采用 pnpm monorepo 架构，结构清晰，优雅易懂。
-   **严格的代码规范**：遵循 SoybeanJS 规范，集成了eslint, prettier 和 simple-git-hooks，保证代码的规范性。
-   **TypeScript**： 支持严格的类型检查，提高代码的可维护性。
-   **丰富的主题配置**：内置多样的主题配置，与 UnoCSS 完美结合。
-   **内置国际化方案**：轻松实现多语言支持。
-   **自动化文件路由系统**：自动生成路由导入、声明和类型。更多细节请查看 Elegant Router。
-   **灵活的权限路由**：同时支持前端静态路由和后端动态路由。
-   **丰富的页面组件**：内置多样页面和组件，包括403、404、500页面，以及布局组件、标签组件、主题配置组件等。
-   **命令行工具**：内置高效的命令行工具，git提交、删除文件、发布等。
-   **移动端适配**：完美支持移动端，实现自适应布局。

版本
--

-   **NaiveUI 版本:**
    -   预览地址
    -   Github 仓库
    -   Gitee 仓库
-   **AntDesignVue 版本:**
    -   预览地址
    -   Github 仓库
    -   Gitee 仓库
-   **ElementPlus 版本:**
    -   预览地址
    -   Github 仓库
-   **旧版:**
    -   预览地址
    -   Github 仓库

文档
--

-   地址
-   旧版文档

合作事项
----

我们非常感谢大家对 `SoybeanAdmin` 的支持！为了进一步回馈社区，并助力企业和开发者实现个性化需求，我们现提供多种合作服务，期待与您携手共赢。

##### 1、定制化管理后台开发

针对企业和开发者的特定业务需求，我们提供基于 `SoybeanAdmin` 的定制化管理后台开发服务。我们的团队具备丰富的行业经验，能够迅速理解并实现您的需求，打造高效、灵活且安全的定制化解决方案。

-   **定制开发**：我们将根据您的具体需求，提供从需求分析、UI设计到功能实现的全方位服务，确保项目高效交付。
-   **功能扩展**：在 `SoybeanAdmin` 基础上，扩展您所需的特定功能模块，提升管理后台的功能和用户体验。

##### 2、企业外包服务

我们承接各类企业级外包项目，特别是在管理后台系统的开发、集成与运维方面。我们以精益求精的态度，确保项目的质量和进度，为您的业务提供强有力的技术支持。

-   **项目开发**：无论是全新的项目，还是现有系统的优化与集成，我们都将为您量身打造高效可靠的解决方案。
-   **系统集成与维护**：我们也提供基于 `SoybeanAdmin` 的系统集成与长期维护服务，确保您的系统稳定、安全地运行。

##### 3、联系方式

如有合作意向或项目咨询，请通过以下方式与我们联系：

-   **Email**: soybeanjs@outlook.com
-   **GitHub Issues**: 欢迎通过 GitHub Issues 联系我们，进行初步的合作洽谈。
-   **商务合作微信**: honghuangdc

期待与您开展深入合作，共同推动 SoybeanAdmin 项目及其在更多领域的成功应用！

示例图片
----

使用
--

**环境准备**

确保你的环境满足以下要求：

-   **git**: 你需要git来克隆和管理项目版本。
-   **NodeJS**: >=18.12.0，推荐 18.19.0 或更高。
-   **pnpm**: >= 8.7.0，推荐 8.14.0 或更高。

**克隆项目**

git clone https://github.com/soybeanjs/soybean-admin.git

**安装依赖**

pnpm i

> 由于本项目采用了 pnpm monorepo 的管理方式，因此请不要使用 npm 或 yarn 来安装依赖。

**启动项目**

pnpm dev

**构建项目**

pnpm build

**代码同步**

参考 代码同步 文档。

周边生态
----

-   react-soybean-admin: 基于SoybeanAdmin的React版本.
-   electron-mock-admin: 一个 Mock Api 管理系统，帮助前端开发伙伴快速实现接口的 mock。
-   T-Shell: 是一个可配置命令提示的终端模拟器和 SSH 客户端。
-   pea : 采用SpringBoot3.2 + JDK21、MyBatis-Plus、SpringSecurity安全框架等，适配 soybean-admin 开发的简单权限系统。
-   MalusAdmin: 基于 Vue3/TypeScript/NaiveUI 和 NET7 & Sqlsugar 开发的后台管理框架。采用最原生最简洁的方式来实现, 前端清新优雅高颜值，后端 结构清晰，优雅易懂，功能强大。
-   PanisAdmin: 采用SpringBoot3、SaToken、MySQL等框架开发，二次修改 soybean-admin，适配动态菜单/按钮级别的鉴权，保留原汁原味、清新优雅、高颜值的后台管理系统脚手架。
-   snail-job: 一款兼具 “高性能、高颜值、高活跃” 的分布式任务重试和分布式任务调度平台。
-   SuperApi: 快速将你的 idea 变成线上稳定运行的产品！ 无实体建库建表，对无实体库表进行增删改查，支持 15 种条件查询，以及分页，列表，无限级树形列表 等功能的 API 部署！ 拥有接口文档，Auth 授权，接口限流，获取客户端真实 IP，先进的服务器缓存组件，动态 API 等功能，期待您的体验！
-   FastSoyAdmin: 基于 FastAPI+Vue3+Naive UI 的现代化轻量管理平台.
-   ba: 基于goFrame框架开发的后端服务对接soybean-admin,适配动态路由,接口鉴权限。
-   soybean-admin-go:基于gin+gorm框架开发的go语言后端服务对接soybean-admin的example分支,适配动态路由,接口鉴权限。

如何贡献
----

我们热烈欢迎并感谢所有形式的贡献。如果您有任何想法或建议，欢迎通过提交 pull requests 或创建 GitHub issue 来分享。

Git 提交规范
--------

本项目已内置 `commit` 命令，您可以通过执行 `pnpm commit` 来生成符合 Conventional Commits 规范的提交信息。在提交PR时，请务必使用 `commit` 命令来创建提交信息，以确保信息的规范性。

浏览器支持
-----

推荐使用最新版的 Chrome 浏览器进行开发，以获得更好的体验。

not support

last 2 versions

last 2 versions

last 2 versions

last 2 versions

开源作者
----

Soybean

贡献者
---

感谢以下贡献者的贡献。如果您想为本项目做出贡献，请参考 如何贡献。

交流
--

`SoybeanAdmin` 是完全开源免费的项目，在帮助开发者更方便地进行中大型管理系统开发，同时也提供微信和 QQ 交流群，使用问题欢迎在群内提问。

QQ交流群

添加下面微信邀请进微信群

Star 趋势
-------

开源协议
----

项目基于 MIT © 2021 Soybean 协议，仅供学习参考，商业使用请保留作者版权信息，作者不保证也不承担任何软件的使用风险。
