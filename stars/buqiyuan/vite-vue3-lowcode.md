---
project: vite-vue3-lowcode
stars: 3362
description: vue3.x + vite2.x + vant + element-plus H5移动端低代码平台 lowcode 可视化拖拽 可视化编辑器 visual editor 类似易企秀的H5制作、建站工具、可视化搭建工具
url: https://github.com/buqiyuan/vite-vue3-lowcode
---

基于 Vite2.x + Vue3.x + TypeScript H5 低代码平台
=========================================

**中文** | English

### 目前还只是一个简单的模板，后面可能会引入较为完善的机制系统，感兴趣的小伙伴可以根据自己的需要去调整, 通过这个项目或许你可以接触到 vue3 很多有趣的新特性和玩法。

`PS: 此项目为个人半年以前做的实验性小玩具，使用的都是最新的技术栈，后面由于个人时间问题，没有持续维护和完善，暂时计划于2022年下半年开始对项目进行整体的重构和重新设计，实现一个基本可用的简易低代码平台。感谢关注~`

计划实现：
-----

-   操作历史快照
-   支持生成 vue 模板组件
-   生成组件大纲树
-   提供常见的表单和列表模板
-   v-for 绑定数据源
-   在 sandbox 中执行自定义逻辑
-   基于 monaco-editor 自定义代码补全规则
-   基于 vue3 createRenderer 自定义渲染器
-   使用 Schema 描述数据结构（因为 schema 可以生成校验函数）
-   (⊙o⊙)…想到再做了~

### 模型驱动的视图

从最简单的结构来看，一个模型驱动的视图体系包含以下要素：

-   模型
    
    -   定义状态结构
    -   定义动作
-   视图
    
    -   订阅状态
    -   触发动作

这是很简单的一种渲染模式，可以适用于大多数的场景。

克隆项目
----

git clone --single-branch https://github.com/buqiyuan/vite-vue3-lowcode.git
or
git clone --depth=1 https://github.com/buqiyuan/vite-vue3-lowcode.git

cd vite-vue3-lowcode

pnpm install

-   run

pnpm serve

-   build

pnpm build

技术栈
---

-   编程语言：TypeScript 4.x + JavaScript
-   构建工具：Vite 2.x
-   前端框架：Vue 3.x
-   路由工具：Vue Router 4.x
-   状态管理：Vuex 4.x
-   PC 端 UI 框架：Element Plus
-   H5 端 UI 框架：vant
-   CSS 预编译：Stylus / Sass / Less
-   HTTP 工具：Axios
-   Git Hook 工具：husky + lint-staged
-   代码规范：EditorConfig + Prettier + ESLint + Airbnb JavaScript Style Guide
-   提交规范：Commitizen + Commitlint
-   单元测试：vue-test-utils + jest + vue-jest + ts-jest
-   自动部署：GitHub Actions

### 功能清单

-   动态添加页面
-   拖拽式生成组件
-   service worker + indexeddb 实现无服务端的前端交互
-   数据源管理(支持导入 swagger JSON 生成数据模型及接口)
-   提供预置函数
-   更多组件的封装
-   其他...

### 简易说明

目前在使用表单时，需要把相关的`表单控件`放到`表单容器`内部，并且需要将`按钮`放到`表单容器`内，然后再讲`按钮的type`设置为`表单提交按钮`这时候点击提交按钮才会自动收集表单容器内部的所有字段和值

### 快速生成组件属性

// 在vant文档中 chrome控制台输入以下代码，快速生成组件属性
let propObj \= {
  string: (config) \=> \`createEditorInputProp(${JSON.stringify(config)})\`,
  number: (config) \=> \`createEditorInputNumberProp(${JSON.stringify(config)})\`,
  boolean: (config) \=> \`createEditorSwitchProp(${JSON.stringify(config)})\`,
};

JSON.stringify(
  $$('#props + table tbody tr').reduce((prev, curr) \=> {
    const children \= curr.children;
    const key \= children\[0\].textContent.replace(/\-(\[a\-z\])/g, (all, i) \=> i.toUpperCase());
    const child3Text \= children\[3\].textContent;
    const defaultValue \= \['true', 'false'\].includes(child3Text)
      ? child3Text
      : \`'${child3Text \== '-' ? '' : child3Text}'\`;
    const value \= (propObj\[children\[2\].textContent\] ?? propObj\['string'\])({
      label: \`'${children\[1\].textContent}'\`,
      defaultValue,
    }).replaceAll('"', '');
    prev\[key\] \= value;
    return prev;
  }, {}),
).replaceAll('"', '');

// 在vant文档中 chrome控制台输入以下代码，快速生成组件事件
JSON.stringify(
  $$('#events + table tbody tr').reduce((prev, curr) \=> {
    const children \= curr.children;
    const event \= {
      label: children\[1\].textContent,
      value: children\[0\].textContent,
    };
    return prev.concat(\[event\]);
  }, \[\]),
)
  .replaceAll(/(?<!:)\\"(?!,|})/g, '')
  .replace(/\\"/g, "'");

部分功能演示
------

浏览器支持
-----

本地开发推荐使用`Chrome 80+` 浏览器

支持现代浏览器, 不支持 IE

  
IE

  
Edge

  
Firefox

  
Chrome

  
Safari

not support

last 2 versions

last 2 versions

last 2 versions

last 2 versions

### 提交规范

-   `feat` 增加新功能
-   `fix` 修复问题/BUG
-   `style` 代码风格相关无影响运行结果的
-   `perf` 优化/性能提升
-   `refactor` 重构
-   `revert` 撤销修改
-   `test` 测试相关
-   `docs` 文档/注释
-   `build` 对构建系统或者外部依赖项进行了修改
-   `chore` 依赖更新/脚手架配置修改等
-   `workflow` 工作流改进
-   `ci` 持续集成
-   `types` 类型定义文件更改
-   `wip` 开发中
