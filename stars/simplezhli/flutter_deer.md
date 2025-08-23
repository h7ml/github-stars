---
project: flutter_deer
stars: 8351
description: 🦌 Flutter 练习项目(包括集成测试、可访问性测试)。内含完整UI设计图，更贴近真实项目的练习。Flutter practice project (including integration testing and accessibility testing). Contains complete UI design drawings for a more realistic practice project.
url: https://github.com/simplezhli/flutter_deer
---

Flutter Deer
============

English | 中文
------------

本项目为个人学习Flutter的练习项目。

通过设置、修改、组合自带部件以及自定义来实现具体的设计效果，满足日常开发的需求。

本项目设计图见design目录，你可以通过我提供的设计图有目标的去练习。所有的实现仅是个人的学习理解，如果有更好的实现方案欢迎交流。

预览
--

部分页面效果如下：

**觉得还可以的话，来个Star、Fork支持一波！本项目持续维护中，有问题欢迎提Issue。**

实现内容（已迁移到空安全）
-------------

-   mvp模式
-   使用`provider` (6.x 版本)做状态管理
-   基于`dio` （5.x 版本）的网络请求封装
-   完整的集成测试、可访问性测试。
-   支持深色模式
-   本地化（感谢 @ghedwards）
-   使用`Sliver` 系列组件实现复杂滚动效果
-   使用高德地图定位选择地址（支持Web）
-   通用Widget的处理封装
-   下拉刷新 + 上拉加载更多
-   应用检查更新
-   PopupWindow
-   扫码功能（qr\_code\_scanner插件）
-   菜单切换动画（圆形扩散、3D翻转）
-   侧滑删除
-   城市选择
-   类似京东选择城市的三级联动
-   各种自定义Dialog
-   列表头部吸顶
-   密码输入键盘
-   验证码输入框
-   自定义简易日历
-   曲线图及饼状图
-   模块化路由管理
-   更多Demo（水波纹动画、刮刮卡、lottie）
-   更多的细节优化

具体可以下载体验：

Android版安装包：点击去下载。

iOS需要自行下载代码运行。

Web体验地址：https://simplezhli.github.io/flutter\_deer/

项目运行环境
------

```
1. Flutter version 3.35.1

2. Dart version 3.9.0
```

注意事项
----

-   `debug`模式下会有部分卡顿现象，这属于正常现象。良好的体验需要打`release` 包。 iOS可以执行命令`flutter build ios` 以创建`release`版本。 Android可以执行命令`flutter build apk` 以创建`release`版本。
    
-   项目运行有问题可以在iOS问题汇总、Android问题汇总中尝试寻找解决办法。
    
-   由于部分插件的原因，本项目在Windows、macOS仅做预览（主要为原生功能方面，UI问题不大）。有兴趣的可自行运行体验。
    
-   可以执行集成测试命令`flutter drive --target=test_driver/driver.dart` 查看功能演示。
    
-   因为页面有点多，一开始可能会导致页面无法与设计图对应上。我在代码注释中有添加设计图的相对路径，可以搜索或查找到对应页面，希望对你有帮助。
    
-   本项目使用FlutterJsonBeanFactory插件来生成Bean。
    
-   Web受制于js等资源过大和部署在Github上，访问会慢一些。
    

心得总结（推荐阅读）
----------

-   Flutter开发中的一些Tips(一)
    
-   Flutter开发中的一些Tips(二)
    
-   Flutter开发中的一些Tips(三)
    
-   Flutter适配深色模式（DarkMode）
    
-   说说Flutter中的RepaintBoundary
    
-   说说Flutter中的Semantics
    
-   说说Flutter中最熟悉的陌生人 —— Key
    
-   说说Flutter中的无名英雄 —— Focus
    
-   Flutter性能优化实践 —— UI篇
    
-   玩玩Flutter的拖拽——实现一款万能遥控器
    
-   玩玩Flutter Web —— 实现高德地图插件
    
-   在GitHub Actions上进行Flutter 的测试和部署
    
-   Flutter动画曲线Curves 效果一览
    
-   Flutter状态管理之Riverpod
    
-   【译】正确操作Dart中的字符串
    
-   【译】学习Flutter中新的Navigator和Router系统
    
-   【译】Flutter 2.2中的新功能
    

使用到的三方库
-------

库

功能

dio

**网络库**

provider

**状态管理**

flutter\_2d\_amap

**高德2D地图**

cached\_network\_image

**图片加载**

fluro

**路由管理**

flutter\_oktoast

**Toast**

common\_utils

**Dart 常用工具类库**

flutter\_slidable

**侧滑删除**

flustars

**Flutter 常用工具类库**

flutter\_swiper

**Flutter 轮播组件**

url\_launcher

**启动URL的插件**

image\_picker

**图片选择插件**

rxdart

**Dart的响应式扩展**

webview\_flutter

**WebView插件**

keyboard\_actions

**处理键盘事件**

azlistview

**城市选择列表**

date\_utils

**常用的日期工具类**

bezier\_chart

**曲线图表**

sprintf

**格式化String**

qr\_code\_scanner

**扫码功能**

intl

**本地化**

device\_info\_plus

**获取设备信息**

vibration

**振动**

lottie

**动画效果**

详细内容可以参看pubspec.yaml文件

后续计划：
-----

-   添加地图功能，具体实现插件见 flutter\_2d\_amap
    
-   下拉刷新 + 上拉加载更多
    
-   引入状态管理，预计使用 provider
    
-   页面添加设计图路径注释，方便寻找对应的设计图。
    
-   添加集成测试。
    
-   深色模式支持。
    
-   添加`Semantics`（语义）
    
-   Web端支持。
    
-   迁移到空安全。（安装包减少135KB，10.3M -> 10.1M）
    
-   迁移至Navigator 2.0。
    

已知存在问题：
-------

-   部分使用的到的三方库没有适配3.0.0，flutter\_swiper（flutter\_swiper\_null\_safety\_flutter3替代）、flustars（flustars\_flutter3替代）、azlistview（升级scrollable\_positioned\_list）。
    
-   3.10.0 已知存在问题(#105203 #113595)
    
-   2.0.0 已知存在问题(#68571 #73351 #74890 #79773 #79931)
    
-   ListView在没有设置分割线的情况下，个别Item之间存在大约1像素的间隔（像素对齐问题）。
    
-   其他历史问题见docs目录下的问题汇总。
    

Thanks For
----------

-   flutter\_wanandroid

License
-------

```
Copyright 2019 simplezhli

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
