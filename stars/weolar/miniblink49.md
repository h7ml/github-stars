---
project: miniblink49
stars: 7638
description: a lighter, faster browser kernel of blink to integrate HTML UI in your app. 一个小巧、轻量的浏览器内核，用来取代wke和libcef
url: https://github.com/weolar/miniblink49
---

声明
==

由于本项目被黑产拿去修改源码后用于非法目的，导致我被人找上门了几次，

经深思熟虑后决定自2019-6-17起不在更新。但于2024年6月22日，重新开源！

此次开源的是49版本，后续最新的108版本也即将新建一个仓库开源，大家敬请期待。

后续更新也会同时上传编译好的可执行文件，请持续关注。

可执行文件及头文件下载地址：https://github.com/weolar/miniblink49/releases

希望大家尊重开源，尊重作者全职几年持续更新付出的劳动。

**且用且珍惜**

如需获得后续支持，请使用以下联系方式：

开发者论坛：https://bbs.miniblink.com/ （注册后，需要加我QQ告诉我，我才能验证通过）

加微信群：

Telegram群：https://t.me/miniblink

Q群：738349226（可加）、94093808（已满勿加）

QQ（weolar）：93527630

email：weolar@miniblink.net

微信：可发邮箱咨询我微信号。暂时不放到github了

简介 Abstract
===========

miniblink is a open source, one file, small browser widget base on chromium.

By using C interface, you can create a browser just some line code.

more information at http://miniblink.net

* * *

miniblink是一个开源的、单文件、且目前已知的最小的基于chromium的，浏览器控件。

通过其导出的纯C接口，几行代码即可创建一个浏览器控件。

您可以通过官网http://miniblink.net 来获取更多的关于miniblink的信息。

* * *

特性 Features
===========

-   极致小巧的体积 (small size)
-   C++，C#，Delphi等语言调用 (support C++，C#，Delphi language to call)
-   内嵌Nodejs，支持electron (with Nodejs, can run electron)
-   随心所欲的定制功能、模拟环境 (simulate other browser environment)
-   支持Windows xp、npapi (support windows xp and npapi)
-   完善的HTML5支持，对各种前端库友好 (support HTML5, and friendly to front framework)
-   关闭跨域开关后，可以使用各种跨域功能 (support cross domain)
-   网络资源拦截，替换任意网站任意js为本地文件 (network intercept, you can replace any resource to local file)
-   headless模式，极大节省资源，适用于爬虫 (headless mode, be suitable for Web Crawler)

* * *

文档 Document
===========

关于miniblink的介绍见这篇文章：https://zhuanlan.zhihu.com/p/22611497?group\_id=764036386641707008

API文档见：https://miniblink.net/views/doc/index.html

* * *

使用 Usage
========

请前往https://github.com/weolar/miniblink49/releases 下载最新编译后的SDK，里面的demo\_src是个完整的用例。

或者前往 https://github.com/weolar/mb-demo 下载

最简单的创建一个窗口：

**Usage**

// 无边框窗体 borderless window
wkeWebView window = wkeCreateWebWindow(WKE\_WINDOW\_TYPE\_TRANSPARENT, NULL, 0, 0, 640, 480);  
wkeLoadURLW(window, L"miniblink.net");

编译 Build
========

不推荐自己编译。请前往https://github.com/weolar/miniblink49/releases 下载编译好的文件使用。

因为每天有大量更新，我无法确保每次更新都能保证编译通过。如果有编译错误，请不要来提问，耐心等待我的下次提交。

* * *

mini-electron
=============

mini-electron项目是一个基于miniblink的独立项目，旨在创建一个更小的electron运行环境。目前已经实现了这一目标。

通过替换mini-electron，打包完后的文件仅仅6m左右。

* * *

联系方式
====

大家有问题可以选择：

-   加微信群：
    
-   邮箱weolar@miniblink.net
    
-   github里留言issue讨论
    
-   加Q群94093808
    
-   关注知乎专栏：https://zhuanlan.zhihu.com/chrome
    

* * *

致谢 Thanks
=========

特别感谢网友zero，他是miniblink的代码的重要贡献者。

感谢网友core，感谢网友“大清知府”。

感谢网友boxue（ https://www.zhihu.com/people/coltor/ ），他致力于对miniblink架构的研究及推广。
