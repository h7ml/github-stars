---
project: my-fingerprint
stars: 642
description: 保护你的浏览器指纹 | Protect Your Browser Fingerprints | Chrome, Edge, Firefox | 扩展 / Extension
url: https://github.com/omegaee/my-fingerprint
---

#### 简体中文 | English

* * *

My Fingerprint
==============

保护你的浏览器指纹，提升隐私安全。支持 `Chrome`、`Edge`、`Firefox`。

轻量、零干扰的浏览器扩展，基于 Manifest V3 构建。

* * *

##### ✨ 功能 | 🧬 指纹 | 🧰 安装 | ⚙️ 配置 | 🧪 测试 | 🛠️ 开发 | 🌱 社区 | 💝 支持 | 📜 声明 | 🙏 鸣谢

✨ 功能特点
------

-   🚀 支持 Chrome、Edge、Firefox 浏览器
-   ⚙️ 安装即生效，无需额外配置
-   📦 基于 Manifest V3，兼容性强
-   🔍 可监控页面对指纹 API 的访问情况
-   🧱 支持白名单控制与自定义配置
-   📤 提供配置导入导出与订阅功能
-   🧩 轻量级原生注入，零依赖，性能开销极低

🧬 指纹保护
-------

-   Canvas 指纹
-   WebGL 指纹
-   Audio 指纹
-   Fonts 指纹
-   WebRTC 保护
-   WebGPU 指纹
-   DomRect 指纹
-   语言与时区
-   图形驱动信息
-   UserAgent
-   屏幕尺寸与分辨率

🧰 安装指南
-------

### 🧩 扩展商店安装

💡 扩展商店的更新可能因审核延迟而滞后于 GitHub。

-   Edge
-   Firefox
-   Chrome: 尚未上架，可通过手动安装使用

### 📦 手动安装

#### Chrome / Edge

-   浏览器版本要求：`Chrome/Edge 102+`
-   推荐版本：120+
-   下载扩展包 `.zip` 文件 → 拖入扩展管理页面 → 启用扩展
-   可选：启用无痕模式支持

#### Firefox

-   浏览器版本要求：`Firefox 136+`
-   下载扩展包 `.xpi` 文件 → 拖入浏览器窗口 → 点击添加

⚙️ 配置模块
-------

扩展支持灵活的配置选项，可通过图标进入设置面板进行调整：

-   **强指纹组**
    
    -   模拟高度唯一的用户特征，通常与其他指纹项或 IP 信息联合使用
-   **弱指纹组**
    
    -   获取重复率高的基础信息，适合轻度保护场景
-   **脚本配置**
    
    -   全局种子：用于“根据全局种子随机值”选项，确保生成结果一致性
    -   注入模式：推荐启用“快速注入”以提升兼容性与性能
-   **白名单机制**
    
    -   支持编辑白名单列表
    -   支持子域名匹配：如 `example.com` 可匹配 `*.example.com`、`*.*.example.com`
-   **订阅机制**
    
    -   可使用配置模板进行初始化（订阅一次后可关闭）
        -   标准模式 - 默认配置
    -   空值表示关闭订阅
    -   支持手动订阅或扩展启动时自动拉取远程配置（JSON 格式）
    -   订阅配置将覆盖原设置，并合并白名单内容

🧪 测试目标
-------

-   webbrowsertools.com
-   browserleaks.com
-   CreepJS
-   browserscan.net
-   yalala.com
-   uutool.cn

🛠️ 开发
------

cd <project\>
npm install
npm run dev          # Chrome / Edge
npm run dev:firefox  # Firefox

🌱 社区
-----

-   欢迎通过 Issues 和 Pull Requests 提交建议与反馈
-   

💝 支持一下
-------

-   如果你觉得项目有帮助，请点个 Star ⭐
-   微信赞赏支持也欢迎！微信赞赏入口

📜 声明
-----

本项目仅用于学习与研究目的。请勿用于非法用途，开发者不对任何损失或问题负责。

🙏 鸣谢
-----

感谢所有贡献者与支持者。特别感谢开源社区的力量！
