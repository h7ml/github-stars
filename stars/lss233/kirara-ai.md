---
project: kirara-ai
stars: 16609
description: 🤖 可 DIY 的 多模态 AI 聊天机器人 | 🚀 快速接入 微信、 QQ、Telegram、等聊天平台 | 🦈支持DeepSeek、Grok、Claude、Ollama、Gemini、OpenAI | 工作流系统、网页搜索、AI画图、人设调教、虚拟女仆、语音对话 | 
url: https://github.com/lss233/kirara-ai
---

Kirara AI
---------

一款支持主流大语言模型、主流聊天平台的聊天的机器人！  
  
**» 查看项目手册 »**  

* * *

* * *

🌟 社区交流
-------

加入我们的社区，获取最新项目动态、视频教程、问题答疑和技术交流！

-   QQ 交流群:
    -   二群（已满）
    -   三群（已满）
    -   四群（已满）
    -   五群
    -   六群

> **提问前请先查看**: 加入群组前，请先查看项目问题列表，看是否能解决你的问题。
> 
> 如需提问，请准备好问题描述、**完整日志**和相关配置文件，以便我们更好地帮助你。  
> 进群请备注：GitHub

-   机器人调试群 - 这里有多个 QQ 机器人供体验，不解答技术问题。
-   开发者交流群 - 欢迎参与 Kirara AI 及生态开发 / 对大模型应用有兴趣的开发者加入，一起交流学习。

📷 功能展示
-------

🧭 WebUI
--------

### 模型管理

### 工作流

### 插件市场

⚡ 核心特性
------

-   图片发送
-   关键词触发回复
-   多账号支持
-   人格设定
-   支持 QQ、Telegram、Discord、微信
-   可作为 HTTP 服务端提供 Web API
-   支持 OpenAI、DeepSeek、Claude、Gemini、Qwen、Mistral、豆包、Minimax、Kimi、Mistral 等主流大模型
-   支持插件机制
-   支持条件触发
-   支持管理员指令
-   支持 Stable Diffusion、Flux、Midjourney 等绘图模型
-   支持语音回复
-   支持多轮对话
-   支持跨平台消息发送
-   支持自定义工作流
-   支持 Web 管理后台
-   内置 Frpc 内网穿透

**🤖 聊天平台**
===========

我们支持多种聊天平台。

平台

群聊回复

私聊回复

条件触发

管理员指令

绘图

语音回复

Telegram

支持

支持

支持

支持

支持

支持

QQ 机器人

支持

支持

支持

支持

支持

平台不支持

Discord

重构中

重构中

重构中

重构中

重构中

重构中

飞书机器人

重构中

重构中

重构中

重构中

重构中

重构中

企业微信应用

支持

支持

支持

不支持

支持

支持

微信公众号

支持

支持

支持

不支持

支持

支持

OneBot

插件支持

插件支持

插件支持

插件支持

插件支持

插件支持

🐎 命令
-----

**你可以在 WebUI 的调度规则中自定义所有命令。**

🔧 搭建
-----

请移步至 快速开始

🕸 HTTP API
-----------

HTTP API 可用于接入其他平台。 在聊天平台管理中启动 http-legacy 适配器后，将提供以下接口：

**POST** `/v1/chat`

**请求参数**

参数名

必选

类型

说明

session\_id

是

String

会话ID，默认：`friend-default_session`

username

是

String

用户名，默认：`某人`

message

是

String

消息，不能为空

**请求示例**

{
    "session\_id": "friend-123456",
    "username": "testuser",
    "message": "ping"
}

**响应格式**

参数名

类型

说明

result

String

SUCESS,DONE,FAILED

message

String\[\]

文本返回，支持多段返回

voice

String\[\]

音频返回，支持多个音频的base64编码；参考：data:audio/mpeg;base64,...

image

String\[\]

图片返回，支持多个图片的base64编码；参考：data:image/png;base64,...

**响应示例**

{
    "result": "DONE",
    "message": \["pong!"\],
    "voice": \[\],
    "image": \[\]
}

**POST** `/v2/chat`

**请求参数**

参数名

必选

类型

说明

session\_id

是

String

会话ID，默认：`friend-default_session`

username

是

String

用户名，默认：`某人`

message

是

String

消息，不能为空

**请求示例**

{
    "session\_id": "friend-123456",
    "username": "testuser",
    "message": "ping"
}

**响应格式** 字符串：request\_id

**响应示例**

```
1681525479905
```

**GET** `/v2/chat/response`

**请求参数**

参数名

必选

类型

说明

request\_id

是

String

请求id，/v2/chat返回的值

**请求示例**

```
/v2/chat/response?request_id=1681525479905
```

**响应格式**

参数名

类型

说明

result

String

SUCESS,DONE,FAILED

message

String\[\]

文本返回，支持多段返回

voice

String\[\]

音频返回，支持多个音频的base64编码；参考：data:audio/mpeg;base64,...

image

String\[\]

图片返回，支持多个图片的base64编码；参考：data:image/png;base64,...

-   每次请求返回增量并清空。DONE、FAILED之后没有更多返回。

**响应示例**

{
    "result": "DONE",
    "message": \["pong!"\],
    "voice": \["data:audio/mpeg;base64,..."\],
    "image": \["data:image/png;base64,...", "data:image/png;base64,..."\]
}

🦊 加载预设
-------

如果你想让机器人自动带上某种聊天风格，可以使用预设功能。

我们自带了 `猫娘` 和 `正常` 两种预设，你可以在 `presets` 文件夹下了解预设的写法。

使用 `加载预设 猫娘` 来加载猫娘预设。

下面是一些预设的小视频，你可以看看效果：

-   MOSS： https://www.bilibili.com/video/av352047018
-   丁真：https://www.bilibili.com/video/av267013053
-   小黑子：https://www.bilibili.com/video/av309604568
-   高启强：https://www.bilibili.com/video/av779555493

关于预设系统的详细教程：Wiki

你可以在 Awesome ChatGPT QQ Presets 获取由大家分享的预设。

你也可以参考 Awesome-ChatGPT-prompts-ZH\_CN 来调教你的 ChatGPT，还可以参考 Awesome ChatGPT Prompts 来解锁更多技能。

🎙 文字转语音
--------

自 v2.2.5 开始，我们支持接入微软的 Azure 引擎 和 VITS 引擎，让你的机器人发送语音。

**提示**：在 Windows 平台上使用语音功能需要安装最新的 VC 运行库，你可以在这里下载。\`

🛠 贡献者名单
--------

欢迎提出新的点子、 Pull Request。

Made with contrib.rocks.

📕 相关项目
-------

-   Kirara Registry - Kirara AI 插件市场
-   Kirara WebUI - Kirara AI 的 WebUI 前端项目
-   Kirara Docs - Kirara AI 的使用手册原始文档

💪 支持我们
-------

如果我们这个项目对你有所帮助，请给我们一颗 ⭐️
