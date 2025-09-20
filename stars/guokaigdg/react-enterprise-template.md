---
project: react-enterprise-template
stars: 529
description: 🚀 react模板 react项目模板 React19 + webpack5 + TypeScript5 + mobx6 + react-router7 react 模板 基于react企业级模板 项目模板 简单模板 快速模板 
url: https://github.com/guokaigdg/react-enterprise-template
---

react 模板
========

  

  

简体中文 | English

⚡️ Vite 版本
----------

-   react-template-vite: https://github.com/guokaigdg/react-template-vite

🔗 在线 Demo
----------

-   在线预览 (PC 端) react-enterprise-template
-   在线预览（移动端） react-template-mobile

👨🏻‍💻 项目说明
------------

-   移动端模板：react-template-mobile
    
-   react 模板, 一个比 CRA 更丰富的模板
    
-   开发配置文档说明 React18 + webpack5 + TypeScript4 + react-router + Mobx
    
-   项目创建教程 《从 0 到 1 搭建一个 React 项目开发模板 》
    

🪅 特性
-----

-   📦 开箱即用，无需配置
-   📝 全面注释说明，学习低成本
-   🚀 启动编译迅速
-   🌱 极易定制, 拓展容易

🚀 技术栈
------

-   React v19
-   react-dom v19
-   TypeScript v4
-   webpack v5
-   axios v1
-   mobx v6
-   mobx-react-lite v3
-   react-router v7

🎄 陆续更新内容：
----------

-   新增样式 ✅ config: 🔧  新增样式文件(css/less/sass/postCss)处理
    
-   代码规范 ✅ config: 🔧  新增 Prettier/ESlint/StyleLint/EditorConfig 代码规范
    
-   路由 ✅ config: 🔧 新增路由管理 react-router-dom v6
    
-   网络请求 ✅ feat: ✨  新增网络请求 Axios v1
    
-   数据共享 ✅ feat: ✨  新增状态管理 Mobx v6
    
-   React Hook 规则 ✅ feat: ✨ 新增 react hooks 规则检查
    
-   封装全局 SVG 组件 ✅ feat: ✨ 封装全局 SVG 组件
    
-   移动端适配 ✅ feat: ✨  增加移动端适配方案: postcss-px-to-viewport
    
-   Mobx 使用区别说明 ✅ feat: ✨  增加 makeObservable 与 makeAutoObservable 说明与使用示例
    
-   mobx-react-lite 优化 ✅ feat: ✨  新增 mobx-react-lite 中 observer 与 Observer 使用与优化
    
-   新增 UI 设计资料 ✅ docs: 📝  更新开发设计资料参考文档
    
-   现代化的 CSS 样式重置 ✅ style: 🎨 A Modern CSS Reset 现代化的 CSS 样式重置
    

⌛️ 安装项目依赖
---------

-   `node` >= 16.0.0
-   `npm` >= 7.0.0
-   `yarn` >= 1.22.17

```
npm install
```

```
yarn
```

```
pnpm install
```

🚀 运行项目
-------

```
npm
$ npm run start

yarn
$ yarn dev
```

📦 打包编译
-------

```
npm run build:qa  // 测试环境
npm run build:prod  // 线上环境
```

🏷 分支说明
-------

分支

说明

main

主分支

dev

开发分支

deploy

demo 部署分支

代码提交规范
------

```
git <type>: <subject>
git commit -m “feat: 项目初始化”
```

### type 参考:

```
fix       🐛 Bug修复
feature   ✨ 引入新特性
docs      📝 文档书写改动
prune     🔥 移除代码或文件
perf      ⚡ 性能相关优化
rocket    🚀 部署功能
style     💄 style修改
init      🎉 初始化提交
release   🔖 发布版本
wip       🚧 正在进行中, 且有可能出现不稳定运行的提交
config    🔧 修改配置文件
refactot  🔨 重构(既不增加新功能, 也不修改bug的代码改动)
merge     🔀 合并分支
```

📂 目录结构
-------

```
    ├── .vscode
    │   └──setting.json                 # 先于vscode全局的settings.json配置
    ├── doc                             # 开发文档记录
    ├── webpack                         # 打包编译
    │   └──config                       # webpack配置
    │       ├── webpack.common.js       # 基础配置
    │       ├── webpack.dev.js          # 开发环境配置
    │       └──webpack.prod.js          # 生产环境配置
    ├── pubilc
    │   ├──favicon.ico                  # HTML图标
    │   └──index.html                   # HTML入口模板
    ├── src
    |   ├── api                         # 接口配置
    |   ├── assets                      # 静态资源
    │   ├── components                  # 项目通用通用组件
    │   ├── http                        # 请求统一封装
    │   ├── httpinterface               # ts类型定义
    │   ├── constData                   # 系统内的常量列表
    │   ├── router                      # 统一路由入口
    │   ├── store                       # 数据共享
    │   ├── styles                      # 全局样式
    │   ├── utils                       # 工具库
    │   ├── view                        # 页面
    │   ├── App.tsx                     # 主界面
    │   └──index.tsx                    # 入口文件
    ├── .babelrc.js                     # babel配置
    ├── .editorconfig                   # 跨编辑器维护一致编码风格
    ├── .env.json                       # 环境变量配置
    ├── .eslintignore                   # ESLint忽略检测文件
    ├── .eslintrc.js                    # ESLint配置
    ├── .gitignore                      # git提交忽略文件
    ├── .npmrc
    ├── .prettierignore                 # prettierc忽略文件
    ├── .prettierrc                     # prettierc配置
    ├── .stylelintrc.js                 # 代码风格配置
    ├── LICENSE                         # 开源协议
    ├── package-lock.json               # npm安装包锁定管理
    ├── package.json                    # 依赖包管理
    ├── README.md                       # 项目说明
    ├── tsconfig.json                   # ts配置文件
    └── yarn.lock                       # yarn安装包锁定管理

```

📚 开发资料参考
---------

-   开发资料参考

🤝 如何贡献
-------

-   📬 有问题直接 issues 或者留言
-   🧙‍♀️ 欢迎所有的贡献者，快来 Issus 或 Pull requests 成为贡献者吧
-   🙋 查看如何贡献代码

💡 开源协议
-------

该项目的代码和文档基于  MIT License  开源协议。
