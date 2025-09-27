---
project: awesome-deno-cn
stars: 479
description: 🦖 长期维护！中文圈下与 Deno 相关的 Awesome 资源全图谱
url: https://github.com/hylerrix/awesome-deno-cn
---

Deno 资源全图谱 · 专注中文版
==================

> 仓库目录可以使用 Github Chrome 插件来浏览。

为什么有这个项目？
---------

Deno v1.0 于 2020 年 05 月 13 日正式发布 v1.0 版本，一个专注于中文技术圈的 Deno 资源列表呼之欲出。

以下资源 🌟 代表品质推荐（尚未正式开始标记），⚠️ 代表注意事项。由于资源分类的多样性考虑，部分章节内容可能会有所重复。

### 独特之处 🦖🦕

-   长期提供更新，收集越来越多高质量的 Deno 资源，愿我们与 Deno 一起成长。
-   随着 Deno 主版本进行版本归档更新。
-   配套独家《Deno 钻研之术》电子书并随着本项目一起成长。
-   及时跟进 @denolib/awesome-deno 仓库。
-   寻找静态站点生成工具来让此资源清单更好看 -> 如果将每个条目“JSON“化就更好了。

还有如下很多事情可以做，期待你的贡献！

-   为每条记录增加一个 150 字以内的简介，让用户能通过本仓库更直接地了解每个项目的核心功能，而不是只有短短的名字外链和十多个字的概要；
-   添加更多资源；
-   推荐适合 awesome 展示页的项目或提交相关 PR；
-   通过大量资源一起梳理出更好的目录结构，绘制出与众不同的 Deno 资源图谱。

技术文档 🌟
-------

-   deno.land：Deno 官网。
    -   中文：https://denoland-cn.deno.dev。🌟。
    -   中文：denolang.cn。⚠️ 访问不了了。
-   deno.land/manual：Deno 手册。
    -   中文：deno-cn.vercel.app/manual。
    -   中文：nugine.github.io/deno-manual-cn。
    -   中文：manual.deno.js.cn/。deno-manual-cn 的镜像站。
    -   中文：denolang.cn/manual。
-   doc.deno.land：Deno API 查阅器，可查看官方/社区文档。
    -   附：官方标准库 API：doc.deno.land/builtin/stable
    -   附：官方非标注库 API：doc.deno.land/builtin/unstable
    -   中文：@denodev/typedoc。
-   deno.land/posts：Deno 官方博客。
    -   中文：deno-cn.vercel.app/posts。
    -   中文：@hylerrix/deno-tutorial：精读《Deno 官方博客系列》。
-   deno.land/x：DenoX 第三方库。
    -   中文：deno-cn.vercel.app/x。
-   deno.land/benchmarks：Deno 基准性能一览。
    -   中文：deno-cn.vercel.app/benchmarks。
-   ...逐步添加中，欢迎 Star & Fork & PR。

源码阅读推荐
------

> 以下仓库从下方其他章节精选。

-   @denoland/deno：🌟。Deno 核心仓库。
-   @denoland/deno\_std：🌟。Deno 标准库。
-   @oakserver/oak：🌟。Den Web 框架。
-   @alephjs/aleph.js：🌟。Deno React 全栈框架。
-   @divy-work/autopilot：🌟。用于 Deno 的跨平台桌面自动化框架。
-   @crewdevio/trex：🌟。像 npm 一样的 deno 软件包管理。
-   @cacjs/cac：🌟。用于构建命令行应用程序的简单但功能强大的框架。
-   denoify：🌟。对于希望支持 Deno 但不想编写和维护端口的 NPM 模块作者。
-   ...逐步添加中，欢迎 Star & Fork & PR。

基础设施
----

### Deno 源

> 虽然 Deno 可以直接导入 URL 代表着一定程度的去中心化，但是有中心化仓库也真香。

-   和 Deno 生态强相关的源
    -   deno.land/x：官方提供的第三方库注册中心。
    -   nest.land：🌟。基于区块链去中心化仓库。
    -   x.deno.js.cn：官方提供的第三方库的中国镜像站。
    -   denopkg：在 Deno 项目中使用 GitHub 上的代码的更简单方法。
-   基于 ES6 模块化机制的源
    -   skypack.dev/：🌟。无需安装和构建工具即可加载优化的npm软件包。
    -   jspm.io：允许从 CDN 中直接加载 NPM 的任何软件包。
    -   jsdelivr.com/：开源下免费的 CDN。
    -   esm.run：快速加载 JavaScript 模块的 CDN。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 包管理 && 配置管理

-   @BentoumiTech/denox：类似于 package.json 脚本，但在 Deno 上具有权限支持。
-   @bevry/make-deno-edition：自动使 package.json 项目（例如 npm 软件包和 node.js 模块）与 Deno 兼容。
-   @drashland/dmm：轻量级 Deno 模块管理器
-   @BoltDoggy/dpm：Deno 软件包管理器，为 Deno 安装全局命令，比如 Denoget。—— DVM。
-   @denodep/dep：Deno 依赖性管理工具。
-   @justjavac/dvm：Deno 版本管理器：管理多个活动的 Deno 版本。
-   @axetroy/dvm：没有运行时相关性的 Deno 版本管理器。
-   @MarkTiedemann/dvm.cmd：Windows 版 Deno 版本管理器，作为单个批处理文件编写。
-   @crewdevio/trex：🌟。像 npm 一样的 deno 软件包管理。
-   @irandeno/coffee：Deno 配置——一种类型安全、易于使用的 Deno 配置管理器。
-   @jinjor/deno-task-runner：像 NPM 脚本一样编写任务。
-   @egoist/dedep：管理依赖版本。
-   @umbopepato/velociraptor：Deno 的 npm 风格脚本运行器。
-   @ebebbington/context-finder：从配置文件中提取上下文块。
-   @eankeen/ensure：确保您运行的是 Deno，Typescript 或 V8 的最低版本。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### Web 框架 - 后端

-   @oakserver/oak：🌟。知名的 Deno Web 框架。
-   @syumai/dinatra：🌟。一个类似于 Sinatra 的轻量级 Deno Web 应用程序框架。
-   @zhmushan/abc：一个不错的 Deno Web 框架。
-   @alosaur/alosaur：具有许多装饰器的 Deno Web 框架。
-   @l2ig/aqua：用于 Deno 的小又快的 Web 框架。
-   @sholladay/pogo：一个 Deno 服务端框架。
-   @drashland/drash：零依赖性的 Deno HTTP 服务器的 REST 微框架。
-   @NMathar/deno-express：Node Express 已移植到 Deno。
-   @aaronwlee/attain：用于 Deno 的中间件 Web 框架，它使用受 Express 和 Oak 启发的 http 标准库，快速稳定地使用适当的内存。
-   @asos-craigmorten/opine：从 ExpressJS 移植的快速，简约的网络框架。
-   @JohannLai/doa：一个移植自 koa 的 Deno web 框架 doa。
-   @keroxp/servest：渐进式 HTTP 服务器/路由器。
-   @Caesar2011/denotrain：带有中间件支持的多合一 Web 框架，如 Express 或 Fastify for Node.js。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### Web 框架 - 前端

-   @alephjs/alephjs：🌟。Deno 下的 React 框架。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 环境变量

-   @cardosomarcos/deno-dotenv：从 .env 加载 deno 项目的环境变量。
-   @crewdevio/dino\_env:小型库，用于使用 deno 管理环境变量。
-   @pietvanzoen/deno-dotenv：Deno 下的 Dotenv。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 命令行

-   @ameerthehacker/cli-spinner：在执行长任务时在终端中显示微调框。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 模板引擎

-   @syumai/dejs：一个用于 Deno 的 ejs 模板引擎。
-   @zekth/deno\_tiny\_templates：Deno 的模板渲染器。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 测试

-   @udibo/mock：提供实用测试工具来帮助模拟测试行为并监视测试函数的调用。
-   @crewdevio/merlin：Deno 的测试和基准框架 🧙‍♂️。
-   @asos-craigmorten/superdeno：🌟。由超级代理驱动的库，用于测试 Deno HTTP 服务器。
-   @drashland/rhum：用于 Deno 的轻量级测试框架。
-   @unexpectedjs/unexpected：可扩展的 BDD 断言工具包。
-   @allain/expect：在 Deno 中编写 Jest 的助手。
-   @bokuweb/deno-pretty-assert：一个 Deno 下的 assertEqual 库。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 数据库

-   @manyuanrong/deno-mysql：MySQL 数据库驱动程序。
-   @keroxp/deno-redis：Redis Client for Deno 的实验性实现。
-   @manyuanrong/deno\_mongo：MongoDB 数据库驱动程序。
-   @buildondata/deno-postgres：PostgreSQL 数据库驱动程序。
-   @eveningkid/denodb：适用于 Deno 的 MySQL、SQLite、MariaDB、PostgreSQL 和 MongoDB ORM。
-   @manyuanrong/dso：一个基于 MySQL 的简单 ORM 库。
-   @halvardssm/deno-nessie：为 PostgreSQL、MySQL 和 SQLite 创建，迁移和回滚迁移。
-   @rahmanfadhil/cotton：Deno 下的 SQL 数据库工具。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### WebSocket

-   @drashland/sockets - 用于 Deno 的 WebSocket 库。
-   @ryo-ma/deno-websocket - 🦕 一个简单的 WebSocket 库，例如 node.js 库的 ws。
-   @keroxp/deno-ws：一个 Websocket 服务器的实验性实现。
-   @JohanWinther/websocket\_server：WebSocket 服务器库 🔌。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 命令行工具

-   @cacjs/cac：🌟。用于构建命令行应用程序的简单但功能强大的框架。
-   @ekaragodin/clone：一个方便克隆 Github 仓库到本地的简单实用程序。
-   @syumai/denoget：Deno 获取安装的可执行 Deno 脚本。
-   @syumai/denoinit：Deno 下简单的命令工具集。
-   @buttercubz/commands：为 Node.js 和 Deno 创建命令快捷方式。
-   @siokas/denomander：Deno 命令行界面的灵感来自 commander.js。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 应用级别

-   @PandawanFr/deno\_notify：在所有平台上发送桌面通知。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 数据类型处理

-   @denolib/ms：轻松地将各种时间格式转换为毫秒。
-   @denolib/qs：具有嵌套支持的 querystring 解析器。
-   @denolib/camelcase：将破折号/点号/下划线/空格分隔的字符串转换为驼峰式；示例：foo-bar→fooBar。
-   @denolib/marked：Markdown -> HTML 转换器。
-   @nekobato/deno-xml-parser：一个从 segmentio/xml-parser 移植的 Deno XML 解析器。
-   @nekobato/deno-yaml：一个使用 Deno 的简单 Yaml 解析器。
-   @manyuanrong/bytes\_formater：格式化字节（Uint8Array，ArrayBufferView ...）输出，在调试 IO 功能时很有用。
-   @manyuanrong/wasm-gzip：为 Deno 加密和解密 gzip。
-   @denolib/marked：Markdown 到 HTML 转换器。
-   @codetyphon/denoshort：URL 缩短器。
-   @zekth/deno\_case\_style：不同大小写样式的字符串验证器和格式化程序，例如 camelCase 等。
-   @jcardama/deno-slugify：Deno 的字符串节流器。
-   @hashrock/deno-fnparse：一个非常简单的 JavaScript 解析器、组合器。
-   @hayd/deno-globrex：glob 转 regex。
-   @OnikurYH/deno-prettystring：格式化，修剪和删除字符串中字符之间的多余空白。
-   @zekth/deno\_random\_interval：帮助器生成随机间隔。
-   @denorg/qrcode：Deno 的 QR 码图像生成器。
-   @denolib/qs：具有嵌套支持的查询字符串解析器。
-   @burhanahmeed/time.ts：Time.ts，简便的 Deno 时区操作。
-   @Maxim-Mazurok/sax-ts：从 sax-js 移植的 SAX 风格的 XML 解析器。
-   @matteocrippa/fossil：值类型验证套件。
-   @manyuanrong/deno-checksum：SHA1/MD5 算法。
-   @denorg/invert-kv：在 Deno 中反转键/值对。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### IDE 插件

-   @denoland/vscode-deno：🌟。VS Code 扩展。
-   @justjavac/typescript-deno-plugin：Deno 语言服务插件，在编辑器中的 TypeScript 文件中提供智能感知。
-   @ameerthehacker/deno-vscode：利用此扩展利用 VS Code 中内置的 typedef 和 intellisense。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 权限相关

-   @denofn/jwt：auth0/jsonwebtoken 的端口。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### JAM Stack/静态站点

-   @xcatliu/pagic：用 Deno 构建从 markdown 生成静态 html 页面的简单方法。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 从 Node 到 Deno

-   @garronej/denoify：🌟。对于希望支持 Deno 但不想编写和维护端口的 NPM 模块作者。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### TypeScript 相关

-   @zhmushan/dev\_server：让 TypeScript 文件直接在 script 标签中使用。
-   @sindresorhus/type-fest：基本 TypeScript 类型的集合（sindresorhus端口/ type-fest）。
-   @neuledge/computed\_types：类似 Joi 的 Typescript 和 Deno 验证器。
-   @motss/deno\_mod：一个 TypeScript 插件，它将允许 Deno 之外的 TypeScript 以类似于在 Deno 内部进行解析的方式来解析模块。⚠️ 已归档。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 进程管理

-   @manyuanrong/deno-deamon：使 Deno 程序在后台运行。
-   @eliassjogreen/denon：像 Nodemon 的 Deno 库。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 热更新

-   @jinjor/watch：文件观察器（热更新）。
-   @joakimunge/denoliver：具有实时重新加载功能的简单，无依赖的文件服务器。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 容器化 & 自动化 & 云

-   @divy-work/autopilot：🌟。用于 Deno 的跨平台桌面自动化框架。
-   @denofn/denofn-selfhosted：使用 Deno 和 Docker 构建的自托管 Deno 函数。
-   @maxmcd/deno-docker：一个 Docker 镜像。
-   @hayd/deno-docker：hayd 的几个 docker 映像。
-   @dontlaugh/packer-provisioner-deno：一个 Packer 插件，可轻松使用 Deno 脚本构建虚拟机映像。
-   @TencentCloudBase/cloudbase-framework/.../framework-plugin-deno：云开发 CloudBase Framework 框架「Deno」插件。
-   @marketplace/actions/update-deno：Github Action，它将具有最新 Deno 版本的文件放入您的存储库。
-   @denorg/starter：带有 GitHub Actions CI 的 Deno 模块入门模板。
-   ...逐步添加中，欢迎 Star & Fork & PR。

#### 其它

-   @denorg/up：检查是否在 Deno 中建立了网站。
-   @denorg/online：检查您当前是否将 Deno 运行在线上。
-   @code-hex/deno-context：将期限，取消和其他要求范围的值传播给多个 Promise，行为就像 Go 的上下文。
-   @hashrock/deno-opn：一个可以打开网站、(可执行)文件之类资源的跨平台工具。
-   @manyuanrong/deno-plugin-prepare：一个用于管理 Deno 原生插件依赖关系的库。
-   @manyuanrong/deno-smtp：SMTP 的 SMTP 邮件发件人。
-   @hayd/deno-using：带有 Deno 语句的 Python 样式。
-   @lucascaro/deno-uuid：Deno 的 UUID 模块。
-   @rbrahul/deno\_cron：cron job 调度程序，使您可以编写具有大量灵活性的可读 cron 语法
-   @eliassjogreen/deno\_tokenizer：Deno 的简单标记器。
-   @garronej/evt：EventEmitter 的安全替代品。
-   @partheseas/gardens：一个无处不在的 JavaScript 日志实用程序。
-   @luvies/lazy：类似于 linq 的惰性求值迭代模块。
-   @thewizardbear/maze\_generator：用于生成、求解、分析和显示迷宫的 Javascript 模块。
-   @matteocrippa/microraptor：轻量级框架，可通过验证轻松进行网络路由。
-   @denorg/recursive-readdir：递归读取 Deno 中的目录。
-   @zhmushan/router：高性能基本路由器可在任何地方工作。
-   @richytong/rubico - 🏞 异步函数组成；它刚刚能运行。
-   @denosaurs/status：Deno 的 HTTP 代码和状态实用程序。
-   @ebebbington/task-runner-v2：deno-task-runner 的版本 2 解决方案。
-   @marcopacini/ts-prometheus：一个 prometheus 客户端。
-   @eliassjogreen/webview：Webview 的 Deno 绑定，这是一个用于创建基于 Web 的桌面 GUI 的小型库。
-   @bokuweb/wu-diff-js：一个差异库，使用 wu（O（NP））算法计算两个切片之间的差异。
-   @akshgpt7/youtube-deno：YouTube 数据 API 的 Deno 客户端库，用于与 YouTube 进行任何交互。
-   @lucascaro/denoversion：Deno 的 SemVer + Git 版本管理。
-   @MarkTiedemann/deno.mk：用于安装和运行 Deno 的跨平台 Makefile。
-   @jinjor/deno-playground：提供一些 Deno 自定义模块。
-   @pikapkg/builders/.../pika-Deno-plugin。
-   @hayd/deno-udd：更新面依赖：将导入语句更新为最新发布的版本。
-   @manyuanrong/sql-builder：SQL 查询生成器。
-   @youngjuning/duck：一个简单的扫描 controller 并自动注册路由的中间件。
-   @timonson/djwt：根据 JWT 和 JWS 规范在 Deno 上创建 JSON Web 令牌（JWT）。
-   @timonson/gentleRpc：用于 Deno 和浏览器的 JSON-RPC 2.0 TypeScript 库。
-   @motss/deno\_mod：提供一些 Deno 自定义模块。
-   @AlpacaBi/qrcode\_terminal。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 在线沙箱

-   deno.town。
-   deno-playground.now.sh。
    -   @maman/deno-playground。
-   playground.denobr.com/。
-   mycompiler.io/new/deno。
-   repl.it/languages/deno。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 机器人

-   Telegram Bot Assistant。
-   @genemators/lander.js。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 数据展示

-   @vicky-gonsalves/deno\_rest：RESTful API 的样板。
-   @tamasszoke/deno-seed：完整的样板可供开发。 🌱
-   @github-profile-trophy：🏆 在你的 README 文件中添加动态生成的 GitHub Trophy。
-   usingdeno.com：使用 Deno 的 Web 应用程序和项目列表 🦕。

-   ...逐步添加中，欢迎 Star & Fork & PR。

成套解决方案
------

如果你有好的解决方案，欢迎提供在这里！

解决方案 - 项目模板
-----------

> 留坑，这里是未来探索的重点。主要罗列如何用 Deno 快速搭建起可供生产环境使用的成套解决方案。之前列到的很多库用来单一方面。 成套解决方案目前先重点探索提供项目模板的库。

-   @tamasszoke/deno-seed - 完整的开发样板 🌱。
-   @youngjuning/deno-oak-mongo-demo。
-   @TencentCloudBase/cloudbase-templates/.../deno-cloud-app\- 可以通过 CLI 一键部署的 Deno 云应用模板。

-   ...逐步添加中，欢迎 Star & Fork & PR。

思考：

-   Deno + Oak + MySQL + RESTful 解决方案？
-   Deno + Oak + MongoDB + GraphQL 解决方案？
-   Deno + React 解决方案？

### 开发 Deno 模块

-   如何开发 Deno （各种类别的）模块？
-   ...逐步添加中，欢迎 Star & Fork & PR。

技术教程
----

### 技术专栏（中文）

-   juejin.im/tag/deno：掘金标签。
-   Deno 开发者社区：知乎专栏。
-   Deno 世界：知乎专栏。
-   Deno 钻研之术：知乎专栏。
-   Deno 进阶开发笔记：不定时更新。
-   极客帮 - Deno。
-   InfoQ - Deno。
-   百度 - InfoQ。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 技术专栏（英文）

-   denobeginner.com

-   freecodecamp.org/news/tag/deno：freeCodeCamp 标签。
-   V8 Docs for Deno：面向 Deno 的 V8 文档。
-   A Guide to Deno Core (Design & For Contributors)：(⚠ 内容过期），发布于 2019 年。
-   Deno 源码贡献指南（英文版）：托管于 Gitbook 上。
-   reddit - deno。
-   Google - Deno。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 单篇文章（中文）

> 专注于收集高质量的博客文章，更多内容可以在谷歌/百度上搜索。目前 Deno 文章不多，尽可能多的罗列不设内容质量限制。 包含翻译。

-   可能是首个支持部署 Deno 前后端应用的部署工具：发布于 2020-08-19
-   从实际案例讲 Deno 的应用场景：发布于 2020-08-14
-   从零开发一款Deno插件并发布：发布于 2020-08-12。
-   基于 Deno 构建 HTTP Server 实践指南：发布于 2020-08-03。
-   Deno从入门到跑路：发布于 2020-07-27。
-   听说要干掉 node.js？用Deno实现价值上亿的AI核心算法试一下：发布于 2020-05-14。
-   了不起的 Deno 入门教程，发布于 2020-05-14。
-   Deno 运行时入门教程：Node.js 的替代品：🌟。发布于 2020-01-26。
-   学得动的 Deno：发布于 2018-10-19。
-   Deno 并不是下一代 Node.js：🌟。发布于 2018-06-04。
-   让我们一起来学习别人学不动的 Deno：发布于 2018-06-03。
-   快速了解 deno 目前的 API：发布于 2018-06-03。
-   玩 Deno 遇到问题的解决方案：发布于 2018-06-02。
-   我不看好 Deno。
-   Deno 1.0 即将发布，你需要知道的都在这里了：原文发布于 2020-05-06 日。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 单篇文章（英文）

-   Continuous Integration with Deno：发布于 2020-06-30。
-   Deploy a Deno Application on AWS Using Docker and Travis CI：发布于 2020-06-14。
-   Create interactive mail utility CLI Tool using Deno：发布于 2020-06-11。
-   Develop and Dockerize a Blogging API With Deno, Oak, and MySQL：发布于 2020-06-10。
-   Building API's using Deno, Oak and MYSQL：发布于 2020-06-05。
-   Create your first News CLI app using Deno：发布于 2020-06-02。
-   Create a simple Note-taking app with Deno：发布于 2020-05-21。
-   First thoughts about Deno：发布于 2020-05-20。
-   Is Deno the new Node?：发布于 2020-05-20。
-   Deno vs. Node.js — Here are the most Important Differences：发布于 2020-05-18。
-   From Node to Deno：发布于 2020-05-17。
-   Why I Believe Deno is a Step in the Wrong Direction for JavaScript Runtime Environments：发布于 2020-05-14。
-   The Deno Handbook: A TypeScript Runtime Tutorial with Code Examples：发布于 2020-05-12。
-   Learn Deno: Chat app：发布于 2020-05-10。
-   Deno 1.0: What you need to know：发布于 2020-05-06。
-   What is Deno? A ‘better’ Node.js：发布于 2020-02-28。
-   Forget NodeJS! Build native TypeScript applications with Deno 🦖：发布于 2020-02-18。
-   -   Write a small API using Deno：发布于 2019-11-12。
-   Deno on AWS Lambda with Architect or SAM：发布于 2019-11-21。
-   What's Deno, and how is it different from Node.js?：发布于 2019-07-12。
-   What’s Deno, and how is it different from Node.js?：发布于 2019-07-09。
-   Deno on Cloud Run：发布于 2019-05-14。
-   Getting started with Deno：发布于 2019-04-18。
-   Develop with Deno and Visual Studio Code：发布于 2019-01-05。
-   Ryan Dahl’s Node.js regrets lead to Deno：发布于 2018-06-21。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 演讲稿（中文）

-   ...逐步添加中，欢迎 Star & Fork & PR。

### 演讲稿（英文）

-   Ryan Dahl - 我为 Node.js 感到遗憾的 10 件事 | JSConf EU 2018
    -   演讲稿
-   Ryan Dahl - Deno, 新的服务器端运行时 | JSDC 2018#A01
    -   演讲稿
-   Ryan Dahl - Deno, 一种新的 JavaScript 方法 | JS Fest 2019 Spring
    -   演讲稿
-   Rafał Pocztarski — 从 Node.js 到 Deno -使用 V8 和 Rust 构建的 JavaScript / TypeScript 运行时\[EN\]
    -   演讲稿
-   Ryan Dahl: JavaScript 和 TypeScript 的安全运行时 | js.la April 2019
    -   演讲稿
-   Ryan Dahl: Deno, 一种新的 JavaScript 方法 | HolyJS 2019 Piter
    -   演讲稿
-   Rafał Pocztarski - 什么是 Deno？ 2020年代用于现代 JavaScript 和 TypeScript 后端的新运行时 | Deno Warsaw
    -   演讲稿
-   Michał Sabiniarz - 如何为 Deno 做贡献 | Deno Warsaw
    -   演讲稿
-   Bartek Iwańczuk - Deno 内部是如何构建现代运行时 | Deno Warsaw
    -   演讲稿
-   Ryan Dahl & Kitson Kelly: Deno 是一种新的 JavaScript 方法 | TSConf 2019
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 在线视频（中文）

-   Bilibilii | 【中英双语】Node 之父 - Deno，一个新的 JS 运行时。
-   Deno 1.0 新特性了解一下。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 在线视频（英文）

-   Deno in 100 Seconds。
-   ...逐步添加中，欢迎 Star & Fork & PR。

电子资源
----

> 专注收集公开免费的 PDF、PNG 以及电子书等资源，放置在本项目的 resources 文件夹下。

-   《Node.js 的设计缺陷（英文版）》。
-   《Node.js 的设计缺陷（中文版）》。
-   ...逐步添加中，欢迎 Star & Fork & PR。

技术社区
----

### 开源组织

> 重点收集专注于使用 & 回馈 Deno 生态圈的第三方 Github 组织。

-   github.com/denodev。
-   github.com/denolib。
-   github.com/denorg。
-   github.com/denodep。

-   github.com/denofn。

-   ...逐步添加中，欢迎 Star & Fork & PR。

### 社区列表（全网）

-   Deno Discord：🌟。Discord 上的 Deno 官方聊天室，有中文社区。
-   deno.dev：🌟。开发中。
-   deno.js.cn：🌟。Deno 中文社区。
-   denocn.org：🌟。Deno 中文社区。
-   yydeno：YY 大前端团队 Deno 仓库。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 讨论热帖（中文）

-   Deno 会在短期内取代 Node 吗？：发布于 2020-05-22。
-   @v2ex/Deno 1.0：发布于 2020-05-13。
-   @v2ex/看了 Deno，感觉 TS 前景不可估量啊：发布于 2020-03-08。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 讨论热帖（英文）

-   Reddit 社区 | Deno。
-   ...逐步添加中，欢迎 Star & Fork & PR。

谁在用 Deno？
---------

> 重点收集已经部署在生产环境的应用，欢迎推荐你的案例，逐步完善中。

-   UsingDeno - 使用 Deno 的 Web 应用程序和项目列表 🦕。

-   ...逐步添加中，欢迎 Star & Fork & PR。

其它订阅
----

### 新闻媒体（英文）

-   Deno 新闻推送
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 社交媒体（英文）

-   twitter@deno\_land：Deno Land 官方推特。
-   ...逐步添加中，欢迎 Star & Fork & PR。

番外篇
---

### 从 Node.js 到 Deno.js

-   《Node.js 的设计缺陷》：官方 PDF 演讲稿。
-   《Design Mistakes in Node》Node 之父 Ryan Dahl 演讲 PPT 中文版 (2018 JS Conf Berlin)：发布于 2018-06-03。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### Deno 依赖的技术清单

> Deno 本身依赖的技术的清单库。

-   @dzharii/awesome-typeScript。
-   @semlinker/awesome-typeScript。
-   @rust-unofficial/awesome-rust。
-   @sindresorhus/awesome-nodejs。
-   @avelino/awesome-go。
-   @jobbole/awesome-go-cn。
-   ...逐步添加中，欢迎 Star & Fork & PR。

### 仓库更新日志

-   2020-04-14 初始化本项目，填充独特的中文版内容。
-   2020-04-14 跟进最新的（180+ Star） @olivewind/awesome-deno-cn 仓库内容。
-   2020-05-13 新增《Deno 钻研之术》项目，将本项目作为前者的配套项目。
-   2020-05-14 同步最新的 @denolib/awesome-deno 仓库内容。
-   2020-05-17 跟进中文化后大改版的（200+ Star） @olivewind/awesome-deno-cn 仓库内容。
-   2020-05-22 全网大量搜索 Deno 中英文资源并入库，发布 v1.0 版本并收录在《Deno 钻研之术》第二篇中。
-   2020-08-07 大幅更新：
    -   跟随 Deno 主版本号同步发布 v1.2.2 版本。
    -   新增 all-contributor 贡献者机器人。
    -   增加如下章节：Deno 版本日志、解决方案。
    -   填充大量内容，新增贡献准则。
-   2021-02-25 大幅更新：
    -   跟随 Deno 主版本号提前发布 v1.8.0 版本。
    -   将之前尚未分类的数十条进行分类
-   2021-xx-xx
    -   引入 Pagic 来展示此资源清单
    -   同步最新的 @denolib/awesome-deno 内容
    -   全网大量搜索 Deno 中英文资料并入库

贡献者 ✨
-----

感谢如下贡献者的贡献 (emoji key)：

  
**hylerrix**  
🤔 📖

  
**JohannLai**  
📖

  
**champ**  
📖

  
**Bd999**  
📖

  
**杨俊宁**  
📖

  
**Booker Zhao**  
📖

  
**木杉**  
📖

  
**kily zhou**  
📖

  
**guzhongren**  
📖

本项目贡献者列表遵循 all-contributors 规范。欢迎你的参与，本仓库贡献准则！

开源协议
----

本项目文档内容均采用 CC-BY-SA-4.0 协议进行共享。
