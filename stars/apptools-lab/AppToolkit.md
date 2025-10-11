---
project: AppToolkit
stars: 590
description: 🐘 The Front-end Env Toolkit（前端环境管理工具）
url: https://github.com/apptools-lab/AppToolkit
---

   

AppToolkit
==========

> 一款帮助开发者更轻松的管理前端开发软件，更快速配置前端环境的前端研发工具箱。

特性
--

-   **一键安装前端开发工具**：包括但不限于：桌面客户端、编辑器插件、浏览器插件、命令行工具等
-   **可视化管理前端开发工具**：覆盖工具查找、安装、升级、卸载完整的软件生命周期管理
-   **可视化配置前端开发环境**：包括但不限于：Node 配置、Git 配置、npm 配置等

安装
--

mac 版本：下载地址

使用说明
----

### 一键安装前端开发必备工具

在首页中点击『一键安装』，选择需要安装的软件，点击『确认』按钮，等待片刻后完成软件的安装。

### Node 管理

#### 切换 Node.js 版本

在 『Node 管理』页面中点击『切换版本』，选择 Node.js 版本后，点击『下一步』开始 Node.js 安装：

目前 Node.js 版本切换依赖 `nvm`，切换版本后，之前安装全局命令模块需要重新安装，非常不方便。在 AppToolkit 中可一键配置统一的全局模块安装路径到 `~/npm-global`：

#### 管理全局 npm 镜像源

AppToolkit 提供一键切换全局 npm 镜像源功能：

#### 管理全局依赖

Toolkit 提供全局 npm 依赖的可视化管理，支持查看、安装、重装、升级和卸载全局依赖。

### Git

#### 全局 Git 配置

目前提供常见的配置项：『用户名』、『邮箱』和『忽略文件名大小写』，后续可根据实际的需要，增加更多的 Git 配置。

#### 用户 Git 配置

当有多个 Git 用户账号时，比如：

-   一个 Github 账号，用于自己进行一些开发；
-   一个 GitLab 账号，用户公司内部的工作开发；

这时就需要在本地配置多份 Git 配置和 SSH 密钥了。Toolkit 为了减少用户的配置成本，支持可视化管理不同用户账号的 Git 配置。

其中，部分字段的说明如下：

-   配置名称：建议填写 Git 服务器的名称，比如 Github、GitLab
-   Git 服务器域名：可以使不同的 Git 仓库使用对应的 SSH Key。以放在 Github 的 appworks-lab/Toolkit 仓库为例，`github.com` 就是 Github 服务器域名了（PS：填写域名时不需要带 `https://`）。在提交代码时，就会自动使用刚才生成好的 Github SSH 密钥了

#### 使用不同的 Git 配置

Toolkit 支持每份 Git 配置中添加一个或多个目录，这些目录下的 Git 仓库都会使用这份 Git 配置。实现原理可参考 Git 文档。

#### 添加 SSH 公钥

1.  首先在 Git 管理页面中复制 SSH 公钥

1.  以 Github 举例，依次点击 Setting -> SSH and GPG keys -> New SSH Key，把刚才的复制的 SSH 公钥添加到 Github 中

1.  SSH 公钥添加完成以后，就可以使用 SSH 协议操作 Git 仓库了

### 桌面客户端管理

AppToolkit 提供常用的前端开发软件的安装、卸载等功能，减少查找软件的时间。

### 浏览器插件管理

AppToolkit 提供推荐的浏览器插件列表，方便用户快速找到好用的插件。由于 AppToolkit 无法直接安装插件，需要用户在浏览器的插件市场安装。假如无法访问浏览器的插件市场，AppToolkit 会下载插件安装包到本地，需要用户在浏览器插件管理页面中自行安装。

贡献代码
----

贡献代码请参考 CONTRIBUTING.md

License
-------

MIT
