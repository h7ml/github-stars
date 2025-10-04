---
project: DataV
stars: 9481
description: Vue数据可视化组件库（类似阿里DataV，大屏数据展示），提供SVG的边框及装饰、图表、水位图、飞线图等组件，简单易用，长期更新(React版已发布)
url: https://github.com/DataV-Team/DataV
---

ENGLISH

DataV
=====

DataV是干什么的?
-----------

-   DataV是一个基于**Vue**的数据可视化组件库（当然也有React版本）
-   提供用于提升页面视觉效果的**SVG**边框和装饰
-   提供常用的**图表**如折线图等
-   飞线图/轮播表等其他组件

### npm安装

$ npm install @jiaminghi/data-view

### 使用

import Vue from 'vue'
import DataV from '@jiaminghi/data-view'

Vue.use(DataV)

// 按需引入
import { borderBox1 } from '@jiaminghi/data-view'
Vue.use(borderBox1)

详细文档及示例请移步HomePage.

### UMD版

`UMD`版可直接使用`script`标签引入，`UMD`版文件位于项目`dist`目录下，引入后将自动把所有组件注册为**Vue全局组件**，引入`DataV`前请确保已引入`Vue`。

UMD版使用示例

### TODO

-   **地图组件**
-   **TS**重构组件库底层依赖

### 致谢

组件库的开发基于个人学习和兴趣，由于技术水平及经验的限制，组件尚有许多不完善之处，如有BUG可及时提交issue或添加反馈群进行反馈，也欢迎提供指正和建议，感谢各位的支持。

### 反馈

### Demo

Demo页面使用了全屏组件，请F11全屏后查看。

-   施工养护综合数据

-   机电运维管理台

-   机电设备电子档案
