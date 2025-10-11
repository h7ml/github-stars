---
project: ChatGPT-wechat-bot
stars: 4731
description: ChatGPT for wechat https://github.com/AutumnWhj/ChatGPT-wechat-bot
url: https://github.com/AutumnWhj/ChatGPT-wechat-bot
---

ChatGPT-wechat-bot🤖
====================

> 几步即可获得一个基于 ChatGPT 的微信机器人 🤖。 English | 中文文档

Support
-------

-   支持上下文语境的对话。
-   支持重置上下文语境，通过关键词(reset)重置对话上下文语境。
-   支持在群聊@你的机器人 🤖，@机器人即可收到回复。
-   支持通过关键词唤醒你的机器人，如当在群组中发送“@机器人 hello xxxx”时才会收到回复。
-   其他

合作
--

默认配置
----

{
  // 填入你的OPENAI\_API\_KEY
  OPENAI\_API\_KEY: "",
  // 反向代理地址，简单说就是你的在国外服务器地址，如何获取看README
  reverseProxyUrl: "",
  // 在群组中设置唤醒微信机器人的关键词
  groupKey: "",
  // 在私聊中设置唤醒微信机器人的关键词
  privateKey: "",
  // 重置上下文的关键词，如可设置为reset
  resetKey: "reset",
  // 是否在群聊中带上提问的问题
  groupReplyMode: true,
  // 是否在私聊中带上提问的问题
  privateReplyMode: false,
}

开始设置机器人 🤖
----------

1.  首先，需要按照以下步骤获你的 ChatGPT 的 OPENAI\_API\_KEY.

> 获取你的 OPENAI\_API\_KEY:
> 
> -   打开 https://platform.openai.com/overview 并登录注册，进入网页。

1.  把 OPENAI\_API\_KEY 填入目录`src/config.ts`下的 `OPENAI_API_KEY` 中
    
2.  把 reverseProxyUrl 填入目录`src/config.ts`下的 `reverseProxyUrl` 中，如何设置可看下面介绍。
    

> 当然也可以选择白嫖山月老师的代理地址：`https://ai.devtool.tech/proxy/v1/chat/completions`，可以关注他的项目

1.  然后在终端运行以下命令。如有需要，请在`src/config.ts`中配置其它配置变量。

  // 安装依赖
  npm i
  npm run dev

  // 也可以使用pnpm
  npm i \-g pnpm
  pnpm i
  pnpm run dev

1.  执行完之后，可以看到终端控制台输出一下信息，扫码登录即可.
    
2.  登录成功，用另外一个微信往你扫码登录的微信发消息，你将会收到来自 ChatGPT 的回复。
    

设置反向代理地址
--------

ChatGPT API 代理https://hub.docker.com/r/mirrors2/chatgpt-api-proxy

chatgpt api 代理,已验证 OpenCat,AssisChat,AMA(问天),chathub

可配置好 OPENAI\_API\_KEY 分享代理地址给他人用.

快速开始

docker run -d -p 80:80 --name chatgpt-api-proxy mirrors2/chatgpt-api-proxy

# 可选 -e OPENAI\_API\_KEY={nide\_api\_key}

docker 跑起来之后你的代理地址就生效了：

官方的：`https://api.openai.com/v1/chat/completions`

你的： `你的域名/v1/chat/completions` 或者 `你的服务器ip和端口/v1/chat/completions`

QA
--

1.  微信无法取消登录问题 可以直接删除`WechatEveryDay.memory-card`文件，重新跑程序
    
2.  支持的 node 版本: Node.js >= 16.8
    
3.  因为 ChatGPT 的长度限制，如果回复消息不完整，可以对它说"请继续" 或者 "请继续写完"。
    

1.  Error: Failed to launch the browser process puppeteer refer to https://github.com/puppeteer/puppeteer/blob/main/docs/troubleshooting.md#chrome-headless-doesnt-launch-on-unix

# ubuntu
sudo apt-get install chromium-browser
sudo apt-get install  ca-certificates fonts-liberation libasound2 libatk-bridge2.0-0 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgbm1 libgcc1 libglib2.0-0 libgtk-3-0 libnspr4 libnss3 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 lsb-release wget xdg-utils

👏🏻 欢迎一起共建
-----------

欢迎贡献你的代码以及想法 🍵。
