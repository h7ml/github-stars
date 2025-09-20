---
project: Fanqie-novel-Downloader
stars: 355
description: null
url: https://github.com/POf-L/Fanqie-novel-Downloader
---

🍅 Tomato Novel Downloader
==========================

现代化 · 高颜值 · 即开即用的番茄小说下载器

功能亮点 · 快速开始 · 命令行用法 · 配置与令牌 · 打包与发布 · 常见问题

* * *

⭐ 星标趋势
------

* * *

⚠️ 下载功能状态
---------

**重要通知：章节下载功能当前已被禁用**

要重新启用下载功能，请：

1.  打开 `config.py` 文件
2.  将 `"download_enabled": False` 改为 `"download_enabled": True`
3.  保存文件并重启程序

* * *

✨ 功能亮点
------

-   图形界面与命令行双形态：新手友好、进阶高效
-   极速搜索与书籍信息展示，整本/按范围下载
-   支持 TXT / EPUB 导出，封面与元数据自动处理（含 HEIC）
-   多线程下载、失败自动重试、请求限速，稳定可靠
-   自动检查更新（GitHub Releases），一键下载并重启生效

> 参考并增强自 Dlmily/Tomato-Novel-Downloader-Lite，修复多个 API 逻辑并重构模块化架构。

* * *

🧭 目录结构
-------

-   gui.py — 图形界面入口（Tkinter）
-   enhanced\_downloader.py — 增强下载器（交互式 CLI）
-   tomato\_novel\_api.py — API/命令行工具（search/novel\_info 等）
-   config.py — 全局配置（并发、重试、限速、导出等）
-   updater.py — 自动更新模块（GitHub Releases）
-   requirements.txt — 依赖清单

* * *

🚀 快速开始
-------

环境要求：Python 3.10+（Windows/macOS/Linux）。GUI 需 Tkinter（Linux 需要安装 tk）。

python -m venv .venv
# Windows
.\\.venv\\Scripts\\activate
# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt

-   启动 GUI：

python gui.py

-   启动交互式 CLI（增强下载器）：

python enhanced\_downloader.py

* * *

⌨️ 命令行用法
--------

tomato\_novel\_api.py 支持：

# 搜索
python tomato\_novel\_api.py search "盗墓"

# 获取书籍信息
python tomato\_novel\_api.py novel\_info 7143038691944959011

# 其它命令
python tomato\_novel\_api.py              # 打印帮助
# 支持: search | novel\_info | book\_details | catalog | chapter\_content | download\_full

* * *

⚙️ 配置与令牌
--------

-   配置集中在 config.py，可调整并发数、重试、超时、限速、默认导出格式等
-   部分数据源需要验证令牌。GUI 首次会弹窗引导；也可使用环境变量：

# Windows PowerShell
$env:TOMATO\_VERIFICATION\_TOKEN = "你的令牌"
# macOS/Linux
export TOMATO\_VERIFICATION\_TOKEN="你的令牌"

* * *

📦 导出与文件
--------

-   支持 txt 与 epub 导出（见 config.py 的 OUTPUT\_CONFIG）
-   支持 HEIC 封面（依赖 pillow-heif）

* * *

🏗️ 打包与发布
---------

本地打包（PyInstaller）：

pip install pyinstaller
python build\_app.py

CI/CD（GitHub Actions）：

-   推送形如 v\* 的标签触发构建并上传产物
-   版本信息位于 version.py（**version**、**github\_repo**）

* * *

* * *

🧭 Roadmap
----------

-   增加批量任务队列与计划任务
-   增强搜索源与可插拔源管理
-   导出模板（含封面样式/章节样式预设）
-   内置更新频道选择（稳定/测试）
-   更丰富的日志与诊断页面

* * *

🤝 贡献
-----

欢迎 PR / Issue：

-   修复 bug、补充文档与截图、改进交互
-   新增数据源、导出格式、性能优化

流程建议：

1.  Fork 仓库并新建分支
2.  本地验证（GUI 与 CLI 至少一种）
3.  提交 PR，说明变更点与验证方式

* * *

📣 支持与反馈
--------

-   提交 Issue：描述问题场景、日志、复现步骤
-   功能建议：说明使用场景与期望交互

如果你觉得项目好用，欢迎点亮 Star ✨

🧰 常见问题
-------

-   Linux 缺少 Tkinter：`sudo apt-get install -y python3-tk tk-dev`
-   fake-useragent 在部分网络环境可能失败：可临时固定 UA 或稍后重试
-   请求失败较多：适当提高超时与限速（config.py: REQUEST\_TIMEOUT、REQUEST\_RATE\_LIMIT）

* * *

📜 许可与声明
--------

本项目仅用于技术学习与交流，请遵守当地法律法规与网站使用条款，勿用于任何商业或非法用途。
