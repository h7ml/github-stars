---
project: open_virapi
stars: 39
description: VirAPI（Virtual API）开源版代码仓库。非侵入式虚拟数据在线请求响应生成接口，支持MockJs语法，请求即可得自定义规则的响应数据。帮助开发者，特别是前端开发者，提供很好的快速开发体验。在线服务请访问：http://virapi.com/
url: https://github.com/bluvenr/open_virapi
---

### VirAPI——在线虚拟数据云接口平台

内置MockJs语法支持，请求接口即可获得自定义规则的虚拟数据。帮助开发者，特别是前端开发者，提供很好的快速开发体验。

VirAPI官网 »

  

文章 · 关于 · 控制台

  

VirAPI简介
--------

VirAPI（Virtual API）—— 在线虚拟数据云接口平台；非侵入式虚拟数据在线请求响应生成接口，支持MockJs语法，请求即可得自定义规则的响应数据；帮助你本地测试或演示项目之用。

通过VirAPI你可以通过远程接口URL访问直接获得自定义的随机虚拟响应数据，若是只想做前端客户端（App、小程序、网页等）的功能演示或业务模拟测试，而又不想耗费时间精力去等待后端接口的开发完成，甚至不想搭建后端服务逻辑，那么VirAPI会是你的好帮手。

**VirAPI的功能特色：**

-   内嵌Mock语法支持，可快速定义虚拟数据结构
-   可视化操作，可视即可得，低门槛快速上手
-   支持多种请求类型（GET、POST、PUT、DELETE）
-   接口请求权限验证，阻止非法请求虚拟接口
-   接口项目应用化管理，还原实际开发场景
-   虚拟接口请求日志数据查看及统计
-   提供应用接口文档管理，高效管理接口及项目计划
-   零污染无侵入，而无需在项目代码中引入Mock包
-   免费开源，可独立部署搭建
-   ......

  

VirAPI开源版
---------

对应前端UI代码仓库：https://github.com/bluvenr/open\_virapi\_front\_end

### 环境依赖

-   NodeJs(NPM)
-   MongoDB

本项目使用了eggjs作为后端逻辑项目框架。

### 运行&部署

搭建好必要环境后，执行`npm install`安装项目所需依赖包。

本地测试运行，则请执行：`npm run dev`

正式环境运行，请执行：`npm start`；此时若想关闭停止项目，则执行：`npm stop`。由于eggjs框架的机制，请每次修改后端代码后重启该项目`npm restart`。

默认服务端口为`7001`，本地可直接访问`http://127.0.0.1:7001/`进入控制台管理页面。若是部署到线上，可配置nginx或apache进行重定向。

### 项目配置相关介绍

项目配置文件放在`config/config.default.js`文件中，若是放置服务器正式环境，则建议复制该文件你需要自定义的配置在同目录下命名为`config.local.js`文件中，并设置你要的配置参数。

默认`config.default.js`文件内容为：

/\* eslint valid-jsdoc: "off" \*/

'use strict';

const fs \= require('fs');
const path \= require('path');

/\*\*
 \* @param {Egg.EggAppInfo} appInfo app info
 \*/
module.exports \= appInfo \=> {
  /\*\*
   \* built-in config
   \* @type {Egg.EggAppConfig}
   \*\*/
  const config \= {
    mongoose: {
      // url: 'mongodb://127.0.0.1:27017/open\_virapi\_db',
      options: {
        // useMongoClient: true,
        autoReconnect: true,
        reconnectTries: Number.MAX\_VALUE,
        bufferMaxEntries: 0,
      },
    },
    bcrypt: {
      saltRounds: 10,
    },
    security: {
      csrf: {
        enable: false,
        ignoreJSON: true,
      },
      domainWhiteList: \[
        'http://localhost:8080',
      \],
    },
    validate: {
      convert: true,
    },
    cors: {
      // origin: '\*',
      allowMethods: 'GET,HEAD,PUT,POST,DELETE,PATCH,OPTIONS',
    },
    jwt: {
      secret: 'virapi-202008192239',
    },
    proxy: true, // 通过ips获取nginx代理层真实IP
    session: {
      key: 'Vir\_SESSION', // 承载 Session 的 Cookie 键值对名字
      maxAge: 2 \* 3600 \* 1000, // Session 的最大有效时间
      httpOnly: true,
      encrypt: true,
      renew: true, // 每次访问页面都会给session会话延长时间
    },
    static: {
      prefix: '/',
      dir: path.join(appInfo.baseDir, 'app/public'),
      dynamic: true,
      preload: false,
      maxAge: 0,
      buffer: false,
    },
  };

  // use for cookie sign key, should change to your own and keep security
  config.keys \= appInfo.name + '\_hNW87vqPkMiMpLBHEtolB3Yg6vQsk5Ip4AJzCih2QCXbZBmjh5I033ELjdwB';

  // add your middleware config here
  config.middleware \= \[
    'errorHandler',
  \];

  config.siteFile \= {
    '/favicon.ico': fs.readFileSync(appInfo.baseDir + '/app/public/favicon.ico'),
  };

  // add your user config here
  const userConfig \= {
    // myAppName: 'egg',
    imgUri: '/images',
    imgDir: appInfo.baseDir + '/app/public/images',
  };

  return {
    ...config,
    ...userConfig,
  };
};

在你的自定义配置参数文件`config.local.js`中，我们建议你配置以下必要参数：

'use strict';

// cookie & session 数据加密安全字符串
exports.keys \= 'xxxxxxxxx';   // 建议你自定义重置该参数，cookie、session等数据加密时会用到该参数

// MongoDB 相关参数
exports.mongoose \= {
  client: {
    url: 'mongodb://127.0.0.1:27017/local\_virapi\_db',   // 你的mongo数据库访问地址
    options: {
      // useMongoClient: true,
      autoReconnect: true,
      reconnectTries: Number.MAX\_VALUE,
      bufferMaxEntries: 0,
    },
  },
};

// 图片资源访问域名
exports.imgUri \= 'http://{你的图片访问地址}';    // 若你要对图片资源独立分配域名可设置该参数

### Mongo数据库

为了能登录控制台系统，需要一个初始化的账号信息。在你的mongo所在服务器执行以下命令，创建初始账号：

```
// 进入Mongo命令台
mongo 127.0.0.1:27017/local_virapi_db;  // 请更换你的Mongo访问地址

// 切换到目标数据库
use local_virapi_db;  // 请更换你的Mongo数据名

// 插入初始账号信息
db.getCollection('user').insertOne({
    "nickname" : "admin",
    "vir_uid" : "vir_admin",
    "vir_uid_updated" : null,
    "email" : "admin@virapi.com",
    "password" : "$2a$10$6fam2XUhNqU0nTNixjuoBuCx5aK2R8t.vEndOuVQ6vxVrinWXu9wy",
    "avatar" : "/default_avatar.jpg",
    "apps_count" : 0,
    "login_date" : ISODate("2020-08-21T12:35:47.312Z"),
    "status" : 1,
    "created" : ISODate("2020-08-19T15:20:43.192Z"),
    "updated" : ISODate("2020-08-21T12:35:47.315Z"),
    "__v" : 0
});
```

其中登录账号即为：`admin@virapi.com`，默认登录密码为：`123456`。

登录成功后，**请注意重置登录密码**，以保障账号安全。

  

部分功能页面截图
--------

新建应用示例截图

新建接口示例截图

应用管理示例截图

接口管理示例截图

  
  

若觉得VirAPI有帮到你，请赞助一下以示支持哦~
-------------------------

😁请备注`virapi`。

支付宝赞助

微信赞助

  
  

欢迎大家通过Gitter与我们沟通和联系。
