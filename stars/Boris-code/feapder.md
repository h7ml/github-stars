---
project: feapder
stars: 3374
description: 🚀🚀🚀feapder is an easy to use, powerful crawler framework | feapder是一款上手简单，功能强大的Python爬虫框架。内置AirSpider、Spider、TaskSpider、BatchSpider四种爬虫解决不同场景的需求。且支持断点续爬、监控报警、浏览器渲染、海量数据去重等功能。更有功能强大的爬虫管理系统feaplat为其提供方便的部署及调度
url: https://github.com/Boris-code/feapder
---

FEAPDER
=======

简介
--

1.  feapder是一款上手简单，功能强大的Python爬虫框架，内置AirSpider、Spider、TaskSpider、BatchSpider四种爬虫解决不同场景的需求。
2.  支持断点续爬、监控报警、浏览器渲染、海量数据去重等功能。
3.  更有功能强大的爬虫管理系统feaplat为其提供方便的部署及调度

读音: `[ˈfiːpdə]`

文档地址
----

-   官方文档：https://feapder.com
-   github：https://github.com/Boris-code/feapder
-   更新日志：https://github.com/Boris-code/feapder/releases
-   爬虫管理系统：http://feapder.com/#/feapder\_platform/feaplat

环境要求：
-----

-   Python 3.6.0+
-   Works on Linux, Windows, macOS

安装
--

From PyPi:

精简版

pip install feapder

浏览器渲染版：

pip install "feapder\[render\]"

完整版：

pip install "feapder\[all\]"

三个版本区别：

1.  精简版：不支持浏览器渲染、不支持基于内存去重、不支持入库mongo
2.  浏览器渲染版：不支持基于内存去重、不支持入库mongo
3.  完整版：支持所有功能

完整版可能会安装出错，若安装出错，请参考安装问题

小试一下
----

创建爬虫

feapder create -s first\_spider

创建后的爬虫代码如下：

import feapder

class FirstSpider(feapder.AirSpider):
    def start\_requests(self):
        yield feapder.Request("https://www.baidu.com")

    def parse(self, request, response):
        print(response)

if \_\_name\_\_ \== "\_\_main\_\_":
    FirstSpider().start()
        

直接运行，打印如下：

Thread-2|2021-02-09 14:55:11,373|request.py|get\_response|line:283|DEBUG|
                -------------- FirstSpider.parse request for ----------------
                url  = https://www.baidu.com
                method = GET
                body = {'timeout': 22, 'stream': True, 'verify': False, 'headers': {'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/27.0.1453.93 Safari/537.36'}}

<Response \[200\]\>
Thread-2|2021-02-09 14:55:11,610|parser\_control.py|run|line:415|DEBUG| parser 等待任务...
FirstSpider|2021-02-09 14:55:14,620|air\_spider.py|run|line:80|INFO| 无任务，爬虫结束

代码解释如下：

1.  start\_requests： 生产任务
2.  parse： 解析数据

参与贡献
----

贡献之前请先阅读 贡献指南

感谢所有做过贡献的人!

爬虫工具推荐
------

1.  爬虫在线工具库：http://www.spidertools.cn
2.  爬虫管理系统：http://feapder.com/#/feapder\_platform/feaplat
3.  验证码识别库：https://github.com/sml2h3/ddddocr

微信赞赏
----

如果您觉得这个项目帮助到了您，您可以帮作者买一杯咖啡表示鼓励 🍹

也可和作者交个朋友，解决您在使用过程中遇到的问题

学习交流
----

知识星球：17321694

作者微信： boris\_tm

QQ群号：521494615

加好友备注：feapder
