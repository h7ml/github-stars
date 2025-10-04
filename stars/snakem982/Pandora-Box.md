---
project: Pandora-Box
stars: 695
description: A Simple Mihomo GUI. 一个简易的 Mihomo 桌面客户端
url: https://github.com/snakem982/Pandora-Box
---

Pandora-Box
===========

🌈 A simple desktop client for **Mihomo**

✨ 一个简易的 **Mihomo** 桌面客户端

✨ Простой настольный клиент для **Mihomo**

🇨🇳 简体中文 | 🇺🇸 English | 🇷🇺 Русский

* * *

📦 Project Overview | 项目简介 | Обзор проекта
------------------------------------------

**Pandora-Box** is a lightweight and user-friendly cross-platform client for Mihomo, supporting multiple proxy protocols, automatic rule grouping, and TUN mode.  
It is designed for both casual and advanced users to easily manage and convert proxy subscriptions.

**Pandora-Box** 是一个跨平台的轻量桌面客户端，适配 Mihomo 内核，支持多种代理协议、规则自动分组与 TUN 模式。界面简洁，功能强大，适合轻量与进阶用户使用。

**Pandora-Box** — это легкий и удобный кроссплатформенный клиент для Mihomo, поддерживающий различные прокси-протоколы, автоматическую группировку правил и режим TUN.  
Он разработан как для обычных пользователей, так и для продвинутых, чтобы облегчить управление и конвертацию подписок прокси.

* * *

📥 Get Started ｜ 快速开始 ｜ Начало работы
-------------------------------------

👉 Download the Latest Release / 下载最新版本 / Скачать последнюю версию

* * *

🛠 Development ｜ 开发 ｜ Разработка
--------------------------------

If you want to contribute or build Pandora-Box locally, refer to the resources below:  
如果你想参与开发或构建 Pandora-Box，可以参考以下资源：  
Если вы хотите принять участие в разработке или собрать Pandora-Box локально, воспользуйтесь следующими ресурсами:

### 🔧 Prerequisites | 前置依赖 | Предварительные требования

-   Node.js ≥ 18 (for building UI components or tooling)
-   Go ≥ 1.24 (for integration with Mihomo or backend modules)

### 🧪 Build Instructions | 构建指南 | Инструкции по сборке

# Install dependencies
npm install
cd src-go
go mod tidy

# Build px backend
CGO\_ENABLED=0 go build -tags=with\_gvisor -trimpath -ldflags "\-X github.com/snakem982/pandora-box/api.Version=v-test" -o px(.exe)
cd ..

# Build desktop app
npm run package

# Run in dev mode
npm run start

* * *

🌐 Language ｜ 语言选择 ｜ Выбор языка
--------------------------------

-   🇨🇳 查看中文文档
-   🇺🇸 View English Documentation
-   🇷🇺 Просмотр русской документации

* * *

🧭 More Information ｜ 更多信息 ｜ Дополнительная информация
------------------------------------------------------

-   ✅ Project Issues
-   📄 License (GPL-3.0)

* * *

📝 This README was generated with the assistance of AI and reviewed by the developer.  
📝 本文档内容由 AI 辅助生成，并由开发者校对。  
📝 Этот README создан при поддержке ИИ и проверен разработчиком.
