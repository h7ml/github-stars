---
project: cloud189-sdk
stars: 18
description: 天翼云sdk
url: https://github.com/wes-lin/cloud189-sdk
---

cloud189-sdk
============

> 基于node.js的天翼网盘sdk

使用方法
----

1.  安装依赖

npm install cloud189-sdk

1.  初始化

const { CloudClient } \= require('cloud189-sdk')
// 使用账号密码初始化
const client \= new CloudClient({
  username: 'username',
  password: 'password'
})

1.  使用

const info \= await client.getUserSizeInfo()
console.log(info)

API 文档
------

Star History
------------
