---
project: pinyin
stars: 7757
description: :cn: 汉字拼音 ➜ hàn zì pīn yīn
url: https://github.com/hotoo/pinyin
---

README
======

pīnyīn, 汉字拼音转换工具。

目录结构
----

这是一个 monorepo，使用 turbo + pnpm 进行管理，目录结构如下：

```
|- apps/
|  `- website               // 文档站点
|- packages/
|  |- pinyin/               // pinyin 主仓库
|  |- pinyin-cli/           // 命令行工具，可以全局安装，并在命令行中随处使用。
|  |- pinyin-react/         // pinyin React 版本，即将推出。
|  `-tools/                 // 其他配套杂项。
|- package.json
`- README.md
```

pinyin.js.org
-------------

pīnyīn 项目主站，网址 pinyin.js.org，代码仓库 @hotoo/pinyin/apps/website， 主要展示 pinyin 项目的文档、演示、工具等。

pinyin
------

pinyin 项目核心代码，npm 安装：

npm install pinyin

使用：

import { pinyin } from 'pinyin';

const py \= pinyin('中文');

更多用法请参考 API 文档， 源码 @hotoo/pinyin/packages/pinyin

pinyin-cli
----------

pinyin 命令行工具，可以全局安装在本地随时随处使用。

安装：

npm install pinyin-cli -g

使用：

pinyin 中文
pinyin --help
