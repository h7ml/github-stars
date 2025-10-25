---
project: simpleui
stars: 3742
description: A modern theme based on vue+element-ui for django admin.一款基于vue+element-ui的django admin现代化主题。全球20000+网站都在使用！喜欢可以点个star✨
url: https://github.com/newpanjing/simpleui
---

   

让Django Admin简单而友好，20000+网站共同选择

Simple and friendly. Django admin theme the simpleui

 

* * *

中文 | English

* * *

社区 | 文档 | Documents

* * *

simpleui 特点

* * *

👍 内置28款流行的主题

⚡️ pip闪电安装100%兼容原生admin无需修改代码

✨ 多标签页面，各个模块更加清晰明了

🎯 配置简单，极速上手，在settings.py中加入simpleui后启动立即生效，效率提升 100%！让后端开发得心应手。

☕️ Element-UI + Vue 加持，让古老的django admin 焕然一新。

🦀 新增支持Django5.3，Python3.12，敢于做第一个吃螃蟹的人。

开发初衷
====

Django Admin默认界面设计语言存在着的一些不足，比如色彩单一，大量线条的使用，分割化明显。将这些不足归类一下就是界面单调、雷同性明显、缺少惊喜。我们认为新的平台类视觉风格可以打破这些束缚，尝试一些新的探索，启发传统的设计认知,因此结合当下设计趋势，构思了Element+Django Admin的Simpleui。让Django Admin和Element产生完美的交互。配以最流行的后台设计风格，让Django Admin更加强大。

QQ群
---

-   QQ群号:722755389
-   QQ群号:747695956
-   QQ群号:873469913(满)
-   QQ群号:786576510(满)

> 我们推荐在在线社区提问，方便以后大家有问题的时候直接查找。

专业版
---

> 如果免费版无法满足您的需求，我们还提供了一个功能更强大的pro版，可以满足更多的需求

> 提供了数十个自定义组件+拖拽式首页设计和图表设计

Demo：http://175.178.229.216:9001/admin/login/?next=/

官网：https://www.noondot.com/simplepro

PRO文档：https://www.noondot.com/docs/simplepro

小广告
---

为了增加一些收入，开发了很多macOS和iOS的app，希望大家可以支持下付费的app。

点击链接就可以进入App Store下载：

https://apps.apple.com/kg/developer/%E6%95%AC-%E6%BD%98/id1630712468

文档
--

文档详细的描述了安装使用方法，以及各种配置项的说明，请点击以下链接查阅。

### 重要的事情说3遍：

👇👇👇👇👇👇👇👇👇👇👇

👉 1.https://newpanjing.github.io/simpleui\_docs/👈

👉 2.https://newpanjing.github.io/simpleui\_docs/👈

👉 3.https://newpanjing.github.io/simpleui\_docs/👈

👆👆👆👆👆👆👆👆👆👆👆

本地Demo下载
--------

如果你没有任何python django基础，可以下载一个可以直接运行的demo进行体验。 😝DEMO源码

Docker
------

docker pull newpanjing/simpleui\_demo

docker run -p 8080:8080 newpanjing/simpleui\_demo

启动成功后访问：http://127.0.0.1:8080

simpleui 是什么？
=============

🚀simpleui 是django admin的一个主题 是一个基于element-ui+vue开发，重写和优化90%以上的页面。 与suit是同类产品。我们是一个更符合国人审美和使用习惯的一个主题。

开始使用
====

详细步骤请浏览 使用文档。 也可以参考Demo

-   安装

pip install django\-simpleui

用pip或者源码方式安装simpleui后，在自己项目的settings.py文件中INSTALLED\_APPS的第一行加入`simpleui`

举个例子🌰：

  \# Application definition

  INSTALLED\_APPS \= \[
      'simpleui',
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',
      ...
  \]

如果不知道怎么配置或者如何使用，请下载本地demo进行学习。或者加入QQ群：786576510 咨询。

升级simpleui
==========

pip install django\-simpleui \-\-upgrade

克隆源码本地安装
========

git clone https://github.com/newpanjing/simpleui
cd simpleui
python setup.py sdist install

常见问题:
-----

1.  如果关闭debug模式后，请执行以下命令将simpleui静态文件静态文件克隆到根目录
    
    python3 manage.py collectstatic
    
2.  克隆静态文件出错 请在settings.py文件中加入：
    
    STATIC\_ROOT = os.path.join(BASE\_DIR, "static")
    
3.  其他问题请参考django官方文档。
    
4.  i18n 国际化 采用js国际化，默认为英文和中文两种语言，随系统切换。具体请看国际化配置
    

其他问题请查看快速上手指南

支持django和python版本
-----------------

查看支持的版本列表

浏览器兼容性
------

✔

✔

✔

11+ ✔

✔

✔

✔

README 徽章
---------

如果你的项目正在使用Simpleui，可以将Simpleui徽章 添加到你的 README 中：

```
[![simpleui](https://img.shields.io/badge/developing%20with-Simpleui-2077ff.svg)](https://github.com/newpanjing/simpleui)
```

赞助💰
----

如果你觉得simpleui对你有帮助，你可以赞助我们一杯咖啡，鼓励我们继续开发维护下去。

登录页
===

主页
==

列表页
===

切换主题
====

密码修改
====

编辑页
===

设置字体大小
======

优质贡献者
-----

simpleui的发展离不开以下优秀贡献者的支持。如果您想为simpleui贡献代码，请fork到自己仓库，然后发起合并请求，合并至dev分支。

Github

贡献范围

@Abraverman666

Developers

@zhangzhibo1014

英文文档翻译

@liaogx

bug修复

@shouyong

bug修复

@Roddy1219

bug修复

@WalkerWang731

优质代码贡献

@初学者

223450427@qq.com，顶级技术顾问

其他项目
----

基于SimpleUI 打造的专业版：Simple Pro

基于vue3和element-plus 打造的纯前端Admin： Simple Admin

Star History
------------
