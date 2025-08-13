---
project: awesome-f2e-libs
stars: 1568
description: 🎉 整理我平时关注的前端库。
url: https://github.com/sorrycc/awesome-f2e-libs
---

awesome-f2e-libs
================

打包工具
----

-   **webpack** - 打包项目。
-   **rollup** - 打包 npm 库。
-   **parcel** - webpack 竞品，但发展前景不乐观，再观察一段时间。
-   **systemjs** - 针对一些特殊场景会比较有用，比如云 ide，支付宝小程序 IDE 等。
-   **microbundle** - 基于 rollup，简化配置。
-   **bili** - 基于 rollup，同上。
-   **father** - 组件打包工具，提供 babel 和 rollup 两种打包方式。
-   **vue-cli** - vue 命令行工具。
-   **create-react-app** - react 官方脚手架。
-   **prepack** - 通过预先执行的方式优化打包结果。
-   **lebab** - 把 es5 代码转成 es6，反向 babel。
-   **esm-to-cjs** - 把 esm 转成 cjs。
-   **tsdx** - Zero-config CLI for TypeScript package development.

### webpack 辅助工具、Loader 和插件

-   **webpack-dev-server** - webpack 开发服务器。
-   **webpack-dev-middleware** - webpack 中间件。
-   **webpack-merge** - 合并 webpack 配置。
-   **webpack-chain** - 通过 chain 风格 api 的方式修改 webpack 配置。
-   **svgr** - svg 转 react 组件。
-   **postcss** - CSS 界的 babel。
-   **autoprefixer** - 为 CSS 选择权自动加 prefix。
-   **cssnano** - CSS 压缩，也有类 preset 的概念。
-   **mini-css-extract-plugin** - 提取 CSS 为单独文件。
-   **webpackbar** - webpack 进度条。
-   **webpack-bundle-analyzer** - 构建产物占比分析。
-   **uglifyjs-webpack-plugin** - JS 压缩，产物为 ES5 语法。
-   **terser-webpack-plugin** - JS 压缩，产物为 ES6 语法。
-   **webpack-manifest-plugin** - 生成 manifest.json。
-   **copy-webpack-plugin** - 复制额外的文件到输出目录。
-   **case-sensitive-paths-webpack-plugin** - 大小写敏感检测，能规避一些问题，但构建时性能消耗较大。
-   **css-hot-loader** - CSS 热更新，搭配 mini-css-extract-plugin 使用。
-   **duplicate-package-checker-webpack-plugin** - 重复依赖检测。
-   **fork-ts-checker-webpack-plugin** - ts 语法检测。
-   **speed-measure-webpack-plugin** - 统计 webpack 各阶段耗时。

### Bundless

-   **vite**
-   **snowpack** - 浏览器里跑 npm 依赖，面向现代浏览器。
-   **es-dev-server**

### 非 JavaScript 编译工具

-   **boa** - 基于 Rust，嵌入式 Javascript 引擎。
-   **cjs-module-lexer** - 通上，cjs 模块解析，也可以用 cjs-module-lexer-rollup-reexports。
-   **deno\_lint** - 基于 Rust，支持 JavaScript 和 TypeScript 的 lint 工具。
-   **dprint** - 基于 Rust，代码格式化工具，Prettier 替代品。
-   **elsa** - 基于 Go，JavaScript 和 TypeScript 的 runtime。
-   **es-module-lexer** - 基于 C，输出 Web Assembly，esm 模块解析。
-   **esbuild** - 基于 Go，Webpack 替代品。
-   **esbuild-node-tsc** - 用 esbuild 编译 TypeScript 项目，但不支持类型检测。
-   **markdown-wasm** - 基于 wasm 的 markdown 解析工具。
-   **minify** - 基于 Go，压缩器，支持 HTML5、CSS3、JS、JSON、SVG 和 XML。
-   **paperclip** - 基于 Rust 和 WAMS，React 视图组件的快速编译和预览。
-   **RSLint** - 基于 Rust，lint 工具。
-   **sucrase** - 基于 Rust，Babel 替代品。
-   **swc** - 基于 rust 的语法转换器，babel 的竞争者。
-   **swc-node**
-   **quick-lint-js** - 基于 C++。
-   **markdown-wasm** - 基于 wasm 的 markdown 解析工具。

包管理
---

-   **npm**
-   **yarn** - 我用这个。

babel
-----

-   **babel**
-   **babel-plugin-dynamic-import-node** - 有些场景下会需要禁用 `import()` 语法。
-   **babel-plugin-macros** - 前端文件写 node 逻辑。
-   **babel-plugin-rawest** - React 的 DOM 直出方案。
-   **babel-plugin-react-require** - 自动为 jsx 语法加 react 引用。
-   **babel-plugin-transform-react-remove-prop-types** - 删除 prop-types，生产环境用。

### macros

-   **import-all.macro**

测试
--

-   **jest**
-   **ts-jest**
-   **enzyme**
-   **jsdom**
-   **puppeteer**
-   **react-test-rerender** - 官方出品。
-   **react-testing-library** - kentcdodds 出品。

框架
--

-   **react**
-   **vue**
-   **next.js**
-   **nuxt.js**
-   **gastby**
-   **umi** - 蚂蚁金服的前端框架，我目前在维护。
-   **rekit** - IDE and toolkit for building scalable web applications with React, Redux and React-router.
-   **choo** - dva 最初的 API 是参考这个实现的，已经不怎么发展了，再关注一段时间。
-   **taro** - 用 React 写小程序，适配微信和支付宝等。
-   **after.js**
-   **mint** - 提供了语言层方案的框架。
-   **quasar** - 基于 vue，一套代码多处适用。

react 相关库
---------

-   **preact** - 轻量级 React 实现。
-   **inferno** - 轻量级 React 实现。
-   **react-router** - React 路由方案。
-   **reach-router** - React 路由方案，较新，优势是可访问性。
-   **router5** - 通用的路由方案。
-   **react-loadable** - 按需加载 react 组件。
-   **ant-design** - 蚂蚁金服的 React UI 库。
-   **material-ui** - UI 库。
-   **react-intl** - React 的国际化方案。
-   **react-dnd** - 拖拽实现。
-   **react-helmet** - 修改 html 的 header 内容。
-   **react-jsonschema-form** - A React component for building Web forms from JSON Schema.

vue 相关库
-------

-   **vue-router**

工具类
---

-   **history**
-   **path-to-regexp** - path 转正则，路由相关处理的底层库。
-   **lodash** - 工具集合。
-   **fastclick**
-   **date-fns** - 时间处理。

数据流
---

-   **dva** - 我写的数据流，基于 redux。
-   **jotai**
-   **immer**
-   **mobx**
-   **ngrx**
-   **recoil**
-   **redux**
-   **redux-toolkit**
-   **rxjs**
-   **rematch** - 基于 redux。
-   **unstated**
-   **valtio**
-   **vuex**
-   **xstate**
-   **zustand**

### redux 扩展

-   **react-redux** - 绑定 react 和 redux。
-   **redux-saga**
-   **redux-persist**
-   **redux-bundler**
-   **redux-box**

性能优化
----

-   **workbox** - PWA 方案，Google 出品。
-   **critical** - 提取关键 CSS。

语言
--

-   **typescript**
-   **flow**
-   **graphql**

文档
--

-   **dumi**
-   **vuepress**
-   **docz**
-   **storybook**
-   **mdx** - jsx + markdown。

工程
--

-   **lerna** - monorepo 管理。
-   **lerna-changelog** - 为 lerna 项目自动生成 changelog。
-   **eslint** - JS 风格约束。
-   **eslint-config-airbnb**
-   **xo** - 封装自 eslint。
-   **prettier** - 更主观的风格自动修改。
-   **yeoman-generator** - 脚手架工具。
-   **serve** - 本地静态服务器。
-   **servor** - 另一个静态服务器。
-   **budo** - 又一个静态服务器。
-   **np** - npm publish 辅助，自动 push、打 tag、升版本等。
-   **lint-staged** - eslint 提速，只 lint 提交的代码。
-   **coveralls** - 覆盖率。
-   **husky** - 添加 git hooks。
-   **cross-env** - 跨平台的环境变量声明。
-   **projj** - 本地 git 项目管理，支持 github 和 gitlab。
-   **nvm** - 管理 node 版本。
-   **concurrently** - 在 npm scripts 里并行执行命令。
-   **@zeit/ncc** - 打包为 npm 包为一个文件。
-   **npm-check** - 检测依赖升级情况，我会和 `yarn upgrade-interactive` 配合着用，主要用来检测冗余依赖。
-   **cpx** - 复制，支持 glob，并且可以 watch。
-   **onchange** - 监听文件变动然后做一些事。
-   **just** - 微软出的任务管理器。
-   **tern** - 代码分析器，为不少编辑器服务。
-   **lightproxy** - 底层协议代理工具，跨平台。

编辑器
---

-   **VSCode**
-   **IntelliJ IDEA** - 我用这个。
-   **codesandbox**
-   **stackblitz**

CloudIDE
--------

-   **che**
-   **codesandbox-client**
-   **theia**

字体
--

-   **Dank Mono**
-   **FiraCode**
-   **Operator Mono**

CSS
---

-   **css modules**
-   **emotion**

命令行
---

-   **ajv** - 参数校验。
-   **chalk** - 输出不同颜色。
-   **cheerio** - 用类 jQuery 语法处理 HTML。
-   **chokidar** - 文件监听。
-   **clipboardy** - 复制文本到粘贴板。
-   **debug** - 打印调试信息。
-   **depd** - 给出 deprecated 警告。
-   **deprecate** - 给过期警告。
-   **enquirer** - 同上，更 cool 一些。
-   **execa** - 比 child\_process 好用，返回 Promise。
-   **figures** - ✔︎ 等特殊字符，做了 windows 兼容处理。
-   **glob** - 文件查找。
-   **ink** - 用 React 处理命令行输出。
-   **inquirer** - 交互式命令接口，比如 prompt。
-   **ora** - 控制命令行光标，显示 loading 等。
-   **rimraf** - 删除文件。
-   **signale** - 漂亮的日志打印。
-   **semver** - semver 版本处理。
-   **tiny-glob** - 文件查找。
-   **update-notifier** - 更新提醒。
-   **why-is-node-running** - 检查 node 没退出的原因。
-   **yargs** - 命令行入口套件。
-   **yargs-parser** - 命令行参数解析。

请求处理
----

-   **axios**
-   **got**
-   **request**
-   **reqwest**
-   **urllib**
-   **whatwg-fetch**

压缩解压缩
-----

-   **compressing** - 压缩和解压缩。
-   **tar-fs** - tar 的压缩和解压缩。
-   **yauzl** - zip 解压缩。
-   **yazl** - zip 压缩。

语法解析
----

-   **esquery** - 语法树查询。

Markdown
--------

-   **markdown-it** - Markdown 转 HTML。
-   **remark** - Markdown 语法解析器。

其他
--

-   **electron**
-   **fx** - 交互式 JSON 查看。
-   **DeskGap** - 类 electron，由于不包含浏览器的部分，所以产物更小

rtfs
----

-   **eslint/rfcs**
-   **gastbyjs/rfcs**
-   **npm/rfcs**
-   **nuxtjs/rfcs**
-   **reactjs/rfcs**
-   **vuejs/rfcs**
-   **yarnpkg/rfcs**

相关
--

-   awesome-tools - 我在用的工具。
