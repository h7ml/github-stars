---
project: qq-music-api
stars: 922
description: QQ 音乐API koa2实现
url: https://github.com/Rain120/qq-music-api
---

QQ Music API
============

  
  

> QQ音乐API koa2 版本, 通过Web网页版请求QQ音乐接口数据, 有问题请提 issue

> 当前代码仅供学习，不可做商业用途

### API结构图

> 目前暂时没有时间做登录模块的接口，欢迎各位大佬给我`PR`, 阿里嘎多

### 环境要求

> 因为本项目采用的是`koa2`, 所以请确保你的`node`版本是7.6.0+

```
node -v
```

### 📦 安装

```
git clone git@github.com:Rain120/qq-music-api.git
cd qq-music-api
npm install
```

### 🔨项目启动

```
// npm i -g nodemon
npm run start

// or don't install nodemon
node app.js
```

项目监听端口是`3200`

### 🐳 Docker

# local local build
npm run build:local-images

# local remote build
npm run build:remote-images

# build images
npm run build:images

# local run
npm run run:images

# remote run
docker pull qq-music-api

### 功能特性

-   获取歌曲播放链接 **2021-01-24**
    
-   支持自定义设置 `cookie` **2021-01-23**
    
-   获取歌曲 + 专辑图片 **2020-05-24**
    
-   获取歌手热门歌曲 **2020-07-04**
    
-   获取QQ音乐产品的下载地址
    
-   获取歌单分类
    
-   获取歌单列表
    
-   获取歌单详情
    
-   获取MV标签
    
-   获取MV播放信息
    
-   获取歌手MV
    
-   获取相似歌手
    
-   获取歌手信息
    
-   获取歌手被关注数量信息
    
-   获取电台列表
    
-   获取专辑
    
-   获取数字专辑
    
-   获取歌曲歌词
    
-   获取MV
    
-   获取新碟信息
    
-   获取歌手专辑
    
-   获取歌曲VKey **2021-01-24**
    
-   获取搜索热词
    
-   获取关键字搜索提示
    
-   获取搜索结果
    
-   获取首页推荐
    
-   获取排行榜单列表
    
-   获取排行榜单详情
    
-   获取评论信息(cmd代表的意思没太弄明白)
    
-   获取票务信息
    
-   获取歌单详情
    
-   获取歌手列表
    

### 使用文档

使用`apis`详见文档

### 关于项目

**灵感来自**

Binaryify/NeteaseCloudMusicApi

Vue2.0开发企业级移动端音乐Web App

**参考内容**

Koa 2

Axios

阮一峰老师 - HTTP Referer 教程

### 项目不足

1.  因为本人没写过`unit test`, 所以本项目尚未添加`unit test`, 等有时间再添加;
    
2.  登录获取个人信息等接口都没做
    

#### 🤝 贡献

We welcome all contributions. You can submit any ideas as pull requests or as a GitHub issue.

#### 👨‍🏭 作者

> Front-End development engineer, technology stack: React + Typescript + Mobx, also used Vue + Vuex for a while

-   Github
-   知乎
-   掘金

#### 📝 License

MIT

Copyright © 2019-present Rain120.
