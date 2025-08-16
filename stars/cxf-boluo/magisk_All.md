---
project: magisk_All
stars: 573
description: magisk 一键集成环境，再也不用每次刷完机繁琐的配置环境了！
url: https://github.com/cxf-boluo/magisk_All
---

magisk\_All
===========

一键集成环境，再也不用每次刷完机繁琐的配置环境了！ 这是一个magisk模块刷入即可!

介绍
--

magisk\_All 是一款 magisk 一键集成环境，可以轻松帮我们部署好基本的逆向工程环境。

-   GitHub：https://github.com/cxf-boluo/magisk\_All

集成工具：MT管理器、Igniter、启用webView调试、HTTPCanary、proxydroid、SSLping

集成模块：lsposed、Shamiko

开机自启动：frida-server android-server

默认抓包证书从用户证书存储移动到系统目录下

视频演示
----

地址：

安装教程
----

1.  正常刷机后，按照最新版的Magisk安装说明安装Magisk，注意本版本仅支持 Magisk Canary 27003及以上； Magisk安装可以直接看公众号文章：https://mp.weixin.qq.com/s/3BrZslKgtWPHostw7kA8eg
2.  Releases 中下载magisk\_All，导入手机；

```
adb push magisk_All.zip /sdcard/download
```

1.  按照Magisk安装模块步骤安装magisk\_All即可，正常重启；
2.  Magisk中找到`设置—Zygisk`打开，同时打开遵守排除列表，重启后再关闭遵守排除列表即可；
3.  模块启动后，抓包证书从用户证书到系统目录下，需要再次重启手机，激活证书挂载功能。

联系我
---

在使用过程中有任何问题，可以通过公众号、微信等联系

Licenses
--------

本工具禁止进行未授权商业用途，禁止二次开发后进行未授权商业用途。

本工具仅面向合法授权的企业安全建设行为，在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。

如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。

在使用本工具前，请您务必审慎阅读、充分理解各条款内容，限制、免责条款或者其他涉及您重大权益的条款可能会以加粗、加下划线等形式提示您重点注意。

除非您已充分阅读、完全理解并接受本协议所有条款，否则，请您不要使用本工具。您的使用行为或者您以其他任何明示或者默示方式表示接受本协议的，即视为您已阅读并同意本协议的约束。
