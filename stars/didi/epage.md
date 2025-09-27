---
project: epage
stars: 490
description: 一款基于schema的低代码可视化页面配置工具
url: https://github.com/didi/epage
---

Epage
=====

一款基于schema的可视化页面配置工具。可基于流行的前端组件库配置表单、页面等。

English Introduction | 中文介绍

推荐
--

大家在遇到bpm流程相关的问题时，推荐结合贺波老师的书《深入Activiti流程引擎：核心原理与高阶实战》，这本书对系统学习和深入掌握Activiti/Flowable的用法非常有帮助。

文档
--

官网：http://epage.didichuxing.com

-   快速起步
-   开发文档
-   设计器API
-   如何开发widget?
-   在线示例

演示地址
----

-   **Demo**

安装
--

此库提供设计器界面及基本交互，是pc端设计器核心依赖，移动端渲染器可以不依赖此库。widget能力及工具面板内容需配合渲染器一起使用，如epage-iview，用户最终使用仅使用渲染器包即可。

开发移动端渲染的话可以直接引入epage-core即可（因为仅完成渲染功能即可，不需要拖动配置界面）。

开发自定义widget推荐通过脚手架 epage-cli 方式创建

# 全局安装
npm i -g epage-cli
# 初始化项目
epage init myWidgets
cd myWidgets
# 启动
npm start

# 需提前安装vue vuex iview vuedraggable
npm install epage -S
# 或者 yarn add epage

仓库更新说明
------

本仓库为`Epage渲染器`及`Epage设计器`核心依赖，更新日志查看CHANGLOG。

更多`Epage渲染器`及相关工具参见：https://github.com/epage-team。

设计器及渲染器示例
---------

import { render } from 'epage-core'
import Epage from 'epage'
import pcWidgets, { entry as PCEntry } from 'epage-iview'
import h5Widgets, { entry as H5Entry } from 'epage-vant'
import 'iview/src/styles/index.less';
import 'vant/lib/index.less' /\* 双端设计才需要 \*/
import 'epage/src/style/main.less'
import 'epage-iview/src/style/main.less'
import 'epage-vant/src/style/main.less' /\* 双端设计才需要 \*/

const el \= document.getElementById('root')
// 实例化设计器，Render为渲染器，widgets为待注册的页面部件
// 关于 Render 和 widgets，可以访问 https://github.com/epage-team/epage-iview
const config \= {
  el,
  pc: {
    widgets: pcWidgets,
    Render: render.VueRender,
    component: PCEntry
  },
  // 移动端同时设计时才需要
  h5: {
    widgets: h5Widgets,
    Render: render.VueRender,
    component: H5Entry
  }
}
new Epage(config)

更多用法参考CHANGELOG#v0.7.0

**epage-iview** 为基于 **iview** 组件库的 epage 渲染器实现

设计理念
----

通过schema方式描述页面功能、展示及交互，以可视化方式配置生成schema，最终生成页面。

项目起源于流程表单场景，定制开发每一个表单成本太高且维护性差，最主要是实施人员希望通过可视化方式配置生成表单。基于此场景，在开发中我们发现，表单场景与其他一些页面（如列表页、详情页、图表报表等）场景非常相似，都应该可以通过可视化方式配置出来，从而达到组件复用、灵活配置、方便维护等效果。在使用过程中，业务的复杂远不是基础组件能覆盖的，于是要求需要具备很强的扩展性，以便定制业务组件，有些项目甚至还使用了不同前端框架。

epage的设计器及渲染器分别基于原生dom节点设计，使得设计器及渲染器分离，结合统一的schema规范，实现一次设计多处渲染。关于如何定制开发widget可以访问 如何开发widget?

License
-------

MIT
