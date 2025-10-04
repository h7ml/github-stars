---
project: whistle
stars: 15129
description: HTTP, HTTP2, HTTPS, Websocket debugging proxy
url: https://github.com/avwo/whistle
---

whistle
=======

中文 · English

Whistle (发音为 /ˈwisəl/)是一款基于 Node.js 实现的跨平台网络抓包调试工具，具有：

1.  **功能强大**
    -   支持 HTTP 代理、HTTPS 代理、Socks 代理、反向代理多种代理模式
    -   支持查看和修改 HTTP、HTTPS、HTTP/2、WebSocket、TCP 请求/响应
    -   内置多种常用调试工具：
        -   Weinre：查看远程页面的 DOM 结构、
        -   Console：查看 console 日志、
        -   Composer：重放及编辑请求
2.  **操作简单**
    -   支持通过配置规则修改请求/响应
    -   提供一站式界面，可查看抓包、配置规则、管理插件、操作 Weinre/Console/Composer 等
3.  **可扩展**
    -   支持通过插件扩展规则及界面功能
    -   支持作为 NPM 模块被项目引用
4.  **跨平台**
    -   支持 macOS、Windows、Linux（Ubuntu/Fedora）等桌面系统
    -   支持无界面 Linux 服务器

安装
==

**macOS、Windows、Linux（Ubuntu/Fedora）等桌面系统推荐使用 Whistle 客户端：https://github.com/avwo/whistle-client**

> 使用 Whistle 客户端可以跳过**安装**步骤

无界面 Linux 服务器等环境，请按以下 4 个步骤操作：

1.  **安装 Whistle**，推荐用 NPM 安装：`npm i -g whistle`（需要先安装 Node.js：https://nodejs.org/ ）
    
    > 也支持通过 brew 安装：`brew install whistle`（需要先安装 brew：https://brew.sh/ ）
    
2.  **启动 Whistle**，命令行执行：`w2 start`
    
3.  **安装根证书**，命令行执行：`w2 ca`
    
    > 根证书安装过程可能需要手动确认：
    > 
    > Windows 需要最后点击 “是(Y)” 确认 macOS 需要输入开机密码或指纹验证
    
4.  **设置代理**，命令行执行：`w2 proxy`
    
    > macOS 首次设置代理可能需要输入锁屏密码
    > 
    > 设置指定 IP 或端口：`w2 proxy "10.x.x.x:8888"`
    > 
    > 关闭系统代理：`w2 proxy 0`
    > 
    > 其它设置代理的方式：
    > 
    > 1.  **（推荐）** 通过安装 Chrome 插件 ZeroOmega 设置代理：https://chromewebstore.google.com/detail/proxy-switchyomega-3-zero/pfnededegaaopdmhkdmcofjmoldfiped （无法访问可手动安装：https://chrome.zzzmh.cn/info/pfnededegaaopdmhkdmcofjmoldfiped）
    >     
    > 2.  直接在客户端上设置代理，如 FireFox、微信开发者工具等内置了设置代理功能
    >     
    >     FireFox 设置代理示例图
    > 3.  通过 Proxifier 设置代理（针对无法设置代理且不使用系统代理的客户端）：https://www.proxifier.com/docs/win-v4/http-proxy.html
    >     
    

快速上手
====

详细使用指南请参考：https://wproxy.org/docs/getting-started.html

License
=======

MIT
