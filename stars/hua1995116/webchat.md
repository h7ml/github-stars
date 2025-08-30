---
project: webchat
stars: 2033
description: :speaker: Websocket project based on vue（基于vue2.0的实时聊天项目）
url: https://github.com/hua1995116/webchat
---

webchat
=======

中文版 English

> 说明: master 分支还不太稳定，可以查看 https://github.com/hua1995116/webchat/tree/v2.2.0 稳定分支， 3.0 版本持续重构中。

功能
--

-   注册登录功能
-   聊天功能
-   查看历史记录
-   多个聊天室
-   与机器人对接
-   图片发送
-   发送链接
-   发送表情
-   图片预览
-   消息未读
-   断线重连
-   好友资料查看
-   添加好友
-   单聊
-   搜索好友
-   热门好友推荐

启动项目
----

Dev环境: MongoDB、Node 8.5.0+、Npm 5.3.0+

Prod环境: Redis、MongoDB、Node 8.5.0+、Npm 5.3.0+

启动客户端

```
$webchat cd client

$client npm install -----安装依赖

$client npm run serve -----运行

```

启动服务端

```
$client cd ..

$webchat npm install

$webchat npm run dev
```

打包
--

打包客户端

```
cd client

npm run build
```

服务端运行

```
cd ..

npm run prod
```

在线观看

技术交流
----

qq群: 437938625

微信群: 加微信拉你进微信群。

技术栈
---

-   前端 vue，vue-router ,vuex
-   后端 nodejs，express
-   数据库 mongodb
-   通讯 websocket
-   脚手架工具 vue-cli

效果
--

版本更新
----

**v3新增功能**

1.  网络异常判断、重连提示
2.  多端信息同步
3.  好友资料查看
4.  添加好友
5.  单聊
6.  搜索好友
7.  热门好友推荐
8.  性别、手机号修改
9.  搜索加好友

版本预览
----

**v2 稳定版本**

https://github.com/hua1995116/webchat/tree/v2.2.0

**其他版本**

RELEASE

项目wiki
------

https://qiufeng.blue/node/#websocket-%E7%B3%BB%E5%88%97

API
---

API

License
-------

MIT

MIT License

Copyright (c) 2018 蓝色的秋风
