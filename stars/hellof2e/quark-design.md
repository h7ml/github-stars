---
project: quark-design
stars: 1936
description: Browser-native component library, framework-agnostic, base on web components.(企业级 H5 UI 组件库，无框架，即插即用。)
url: https://github.com/hellof2e/quark-design
---

Quark Design
------------

Next-gen frontend component library, it can be used in any framework or no framework.

哈啰集团面向 C 端 UI 组件库，支撑哈啰几乎所有 C 端 H5 项目，包括交易，支付，两轮，商城等。这是一个设计轻盈优雅的企业级 UI 组件库，可以满足日常所需所有基础组件，且支持跨技术栈运行。

English | 简体中文

* * *

Features
--------

🚀 Cross framework: Any front-end framework can be used.

❤️ Lightweight: Crafted with minimalistic Code design.

⚡️ Fast: Native HTML/CSS/JS build.

Documentation
-------------

For full documentation, visit https://quark-ecosystem.github.io/quarkd-docs.

Install
-------

npm install quarkd

Usage example
-------------

import "quarkd/lib/button";

// like a normal div tag \`<div>xx</div>\`, can be used in any browser.
<quark-button type\="primary" onclick\="onClick"\>
  Button
</quark-button\>;

// react
<quark-button type\="primary" onClick\="onClick"\>Button</quark-button\>

// vue
<quark-button type\="primary" @click\="onClick"\>Button</quark-button\>

// svelte
<quark-button type\="primary" on:click\="{onClick}"\>Button</quark-button\>

// angular
<quark-button type\="primary" (click)\="onClick"\>Button</quark-button\>

Vs Code plugin
--------------

Visual Studio | Marketplace

Community
---------

For help, discussion about best practices, or any other conversation that would benefit from being searchable:

Discuss Quark design on Github

Contributing
------------

If you're interested in contributing to quark design, please read our contributing docs **before submitting a pull request**.
