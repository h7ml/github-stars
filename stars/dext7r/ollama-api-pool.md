---
project: ollama-api-pool
stars: 12
description: 🚀 Intelligent Ollama API proxy pool based on Cloudflare Workers - 基于 Cloudflare Workers 的智能 Ollama API 代理池，支持多账号轮询、自动故障转移、负载均衡和统一鉴权
url: https://github.com/dext7r/ollama-api-pool
---

Ollama API Pool
===============

基于 Cloudflare Workers 的智能 Ollama/OpenRouter API 代理池，支持多 Provider、多账号轮询、自动故障转移和统一鉴权。

English | 简体中文

**🚀 在线演示** | **📚 API 文档** | **📊 实时统计** | **💬 讨论区**

* * *

✨ 功能特性
------

### 🌐 多 Provider 支持

-   🦙 **Ollama** - 支持 Ollama 官方 API
-   🔀 **OpenRouter** - 支持 OpenRouter API，访问多种 LLM 模型
-   🔌 **统一接口** - 所有 Provider 使用相同的 OpenAI 兼容接口
-   🎯 **智能路由** - 根据路径自动识别 Provider（如 `/openrouter/v1/chat/completions`）
-   🎚️ **独立控制** v3.1.0 - 可单独启用/禁用每个 Provider，灵活配置服务范围

### 💡 核心功能

-   🔄 **API 轮询** - 自动轮换多个 API Key，均衡负载
-   🛡️ **故障转移** - 检测失效 Key 并自动切换
-   🤖 **智能管理** - 自动禁用连续失败的 Key，支持手动启用/禁用
-   📊 **使用统计** - 实时统计每个 Key 的请求、成功率、失败次数
-   🏥 **健康检查** - 批量验证 API Key 可用性
-   🔐 **统一鉴权** - 自定义客户端 Token，保护上游 API Key

### 📦 管理功能

-   🎯 **分类管理** - 导入时自动识别并分类 API Key（kimi/llama/qwen 等）
-   📥 **批量导入** - 支持从 ollama.txt 文件导入账号
-   🔍 **验证导入** - 逐行验证 API Key 有效性并自动分类
-   🎛️ **管理后台** - Web 界面管理 API Keys 和客户端 Tokens

### 👥 用户系统 v3.0.0

-   📧 **邮箱注册** - 用户可通过邮箱自助注册账户，获取专属 API 访问凭证
-   🔑 **双模式登录** - 支持验证码登录和密码登录两种方式
-   ✉️ **邮件验证** - 集成 push-all-in-one 邮件服务，发送精美 HTML 验证码邮件
-   🎯 **用户仪表盘** - 独立用户控制台，查看个人信息、API 密钥和使用统计
-   📅 **每日签到** - 用户每日签到可自动延长 API 凭证有效期（+24 小时）
-   📜 **签到历史** - 完整的签到记录查询，支持分页浏览
-   🛡️ **Turnstile 验证** - 集成 Cloudflare Turnstile 人机验证，防止滥用
-   👨‍💼 **用户管理** - 管理员可批量启用/禁用用户、延长凭证、重置密钥

### ⚡ 性能与存储

-   🚀 **高性能** - 基于 Cloudflare Workers，全球 CDN 加速
-   🗄️ **多层存储** - 支持 PostgreSQL + Redis + KV 混合架构
-   💾 **灵活配置** - 可选启用数据库与缓存承载大规模流量
-   📈 **可扩展** - 轻松承载十万级账号池或高频调用

🚀 快速开始
-------

### 前置要求

-   **Node.js**: >= 20.0.0
-   **pnpm**: >= 8.0.0 (推荐) 或 npm

安装 pnpm:

npm install -g pnpm

如果您的 Node.js 版本低于 20，可以使用 nvm 升级:

# 安装 nvm (如果还没安装)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# 安装 Node.js 20
nvm install 20
nvm use 20

### 1\. 安装依赖

pnpm install

### 2\. 登录 Cloudflare

pnpm wrangler login

### 3\. 配置项目

复制配置模板并修改:

cp wrangler.toml.example wrangler.toml

**创建 KV 命名空间**:

pnpm wrangler kv:namespace create "API\_KEYS"
pnpm wrangler kv:namespace create "ACCOUNTS"

将返回的 namespace ID 填入 `wrangler.toml`:

\[\[kv\_namespaces\]\]
binding = "API\_KEYS"
id = "your-api-keys-kv-id"  # 替换为实际 ID

\[\[kv\_namespaces\]\]
binding = "ACCOUNTS"
id = "your-accounts-kv-id"  # 替换为实际 ID

\[vars\]
# 管理员配置
ADMIN\_TOKEN = "your-secure-admin-token-here"  # 设置强密码

# Provider 控制 (v3.1.0+)
DISABLE\_OLLAMA = "false"         # 是否禁用 Ollama（默认启用）
DISABLE\_OPENROUTER = "false"     # 是否禁用 OpenRouter（默认启用）

# 用户系统配置 (v3.0.0+)
AUTH\_SECRET = "your-jwt-secret-key-here"  # JWT 签名密钥，建议使用 32 位以上随机字符串
ENABLE\_TURNSTILE = "true"  # 是否启用 Turnstile 人机验证
TURNSTILE\_SITE\_KEY = "your-turnstile-site-key"  # Cloudflare Turnstile Site Key
TURNSTILE\_SECRET\_KEY = "your-turnstile-secret-key"  # Cloudflare Turnstile Secret Key

# 邮件服务配置 (v3.0.0+)
EMAIL\_FORWARD\_URL = "your-push-all-in-one-url"  # push-all-in-one 邮件转发服务地址
EMAIL\_HOST = "smtp.example.com"  # SMTP 服务器地址
EMAIL\_PORT = "587"  # SMTP 端口
EMAIL\_AUTH\_USER = "your-email@example.com"  # SMTP 用户名
EMAIL\_AUTH\_PASS = "your-email-password"  # SMTP 密码
EMAIL\_SECURE = "true"  # 是否使用 TLS

> ⚠️ **重要**: `wrangler.toml` 包含敏感信息，已添加到 `.gitignore`，不会被提交到仓库
> 
> 📧 **邮件服务**: 推荐使用 push-all-in-one 作为邮件转发服务
> 
> 🛡️ **Turnstile**: 在 Cloudflare Dashboard 创建 Turnstile 站点获取密钥
> 
> 🎚️ **Provider 控制**: 详细说明请参考 PROVIDER\_TOGGLE.md

### 4\. 部署

pnpm deploy

部署成功后会显示访问地址，如: `https://ollama-api-pool.your-name.workers.dev`

🚀 GitHub Actions 自动部署
----------------------

本项目配置了 GitHub Actions 自动部署到 Cloudflare Workers。

### 配置步骤

1.  **在 GitHub 仓库设置中添加 Secrets** (Settings > Secrets and variables > Actions):
    
    必需的 Secrets:
    
    -   `CLOUDFLARE_API_TOKEN`: Cloudflare API Token
    -   `CLOUDFLARE_ACCOUNT_ID`: Cloudflare Account ID
    -   `ADMIN_TOKEN`: 管理后台密钥
    -   `API_KEYS_KV_ID`: API Keys KV 命名空间 ID
    -   `ACCOUNTS_KV_ID`: Accounts KV 命名空间 ID
2.  **获取 Cloudflare API Token**:
    
    -   访问 https://dash.cloudflare.com/profile/api-tokens
    -   点击 "Create Token"
    -   选择 "Edit Cloudflare Workers" 模板
    -   创建并复制 Token
3.  **获取 Account ID**:
    
    -   访问 https://dash.cloudflare.com/
    -   选择你的域名，右侧可以看到 Account ID
4.  **获取 KV 命名空间 ID**:
    
    pnpm wrangler kv:namespace list
    
5.  **推送代码到 main 分支**即可自动部署,部署成功后会在 Actions 日志中显示访问地址
    

### 手动触发部署

在 GitHub Actions 页面，选择 "Deploy to Cloudflare Workers" 工作流，点击 "Run workflow"。

📊 架构
-----

graph TB
    Client\[客户端应用\]
    CF\[Cloudflare Workers<br/>全球 CDN 边缘节点\]
    Auth\[鉴权模块\]
    Pool\[API 池管理器\]
    Cache\[缓存层\]
    Storage\[存储层\]

    Ollama\[Ollama API\]
    OpenRouter\[OpenRouter API\]

    Redis\[(Redis<br/>缓存)\]
    PG\[(PostgreSQL<br/>Supabase)\]
    KV\[(Cloudflare KV)\]

    Client -->|HTTPS Request| CF
    CF --> Auth
    Auth -->|验证 Token| Pool
    Pool --> Cache
    Cache --> Storage

    Pool -->|轮询分发| Ollama
    Pool -->|轮询分发| OpenRouter

    Storage --> Redis
    Storage --> PG
    Storage --> KV

    style CF fill:#f96,stroke:#333,stroke-width:2px
    style Pool fill:#6c6,stroke:#333,stroke-width:2px
    style Storage fill:#69f,stroke:#333,stroke-width:2px

Loading

📖 使用说明
-------

### 管理后台

访问部署后的 URL (如 `https://ollama-api-pool.your-name.workers.dev`)，输入管理员 Token 进入后台。

**📥 导入 API Keys**

#### 方式一: 单个添加

在 "API Keys" 标签页输入 Ollama API Key 点击添加。

#### 方式二: 批量导入

1.  切换到 "批量导入" 标签
2.  粘贴 `ollama.txt` 文件内容
3.  点击导入

格式示例:

```
test@example.com----password123----session_token----ollama-abc123...
user@test.com----pass456----session_data----ollama-def456...
```
**🔑 创建客户端 Token**

1.  切换到 "客户端 Tokens" 标签
2.  输入 Token 名称
3.  点击创建
4.  复制生成的 Token 提供给客户端使用

**📊 查看 Key 使用统计**

1.  切换到 "统计分析" 标签
2.  查看每个 Key 的详细统计：
    -   总请求数、成功/失败次数
    -   成功率百分比
    -   最后使用时间
    -   当前状态（active/disabled）
3.  可手动启用/禁用 Key
4.  运行批量健康检查

### API 调用

使用客户端 Token 调用 API:

curl https://ollama-api-pool.your-name.workers.dev/v1/chat/completions \\
  -H "Content-Type: application/json" \\
  -H "Authorization: Bearer sk-xxxxxxxxxxxxxx" \\
  -d '{
    "model": "llama3.2:1b",
    "messages": \[{"role": "user", "content": "Hello"}\],
    "stream": false
  }'

### API 端点

#### Ollama API

端点

方法

说明

`/v1/chat/completions`

POST

Ollama Chat Completions (OpenAI 兼容)

`/v1/models`

GET

获取 Ollama 模型列表

#### OpenRouter API

端点

方法

说明

`/openrouter/v1/chat/completions`

POST

OpenRouter Chat Completions (OpenAI 兼容)

`/openrouter/v1/models`

GET

获取 OpenRouter 模型列表

#### 管理 API

端点

方法

说明

`/`

GET

管理后台首页

`/health`

GET

健康检查

`/stats`

GET

公开统计页面

`/api-docs`

GET

API 使用文档

`/admin/public-stats`

GET

公开统计数据 API

`/admin/api-keys`

GET/POST/DELETE

管理 API Keys

`/admin/api-keys/import`

POST

批量导入 API Keys

`/admin/api-keys/import-from-txt`

POST

从 ollama.txt 格式导入

`/admin/api-keys/import-with-validation`

POST

验证导入 API Keys (逐行验证)

`/admin/keys/stats`

GET

获取 Key 使用统计

`/admin/keys/enable`

POST

手动启用 API Key

`/admin/keys/disable`

POST

手动禁用 API Key

`/admin/keys/health-check`

POST

批量健康检查

`/admin/tokens`

GET/POST/DELETE

管理客户端 Tokens

`/admin/stats`

GET

获取统计概览

`/admin/cache/stats`

GET

获取缓存统计

`/admin/cache/clear`

POST

清除缓存

> 💡 **提示**：管理 API 支持通过 `?provider=openrouter` 参数指定 Provider

🛠️ 配置选项
--------

**📝 wrangler.toml 配置详解**

name = "ollama-api-pool"
main = "src/index.js"
compatibility\_date = "2025-01-01"

\[\[kv\_namespaces\]\]
binding = "API\_KEYS"
id = "your-kv-namespace-id"

\[\[kv\_namespaces\]\]
binding = "ACCOUNTS"
id = "your-accounts-kv-id"

\[vars\]
# 管理后台密钥（必须修改）
ADMIN\_TOKEN = "your-admin-secret-token"

# Provider 控制 (v3.1.0+)
DISABLE\_OLLAMA = "false"         # 是否禁用 Ollama（默认启用）
DISABLE\_OPENROUTER = "false"     # 是否禁用 OpenRouter（默认启用）

# 功能开关
ENABLE\_ANALYTICS = "true"        # 启用统计分析
ENABLE\_RATE\_LIMIT = "true"       # 启用 IP 速率限制
ENABLE\_BOT\_DETECTION = "true"    # 启用 Bot 检测
DISABLE\_KV\_STORAGE = "true"      # 禁用 KV 写入，使用 Redis/Postgres

# 速率限制配置
RATE\_LIMIT\_REQUESTS = "60"       # 每个 IP 每分钟最大请求数
RATE\_LIMIT\_WINDOW = "60"         # 时间窗口（秒）

# 统计采样率（降低 KV 写入压力）
STATS\_SAMPLE\_RATE = "0.1"        # 全局统计采样率（0.1 = 10%）
MODEL\_STATS\_SAMPLE\_RATE = "0.2"  # 模型统计采样率（0.2 = 20%）

# 外部存储（可选但强烈推荐）
REDIS\_URL = "rediss://default:\*\*\*@your-redis.upstash.io:6379"
DATABASE\_URL = "postgresql://postgres.\*\*\*:\*\*\*@aws-1-ap-south-1.pooler.supabase.com:6543/postgres?pgbouncer=true"
SUPABASE\_REST\_URL = "https://your-project.supabase.co/rest/v1"
SUPABASE\_SERVICE\_ROLE\_KEY = "eyJhbGciOi..."

> ✅ **推荐配置**: PostgreSQL（Supabase）+ Redis（Upstash）+ Cloudflare KV

**🗄️ PostgreSQL（Supabase）数据库集成**

### 创建数据库表

1.  在 Supabase 项目中执行以下 SQL：

\-- API Keys 主表
create table if not exists ollama\_api\_keys (
  api\_key text primary key,
  username text,
  status text default 'active',
  created\_at timestamptz default now(),
  expires\_at timestamptz,
  failed\_until timestamptz,
  disabled\_until timestamptz,
  consecutive\_failures integer default 0
);

\-- API Keys 统计表
create table if not exists ollama\_api\_key\_stats (
  api\_key text primary key references ollama\_api\_keys(api\_key) on delete cascade,
  total\_requests bigint default 0,
  success\_count bigint default 0,
  failure\_count bigint default 0,
  success\_rate numeric default 0,
  last\_used timestamptz,
  last\_success timestamptz,
  last\_failure timestamptz,
  consecutive\_failures integer default 0,
  created\_at timestamptz default now()
);

\-- 客户端 Tokens 表
create table if not exists ollama\_api\_client\_tokens (
  token text primary key,
  name text,
  created\_at timestamptz default now(),
  expires\_at timestamptz,
  request\_count bigint default 0
);

\-- 全局统计表
create table if not exists ollama\_api\_global\_stats (
  id text primary key default 'global',
  total\_requests bigint default 0,
  success\_count bigint default 0,
  failure\_count bigint default 0,
  updated\_at timestamptz default now()
);

\-- 模型统计表（支持多 Provider）
create table if not exists ollama\_api\_model\_stats (
  id serial primary key,
  provider text default 'ollama',
  model text not null,
  total\_requests bigint default 0,
  success\_count bigint default 0,
  failure\_count bigint default 0,
  last\_used timestamptz,
  created\_at timestamptz default now(),
  unique(provider, model)
);

\-- 小时级模型统计（用于趋势图表）
create table if not exists ollama\_api\_model\_hourly (
  id serial primary key,
  provider text default 'ollama',
  model text not null,
  hour timestamptz not null,
  requests bigint default 0,
  success bigint default 0,
  failure bigint default 0,
  created\_at timestamptz default now(),
  unique(provider, model, hour)
);

1.  在 Supabase 项目设置中获取：
    
    -   **Service Role Key** → `SUPABASE_SERVICE_ROLE_KEY`
    -   **REST URL** → `SUPABASE_REST_URL`
    -   **Connection String** → `DATABASE_URL`
2.  将配置添加到 `wrangler.toml` 或 GitHub Secrets
    

### OpenRouter 表结构

如需支持 OpenRouter，添加前缀为 `openrouter_api_` 的表：

\-- OpenRouter API Keys 表
create table if not exists openrouter\_api\_keys (
  api\_key text primary key,
  username text,
  status text default 'active',
  created\_at timestamptz default now(),
  expires\_at timestamptz,
  failed\_until timestamptz,
  disabled\_until timestamptz,
  consecutive\_failures integer default 0
);

\-- 其他表类似命名...

📚 文档
-----

-   **配置指南** - 详细的环境变量配置说明
-   **Provider 开关** - Ollama/OpenRouter 启用禁用指南 v3.1.0
-   **API 参数说明** - 透传参数与防封禁机制 v3.1.0
-   **优化措施** - KV 优化和性能调优
-   **贡献指南** - 如何参与项目开发
-   **API 文档** - 在线 API 文档
-   **实时统计** - 公开统计图表

* * *

📊 工作原理
-------

### 请求流程

sequenceDiagram
    participant C as 客户端
    participant W as Workers
    participant A as 鉴权模块
    participant P as API 池
    participant O as Ollama API
    participant R as OpenRouter API

    C->>W: HTTPS 请求
    W->>A: 验证 Client Token
    A-->>W: Token 有效
    W->>P: 获取可用 API Key
    P->>P: Round-robin 轮询

    alt Ollama 请求
        P->>O: 使用 API Key 转发
        O-->>P: 响应
    else OpenRouter 请求
        P->>R: 使用 API Key 转发
        R-->>P: 响应
    end

    alt 请求成功
        P->>P: 记录成功统计
        P-->>W: 返回结果
    else 请求失败
        P->>P: 标记失败 + 重试
        P->>P: 连续失败 3 次自动禁用
    end

    W-->>C: 返回响应

Loading

**⚙️ Key 轮询策略**

-   **轮询算法**: Round-robin 轮询
-   **失败标记**: API Key 失效后标记 1 小时
-   **自动恢复**: 1 小时后自动重新尝试
-   **最大重试**: 单次请求最多重试 3 次

**🤖 智能管理机制**

-   **自动禁用**: 连续失败 3 次自动禁用 1 小时
-   **手动控制**: 支持手动启用/禁用任意 Key，可自定义禁用时长
-   **健康检查**: 批量验证所有 Key 可用性，自动更新状态
-   **统计分析**: 实时追踪每个 Key 的：
    -   总请求数、成功/失败次数
    -   成功率百分比
    -   最后使用时间
    -   连续失败次数
    -   禁用原因（自动/手动）

🔒 安全建议
-------

**🛡️ 安全最佳实践**

1.  **保护管理员 Token**: 使用强随机密码
2.  **限制客户端 Token**: 为不同用户创建独立 Token
3.  **定期轮换**: 定期更新 API Keys 和 Tokens
4.  **监控日志**: 定期检查统计信息
5.  **访问控制**: 限制管理后台访问 IP

📝 开发
-----

**🔧 开发命令**

### 本地测试

pnpm dev

### 查看日志

pnpm wrangler tail

### 更新部署

pnpm deploy

🐛 故障排除
-------

**❓ 常见问题与解决方案**

### API Key 频繁失效

检查上游 Ollama API Key 是否有效:

curl https://ollama.com/v1/chat/completions \\
  -H "Authorization: Bearer ollama-xxx..." \\
  -H "Content-Type: application/json" \\
  -d '{"model":"llama3.2:1b","messages":\[{"role":"user","content":"test"}\]}'

### 客户端无法连接

-   检查客户端 Token 是否有效
-   查看 Worker 日志: `pnpm wrangler tail`
-   验证 CORS 配置

### 导入失败

确保 ollama.txt 格式正确:

```
email----password----session----api_key
```

📦 项目结构
-------

**📁 目录结构**

```
ollama-api-pool/
├── .github/
│   └── workflows/
│       ├── api-test.yml       # API 自动化测试工作流
│       └── deploy.yml         # 自动部署工作流
├── scripts/
│   ├── api-test.js            # API 测试脚本
│   └── README.md              # 测试脚本说明
├── src/
│   ├── html/
│   │   ├── login.js           # 登录页面
│   │   └── main-dashboard.js  # 主控制台页面
│   ├── static/
│   │   ├── api-docs-html.js   # API 文档 HTML
│   │   ├── dashboard-js.js    # 控制台 JS
│   │   ├── login-js.js        # 登录 JS
│   │   └── stats-html.js      # 统计页面 HTML
│   ├── admin.js               # 管理 API
│   ├── auth.js                # 鉴权模块
│   ├── buildInfo.js           # 构建信息
│   ├── cache.js               # 缓存模块
│   ├── dashboard.js           # 管理后台
│   ├── index.js               # 主入口
│   ├── keyManager.js          # Key 管理
│   ├── postgres.js            # PostgreSQL 集成
│   ├── providers.js           # Provider 配置
│   ├── proxy.js               # API 代理
│   ├── redis.js               # Redis 集成
│   └── utils.js               # 工具函数
├── .gitignore                 # Git 忽略文件
├── CONFIGURATION.md           # 配置指南
├── CONTRIBUTING.md            # 贡献指南
├── LICENSE                    # MIT 许可证
├── OPTIMIZATION.md            # 优化措施
├── package.json               # 依赖配置
├── PROJECT_SUMMARY.md         # 项目概要
├── README.md                  # 中文文档
├── README_EN.md               # 英文文档
├── wrangler.toml.example      # Cloudflare 配置模板
└── wrangler.toml              # Cloudflare 配置（本地）
```

🤝 贡献
-----

欢迎提交 Issue 和 Pull Request!

请查看 贡献指南 了解详细信息。

📄 许可证
------

MIT License - 详见 LICENSE 文件

⭐ Star History
--------------

🔗 相关链接
-------

-   Cloudflare Workers 文档
-   Ollama 官网
-   OpenAI API 文档

* * *

🌐 在线资源
-------

-   🚀 **在线演示**: https://ollama-api-pool.h7ml.workers.dev
-   📚 **API 文档**: https://ollama-api-pool.h7ml.workers.dev/api-docs
-   💬 **问题反馈**: https://github.com/dext7r/ollama-api-pool/issues
-   📖 **贡献指南**: https://github.com/dext7r/ollama-api-pool/blob/main/CONTRIBUTING.md

如果这个项目对您有帮助，请给个 ⭐ Star 支持一下！
