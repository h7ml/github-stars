---
project: node-examples
stars: 93
description: 学习 node.js 最好的示例代码
url: https://github.com/shfshanyue/node-examples
---

关于 node.js 学习过程中的示例
===================

Node.js 版本最好使用 `node v16` 或者 `node v18`，强烈不建议使用 `node v14`。见下图：

> 图出自 nodejs/Release

$ git clone git@github.com:shfshanyue/node-examples.git

# 进入到示例文件根目录
$ cd node-examples

# 在根目录直接装包
$ npm i

# 进入对应的目录，可使用 autojump 快速进入目录
$ cd engineering/webpack/cjs

# 执行对应的文件，查看文件中的示例及注释
$ node build.js

> 由于目录嵌套较深，可使用 autojump 或者 zoxide 快速跳转目录。

目录结构
----

-   node-native: 关于 node.js 的原生模块
-   node-server: 关于 node.js 作为服务端的代码
-   cc: 关于一些简单的 cc 示例
-   go: 关于一些简单的 go 示例
-   webpack: 关于一些简单的 webpack 示例
-   data-structure: 关于基础的数据结构示例
