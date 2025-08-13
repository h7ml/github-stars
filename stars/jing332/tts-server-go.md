---
project: tts-server-go
stars: 406
description: 微软TTS服务转发，以便在阅读APP中通过网络导入方式收听微软TTS / Edge大声朗读
url: https://github.com/jing332/tts-server-go
---

安卓系统推荐使用 tts-server-android 安装即用
================================

https://github.com/jing332/tts-server-android

下载
==

请从 Release 下载稳定版。

或者从 Actions 下载最新代码构建程序。

使用方法
====

直接运行，默认监听1233端口。

然后浏览器 `http://localhost:1233` 打开网页，选好配置导入阅读后即可朗读。

提示
==

接口与ms-ra-forwarder 相同:

微软Azure接口(延迟高): `http://localhost:1233/api/azure`

Edge大声朗读接口: `http://localhost:1233/api/ra`
