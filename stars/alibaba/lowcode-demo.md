---
project: lowcode-demo
stars: 1841
description: An enterprise-class low-code technology stack with scale-out design / 一套面向扩展设计的企业级低代码技术体系
url: https://github.com/alibaba/lowcode-demo
---

Low-Code Engine Demo
--------------------

demo 是一个组合内核、setter、插件、物料的示范工程，因为未经长期生产环境打磨，可能还会有一些各个模块间结合的 bug，希望大家理解~

如何使用
----

目前包含多个独立 demo 工程目录，每个 demo 目录都是一个独立的工程，代表一个特定的 demo 场景，可以选择其一单独使用。

\[推荐\]使用yarn

git clone git@github.com:alibaba/lowcode-demo.git
cd lowcode-demo
cd demo-general
yarn
yarn run start

使用npm

git clone git@github.com:alibaba/lowcode-demo.git
cd lowcode-demo
cd demo-general
npm install
npm run start

场景列表：

-   general：此 demo 尽可能将引擎常用能力展示出来，在试用时建议使用该 demo 工程，其他 demo 均各有侧重展示内容。
-   basic-fusion：此 fusion 的元数据描述是很老的版本，只为了示意描述结构，请勿用于生产环境
-   basic-antd
-   node-extended-actions
-   next-pro
-   lowcode-component
-   lowcode-workspace

更多参考资料：

-   马上玩一下
-   低代码引擎官网
-   引擎主仓库
