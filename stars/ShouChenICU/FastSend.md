---
project: FastSend
stars: 1019
description: FastSend 是一个基于 WebRTC 技术的点对点文件传输工具，支持快速的目录同步和文件传输。通过浏览器即可实现安全、高效的文件共享。
url: https://github.com/ShouChenICU/FastSend
---

FastSend 文件快传 🚀
================

📖 项目介绍
-------

FastSend 是一个基于 WebRTC 技术的点对点文件传输工具，支持快速的目录同步和文件传输。通过浏览器即可实现安全、高效的文件共享。

🌐 在线体验：fastsend.ing

✨ 特性
----

-   🔒 点对点加密传输，确保数据安全
-   📁 支持文件和文件夹传输
-   🚀 局域网自动优化，传输更快
-   🎯 简单易用的界面设计
-   🌍 支持中英文界面
-   📲 支持PWA轻量安装

🛠️ 技术栈
-------

-   WebRTC
-   Vue.js
-   Nuxt3
-   TypeScript
-   Modern File System API

📦 安装与构建
--------

# 安装依赖
yarn install

# 构建项目
yarn build

🚀 使用方法
-------

# 启动服务
node .output/server/index.mjs

**注意：** 目录传输需要`HTTPS`以及浏览器支持，一般新版本的桌面浏览器都支持

🐳 Docker和Docker Compose
------------------------

### Docker 构建

docker build -t fastsend .
docker run -d --name fastsend -p 3000:3000 fastsend

### Docker Compose

将项目拉取到本地，然后运行：

docker-compose up -d

访问 `http://localhost:3000` 即可使用。

💡 使用提示
-------

1.  确保浏览器启用了 WebRTC 功能
2.  如需传输文件夹，请确保浏览器支持现代文件系统 API
3.  在同一局域网内传输速度最快
4.  建议在网络状态良好时使用

👨‍💻 作者
--------

**ShouChen**

-   博客: shouchen.blog
-   X: @ShouChen\_

🤝 贡献
-----

欢迎提交 Issue 和 Pull Request！

📝 开源协议
-------

本项目基于 MIT 协议开源。

⭐ 支持项目
------

如果这个项目对你有帮助，欢迎给一个 star 支持一下！

* * *
