---
project: Clean-Architecture-zh
stars: 822
description: 《架构整洁之道》中文翻译
url: https://github.com/leewaiho/Clean-Architecture-zh
---

Clean-Architecture-zh
=====================

《架构整洁之道》中文翻译

在线阅读：http://gdut\_yy.gitee.io/doc-cleanarch/

前言
--

Index
-----

-   第一部分 概述
-   第 1 章 设计与架构究竟是什么
-   第 2 章 两个价值维度

* * *

-   第二部分 从基础构件开始：编程范式
-   第 3 章 编程范式总览
-   第 4 章 结构化编程
-   第 5 章 面向对象编程
-   第 6 章 函数式编程

* * *

-   第三部分 设计原则
-   第 7 章 SRP：单一职责原则
-   第 8 章 OCP：开闭原则
-   第 9 章 LSP：里氏替换原则
-   第 10 章 ISP：接口隔离原则
-   第 11 章 DIP：依赖反转原则

* * *

-   第四部分 组件构建原则
-   第 12 章 组件
-   第 13 章 组件聚合
-   第 14 章 组件耦合

* * *

-   第五部分 软件架构
-   第 15 章 什么是软件架构
-   第 16 章 独立性
-   第 17 章 划分边界
-   第 18 章 边界剖析
-   第 19 章 策略与层次
-   第 20 章 业务逻辑
-   第 21 章 尖叫的软件架构
-   第 22 章 整洁架构
-   第 23 章 展示器和谦卑对象
-   第 24 章 不完全边界
-   第 25 章 层次与边界
-   第 26 章 Main 组件
-   第 27 章 服务：宏观和微观
-   第 28 章 测试边界
-   第 29 章 整洁的嵌入式架构

* * *

-   第六部分 实现细节
-   第 30 章 数据库只是实现细节
-   第 31 章 Web 是实现细节
-   第 32 章 应用程序框架是实现细节
-   第 33 章 案例分析：视频销售网站
-   第 34 章 拾遗

本地开发 & 阅读
---------

本项目基于 vuepress 进行开发，以提供比 github mardown 更佳的阅读体验

依赖于 `node.js`、`yarn`、`vuepress` 等环境

# vuepress
yarn global add vuepress

# 本地开发
git clone https://github.com/gdut-yy/Clean-Architecture-zh.git
cd Clean-Architecture-zh/
yarn docs:dev

# 本地阅读
http://localhost:8080/doc-cleanarch/

License
-------

MIT
