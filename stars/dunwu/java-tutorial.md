---
project: java-tutorial
stars: 1925
description: :coffee: 老司机在 Java 技术领域的十年积累。
url: https://github.com/dunwu/java-tutorial
---

JavaTutorial
============

> ☕ **java-tutorial** 是一个 Java 教程，汇集一个老司机在 Java 领域的十年积累。
> 
> -   🔁 项目同步维护：Github | Gitee
> -   📖 电子书阅读：Github Pages | Gitee Pages
> 
> 说明：
> 
> -   下面的内容清单中，凡是有 📚 标记的技术，都已整理成详细的教程。
> -   部分技术因为可以应用于不同领域，所以可能会同时出现在不同的类别下。

📖 内容
-----

### JavaSE

> 📚 javacore 是一个 Java 核心技术教程。内容包含：Java 基础特性、Java 高级特性、Java 并发、JVM、Java IO 等。

### JavaEE

#### JavaWeb

-   JavaWeb 面经
-   JavaWeb 之 Servlet 指南
-   JavaWeb 之 Jsp 指南
-   JavaWeb 之 Filter 和 Listener
-   JavaWeb 之 Cookie 和 Session

#### Java 服务器

> Tomcat 和 Jetty 都是 Java 比较流行的轻量级服务器。
> 
> Nginx 是目前最流行的反向代理服务器，也常用于负载均衡。

-   Tomcat 快速入门
-   Tomcat 连接器
-   Tomcat 容器
-   Tomcat 优化
-   Tomcat 和 Jetty
-   Jetty

### Java 软件

#### Java 构建

> Java 项目需要通过 **构建工具** 来管理项目依赖，完成编译、打包、发布、生成 JavaDoc 等任务。
> 
> -   目前最主流的构建工具是 Maven，它的功能非常强大。
> -   Gradle 号称是要替代 Maven 等构件工具，它的版本管理确实简洁，但是需要学习 Groovy，学习成本比 Maven 高。
> -   Ant 功能比 Maven 和 Gradle 要弱，现代 Java 项目基本不用了，但也有一些传统的 Java 项目还在使用。

-   Maven 📚
    -   Maven 快速入门
    -   Maven 教程之 pom.xml 详解
    -   Maven 教程之 settings.xml 详解
    -   Maven 实战问题和最佳实践
    -   Maven 教程之发布 jar 到私服或中央仓库
    -   Maven 插件之代码检查
-   Ant 简易教程

#### Java IDE

> 自从有了 **IDE**，写代码从此就告别了刀耕火种的蛮荒时代。
> 
> -   Eclipse 是久负盛名的开源 Java IDE，我的学生时代一直使用它写 Java。
> -   曾经抗拒从转 Intellij Idea ，但后来发现真香，不得不说，确实是目前最优秀的 Java IDE。
> -   你可以在 vscode 中写各种语言，只要安装相应插件即可。如果你的项目中使用了很多种编程语言，又懒得在多个 IDE 之间切换，那么就用 vscode 来一网打尽吧。

-   Intellij Idea
-   Eclipse
-   vscode

#### Java 监控诊断

> 监控/诊断 工具主要用于 Java 应用的运维。通过采集、分析、存储、可视化应用的有效数据，帮助开发者、使用者快速定位问题，找到性能瓶颈。

-   监控工具对比
-   CAT
-   Zipkin
-   SkyWalking
-   Arthas

### Java 工具

#### Java IO

-   JSON 序列化 - fastjson、Jackson、Gson
-   二进制序列化 - Protobuf、Thrift、Hessian、Kryo、FST

#### JavaBean 工具

-   Lombok
-   Dozer

#### Java 模板引擎

-   Freemark
-   Velocity
-   Thymeleaf

#### Java 测试工具

-   Junit
-   Mockito
-   Jmeter
-   JMH

#### 其他

-   Java 日志
-   Java 工具包
-   Reflections
-   JavaMail
-   Jsoup
-   Thumbnailator
-   Zxing

### Java 框架

#### ORM

-   Mybatis 快速入门
-   Mybatis 原理

#### Spring

📚 spring-tutorial 是一个 Spring 实战教程。

#### Spring Boot

📚 Spring Boot 教程 是一个 Spring Boot 实战教程。

#### 安全

> Java 领域比较流行的安全框架就是 shiro 和 spring-security。
> 
> shiro 更为简单、轻便，容易理解，能满足大多数基本安全场景下的需要。
> 
> spring-security 功能更丰富，也比 shiro 更复杂。值得一提的是由于 spring-security 是 spring 团队开发，所以集成 spring 和 spring-boot 框架更容易。

-   Shiro
-   SpringSecurity

#### IO

-   Shiro

#### 微服务

-   Dubbo

### Java 中间件

#### MQ

> 消息队列（Message Queue，简称 MQ）技术是分布式应用间交换信息的一种技术。
> 
> 消息队列主要解决应用耦合，异步消息，流量削锋等问题，实现高性能，高可用，可伸缩和最终一致性架构。是大型分布式系统不可缺少的中间件。
> 
> 如果想深入学习各种消息队列产品，建议先了解一下 消息队列基本原理 ，有助于理解消息队列特性的实现和设计思路。

-   消息队列面试
-   消息队列基本原理
-   RocketMQ
-   ActiveMQ

#### 缓存

> 缓存可以说是优化系统性能的第一手段，在各种技术中都会有缓存的应用。
> 
> 如果想深入学习缓存，建议先了解一下 缓存基本原理，有助于理解缓存的特性、原理，使用缓存常见的问题及解决方案。

-   缓存面试题
-   Java 缓存中间件
-   Memcached 快速入门
-   Ehcache 快速入门
-   Java 进程内缓存
-   Http 缓存

#### 流量控制

-   Hystrix

### 大数据

> 大数据技术点以归档在：bigdata-tutorial

-   Hdfs 📚
-   Hbase 📚
-   Hive 📚
-   MapReduce
-   Yarn
-   ZooKeeper 📚
-   Kafka 📚
-   Spark
-   Storm
-   Flink

📚 资料
-----

-   Java 经典书籍
    -   《Effective Java 中文版》 - 本书介绍了在 Java 编程中 78 条极具实用价值的经验规则，这些经验规则涵盖了大多数开发人员每天所面临的问题的解决方案。同推荐《重构 : 改善既有代码的设计》、《代码整洁之道》、《代码大全》，有一定的内容重叠。
    -   《Java 并发编程实战》 - 本书深入浅出地介绍了 Java 线程和并发，是一本完美的 Java 并发参考手册。
    -   《深入理解 Java 虚拟机》 - 不去了解 JVM 的工程师，和咸鱼有什么区
    -   《Maven 实战》 - 国内最权威的 Maven 专家的力作，唯一一本哦！
-   其他领域书籍
    -   《Redis 设计与实现》 - 系统而全面地描述了 Redis 内部运行机制。图示丰富，描述清晰，并给出大量参考信息，是 NoSQL 数据库开发人员案头必备。
    -   《鸟哥的 Linux 私房菜 （基础学习篇）》 - 本书是最具知名度的 Linux 入门书《鸟哥的 Linux 私房菜基础学习篇》的最新版，全面而详细地介绍了 Linux 操作系统。内容非常全面，建议挑选和自己实际工作相关度较高的，其他部分有需要再阅读。
    -   《Head First 设计模式》 - 《Head First 设计模式》(中文版)共有 14 章，每章都介绍了几个设计模式，完整地涵盖了四人组版本全部 23 个设计模式。
    -   《HTTP 权威指南》 - 本书尝试着将 HTTP 中一些互相关联且常被误解的规则梳理清楚，并编写了一系列基于各种主题的章节，对 HTTP 各方面的特性进行了介绍。纵观全书，对 HTTP“为什么”这样做进行了详细的解释，而不仅仅停留在它是“怎么做”的。
    -   《TCP/IP 详解 系列》 - 完整而详细的 TCP/IP 协议指南。针对任何希望理解 TCP/IP 协议是如何实现的读者设计。
    -   《剑指 Offer：名企面试官精讲典型编程题》 - 剖析了 80 个典型的编程面试题，系统整理基础知识、代码质量、解题思路、优化效率和综合能力这 5 个面试要点。

🚪 传送
-----

◾ 🏠 JAVA-TUTORIAL 首页 ◾ 🎯 我的博客 ◾

> 你可能会感兴趣：

-   Java 教程 📚
-   JavaCore 教程 📚
-   Spring 教程 📚
-   Spring Boot 教程 📚
-   数据库教程 📚
-   数据结构和算法教程 📚
-   Linux 教程 📚
-   Nginx 教程 📚
