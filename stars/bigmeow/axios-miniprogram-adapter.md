---
project: axios-miniprogram-adapter
stars: 301
description: :lollipop: axios的小程序适配器，以便于在小程序中使用axios，支持微信、支付宝、钉钉、百度小程序
url: https://github.com/bigmeow/axios-miniprogram-adapter
---

axios的小程序适配器，支持在各个平台小程序中使用axios.

Taro 适配器请点击这里

⭐ 特性
----

-   支持微信、支付宝、钉钉、百度小程序，放心使用axios，最大限度复用web端axios的代码
-   支持TypeScript

微信小程序

支付宝小程序

钉钉小程序

百度小程序

催更、钉钉交流群：
---------

📂 目录介绍
-------

```
.
├── demo 使用demo
├── dist 编译产出代码
├── doc 项目文档
├── src 源代码目录
├── test 单元测试
├── CHANGELOG.md 变更日志
└── TODO.md 计划功能
```

🚀 使用者指南
--------

### 1.如果你是webpack等环境

通过npm下载安装代码

$ npm i axios axios-miniprogram-adapter

import axios from 'axios'
import mpAdapter from 'axios-miniprogram-adapter'
axios.defaults.adapter \= mpAdapter
// or with extra config transformer
axios.defaults.adapter \= config \=> mpAdapter(config, { transformRequestOption: requestOption \=> { /\* modify requestOption here \*/ return requestOption } })

### 2.如果你没有使用任何脚手架工具

直接使用小程序开发工具自带的`构建npm`，请按下面几个步骤引入：

-   确保项目目录下有package.json文件，已有的跳过这一步

$ npm init

-   安装

```
$ npm i axios axios-miniprogram-adapter
```

-   在小程序开发者工具中依次找到并点击`工具`\->`构建npm`，构建完成后你的项目目录会多出一个`miniprogram_npm`目录
    
-   代码引入使用
    

import axios from 'axios'
import mpAdapter from 'axios-miniprogram-adapter'
axios.defaults.adapter \= mpAdapter

这里有一个代码片段demo可直接供你使用:https://developers.weixin.qq.com/s/oIqQtBml7F4N,DEMO源码点这里也可查看

### 3.如果你没有使用任何脚手架工具且npm也不用(不推荐)

直接拷贝编译后的axios、axios-miniprogram-adapter到项目中:

import axios from '你的目录/axios.js'
import mpAdapter from '你的目录/axios-miniprogram-adapter.js'
axios.defaults.adapter \= mpAdapter

### 三种方式区别

小程序自带的npm不支持解析node\_modules中的库再有外部依赖：例如本库中依赖了`axios`库的某些工具包，在源码中有下面的代码：

import utils from 'axios/lib/utils'

在小程序开发工具中会报错，找不到此依赖。为此，我将依赖打包到一起，这样带来的问题是库的体积多了2kb，基于此，强烈推荐你使用类似于webpack的脚手架工具开发

📑 文档
-----

-   同axios官方仓库一致
-   与官方API的差异、注意事项

🌰 Demo
-------

打开小程序开发者工具，根据不同平台，选择各自的目录作为项目根目录：

-   微信`axios-miniprogram-adapter/demo/miniprograme-example/dist-wechat`
-   支付宝、钉钉`axios-miniprogram-adapter/demo/miniprograme-example/dist-alipay`
-   百度 `axios-miniprogram-adapter/demo/miniprograme-example/dist-swan`

该demo示范了几个常用功能的用法:

点击查看代码具体用法示例

⚙️ 更新日志
-------

CHANGELOG.md

✈️ 计划列表
-------

TODO.md
