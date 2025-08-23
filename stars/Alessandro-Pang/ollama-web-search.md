---
project: ollama-web-search
stars: 25
description: LLM + SearXNG 搜索，实现 AI 联网回答, 支持多 LLM 接口
url: https://github.com/Alessandro-Pang/ollama-web-search
---

LLM Web Search
==============

**AI 辅助网络搜索与问答 - 智能、准确、高效**

📝 项目介绍
-------

LLM Web Search 是一个结合大语言模型与网络搜索功能的智能问答应用，通过整合 LLM 模型与 SearXNG 搜索 API，实现了高效、准确的网络信息检索与智能回答。项目采用现代化的蓝紫色主题设计，提供了简洁优雅的用户界面，支持 Markdown 渲染，适配深色/浅色模式。

> 原 Ollama Web Search 项目，但原项目仅支持 Ollama 及 Google 搜索，同时仅支持命令行调用且不支持多轮对话，所以该项目调整为 SearXNG 和多 AI API 的支持。该项目提供了一个基于大语言模型的网络信息检索与智能问答平台，通过整合 LLM（如 OpenAI、DeepSeek 等）和搜索引擎 API（SearXNG），实现高效准确的网络内容检索与智能回答。

✨ 特性
----

-   🔍 **智能搜索**：结合 SearXNG 搜索 API 获取最新网络信息
-   🧠 **LLM 支持**：支持多种大语言模型，如 OpenAI、DeepSeek、Ollama 等
-   🌐 **网页抓取**：智能抓取搜索结果页面内容，提供更全面的信息
-   💬 **优雅界面**：现代化的蓝紫色主题设计，支持深色/浅色模式
-   ✏️ **Markdown 支持**：回答内容支持 Markdown 格式，提供更好的阅读体验
-   🔄 **实时反馈**：输入框自动调整大小，提供打字动画和加载状态

🛠️ 技术栈
-------

-   **前端**：Next.js 14, TypeScript, React
-   **UI**：自定义 CSS 变量, Markdown-it
-   **AI**：AI SDK, Ollama API
-   **搜索**：SearXNG 搜索 API
-   **数据存储**：ChromaDB (向量数据库)

🚀 快速开始
-------

### 前置要求

1.  安装 Ollama： Ollama 部署本地大模型与使用
2.  安装 ChromaDB： ChromaDB 安装与使用参考文章
3.  安装 SearXNG： SearXNG 安装与使用参考文章

> 注：如果不是用本地 Ollama 模型，可以不安装 Ollama

### 安装与运行

1.  克隆项目

git clone https://github.com/Alessandro-Pang/ollama-web-search
cd ollama-web-search

1.  安装依赖

pnpm install
# 或
npm install
# 或
yarn install

1.  配置环境变量

创建 `.env.local` 文件并添加以下内容：

```
AI_PROVIDER_TYPE = "AI 类型，目前支持 ollama、deepseek、openai"
AI_PROVIDER_BASE_URL = "AI 供应商的 API URL"
AI_PROVIDER_API_KEY = "AI 供应商的 API Key"
AI_MODEL_NAME = "AI 模型名称"

CHROMADB_PATH = "ChromaDB 的地址"
SEARXNG_API_URL = "SearXNG API 地址"
```

1.  启动开发服务器

pnpm dev
# 或
npm run dev
# 或
yarn dev

1.  打开浏览器访问 http://localhost:3000

📷 界面预览
-------

> **注意：** 当前项目仍在开发中，界面中的内容并未完全实现，尽请谅解

📚 使用指南
-------

1.  在输入框中输入您的问题
2.  系统会自动搜索相关网页内容
3.  LLM 模型会分析搜索结果并生成回答
4.  回答将以 Markdown 格式呈现，支持代码块、列表等格式

🤝 贡献
-----

欢迎提交 Issues 和 Pull Requests 来帮助改进项目！

📄 许可证
------

MIT License

🙏 致谢
-----

-   Next.js - React 框架
-   Ollama - 本地大语言模型运行工具
-   ChromaDB - 开源向量数据库
-   SearXNG - 网络搜索引擎

* * *

© 2025 Alessandro-Pang
