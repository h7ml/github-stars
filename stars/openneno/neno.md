---
project: neno
stars: 534
description: 使用svelte+tailwindcss 仿照 浮墨 写的pwa应用
url: https://github.com/openneno/neno
---

NENO
====

仿照浮墨的开源版本

-   svelte+tailwindcss构建的PWA应用
-   基本功能上与浮墨保持相同
-   **无需后端,完全使用github或者gitee进行存储你的所有数据,文字和图片**
-   **支持完全离线使用**
-   **支持完整版数据导入导出**
-   **支持同步内容到Notion(使用gihub action)**
-   **支持utools的neno插件**
-   **支持微信公众号记录笔记到neno**
-   **支持Telegram Bot记录笔记到neno**
-   **支持CLI工具记录笔记到neno**
-   **支持浏览器插件记录笔记到neno**

### neno的外部扩展工具

1.  utools 是一个快速的工具平台。在utools上搜索neno插件，即可使用。
    
    > 项目地址neno-extension
    
2.  使用微信公众号进行输入。
    
    > 项目地址neno-wx
    
3.  使用Telegram Bot进行输入。
    
    > 项目地址neno-telegram 体验地址neno Bot
    
4.  使用CLI进行输入。
    
    > 项目地址neno-cli
    
5.  使用谷歌浏览器插件进行快速选择文本输入
    
    > 项目地址neno-chrome-plugin
    

马上体验

### 前端部署方式

#### 自己打包

```
npm install
node run build
dist 目录下面为构建好的前端页面
```

### 部署到vercel

如何使用
----

填上自己的githubtoken,然后点击获取github用户名,填上用于存储数据的仓库名称,点击保存即可

### Todo

-   分享出图片
-   完全基于浏览器的离线版本
-   使用github进行存储
-   基于github action 的notion 同步
-   基于serverless的 的微信公众号输入笔记
-   基于serverless的 的TelegramBot输入笔记
-   每日回顾
-   随机漫步

* * *

License
-------

GPL
