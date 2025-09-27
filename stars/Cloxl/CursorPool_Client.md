---
project: CursorPool_Client
stars: 568
description: CursorPool客户端，支持windows系统和mac，支持cursor一键换号、重置机器码、禁用Cursor自动更新
url: https://github.com/Cloxl/CursorPool_Client
---

Cursor Pool - 多账户管理解决方案
=======================

🌟 核心功能
-------

### 账户管理

-   **多账户切换**：快速在不同 Cursor 账户间无缝切换
-   **智能重置**：一键重置机器码破解使用限制
-   **状态监控**：实时追踪账户使用情况
    -   高级模型用量统计
    -   基础模型用量分析
    -   账户有效期监测

### 用户体验

-   🎨 主题支持：深色/浅色双模式自由切换
-   🌐 多语言：国际化支持（持续更新中）
-   ⚙️ 会员系统：解锁更多高级功能

* * *

构建教程
----

### 步骤

**1\. 获取代码**

git clone https://github.com/Cloxl/CursorPool\_Client.git && cd CursorPool\_Client && pnpm i

**2\. 后端开发**  
根据 `swagger.json` 编写 API

**3\. 密钥配置**  
根据文档tauri updater生成密钥 → 配置到 `tauri.conf.json` 和 GitHub 项目密钥中

**4\. 安装依赖和构建**

pnpm tauri build

* * *

### cursor pool 官方后端技术栈:

后端可以使用任何语言 满足swagger.json的api即可

### **相关**: Cursor纯协议注册机项目

* * *

📜 开源协议声明
---------

### 使用条款

本代码库遵循 **MIT 许可证**，但请注意：

-   **保留作者信息**：必须在设置页面优先展示原作者：
    -   Cloxl
    -   Sanyela
-   **禁止使用品牌元素**：
    -   ❌ `Cursor Pool` 名称及变体
    -   ❌ 原版软件图标
    -   ❌ 安装包显示原名称

### 允许行为（需满足上述条件）

-   ✅ 代码复制/修改
-   ✅ 二次分发
-   ✅ 商业用途

> **版本说明**：自 v1.8.4 起，代码同步策略调整为仅同步版本号，不保留 commit 历史。

* * *

🛠️ 开发架构
--------

```
技术栈
├── 核心框架: Tauri
├── 前端框架: Vue3 + TypeScript
├── 状态管理: Pinia
└── UI组件: Naive UI
```
