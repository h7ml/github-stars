---
project: mcp-cn
stars: 52
description: MCP Hub 中国是一个专注于 Model Context Protocol (MCP) 生态的开源平台。它致力于汇聚全球优质的 MCP 服务,提供一站式的解决方案,包括服务发现、接入指南和使用示例,并建立完善的中文生态,欢迎开发者参与贡献和完善平台功能。
url: https://github.com/mengjian-github/mcp-cn
---

MCP Hub 中国 🇨🇳
===============

**精选优质 MCP 服务，只推荐最好用的**

🌐 在线体验 | 📖 官方文档 | 💬 问题反馈

🎯 项目简介
-------

MCP Hub 中国是一个专注于精选优质 MCP 服务的 Monorepo 项目，包含：

-   🌐 **Web 应用** - MCP 服务展示平台
-   🛠️ **CLI 工具** - 命令行管理工具
-   📦 **MCP 服务器** - 高质量的 MCP 服务实现

🚀 快速开始
-------

### 🎯 Cursor 一键安装（推荐）

如果你使用 Cursor IDE，可以享受最便捷的安装体验：

1.  访问 MCP Hub 中国
2.  找到你需要的 MCP 服务
3.  点击 ⚡ 一键安装按钮
4.  Cursor 会自动打开并配置服务

### 🛠️ CLI 工具安装

# 全局安装 CLI 工具
npm install -g @mcp\_hub\_org/cli

# 安装 MCP 服务到 Cursor
mcp install sequential-thinking --client cursor

# 生成 Cursor 深链接
mcp deeplink sequential-thinking --platform mac

### 💻 本地开发

# 克隆项目
git clone https://github.com/mengjian-github/mcp-cn.git
cd mcp-cn

# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 访问应用
# http://localhost:7777

📦 项目结构
-------

```
mcp-cn/
├── packages/
│   ├── web/                    # Web 应用
│   ├── cli/                    # CLI 工具
│   └── servers/                # MCP 服务器集合
│       ├── file-operations/    # 文件操作服务器
│       └── weather-api/        # 天气 API 服务器
```

🛠️ 开发命令
--------

pnpm dev              # 启动 Web 开发服务器
pnpm build            # 构建所有包
pnpm lint             # 代码检查
pnpm clean            # 清理构建产物

🤝 参与贡献
-------

欢迎通过以下方式参与贡献：

-   🐛 报告 Bug
-   ✨ 推荐优质 MCP 服务
-   📖 完善文档
-   🔧 提交代码

### 贡献流程

1.  Fork 项目
2.  创建特性分支 (`git checkout -b feature/AmazingFeature`)
3.  提交更改 (`git commit -m 'Add some AmazingFeature'`)
4.  推送分支 (`git push origin feature/AmazingFeature`)
5.  创建 Pull Request

👥 贡献者
------

### 🌟 感谢所有为 MCP Hub 中国做出贡献的优秀开发者们！

  

  
**孟健**  
项目发起人

  
**Zwe1**  
核心贡献者

  
**ylx911229**  
核心贡献者

  
**reekystive**  
核心贡献者

  
**XiaogeAIBreaker**  
贡献者

  
**MycodeHero**  
贡献者

  

**💖 每一份贡献都让这个项目变得更好！**

想加入我们吗？查看贡献指南 开始你的开源之旅！

📞 联系我们
-------

**扫码添加微信**

商务合作 | 技术交流 | 开源协作

📄 开源协议
-------

本项目基于 MIT License 开源协议。

* * *

**⭐ 如果这个项目对你有帮助，请给个 Star 支持一下！**

Made with ❤️ in China | © 2025 MCP Hub 中国
