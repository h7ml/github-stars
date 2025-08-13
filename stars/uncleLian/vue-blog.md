---
project: vue-blog
stars: 241
description: 🎉 基于vue全家桶 + element-ui 构建的一个后台管理集成解决方案
url: https://github.com/uncleLian/vue-blog
---

vue-blog
========

简介
--

vue-blog 是基于 vue.js，配合使用 element-ui 组件库的一个前端管理后台集成解决方案。它使用了目前主流的技术栈，提供了丰富的功能组件，它可以帮助你快速搭建企业级中后台产品原型。

-   在线访问
-   使用文档

注：本项目的定位是后台集成方案，不适合当基础模板来进行二次开发。你可以把它当做工具集，在基础模板上进行开发时，想要什么功能或者组件就去复制过来。

-   基础模板：vueBlog-template

前序准备
----

你的本地环境需要安装 Node 和 Git，本项目技术栈基于 ES2015+、vue、vue-router、vuex、axios 和 element-ui，所有的请求数据都使用 mock.js 模拟，提前了解和学习这些知识会对使用本项目有很大的帮助。

如果你是Vue初学者，这里有一些资源可以帮助到你

-   新手向 Vue 2.0 的建议学习顺序
-   ES6入门 阮一峰
-   Vue入门项目系列

功能
--

功能持续迭代中，欢迎 pr 和 issue

```
* 核心功能
    - 登录/注销
    - 权限验证
        - 页面级权限
        - 按钮级权限
    - 多环境
        - dev
        - prod
        - stage
    - 动态侧边栏
    - 动态面包屑
    - 导航标签
    - 错误处理
        - 401
        - 404
        - 错误日志
    - 其他处理
        - axios封装
        - cache封装
        - 页面平滑过渡
        - css预处理器全局变量
        - 包体积优化
    - svg icon / iconfont

* 其他扩展
    - mock
    - 引导页
    - 图钉
    - 返回顶部
    - 动态数值
    - 进度条
    - 剪切板
    - 富文本编辑器
    - Markdown编辑器
    - 动态换肤
    - 全屏化
    - 国际化多语言
    - 文件处理
        - 导入Excel
        - 导出Excel
        - 导出Zip
    - 拖拽功能
        - 拖拽弹框
        - 拖拽表格
        - 拖拽列表
    - 单个弹框

```

开发
--

# 克隆项目
git clone https://github.com/uncleLian/vue-blog.git

# 安装依赖
npm install

# 启动服务：localhost:8002
npm run dev

发布
--

# 构建测试环境
npm run build:stage

# 构建生产环境
npm run build

# 查看构建报告
npm run build:report

版本日志
----

发行说明中记录了每个版本的详细更改。

Browsers support
----------------

  
IE / Edge

  
Firefox

  
Chrome

  
Safari

  
Opera

IE10, IE11, Edge

last 2 versions

last 2 versions

last 2 versions

last 2 versions

捐赠
--

如果觉得这个项目帮助到了你，你可以请作者喝杯饮料表示支持 💚

交流
--

欢迎热爱学习、忠于分享的朋友一起来交流

-   Vue交流群：338241465

License
-------

MIT

Copyright (c) 2018-present，uncleLian
