---
project: packycode-cost
stars: 8
description: null
url: https://github.com/94mashiro/packycode-cost
---

PackyCode Cost Monitor
======================

一个 Chrome 浏览器扩展，帮助用户实时监控 PackyCode 的使用额度和预算。

📷 功能预览
-------

_实时监控您的 PackyCode 使用情况和预算_

✨ 功能特性
------

-   📊 **实时监控**: 查看每日和每月的 API 使用情况
-   💰 **预算跟踪**: 可视化预算进度条和余额显示
-   🎯 **智能提醒**: 预算即将耗尽时的智能提醒
-   🔒 **安全认证**: 安全的 Token 管理和用户认证
-   🎨 **现代 UI**: 基于 Tailwind CSS 的现代化界面设计
-   ⚡ **轻量级**: 基于 Plasmo 框架，高性能低内存占用

🚀 快速开始
-------

### 安装

#### 方式一：Chrome Web Store 安装（推荐）

-   从 Chrome Web Store 安装
-   **优点**：安装方便，自动更新，无需手动管理
-   **缺点**：更新可能不够及时，需要等待商店审核

#### 方式二：手动安装（获取最新版本）

-   从 Releases 下载最新版本
-   **优点**：可以第一时间获取最新功能和修复
-   **缺点**：需要手动下载和更新，安装步骤相对复杂

### 开发环境设置

# 克隆仓库
git clone https://github.com/94mashiro/packycode-cost.git
cd packycode-cost

# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

开发模式下，在浏览器中加载 `build/chrome-mv3-dev` 目录。

### 构建生产版本

pnpm build

构建完成后，可以在 `build/` 目录中找到生产版本。

🛠️ 技术栈
-------

-   **框架**: Plasmo - 现代浏览器扩展开发框架
-   **UI 库**: React 18 + TypeScript
-   **样式**: Tailwind CSS
-   **状态管理**: Plasmo Storage API
-   **构建工具**: Plasmo CLI
-   **代码质量**: ESLint + Prettier

📖 使用指南
-------

1.  **初次使用**: 安装扩展后，点击扩展图标开始使用
2.  **自动认证**: 扩展会自动获取 PackyCode dashboard 的登录状态，无需手动配置 Token
3.  **监控数据**: 自动查询并展示实时的使用情况

🤝 贡献指南
-------

我们欢迎所有形式的贡献！请查看 CONTRIBUTING.md 了解详细信息。

### 开发流程

1.  Fork 本仓库
2.  创建功能分支 (`git checkout -b feature/amazing-feature`)
3.  提交更改 (`git commit -m 'Add some amazing feature'`)
4.  推送到分支 (`git push origin feature/amazing-feature`)
5.  创建 Pull Request

📝 版本历史
-------

查看 Releases 了解版本更新历史。

🐛 问题反馈
-------

如果您遇到任何问题或有功能建议，请通过以下方式联系我们：

-   提交 Issue
-   功能请求
-   Bug 报告

📄 许可证
------

本项目基于 MIT License 开源。

🔗 相关链接
-------

-   PackyCode 官网
-   Plasmo 文档
-   Chrome Extension 开发指南

💖 致谢
-----

感谢所有为这个项目做出贡献的开发者和用户！

* * *

如果这个项目对您有帮助，请给我们一个 ⭐️
