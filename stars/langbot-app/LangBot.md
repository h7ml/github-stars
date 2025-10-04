---
project: LangBot
stars: 13658
description: 🤩 Easy-to-use global IM bot platform designed for LLM era / 简单易用的大模型即时通信机器人开发平台 ⚡️ Bots for QQ / QQ频道 / Discord / LINE / WeChat(微信, 企业微信)/ Telegram / 飞书 / 钉钉 / Slack 🧩 Integrated with ChatGPT(GPT), DeepSeek, Dify, n8n, Langflow, Claude, Google Gemini, xAI, PPIO, Ollama, 阿里云百炼, SiliconFlow, Qwen, Moonshot, SillyTraven, MCP etc. LLM & Agent & RAG
url: https://github.com/langbot-app/LangBot
---

English / 简体中文 / 繁體中文 / 日本語 / (PR for your language)

项目主页 ｜ 部署文档 ｜ 插件介绍 ｜ 提交插件

LangBot 是一个开源的大语言模型原生即时通信机器人开发平台，旨在提供开箱即用的 IM 机器人开发体验，具有 Agent、RAG、MCP 等多种 LLM 应用功能，适配全球主流即时通信平台，并提供丰富的 API 接口，支持自定义开发。

📦 开始使用
-------

#### Docker Compose 部署

git clone https://github.com/langbot-app/LangBot
cd LangBot/docker
docker compose up -d

访问 http://localhost:5300 即可开始使用。

详细文档Docker 部署。

#### 宝塔面板部署

已上架宝塔面板，若您已安装宝塔面板，可以根据文档使用。

#### Zeabur 云部署

社区贡献的 Zeabur 模板。

#### Railway 云部署

#### 手动部署

直接使用发行版运行，查看文档手动部署。

😎 保持更新
-------

点击仓库右上角 Star 和 Watch 按钮，获取最新动态。

✨ 特性
----

-   💬 大模型对话、Agent：支持多种大模型，适配群聊和私聊；具有多轮对话、工具调用、多模态、流式输出能力，自带 RAG（知识库）实现，并深度适配 Dify。
-   🤖 多平台支持：目前支持 QQ、QQ频道、企业微信、个人微信、飞书、Discord、Telegram 等平台。
-   🛠️ 高稳定性、功能完备：原生支持访问控制、限速、敏感词过滤等机制；配置简单，支持多种部署方式。支持多流水线配置，不同机器人用于不同应用场景。
-   🧩 插件扩展、活跃社区：支持事件驱动、组件扩展等插件机制；适配 Anthropic MCP 协议；目前已有数百个插件。
-   😻 Web 管理面板：支持通过浏览器管理 LangBot 实例，不再需要手动编写配置文件。

详细规格特性请访问文档。

或访问 demo 环境：https://demo.langbot.dev/

-   登录信息：邮箱：`demo@langbot.app` 密码：`langbot123456`
-   注意：仅展示 WebUI 效果，公开环境，请不要在其中填入您的任何敏感信息。

### 消息平台

平台

状态

备注

QQ 个人号

✅

QQ 个人号私聊、群聊

QQ 官方机器人

✅

QQ 官方机器人，支持频道、私聊、群聊

企业微信

✅

企微对外客服

✅

企微智能机器人

✅

个人微信

✅

微信公众号

✅

飞书

✅

钉钉

✅

Discord

✅

Telegram

✅

Slack

✅

LINE

✅

### 大模型能力

模型

状态

备注

OpenAI

✅

可接入任何 OpenAI 接口格式模型

DeepSeek

✅

Moonshot

✅

Anthropic

✅

xAI

✅

智谱AI

✅

胜算云

✅

全球大模型都可调用（友情推荐）

优云智算

✅

大模型和 GPU 资源平台

PPIO

✅

大模型和 GPU 资源平台

302.AI

✅

大模型聚合平台

Google Gemini

✅

Dify

✅

LLMOps 平台

Ollama

✅

本地大模型运行平台

LMStudio

✅

本地大模型运行平台

GiteeAI

✅

大模型接口聚合平台

SiliconFlow

✅

大模型聚合平台

小马算力

✅

大模型聚合平台

阿里云百炼

✅

大模型聚合平台, LLMOps 平台

火山方舟

✅

大模型聚合平台, LLMOps 平台

ModelScope

✅

大模型聚合平台

MCP

✅

支持通过 MCP 协议获取工具

百宝箱Tbox

✅

蚂蚁百宝箱智能体平台，每月免费10亿大模型Token

### TTS

平台/模型

备注

FishAudio

插件

海豚 AI

插件

AzureTTS

插件

### 文生图

平台/模型

备注

阿里云百炼

插件

😘 社区贡献
-------

感谢以下代码贡献者和社区里其他成员对 LangBot 的贡献：
