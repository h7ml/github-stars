---
project: hutool
stars: 30082
description: 🍬A set of tools that keep Java sweet.
url: https://github.com/chinabugotech/hutool
---

**🍬A set of tools that keep Java sweet.**

👉 https://hutool.cn/ 👈

  

* * *

\=======

**🌎English Documentation**

* * *

📚简介
----

`Hutool`是一个功能丰富且易用的**Java工具库**，通过诸多实用工具类的使用，旨在帮助开发者快速、便捷地完成各类开发任务。 这些封装的工具涵盖了字符串、数字、集合、编码、日期、文件、IO、加密、数据库JDBC、JSON、HTTP客户端等一系列操作， 可以满足各种不同的开发需求。

### 🎁Hutool名称的由来

Hutool = Hu + tool，是原公司项目底层代码剥离后的开源库，“Hu”是公司名称的表示，tool表示工具。Hutool谐音“糊涂”，一方面简洁易懂，一方面寓意“难得糊涂”。

### 🍺Hutool理念

`Hutool`既是一个工具集，也是一个知识库，我们从不自诩代码原创，大多数工具类都是**搬运**而来，因此：

-   你可以引入使用，也可以**拷贝**和修改使用，而**不必标注任何信息**，只是希望能把bug及时反馈回来。
-   我们努力健全**中文**注释，为源码学习者提供良好地学习环境，争取做到人人都能看得懂。

* * *

🛠️包含组件
-------

一个Java基础工具类，对文件、流、加密解密、转码、正则、线程、XML等JDK方法进行封装，组成各种Util工具类，同时提供以下组件：

模块

介绍

hutool-aop

JDK动态代理封装，提供非IOC下的切面支持

hutool-bloomFilter

布隆过滤，提供一些Hash算法的布隆过滤

hutool-cache

简单缓存实现

hutool-core

核心，包括Bean操作、日期、各种Util等

hutool-cron

定时任务模块，提供类Crontab表达式的定时任务

hutool-crypto

加密解密模块，提供对称、非对称和摘要算法封装

hutool-db

JDBC封装后的数据操作，基于ActiveRecord思想

hutool-dfa

基于DFA模型的多关键字查找

hutool-extra

扩展模块，对第三方封装（模板引擎、邮件、Servlet、二维码、Emoji、FTP、分词等）

hutool-http

基于HttpUrlConnection的Http客户端封装

hutool-log

自动识别日志实现的日志门面

hutool-script

脚本执行封装，例如Javascript

hutool-setting

功能更强大的Setting配置文件和Properties封装

hutool-system

系统参数调用封装（JVM信息等）

hutool-json

JSON实现

hutool-captcha

图片验证码实现

hutool-poi

针对POI中Excel和Word的封装

hutool-socket

基于Java的NIO和AIO的Socket封装

hutool-jwt

JSON Web Token (JWT)封装实现

hutool-ai

AI大模型封装实现

可以根据需求对每个模块单独引入，也可以通过引入`hutool-all`方式引入所有模块。

* * *

📝文档
----

📘中文文档

📘中文备用文档

📙参考API

🎬视频介绍

* * *

📦安装
----

### 🍊Maven

在项目的pom.xml的dependencies中加入以下内容:

<dependency\>
    <groupId\>cn.hutool</groupId\>
    <artifactId\>hutool-all</artifactId\>
    <version\>5.8.40</version\>
</dependency\>

### 🍐Gradle

```
implementation 'cn.hutool:hutool-all:5.8.40'
```

### 📥下载jar

点击以下链接，下载`hutool-all-X.X.X.jar`即可：

-   Maven中央库

> 🔔️注意 Hutool 5.x支持JDK8+，对Android平台没有测试，不能保证所有工具类或工具方法可用。 如果你的项目使用JDK7，请使用Hutool 4.x版本（不再更新）

### 🚽编译安装

访问Hutool的Gitee主页：https://gitee.com/chinabugotech/hutool 下载整个项目源码（v5-master或v5-dev分支都可）然后进入Hutool项目目录执行：

./hutool.sh install

然后就可以使用Maven引入了。

* * *

🏗️添砖加瓦
-------

### 🎋分支说明

Hutool的源码分为两个分支，功能如下：

分支

作用

v5-master

主分支，release版本使用的分支，与中央库提交的jar一致，不接收任何pr或修改

v5-dev

开发分支，默认为下个版本的SNAPSHOT版本，接受修改或pr

### 🐞提供bug反馈或建议

提交问题反馈请说明正在使用的JDK版本呢、Hutool版本和相关依赖库版本。

-   Gitee issue
-   Github issue
-   Gitcode issue

### 🧬贡献代码的步骤

1.  在Gitee或者Github/Gitcode上fork项目到自己的repo
2.  把fork过去的项目也就是你的项目clone到你的本地
3.  修改代码（记得一定要修改v5-dev分支）
4.  commit后push到自己的库（v5-dev分支）
5.  登录Gitee或Github/Gitcode在你首页可以看到一个 pull request 按钮，点击它，填写一些说明信息，然后提交即可。
6.  等待维护者合并

### 📐PR遵照的原则

Hutool欢迎任何人为Hutool添砖加瓦，贡献代码，不过维护者是一个强迫症患者，为了照顾病人，需要提交的pr（pull request）符合一些规范，规范如下：

1.  注释完备，尤其每个新增的方法应按照Java文档规范标明方法说明、参数说明、返回值说明等信息，必要时请添加单元测试，如果愿意，也可以加上你的大名。
2.  Hutool的缩进按照Eclipse（不要跟我说IDEA多好用，维护者非常懒，学不会，IDEA真香，改了Eclipse快捷键后舒服多了）默认（tab）缩进，所以请遵守（不要和我争执空格与tab的问题，这是一个病人的习惯）。
3.  新加的方法不要使用第三方库的方法，Hutool遵循无依赖原则（除非在extra模块中加方法工具）。
4.  请pull request到`v5-dev`分支。Hutool在5.x版本后使用了新的分支：`v5-master`是主分支，表示已经发布中央库的版本，这个分支不允许pr，也不允许修改。
5.  我们如果关闭了你的issue或pr，请不要诧异，这是我们保持问题处理整洁的一种方式，你依旧可以继续讨论，当有讨论结果时我们会重新打开。

### 📖文档源码地址

文档源码地址 点击前往添砖加瓦

* * *

⭐Star Hutool
------------
