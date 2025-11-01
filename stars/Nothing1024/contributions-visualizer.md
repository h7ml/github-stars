---
project: contributions-visualizer
stars: 1
description: null
url: https://github.com/Nothing1024/contributions-visualizer
---

📊 Contributions Visualizer
===========================

> GitHub 风格的多平台活跃度热力图生成器

这是什么?
-----

一个扫描你本地 Claude Code、Codex 使用记录并结合 GitHub 活动,生成 GitHub 风格贡献热力图的工具。

**特色**:

-   🎨 支持横纵布局
-   🚀 一键同步到 GitHub (自动 commit + push)
-   📊 多种展示模式 (纵向/横向布局)
-   🔒 隐私优先 (本地扫描)
-   🔗 支持 iframe 嵌入

预览效果
----

快速开始
----

### 1\. 安装依赖并配置环境变量

npm install
cp .env.example .env
# 编辑 .env,添加: VITE\_GITHUB\_USERNAME==your\_github\_name

配置环境变量

### 2\. 生成数据

# 🚀 推荐: 一键扫描 + 自动提交到 GitHub
npm run sync

# 或者只生成数据 (不提交 Git)
npm run update

# 或者使用脚本 (Windows)
.\\sync.cmd

# 或者使用脚本 (Linux/macOS)
./sync.sh

### 3\. 查看效果

npm run dev
# 打开 http://localhost:5173

核心功能
----

### 多平台支持

-   ✅ **Claude Code**: 扫描 `~/.claude` 目录
-   ✅ **Codex**: 扫描 `~/.codex` 目录
-   ✅ **GitHub**: 通过 GitHub API 获取提交记录

### 一键同步

npm run sync

自动完成: 扫描数据 → 生成 JSON → Git commit → Git push

### 移动端优化

-   📱 **自适应布局**:
    -   竖屏 (portrait): 单列纵向布局
    -   横屏 (landscape): 三列紧凑布局
-   📏 **响应式尺寸**: 根据屏幕宽度自动调整热力图单元格大小
-   👆 **滚动优化**:
    -   桌面端: 6px 半透明滚动条
    -   移动端: 完全隐藏滚动条 (保留滑动功能)
    -   默认滚动到最右侧 (显示最新数据)

### 多种导出

-   📸 **PNG 图片**: 高清截图导出
-   📄 **HTML 文件**: 单文件独立页面
-   🔗 **iframe 嵌入**: 生成嵌入代码

配置 GitHub Token (可选)
--------------------

cp .env.example .env
# 编辑 .env,添加: GITHUB\_TOKEN=your\_token\_here

获取 Token: GitHub Settings → Developer settings → Tokens

嵌入到网站
-----

### 纵向布局 (推荐)

<iframe src\="https://your-domain.com/?mode=embed&show=claude,codex,github" width\="100%" height\="640" frameborder\="0"\> </iframe\>

### 横向布局 (紧凑)

<iframe src\="https://your-domain.com/?mode=embed&view=horizontal&show=claude,codex,github" width\="100%" height\="280" frameborder\="0"\> </iframe\>

URL 参数说明
--------

支持通过 URL 参数自定义显示效果:

参数

可选值

默认值

说明

`mode`

`embed` / `normal`

`normal`

嵌入模式 (隐藏导出按钮)

`view`

`vertical` / `horizontal`

`vertical`

布局方向

`show`

`claude,codex,github`

全部显示

显示的平台 (逗号分隔)

示例:

```
https://your-domain.com/?mode=embed&view=horizontal&show=claude,github
```

项目结构
----

```
contributions-visualizer/
├── src/
│   ├── cli/                    # 命令行工具
│   │   ├── index.ts           # CLI 入口
│   │   ├── scanner.ts         # 本地文件扫描
│   │   ├── githubFetcher.ts   # GitHub API 集成
│   │   ├── gitSync.ts         # Git 自动同步
│   │   └── exporter.ts        # 数据导出
│   ├── features/
│   │   └── visualizer/        # 可视化核心
│   │       ├── components/    # React 组件
│   │       ├── data/          # 数据处理
│   │       ├── hooks/         # React Hooks
│   │       └── pages/         # 页面
│   └── shared/                # 共享工具
│       ├── utils/             # 工具函数
│       └── types/             # TypeScript 类型
├── public/
│   └── data.json             # 生成的数据文件
└── scripts/
    └── build-cli.mjs         # CLI 构建脚本
```

技术栈
---

-   **前端框架**: React 19.2 + TypeScript 5.8
-   **构建工具**: Vite 7.1
-   **样式方案**: Tailwind CSS 3.4
-   **CLI 工具**: Commander.js
-   **截图导出**: html2canvas
-   **部署平台**: Vercel (支持)

开发指南
----

### 本地开发

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 预览生产构建
npm run preview

### 构建 CLI 工具

npm run build:cli

### 数据格式

生成的 `data.json` 格式:

{
  "claude": {
    "2025-10-31": 15,
    "2025-10-30": 8
  },
  "codex": {
    "2025-10-31": 12,
    "2025-10-29": 5
  },
  "github": {
    "2025-10-31": 3,
    "2025-10-30": 7
  }
}

部署
--

### Vercel 部署 (推荐)

1.  Fork 本仓库
2.  在 Vercel 导入项目
3.  配置环境变量 (可选):
    -   `GITHUB_TOKEN`: GitHub Personal Access Token
4.  部署完成

### 自定义域名

在 Vercel 项目设置中添加自定义域名即可。

常见问题
----

### Q: 为什么没有扫描到数据?

A: 检查以下路径是否存在:

-   Claude Code: `~/.claude/` (Windows: `%USERPROFILE%\.claude\`)
-   Codex: `~/.codex/` (Windows: `%USERPROFILE%\.codex\`)

### Q: GitHub 数据获取失败?

A: 确保:

1.  已配置 `GITHUB_TOKEN` 环境变量
2.  Token 具有 `repo` 权限
3.  网络连接正常

### Q: 如何自定义颜色方案?

A: 编辑 src/shared/utils/colorScale.ts 中的颜色配置。

### Q: 支持哪些浏览器?

A: 支持所有现代浏览器 (Chrome, Firefox, Safari, Edge)。

贡献指南
----

欢迎提交 Issue 和 Pull Request!

1.  Fork 本仓库
2.  创建特性分支 (`git checkout -b feature/AmazingFeature`)
3.  提交更改 (`git commit -m 'Add some AmazingFeature'`)
4.  推送到分支 (`git push origin feature/AmazingFeature`)
5.  开启 Pull Request

许可证
---

MIT License - 详见 LICENSE 文件

致谢
--

-   灵感来源于 GitHub Contributions Graph
-   感谢 Claude Code 和 Codex 团队提供的优秀工具

更新日志
----

### v1.0.0 (2025-10-31)

-   初始版本发布
-   支持 Claude Code、Codex、GitHub 三平台
-   实现横纵布局切换
-   添加一键同步功能
-   移动端优化
-   支持 PNG/HTML 导出
-   iframe 嵌入支持

* * *

**Star** 本项目如果你觉得有用! ⭐
