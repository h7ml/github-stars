---
project: law-cn-ai
stars: 4903
description: ⚖️ AI 法律助手
url: https://github.com/lvwzhen/law-cn-ai
---

AI 法律助手
=======

法律文件来源：https://github.com/LawRefBook/Laws

项目模板：https://github.com/supabase-community/nextjs-openai-doc-search

这个项目从 `pages` 目录中获取所有的 `.mdx` 文件，并将其处理成自定义上下文，以在OpenAI 文本自动补全提示中使用。

更多好玩
----

智能写作助手

AI 百科全书

Prompt 生成器

AI 翻译专家

❤️ 打赏赞助 ❤️

部署
--

部署此 starter 到 Vercel。Supabase 集成将自动设置所需的环境变量并配置您的数据库概要。您只需要设置 `OPENAI_KEY`，然后就可以开始了！

楼主太懒了，感谢 GoJun 帮忙写了教程：https://eibot3u32o.feishu.cn/docx/L46Pdp3fjouPUvxaNzPckKctno3

技术细节
----

构建您自己的自定义 ChatGPT 涉及四个步骤：

1.  \[👷 构建时间\] 预处理知识库（您的 `pages` 文件夹中的 `.mdx` 文件）。
2.  \[👷 构建时间\] 在 PostgreSQL 中使用 pgvector 存储嵌入向量。
3.  \[🏃 运行时\] 执行向量相似性搜索，查找与问题相关的内容。
4.  \[🏃 运行时\] 将内容注入到 OpenAI GPT-3 文本自动补全中，并将响应流式传输到客户端。

👷 构建时间
-------

步骤 1 和 2 发生在构建时间，例如当 Vercel 构建您的 Next.js 应用程序时。此时执行 `generate-embeddings` 脚本，该脚本执行以下任务：

sequenceDiagram
    participant Vercel
    participant DB (pgvector)
    participant OpenAI (API)
    loop 1. 预处理知识库
        Vercel->>Vercel: 将 .mdx 页面划分为部分
        loop 2. 创建并存储嵌入
            Vercel->>OpenAI (API): 为页面部分创建嵌入
            OpenAI (API)->>Vercel: 嵌入向量(1536)
            Vercel->>DB (pgvector): 存储页面部分的嵌入
        end
    end

Loading

除了存储嵌入向量之外，此脚本还为每个 `.mdx` 文件生成一个校验和，并将其存储在另一个数据库表中，以确保仅当文件更改时才重新生成嵌入向量。

🏃 运行时
------

步骤 3 和 4 在运行时发生，即用户提交问题时。发生这种情况时，执行以下一系列任务：

sequenceDiagram
    participant Client
    participant Edge Function
    participant DB (pgvector)
    participant OpenAI (API)
    Client->>Edge Function: { query: lorem ispum }
    critical 3. 执行向量相似性搜索
        Edge Function->>OpenAI (API): 为查询创建嵌入
        OpenAI (API)->>Edge Function: 嵌入向量(1536)
        Edge Function->>DB (pgvector): 向量相似性搜索
        DB (pgvector)->>Edge Function: 相关文档内容
    end
    critical 4. 将内容注入到提示中
        Edge Function->>OpenAI (API): 完成请求提示：查询+相关文档内容
        OpenAI (API)-->>Client: text/event-stream：自动补全响应
    end

Loading

此为 `SearchDialog（客户端）`组件和`vector-search（边缘函数）`负责的相关文件。

数据库的初始化，包括 `pgvector` 扩展的设置存储在 `supabase/migrations`文件夹中，并在运行 `supabase start` 时自动应用于本地 PostgreSQL 实例。

本地开发
----

### 配置

-   `cp .env.example .env`
-   在新创建的 `.env` 文件中设置 `OPENAI_KEY`。

### 启动 Supabase

确保已安装并在本地运行 Docker。然后运行

npx supabase start

### 启动 Next.js 应用程序

在新的终端窗口中运行

pnpm dev

部署
--

仅需将此 starter 部署到 Vercel。Supabase 集成将自动设置所需的环境变量并配置您的数据库 Schema。您只需设置 `OPENAI_KEY` 并开始使用即可！

了解更多
----

-   阅读我们如何建立Supabase 文档的 ChatGPT的博客帖子。
-   \[Docs\] pgvector：嵌入和向量相似性函数。
-   观看Greg 关于Rabbit Hole Syndrome YouTube Channel的 "How I built this" video:

```
此文件由 ChatGPT 提供翻译
```

Star History
------------
