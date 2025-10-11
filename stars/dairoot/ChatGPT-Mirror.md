---
project: ChatGPT-Mirror
stars: 1256
description: 🚀 一键部署个人的 ChatGPT 镜像站
url: https://github.com/dairoot/ChatGPT-Mirror
---

ChatGPT Mirror
==============

ChatGPT Mirror 后台是一个 ChatGPT 镜像站，允许多账号共享管理。实现多人同时使用 ChatGPT 服务。

特点
--

-   提供与官网同等的极致体验。
-   提供 ChatGPT 聊天接口 转 API `/v1/chat/completions`
-   用户无需翻墙，便可轻松访问并使用 ChatGPT 官方网站的所有功能。
-   通过在 `Mirror` 后台录入 `ChatGPT Token`，让团队成员每人拥有独立账号 (或共享同一个`ChatGPT Plus`账号)。
-   提供便捷的管理后台，帮助管理员高效管理账号。

在线体验
----

https://chatgpt.dairoot.cn

部署
--

为了获得最佳体验，请先观看以下视频教程

tutorials.mov

打开命令行终端，执行以下命令

# 切换到 home 目录，并克隆 ChatGPT-Mirror 仓库
cd /home/ && git clone https://github.com/dairoot/ChatGPT-Mirror.git

cd ChatGPT-Mirror/

# 修改管理后台账号密码
cp .env.example .env && vi .env

# 启动
./deploy.sh

访问 http://127.0.0.1:50002 或访问 http://外网ip:50002

配置域名，请点击查看完整部署流程

环境变量
----

分类

变量名

类型

默认值

描述

镜像后台

`ADMIN_USERNAME`

`String`

`None`

管理后台账号

`ADMIN_PASSWORD`

`String`

`None`

管理后台密码

`ALLOW_REGISTER`

`Boolean`

`true`

是否允许注册

`WEB_HATD`

`Boolean`

`false`

WEB 开启临时聊天（不保存聊天记录）

API 相关

`ENABLE_MIRROR_API`

`Boolean`

`true`

是否开启 API 访问

`MIRROR_API_PREFIX`

`String`

`None`

API 访问前缀，建议配置

`API_HATD`

`Boolean`

`false`

API 开启临时聊天（不保存聊天记录）

系统变量

`PROXY_URL_POOL`

`String`

`None`

代理池链接，多个代理用逗号分隔  
`http://username:password@ip:port,`  
`socks5://username:password@ip:port,`  
`socks5h://username:password@ip:port`

`VOICE_PROXY_URL`

`String`

`None`

语音代理地址 点击自建  
若不配置，则用户需要翻墙才能使用语音功能

聊天 API 接口
=========

可搭配 ChatGPT-Next-Web、Lobe-Chat 使用

```
accessToken 获取地址：https://chatgpt.com/api/auth/session

API 地址为：https://你的地址
```

聊天接口请求示例：

export accessToken=XXXXX  # 获取地址：https://chatgpt.com/api/auth/session
export yourUrl=http://127.0.0.1:50002


curl --location "${yourUrl}/v1/chat/completions" \\
--header 'Content-Type: application/json' \\
--header "Authorization: Bearer ${accessToken}" \\
--data '{
     "model": "gpt-4o-mini",
     "messages": \[{"role": "user", "content": "你好呀!"}\],
     "stream": true,
     "conversation\_id": null,
     "parent\_message\_id": null,
     "hatd": false
   }'

更多 API 请点击查看：高阶玩法

FQA
---

简体中文 > 常见问题

捐赠
--

Buy Me a Coffee

Star History
------------
