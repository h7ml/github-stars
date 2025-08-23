---
project: Stapxs-QQ-Lite
stars: 162
description: 一个兼容 oicq-http 的非官方网页版 QQ 客户端
url: https://github.com/Stapxs/Stapxs-QQ-Lite
---

Stapxs-QQ-Lite
==============

### 去看看 2.0 版本吧 ——

Stapxs QQ Lite 1.0 已停止维护，如果你对它感兴趣 —— 不如来看看 2.0 版本。

  

  

Stapxs QQ Lite
==============

### 一个兼容 oicq-http 的非官方网页版 QQ 客户端

  
  
**本网页仅供学习交流使用，请勿用于其他用途**  
**版权争议请提出 issue 协商**  
本网页存在大量不规范的写法和操作  
请不要使用此网页作为 JavaScript 开发参考

  
  

在线演示
----

### GitHub Pages

本仓库开启了 GitHub Pages, 你可以选择直接访问本仓库的页面来使用: https://stapxs.github.io/Stapxs-QQ-Lite

部署
--

### 克隆仓库

此项目为完整的纯前端静态页面,你可以克隆仓库,非常暴力的直接打开 `index.html` 来使用; 但是需要注意的是部分浏览器在使用 `file://` 协议的时候无法正常允许页面发起通知, 同时文件也无法唤起 PWA 功能进行 PWA APP 安装。 在 `v1.2.0` 版本之后，依赖 cookie 的功能也完全无法在文件打开时使用，敬请注意。

同样由于此项目是静态页面,你也可以将它部署在任何 Web 服务端或者静态页面托管服务上。

使用
--

本程序依赖 oicq-http v1 作为后端服务, 关于 oicq-http 可以参考 此处。

### 部署 OICQ

你可以参考 oicq-http 的简单教程部署 oicq-http Bot, 或者看下面。

1.  运行 oicq 需要依赖 Node.js (12.16+), 确保你已经安装了 Node.js (和 NPM), 执行如下指令安装 oicq-http:  
    `npm i oicq@1 -g`  
    如果你使用 Yarn:  
    `yarn global add oicq@1`
    
2.  接下来使用你的 QQ 号登录 oicq:  
    `oicq < QQ 号 >`
    
3.  首次运行将生成配置文件, 需要修改配置文件来使 Web 可以交互:  
      
    打开生成的配置文件修改一些东西, 确保启用了 ws 服务并设置了连接 token:  
    
4.  再次使用你的 QQ 号登录 oicq, oicq-http 应当正常启动:  
    

### 连接 OICQ

接下来就可以打开页面连接到 oicq-http 了; 如果在本地部署了 oicq-http 直接连接本地即可, 网络服务则建议开启 wss 并连接, 此处不过多累述。

其他提醒
----

### 关于不安全连接

-   当使用 https 页面连接 ws 服务（反之相同）的情况下，连接将会失败；这是由于其中某一者是不安全的。在这种情况下，你可以选择将 ws 提升为 wss 或者将 https 降级为 http（不安全）来解决问题，此处不提供解决方案。#32

更多问题
----

### 我能使用其他 QQ Http Bot 吗

-   如果它兼容 OneBot 11 协议, 你可以尝试连接它, 但是由于消息体格式和接口扩展的差异，大部分情况下都不能完全正常使用。以下是已经经过兼容的 Bot:
    
    -   oicq http v1：完全兼容
    -   go-cqhttp：基本兼容，目前 @ 消息不能正常显示

### 使用 Bot 是否有风险

-   如果你使用的是 oicq-http, 可以查看此处了解 使用风险, 如果你尝试使用其他 QQ Bot (参见上一条问题), 请自行参考它的文档。

### 我遇到了问题

-   如果有什么奇奇怪怪的问题, 欢迎发起 issue 询问! 如果有什么 BUG 和优化建议也可以哦!

依赖和许可声明
-------

Stapxs QQ Lite

(C) Stapx Steve \[ 林槐 \]. licensed under Apache 2.0

Border Card UI

(C) Stapx Steve \[ 林槐 \]. licensed under Apache 2.0

Bootstrap

(C) Fathom. licensed under MIT

Font Awesome

(C) Fonticons, Inc. licensed under SIL OFL 1.1

JQuery & JQuery UI

(C) OpenJS Foundation. licensed under MIT

QFace

https://github.com/koishijs/QFace

  
  
README v1.3  
林槐出品, 必属稽品
