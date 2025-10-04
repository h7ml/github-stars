---
project: anti-redirect
stars: 504
description: :rocket:去除各搜索引擎/常用网站的重定向
url: https://github.com/axetroy/anti-redirect
---

### GM 脚本，反重定向

去除各搜索引擎/常用网站的重定向

> 注意事项：
> 
> 重定向一般有两种目的
> 
> 1.  追踪用户打开了哪些 URL
> 2.  在用户跳转到站外之前进行确认地址，防止打开不明的页面

### 反馈地址

> 反馈最好能带上出问题的网页地址

-   https://github.com/axetroy/anti-redirect/issues/new/choose
-   https://github.com/axetroy/anti-redirect/issues/new/choose
-   https://github.com/axetroy/anti-redirect/issues/new/choose

### 如果这能够帮助到你, 不妨点个 star, 你的支持就是我更新的动力

点击从 Github 安装

点击从 GreasyFork 安装

点击从 CDN 安装(国内用户)

### 工作原理

1.  根据 URL 上暴露出来的跳转链接，正则匹配提取真实的地址，例如知乎，Google
2.  如果 A 标签的内容为真实的地址，则替换，例如百度贴吧
3.  逐一发送请求，获取真实的地址，例如百度搜索
4.  根据请求特殊页面，这个特殊页面没有重定向地址，然后覆盖当前页，例如百度搜索，搜狗搜索
5.  覆盖原本的链接点击事件，比如 qq 邮箱

### 更新日志

https://github.com/axetroy/anti-redirect/blob/master/CHANGELOG.md

### 支持的站点

-   知乎
-   知乎专栏
-   知乎日报
-   Google 搜索
-   Google 文档
-   Google Play
-   Google Gmail
-   Google Youtube
-   Steam
-   360 搜索
-   新浪微博
-   Twitter
-   搜狗搜索
-   百度搜索
-   百度视频
-   百度学术
-   百度贴吧
-   掘金
-   QQ 邮箱
-   Mozilla
-   简书
-   豆瓣
-   Pocket
-   DogeDoge
-   秘迹
-   CSDN
-   开源中国
-   印象笔记
-   标志情报局
-   爱发电
-   51 CTO
-   InfoQ
-   Gitee
-   少数派

更多

-   51.ruyo.net

### 我想支持更多的站点

点击这个链接，提交 issues，说出你想要支持的站点

### 贡献代码

需要通过 NodeJs 把 TypeScript 编译成 javascript

git clone https://github.com/axetroy/anti-redirect.git

cd ./anti-redirect

npm install
npm run watch

### 开源许可

The Anti 996 License

请仔细阅读开源许可。

简而言之： 如果你正在 996，或者你的公司/单位正在 996 ，那么请不要安装这个脚本！
