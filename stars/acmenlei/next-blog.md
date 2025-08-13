---
project: next-blog
stars: 449
description: A blog system based on nextjs.
url: https://github.com/acmenlei/next-blog
---

next-ssr-blog
-------------

技术栈
---

-   **前台**：nextjs + typescript + antd
    
-   **管理台**：vue2 + element-ui + echarts
    
-   **服务端**：nodejs + mysql + redis
    

介绍
--

基于nextjs的博客网站，自己练手玩的项目，配套后台管理系统和服务端，博客一些常规功能都有，感兴趣的可以自己部署试试

项目启动
----

### 前台

1.  安装依赖

yarn install 或者 npm install

1.  启动项目

yarn dev 或者 npm run dev

### 后台

1.  启动后端之前请先启动`redis`, 后端依赖`redis`。

# 启动命令
redis-server

1.  导入必要的`mysql`结构，以及启动`mysql`，表结构在后端仓库自取
2.  完成以上操作后即可启动后端

yarn start
