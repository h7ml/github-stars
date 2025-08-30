---
project: weread
stars: 9
description: 基于 Fresh (Deno) 构建的现代化微信读书 Web 阅读应用，具有高级 TTS 功能和优雅的阅读界面。
url: https://github.com/h7ml/weread
---

微信读书 Web 阅读应用
=============

* * *

基于 Fresh (Deno) 构建的现代化微信读书 Web 阅读应用，具有高级 TTS 功能和优雅的阅读界面。

📋 MVP 核心功能
-----------

**微信读书 Web 阅读应用** 是一个全功能的电子书阅读平台，从 2025-08-14 项目初始化开始，在短短2天内（至2025-08-16）快速迭代开发，已实现了完整的 MVP 功能集。

**🎯 MVP 功能概览**

### 📚 阅读核心

-   **电子书阅读器**：完整的章节导航和进度跟踪
-   **多主题支持**：护眼模式、夜间模式、自定义字体
-   **响应式阅读**：完美适配手机、平板、桌面设备

### 🔊 智能语音

-   **三引擎TTS**：OpenXing + t.leftsite.cn + 浏览器回退
-   **29+中文语音**：多音色、情感风格可选
-   **智能朗读**：句子级高亮、自动滚动、跨章节连读

### 👤 用户系统

-   **微信读书登录**：SSE实时登录状态同步
-   **个人中心**：完整的个人信息管理
-   **安全会话**：KV存储的会话管理和安全退出

### 📊 数据分析

-   **阅读统计**：热力图、时间分布、偏好分析
-   **进度同步**：跨设备阅读进度一致性
-   **笔记管理**：书签、批注、书评集成管理

**🏗️ 项目架构概览**

### 核心技术栈

```
Frontend:  Preact 10.22.0 + Signals + TailwindCSS 3.4.0
Backend:   Deno + Fresh 1.7.3 + Unstable KV
TTS:       多引擎架构（OpenXing + t.leftsite.cn + WebSpeech）
Storage:   Deno KV (会话/设置/日志) + localStorage (客户端缓存)
Security:  XSS防护 + 内容解密 + 请求签名 + CORS支持
```

### 系统架构图

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Client Side   │    │   Server Side   │    │  External APIs  │
│                 │    │                 │    │                 │
│  ┌───────────┐  │    │  ┌───────────┐  │    │  ┌───────────┐  │
│  │Islands    │  │◄──►│  │Fresh      │  │◄──►│  │微信读书   │  │
│  │Components │  │    │  │Routes     │  │    │  │API        │  │
│  └───────────┘  │    │  └───────────┘  │    │  └───────────┘  │
│  ┌───────────┐  │    │  ┌───────────┐  │    │  ┌───────────┐  │
│  │Preact +   │  │    │  │Deno KV    │  │    │  │TTS        │  │
│  │Signals    │  │    │  │Storage    │  │    │  │Services   │  │
│  └───────────┘  │    │  └───────────┘  │    │  └───────────┘  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### 数据流架构

```
用户交互 → Islands组件 → API调用 → 业务逻辑 → 数据存储/外部API
    ↓         ↓          ↓         ↓           ↓
响应更新 ← Signals状态 ← JSON响应 ← 数据处理 ← KV/微信读书API
```

### 模块化设计

```
src/
├── apis/              # 外部API集成层
│   └── web/          # 微信读书API封装
├── kv/               # 数据持久化层
│   ├── credential.ts # 用户凭证管理
│   ├── setting.ts    # 应用设置存储
│   └── systemLog.ts  # 系统日志记录
├── utils/            # 工具函数库
│   ├── crypto.ts     # 加密解密工具
│   └── request.ts    # 网络请求封装
└── types/            # TypeScript类型定义
```
**🚀 开发历程**

### 项目时间线

-   **2025-08-14**：项目初始化 (Commit: abd1f21 - feat: 初始化 Fresh 项目)
-   **2025-08-16**：MVP功能完成 (当前版本: 1.0.0)
-   **开发周期**：2天快速迭代

### 关键里程碑

```
Day 1 (2025-08-14):
├── ✅ Fresh项目基础架构搭建
├── ✅ 基本路由和组件结构
├── ✅ TailwindCSS样式系统配置
└── ✅ Preact组件和计数器逻辑实现

Day 2 (2025-08-15 - 2025-08-16):
├── ✅ 微信读书API集成完成
├── ✅ 多引擎TTS系统实现
├── ✅ 用户登录和会话管理
├── ✅ 阅读器核心功能
├── ✅ 数据统计和可视化
├── ✅ 笔记和书架管理
└── ✅ 生产环境部署优化
```

### 技术债务和优化

-   ✅ **CSS生产问题修复**：解决了生产环境样式丢失
-   ✅ **登录数据完整性**：修复SSE用户信息存储逻辑
-   ✅ **错误处理优化**：完善登录过期和用户体验
-   ✅ **TTS功能增强**：优化文本转语音和语音试听

🚀 特性
-----

### 📚 阅读体验

-   **完整的电子书阅读器**：支持章节导航、阅读进度跟踪
-   **多种阅读主题**：护眼模式、夜间模式等
-   **响应式设计**：适配桌面端和移动端
-   **阅读统计**：详细的阅读数据分析和可视化
-   **进度同步**：跨设备阅读进度同步

### 🔊 多引擎 TTS 系统

-   **三引擎支持**：OpenXing TTS + t.leftsite.cn + 浏览器 Web Speech API 智能回退
-   **29+ 中文语音**：支持多种音色和情感风格
-   **智能功能**：
    -   句子级阅读和可视化高亮
    -   实时进度跟踪和动画进度条
    -   自动滚动，可配置速度和平滑度
    -   跨章节连续阅读
    -   自动故障转移和服务检测

### 👤 用户系统

-   **完整个人中心**：个人信息管理、阅读成就展示
-   **安全登录**：完善的登录认证和会话管理
-   **个性化设置**：主题、字体、TTS 偏好设置
-   **安全退出**：服务端会话清理和客户端状态重置

### 📊 内容管理

-   **智能搜索**：全文搜索和图书发现
-   **书架管理**：个人图书收藏和分类
-   **笔记系统**：支持笔记、书签、书评管理
-   **统计分析**：阅读热力图、时间分布、偏好分析

### 🔐 微信读书集成

-   **完整 API 集成**：支持公开和认证模式
-   **内容解密**：处理受保护的章节内容
-   **会话管理**：基于 Cookie 的认证和 KV 存储
-   **实时登录**：Server-Sent Events 实时登录状态更新

### 🛠️ 技术栈

-   **框架**：Fresh 1.7.3 (Deno 全栈框架)
-   **前端**：Preact 10.22.0 + Signals 状态管理
-   **样式**：TailwindCSS 3.4.0 + PostCSS
-   **后端**：Deno + Unstable KV 存储 + 定时任务
-   **TTS**：多引擎服务集成 + 浏览器回退
-   **数据存储**：Deno KV (用户会话、设置、日志、任务)
-   **安全性**：XSS 防护、内容解密、请求签名

📦 安装和使用
--------

**💻 环境要求**

-   Deno 最新版本

**🚀 开发模式**

# 启动开发服务器（热重载）
deno task dev

服务将在 http://localhost:8888 启动（或 PORT 环境变量指定的端口）

**🔍 代码质量检查**

# 格式检查 + Lint 检查（推荐日常使用）
deno task check

# 仅类型检查
deno task check-types  

# 完整检查（格式 + Lint + 类型）
deno task check-all

# 格式化代码
deno fmt

# 仅 Lint 检查
deno lint

**📦 生产部署**

# 构建生产版本
deno task build

# 启动生产服务器
deno task start

**⬆️ 更新框架**

# 更新 Fresh 框架
deno task update

🗂️ 项目结构
--------

```
weread/
├── routes/                 # Fresh 基于文件的路由
│   ├── api/               # API 端点
│   │   ├── book/          # 书籍相关 API
│   │   ├── tts/           # TTS 相关 API
│   │   └── login/         # 登录相关 API
│   └── reader/            # 阅读器页面
├── islands/               # 客户端交互组件（水合）
├── src/
│   ├── apis/              # 业务逻辑和外部 API 集成
│   │   └── web/           # 微信读书 API 封装
│   ├── kv/                # Deno KV 数据操作
│   ├── utils/             # 工具函数和助手
│   └── types/             # TypeScript 类型定义
├── static/                # 静态资源
└── components/            # 可复用组件
```

🔧 配置
-----

**🌍 环境变量**

PORT=8888                  # 服务端口（默认：8888）
DENO\_ENV=production        # 环境（local/development/production）
KV\_NAMESPACE=weread        # Deno KV 命名空间
LOG\_LEVEL=info             # 日志级别

# TTS 服务配置
OPENXING\_TTS\_URL=          # OpenXing TTS 服务 URL
LEFTSITE\_TTS\_URL=          # Leftsite TTS 服务 URL

# 微信读书 API 配置
WEREAD\_API\_BASE=           # 微信读书 API 基础地址
WEREAD\_COOKIE=             # 微信读书 Cookie（可选）

**📁 路径别名**

项目配置了以下路径别名：

-   `@/utils` → `src/utils/mod.ts`
-   `@/apis` → `src/apis/mod.ts`
-   `@/kv` → `src/kv/mod.ts`
-   `@/cron` → `src/cron/mod.ts`
-   `@/config` → `src/config.ts`
-   `@/types` → `src/types/mod.ts`

🎯 核心功能
-------

**📱 页面路由**

-   **主页面**：`/` - 首页、`/dashboard` - 仪表板、`/profile` - 个人中心
-   **图书相关**：`/book/[id]` - 图书详情、`/reader/[bookId]/[chapterUid]` - 阅读器、`/shelf` - 书架
-   **功能页面**：`/search` - 搜索、`/notes` - 笔记、`/login` - 登录

**🔌 API 端点**

#### TTS 语音服务

-   `GET /api/tts` - 主 TTS 服务（t.leftsite.cn）
-   `POST /api/tts/openxing` - OpenXing TTS 服务
-   `GET /api/tts/voices` - 获取可用语音列表
-   `GET /api/tts/openxing-voices` - OpenXing 语音列表

#### 图书服务

-   `GET /api/book/info` - 获取图书信息
-   `GET /api/book/chapters` - 获取章节列表
-   `GET /api/book/content` - 获取章节内容（支持解密）

#### 用户服务

-   `GET /api/user/profile` - 个人资料管理
-   `GET /api/user/weread` - 微信读书用户信息
-   `GET /api/user/credential` - 用户凭证获取
-   `POST /api/logout` - 安全退出登录

#### 内容管理

-   `GET /api/search` - 统一搜索接口（全局搜索+建议）
-   `GET /api/shelf` - 书架管理
-   `POST /api/shelf/manage` - 书架操作（添加/删除）
-   `GET /api/notes` - 笔记和书评 CRUD
-   `GET /api/progress` - 阅读进度同步
-   `GET /api/stats` - 阅读统计数据

#### 登录认证

-   `POST /api/login` - 登录接口
-   `GET /api/login/sse` - Server-Sent Events 实时登录状态

**🏝️ Islands 组件**

-   **核心阅读器**：`WeReadStyleReaderComponent` - 完整阅读体验和 TTS 功能
-   **用户界面**：`LoginComponent` - 登录认证、`ProfileComponent` - 个人中心
-   **内容管理**：`DashboardComponent` - 数据统计、`SearchComponent` - 搜索发现
-   **功能组件**：`NotesComponent` - 笔记管理、`ShelfComponent` - 书架管理
-   **系统组件**：`ProgressSyncComponent` - 进度同步

🛡️ 安全特性
--------

-   **内容解密**：处理微信读书的内容保护机制
-   **请求签名**：复杂的签名系统确保 API 安全性
-   **会话管理**：基于 KV 存储的安全用户认证
-   **XSS 防护**：使用 xss 库防止跨站脚本攻击
-   **CORS 支持**：所有 API 端点支持跨域请求
-   **Token 认证**：支持 URL 参数和 Authorization header
-   **安全退出**：服务端会话清理和客户端状态重置

📝 开发注意事项
---------

**⚠️ 核心要求**

1.  **代码质量**：使用 `deno task check-all` 确保完整的代码质量检查
2.  **KV 存储**：通过 `@/kv` 模块进行数据持久化，支持用户会话、设置、日志
3.  **TTS 开发**：支持多引擎 TTS，需要测试服务可用性和故障转移
4.  **Fresh Islands**：交互组件放在 `islands/` 目录，使用 Preact Signals 状态管理
5.  **CSS 样式**：避免内联样式，使用 `static/styles.css` 和 TailwindCSS safelist
6.  **API 开发**：遵循 RESTful 设计，支持 CORS 和统一错误处理
7.  **生产部署**：确保 CSS 构建、TTS 服务配置和环境变量设置正确

📊 项目状态
-------

-   ✅ **格式检查**：完全通过
-   ✅ **Lint 检查**：完全通过
-   ✅ **类型检查**：完全通过（Fresh 1.7.3 兼容）
-   ✅ **部署状态**：正常运行
-   ✅ **多引擎 TTS**：OpenXing + t.leftsite.cn + 浏览器回退
-   ✅ **用户系统**：完整的登录、个人中心、安全退出
-   ✅ **CSS 生产**：解决了生产环境样式丢失问题
-   ✅ **数据完整性**：修复了登录 SSE 用户数据存储
-   🔄 **持续集成**：GitHub Actions 自动部署

🌟 Star History
---------------

🤝 贡献
-----

我们欢迎任何形式的贡献！请查看 贡献指南 了解如何参与项目开发。

### 贡献类型

-   🐛 **Bug 报告**：发现问题请提交 Issue
-   💡 **功能建议**：有好的想法请分享
-   🔧 **代码贡献**：欢迎提交 Pull Request
-   📚 **文档改进**：帮助完善项目文档
-   🌐 **翻译**：支持多语言本地化

### 快速开始贡献

1.  Fork 本仓库
2.  创建功能分支：`git checkout -b feature/amazing-feature`
3.  提交更改：`git commit -m 'Add some amazing feature'`
4.  推送分支：`git push origin feature/amazing-feature`
5.  提交 Pull Request

### 开发规范

-   使用 `deno task check` 确保代码质量
-   遵循项目的 TypeScript 类型规范
-   提交前运行完整测试
-   保持代码风格一致

🏗️ 项目架构
--------

### 技术选型理由

-   **Deno**：现代 JavaScript/TypeScript 运行时，内置安全性和工具链
-   **Fresh**：轻量级全栈框架，零配置 SSR 和 Islands 架构
-   **Preact**：React 的轻量级替代品，更小的包体积
-   **TailwindCSS**：实用优先的 CSS 框架，开发效率高

### 文件结构说明

```
weread/
├── routes/                 # 基于文件的路由系统
│   ├── api/               # API 端点
│   ├── reader/            # 阅读器相关页面
│   └── _404.tsx           # 自定义 404 页面
├── islands/               # 客户端组件（Islands 架构）
├── src/                   # 核心业务逻辑
│   ├── apis/              # 外部 API 集成
│   ├── kv/                # 数据存储层
│   ├── utils/             # 工具函数
│   └── types/             # 类型定义
├── static/                # 静态资源
├── components/            # 可复用组件
└── docs/                  # 项目文档
```

📊 性能指标
-------

-   **首屏加载时间**：< 1.5s（LCP）
-   **交互延迟**：< 100ms（FID）
-   **布局稳定性**：< 0.1（CLS）
-   **SEO 友好**：服务端渲染支持

🔒 安全特性
-------

-   **内容安全策略**：防止 XSS 攻击
-   **HTTPS 强制**：所有通信加密传输
-   **环境变量管理**：敏感信息安全存储
-   **输入验证**：严格的数据校验机制

🌐 国际化
------

项目支持多语言本地化：

-   🇨🇳 **简体中文**（默认）
-   🇺🇸 **English**（计划中）
-   🇯🇵 **日本語**（计划中）

📈 路线图
------

### v1.0.0（当前版本 - 2025-08-16）

-   ✅ **MVP核心功能**：完整的电子书阅读体验
-   ✅ **多引擎TTS系统**：OpenXing + t.leftsite.cn + 浏览器回退
-   ✅ **用户系统**：微信读书登录、个人中心、安全会话管理
-   ✅ **数据统计**：阅读热力图、时间分布、偏好分析
-   ✅ **内容管理**：搜索、书架、笔记、进度同步
-   ✅ **生产优化**：CSS构建、样式稳定性、部署配置
-   ✅ **快速迭代**：2天内从项目初始化到MVP完成

### v1.1.0（开发中）

-   移动端响应式体验进一步优化
-   离线阅读支持
-   阅读目标设置和跟踪
-   更多 TTS 语音和自定义选项

### v1.2.0（计划中）

-   多用户支持和权限管理
-   增强的笔记和标注功能
-   社交分享和阅读动态
-   性能优化和缓存策略

### v2.0.0（长期目标）

-   跨平台客户端（PWA、桌面应用）
-   AI 推荐系统和智能阅读助手
-   实时协作和阅读小组功能
-   多语言支持和国际化

🆘 支持
-----

遇到问题？我们提供多种支持方式：

-   📖 **文档**：查看 项目文档
-   🐛 **Issue**：GitHub Issues
-   💬 **讨论**：GitHub Discussions
-   📧 **邮件**：h7ml@qq.com
-   💬 **微信**：联系作者

👤 作者
-----

-   **姓名**：h7ml
-   **邮箱**：h7ml@qq.com
-   **GitHub**：@h7ml
-   **微信**：扫码添加

_扫描二维码添加作者微信_

🙏 致谢
-----

感谢以下优秀的开源项目：

-   Deno - 现代 JavaScript 运行时
-   Fresh - 全栈 Web 框架
-   Preact - 快速 React 替代方案
-   TailwindCSS - 实用优先 CSS 框架

📄 许可证
------

本项目采用 MIT 许可证 开源。

* * *

**⭐ 给个 Star | 🍴 Fork 项目 | 💞 赞助开发**

Made with ❤️ by h7ml and contributors
