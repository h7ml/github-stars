---
project: dimina
stars: 751
description: 星河小程序 - 滴滴开源小程序 / Dimina MiniProgram - DiDi's Open-Source MiniProgram
url: https://github.com/didi/dimina
---

星河小程序（Dimina）——滴滴开源跨端小程序
========================

> Dimina 发音为 /diːminə/，是 didi miniprogram 的缩写，旨在打造灵活、轻量的小程序跨端开发框架。

简介 • 效果展示 • 上手使用 • 参与共建 • 星标趋势 • 开源协议

简介
--

星河小程序（以下简称 `Dimina`）是滴滴自研的一套轻量级跨端小程序框架，可以理解为开源版的小程序方案，致力于为开发者提供高性能、跨平台、低门槛的开发体验。

目前，Dimina 已支持 Android、iOS、Harmony 和 Web 四大平台。开发者可以将 Dimina 作为**移动端跨平台开发框架**，将已有小程序逻辑以独立模块方式集成到现有 App，或直接采用小程序语法进行开发，并一键打包生成独立原生 App。

### 🔧 技术特性

-   **资源离线化**: 资源本地存储减少网络请求
-   **逻辑视图分离**: 独立 JS 引擎避免主线程阻塞
-   **原生能力封装**: 统一 API 调用原生功能
-   **页面预加载**: WebView 预热提升性能

### 🚀 跨平台支持

-   **Android**: QuickJS + Android WebView
-   **iOS**: JavaScriptCore + WKWebView
-   **Harmony**: QuickJS + Harmony WebView
-   **Web**: Web Worker + Browser

效果展示
----

在线演示：https://didi.github.io/dimina/

Android

iOS

Harmony

上手使用
----

graph TD
    A\[创建小程序项目\] --> B\[开发小程序页面\]
    B --> C\[使用小程序语法编写逻辑\]
    C --> D\[使用DMCC编译打包\]
    D --> E\[生成星河小程序包\]
    E --> F{目标平台}
    F -->|Android| G\[集成Android SDK\]
    F -->|iOS| H\[集成iOS SDK\]
    F -->|Harmony| I\[集成Harmony SDK\]
    G --> J\[运行到Android设备\]
    H --> K\[运行到iOS设备\]
    I --> L\[运行到Harmony设备\]

Loading

### 详细步骤

1.  **创建小程序项目**
    
    -   使用小程序开发工具创建项目
    -   配置 `app.json` 和页面路由
2.  **开发小程序页面**
    
    -   编写 WXML 模板
    -   添加 WXSS 样式
    -   使用 JavaScript 编写页面逻辑
3.  **编译打包**
    
    -   使用 DMCC 编译器 将小程序代码编译为跨端代码
    -   打包星河小程序包
    -   将星河小程序包放置到各平台对应目录
4.  **平台接入**
    
    -   Android 接入说明
    -   iOS 接入说明
    -   Harmony 接入说明
5.  **调试与发布**
    
    -   集成 App 进行真机调试
    -   打包发布到各应用商店

参与共建
----

Dimina 遵循小程序标准化白皮书进行设计，目前已对齐微信小程序的主要功能。

已支持能力详见Dimina 能力参考指南。

得益于 Vue3 与小程序语法的高度相似，Dimina 底层视图渲染框架选择基于 Vue 构建。 Dimina 框架通过DMCC将小程序语法转译为 Vue 语法，并在此基础上实现了完整的小程序标准 Vue 组件体系。最终，通过实现端侧小程序容器来提供原生能力，同时灵活加载并展示视图页面。

如需了解更多关于框架底层实现的原理，欢迎查阅详细文档。

由于行业内各类小程序方案已迭代多年，Dimina 目前尚未完全覆盖全部小程序 **API/组件/特性**。欢迎大家积极贡献代码、提出建议，与我们共同完善 Dimina。

-   Bug 报告和新功能需求请提交到 Issues
-   讨论和提案欢迎到 Discussions 进行交流

星标趋势
----

如果你觉得 Dimina 对你有帮助，欢迎点击右上角 ⭐Star 支持我们，让更多人了解和使用这个项目。

开源协议
----

Dimina 遵循 Apache-2.0 协议进行分发和使用，更多详情请参见协议文件。
