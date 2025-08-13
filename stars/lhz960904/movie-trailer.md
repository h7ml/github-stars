---
project: movie-trailer
stars: 482
description: :popcorn:Vue3 + TypeScript开发的电影预告片webAPP，可以查看正在热映与即将上映的电影信息和短片
url: https://github.com/lhz960904/movie-trailer
---

movie-trailer
=============

Caution

由于项目复杂度较低、技术栈落后，后续不会继续维护此项目

> Vue全家桶开发的电影预告片webAPP，可以查看正在热映与即将上映的电影信息和短片。

**相关项目**:

-   后台API支持movie-api (已升级成Egg)
    
-   电影数据爬虫movie-crawler (python爬取，已废弃)
    
-   Flutter项目 链接
    

### 扫码体验

### 效果截图

### 更新日志

**V4.0.0**

-   使用 Nuxt3
-   使用`vercel`实现持续集成，自动发布

**V3.0.0**

-   使用vue3 + TypeScript进行重构
-   使用`travis`实现持续集成，自动发布

**V2.0.0**

-   尝试使用持续集成工具`travis`进行打包测试(有待继续探索、实现自动发布)
-   评分区间筛选器从 _点击_ 改为 _手指滑动_ 、提升体验
-   ESLint加强增加`@vue/standard`、对组件重新、抽离全局组件
-   `axios`进行封装，处理不同的返回值code、增加`error`页面
-   脚手架升级`vue-cli3`

**V1.0.0**

-   首页推荐正在上映、即将上映的电影
-   通过分类、上映状态、评分区间进行筛选电影
-   通过搜索进行筛选电影、搜索历史通过localStorage存储
-   个人中心页面，注册和登录
-   电影详情短片播放、相关电影推荐、剧情简介
