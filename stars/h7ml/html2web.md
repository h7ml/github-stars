---
project: html2web
stars: 11
description: HTML2WEB - 粘贴代码，分享创意！一个支持 HTML 和 Markdown 在线编辑、预览和分享的现代化平台
url: https://github.com/h7ml/html2web
---

HTML2WEB - 粘贴代码，分享创意！
=====================

**一个支持 HTML 和 Markdown 在线编辑、预览和分享的现代化平台**

在线演示 · 报告问题 · 功能建议

* * *

✨ 核心特性
------

-   🎨 **Monaco Editor** - 专业的代码编辑器，支持语法高亮和智能提示
-   📝 **双模式支持** - HTML 和 Markdown 两种编辑模式自由切换
-   👁️ **实时预览** - 所见即所得的编辑体验
-   🔗 **一键分享** - 生成永久分享链接，轻松分享你的创意
-   🔐 **管理系统** - 完善的后台管理，支持文件增删改查
-   🌓 **主题切换** - 支持亮色/暗色主题
-   📱 **响应式设计** - 完美适配各种设备屏幕
-   ⚡ **实时通信** - Socket.IO 支持，未来可扩展协作功能
-   🗄️ **数据持久化** - Prisma + SQLite 数据库存储

🚀 快速开始
-------

### 前置要求

-   Node.js 18+
-   npm/pnpm

### 安装步骤

# 克隆项目
git clone git@github.com:h7ml/html2web.git
cd html2web

# 安装依赖
npm install

# 配置环境变量（可选，使用默认配置即可）
cp .env.example .env

# 初始化数据库和管理员账号
npm run db:setup

# 启动开发服务器
npm run dev

打开浏览器访问 http://localhost:3000

### 默认管理员账号

-   **用户名**: `admin`
-   **密码**: `123456`
-   **登录地址**: http://localhost:3000/admin/login

📦 技术栈
------

本项目由以下现代化技术驱动：

### 核心框架

-   **Next.js 15.3.5** - React 服务端渲染框架，使用 App Router 架构
-   **React 19** - 现代化的用户界面构建库
-   **TypeScript 5** - 类型安全的 JavaScript 超集
-   **Tailwind CSS 4** - 实用优先的原子化 CSS 框架

### UI 组件库

-   **shadcn/ui** - 高质量、可定制的 React 组件集合（基于 Radix UI）
-   **@monaco-editor/react** - VS Code 同款代码编辑器，支持语法高亮和智能提示
-   **Lucide React** - 简洁美观的开源图标库（600+ 图标）
-   **Framer Motion** - 流畅的动画和手势库
-   **Sonner** - 优雅的 Toast 通知组件

### 数据库与 ORM

-   **Prisma 6.16.3** - 类型安全的现代化 ORM
-   **SQLite** - 轻量级嵌入式数据库（支持切换到 PostgreSQL/MySQL）

### 实时通信

-   **Socket.IO 4.8.1** - 可靠的实时双向事件通信库（支持 WebSocket、长轮询等传输方式）

### 表单与验证

-   **React Hook Form** - 高性能、灵活的表单处理库
-   **Zod** - TypeScript 优先的 Schema 验证库
-   **@hookform/resolvers** - 表单验证解析器集合

### Markdown 处理

-   **remark** - Markdown 处理器核心
-   **remark-gfm** - GitHub Flavored Markdown 支持
-   **remark-rehype** - Markdown 到 HTML 转换
-   **rehype-highlight** - 代码语法高亮（基于 highlight.js）
-   **rehype-raw** - 解析 Markdown 中的原始 HTML

### 认证与安全

-   **jsonwebtoken** - JWT 生成与验证
-   **bcryptjs** - 密码加密库

### 工具库

-   **Axios** - 基于 Promise 的 HTTP 客户端
-   **date-fns** - 现代化的日期工具库
-   **clsx** + **tailwind-merge** - 条件化 className 合并
-   **uuid** - 唯一标识符生成

### 开发工具

-   **ESLint 9** - JavaScript/TypeScript 代码检查
-   **Nodemon** - 开发环境自动重启
-   **tsx** - TypeScript 脚本执行器

### 部署平台

-   **Vercel** - Next.js 官方推荐的无服务器部署平台（本项目已部署）

* * *

📁 项目结构
-------

```
html2web/
├── prisma/
│   └── schema.prisma          # 数据库模型定义
├── scripts/
│   └── init-admin.ts          # 管理员初始化脚本
├── src/
│   ├── app/
│   │   ├── admin/            # 管理后台页面
│   │   ├── api/              # API 路由
│   │   │   ├── admin/        # 管理员认证
│   │   │   ├── files/        # 文件管理
│   │   │   ├── markdown/     # Markdown 处理
│   │   │   └── share/        # 分享功能
│   │   ├── preview/          # 预览页面
│   │   └── page.tsx          # 主页
│   ├── components/
│   │   ├── ui/               # shadcn/ui 组件
│   │   └── MonacoEditor.tsx  # Monaco 编辑器封装
│   └── lib/
│       ├── db.ts             # Prisma 客户端
│       ├── socket.js         # Socket.IO 配置
│       └── utils.ts          # 工具函数
├── server.js                 # 自定义服务器（集成 Socket.IO）
├── .env                      # 环境变量配置
└── package.json              # 依赖配置
```

🎯 主要功能
-------

### 1\. 代码编辑

-   Monaco Editor 提供专业的编辑体验
-   支持语法高亮、代码补全、快捷键等
-   HTML 和 Markdown 双模式

### 2\. 实时预览

-   所见即所得的预览
-   支持 HTML 直接渲染
-   Markdown 自动转换为 HTML（支持 GitHub Flavored Markdown）

### 3\. 文件管理

-   创建、编辑、删除文件
-   公开/私密设置
-   文件列表查看
-   管理员权限控制

### 4\. 分享系统

-   生成唯一的分享链接
-   永久访问，无需登录
-   支持复制分享链接

### 5\. 管理后台

-   JWT 身份验证
-   文件列表管理
-   密码修改
-   操作日志

🛠️ 可用脚本
--------

# 开发
npm run dev              # 启动开发服务器（带 hot reload）

# 构建
npm run build            # 构建生产版本
npm start                # 启动生产服务器

# 数据库
npm run db:setup         # 一键初始化（生成 Client + 推送 Schema + 创建管理员）
npm run db:push          # 推送 Schema 到数据库
npm run db:generate      # 生成 Prisma Client
npm run db:migrate       # 创建迁移文件
npm run db:reset         # 重置数据库

# 代码质量
npm run lint             # ESLint 检查

🔐 环境变量
-------

创建 `.env` 文件：

# 数据库连接（SQLite 默认）
DATABASE\_URL\="file:./dev.db"

# JWT 密钥（生产环境务必更换）
JWT\_SECRET\="your-super-secret-key-change-in-production"

📝 API 文档
---------

访问 https://html2web.h7ml.cn/api-docs 查看完整的 API 文档。

### 主要 API 端点

端点

方法

描述

`/api/admin/auth`

POST / GET

登录 / 验证

`/api/admin/password`

POST

修改密码

`/api/files`

GET / POST

文件列表 / 创建

`/api/files/[id]`

GET / PUT / DELETE

文件详情 / 更新 / 删除

`/api/markdown`

POST

Markdown 转 HTML

`/api/share`

POST / GET

创建 / 获取分享

`/api/health`

GET

健康检查

🌐 部署
-----

### Vercel（已部署 - 推荐）

本项目已部署至 **Vercel**，访问地址：https://html2web.h7ml.cn

#### 自行部署到 Vercel

# 方式 1: 使用 Vercel CLI
npm i -g vercel
vercel --prod

# 方式 2: 通过 GitHub 自动部署
# 1. Fork 本仓库
# 2. 访问 https://vercel.com/new 导入项目
# 3. 选择 vercel-deploy 分支
# 4. 配置环境变量后部署

**必需环境变量**：

-   `DATABASE_URL` - 数据库连接字符串（推荐 Vercel Postgres 或 Neon）
-   `JWT_SECRET` - JWT 密钥（至少 32 字符）

**⚠️ 注意事项**：

-   Vercel 不支持自定义 Node.js 服务器
-   Socket.IO 功能需使用 Vercel Serverless Functions 改造
-   建议使用 Vercel Postgres 或外部 PostgreSQL 数据库

* * *

### Cloudflare Pages（备用方案 - 免费且快速）

#### 前置条件

-   Cloudflare 账号
-   GitHub 账号（用于自动部署）
-   外部数据库（推荐 Neon PostgreSQL 或 PlanetScale MySQL）

#### 部署步骤

1.  **准备外部数据库**

# 使用 Neon（推荐 - PostgreSQL）
# 1. 访问 https://neon.tech 创建免费数据库
# 2. 获取连接字符串，如：postgresql://user:pass@host/db?sslmode=require

# 或使用 PlanetScale（MySQL）
# 1. 访问 https://planetscale.com 创建免费数据库
# 2. 获取连接字符串

1.  **更新 Prisma Schema**

// prisma/schema.prisma
datasource db {
  provider \= "postgresql" // 或 "mysql"
  url      \= env("DATABASE\_URL")
}

1.  **在 Cloudflare Dashboard 部署**

-   登录 Cloudflare Dashboard
-   进入 **Workers & Pages** > **Create Application** > **Pages** > **Connect to Git**
-   选择 `h7ml/html2web` 仓库
-   配置构建设置：
    -   **Framework preset**: `Next.js`
    -   **Build command**: `npm run build`
    -   **Build output directory**: `.next`
    -   **Root directory**: `/`
-   添加环境变量：
    -   `DATABASE_URL`: 你的数据库连接字符串
    -   `JWT_SECRET`: 生产环境密钥（至少 32 字符）
    -   `CF_PAGES`: `true`（启用 Cloudflare 优化）
-   点击 **Save and Deploy**

1.  **初始化数据库**

# 本地执行（使用生产数据库 URL）
DATABASE\_URL="你的数据库URL" npm run db:push
DATABASE\_URL="你的数据库URL" npx tsx scripts/init-admin.ts

#### 注意事项

⚠️ **Cloudflare 限制**：

-   **不支持 Socket.IO**：实时通信功能在 Cloudflare 上不可用（可用 Cloudflare Durable Objects 替代，需额外开发）
-   **函数执行时间限制**：免费版最多 100ms CPU 时间
-   **冷启动**：首次请求可能较慢

✅ **优化建议**：

-   使用 **Cloudflare Images** 处理图片
-   启用 **Cloudflare R2** 存储大文件
-   使用 **Cloudflare D1**（SQLite）作为数据库（需调整代码）

* * *

### Vercel（简单快速）

# 安装 Vercel CLI
npm i -g vercel

# 部署
vercel

# 配置环境变量（在 Vercel Dashboard）
# - DATABASE\_URL
# - JWT\_SECRET

* * *

### Docker

FROM node:18-alpine

WORKDIR /app
COPY package\*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build
RUN npm run db:setup

EXPOSE 3000
CMD \["npm", "start"\]

* * *

### 传统服务器

# 构建
npm run build

# 配置环境变量
export NODE\_ENV=production
export DATABASE\_URL="file:./prod.db"
export JWT\_SECRET="your-production-secret"

# 初始化数据库
npm run db:push
npx tsx scripts/init-admin.ts

# 启动
npm start

🤝 贡献
-----

欢迎贡献代码！请查看 CONTRIBUTING.md 了解详情。

1.  Fork 本仓库
2.  创建特性分支 (`git checkout -b feature/AmazingFeature`)
3.  提交更改 (`git commit -m 'Add some AmazingFeature'`)
4.  推送到分支 (`git push origin feature/AmazingFeature`)
5.  开启 Pull Request

📄 许可证
------

本项目采用 MIT 许可证 - 查看 LICENSE 文件了解详情。

🙏 致谢
-----

-   Next.js - React 框架
-   shadcn/ui - 组件库
-   Monaco Editor - 代码编辑器
-   Prisma - ORM
-   Socket.IO - 实时通信

📮 联系方式
-------

-   GitHub Issues: https://github.com/h7ml/html2web/issues
-   邮箱: your-email@example.com

* * *

**⭐ 如果这个项目对你有帮助，请给一个 Star！**

Made with ❤️ by h7ml
