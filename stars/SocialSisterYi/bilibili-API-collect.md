---
project: bilibili-API-collect
stars: 19288
description: 哔哩哔哩-API收集整理【不断更新中....】
url: https://github.com/SocialSisterYi/bilibili-API-collect
---

哔哩哔哩 - API 收集整理
===============

### 野生 API 文档

### 不断更新中....

本项目旨在对 B 站 WEB、APP、TV 等客户端中，散落在世界各地的野生 API 进行收集整理，研究使用方法并对其进行说明，运用了黑箱法、控制变量法、代码逆向分析、拆包及反编译法、网络抓包法等研究办法

本文档探讨的对象是主站业务接口，官方开放平台 和 直播开放平台 均不属于本项目范畴，请移步

B站 API 采用 C/S 结构，大多数接口为 REST API 和 gRPC，少部分接口为 WebSocket；REST API 接口请求数据大多为 url query 表单或 JSON，返回数据大多为 JSON 或 Protobuf，强制使用 https 协议

📖阅读地址：Github Pages

小小的 Demo：av583785685 视频失效原因 (Youtube 备链)

::: warning 声明

1.  本项目遵守 CC-BY-NC 4.0 协议，禁止一切商业使用，如需转载请注明作者 ID
2.  **请勿滥用，本项目仅用于学习和测试！请勿滥用，本项目仅用于学习和测试！请勿滥用，本项目仅用于学习和测试！**
3.  利用本项目提供的接口、文档等造成不良影响及后果与本人无关
4.  由于本项目的特殊性，可能随时停止开发或删档
5.  本项目为开源项目，不接受任何形式的催单和索取行为，更不容许存在付费内容
6.  **上传任何信息时请注意脱敏，删去账户密码、敏感 cookies 等可能泄漏个人信息的数据（例如 `SESSDATA`、`bili_jct` 之类的 cookies）**

:::

🌱参与贡献
------

欢迎各位 dalao 对本项目做出贡献，也希望每个使用者都能提出宝贵的意见

目前本项目存在的问题包括但不限于：

1.  文档二级目录尚未完成
2.  部分文档较旧，修改与更新没有跟进
3.  目前文档使用 Markdown 语法编写，不易生成编程语言的 SDK，详见 #604

更多信息请浏览 贡献指南

🍴目录
----

计划整理分类 & 目录：(文档已完结请选中 checkbox)

-   接口签名与验证
    -   APP API 签名（`appkey` 与 `sign`）
    -   已知的 APPKey
    -   Wbi 签名（`wts`与`w_rid`）
    -   bili\_ticket
    -   v\_voucher 验证
-   杂项
    -   获取当前时间戳
    -   公共错误码
    -   图片格式化
    -   表达式渲染
    -   bvid 说明
    -   设备唯一标识 BUVID
    -   获取 buvid3 / buvid4 / b\_nut
    -   b23.tv 短链
-   gRPC API 接口定义
-   登录
    -   登录操作 (人机认证)
        -   短信登录
        -   密码登录
        -   二维码登录
        -   SNS 登录 (QQ & 微信 & 微博)
    -   登录基本信息
    -   个人中心
    -   注销登录
    -   登录记录
    -   Web 端 Cookie 刷新
-   消息中心
    -   通知类消息
    -   私信
        -   私信消息类型、内容说明
    -   设置
-   用户
    -   基本信息
    -   状态数
    -   关系
    -   个人空间
    -   检查昵称是否可注册 (已失效)
    -   用户注册
    -   用户认证类型一览
    -   加入老粉计划
    -   所有粉丝勋章
    -   批量查询
-   大会员
    -   大会员基本信息
    -   大会员中心
    -   大会员签到
    -   大会员操作
-   视频
    -   视频分区一览 (分区代码)
    -   视频分区一览 (分区代码) (v2)
    -   基本信息
    -   状态数 (已失效)
    -   快照
    -   点赞 & 投币 & 收藏 & 分享
    -   TAG
    -   视频推荐
    -   播放 & 下载地址 (视频流)
    -   互动视频
    -   高能进度条
    -   信息上报 (心跳及记录历史)
    -   视频属性数据
    -   视频在线人数
    -   视频 AI 摘要
    -   稿件投诉
    -   视频合集
    -   播放器
-   剧集 (番剧、影视)
    -   基本信息
    -   播放 & 下载地址（视频流）
    -   时间轴
    -   追番相关
    -   状态数
    -   操作
-   视频弹幕
    -   protobuf 实时弹幕
    -   protobuf 弹幕元数据（BAS 弹幕 / 互动弹幕）
    -   xml 实时弹幕
    -   历史弹幕
    -   快照
    -   弹幕操作
    -   高级弹幕
    -   屏蔽管理
    -   智能防挡弹幕
    -   弹幕个人配置修改
    -   名词解释
    -   点赞查询
-   视频笔记
    -   笔记列表
    -   笔记详细信息
    -   笔记操作
-   图文
    -   图文详细
    -   空间图文
    -   功能模块
    -   富文本节点
-   专栏
    -   专栏内容
    -   专栏分类
    -   卡片信息
    -   基本信息
    -   点赞 & 投币 & 收藏 & 分享
    -   文集基本信息
-   动态
    -   获取动态列表
    -   用户空间动态
    -   动态基本信息
    -   动态卡片信息字段
    -   获取动态详情
    -   动态类型对照
    -   动态信息
    -   发送 & 转载动态
    -   根据关键字搜索用户（at 别人时的填充列表）
    -   操作
    -   话题
    -   动态内容
    -   导航栏动态
    -   首页公告栏
-   创作中心
    -   投稿
    -   统计与数据
    -   列表查询相关
    -   电磁力数据
    -   合集管理
    -   视频相关杂项
    -   图文操作
-   音频
    -   歌曲基本信息
    -   歌单 & 音频收藏夹详细信息
    -   状态数
    -   投币 & 收藏
    -   播放 & 下载地址（音频流）
    -   音频榜单
-   排行榜 & 最新视频
    -   排行榜
    -   热门视频
    -   最新视频
    -   入站必刷视频
-   搜索
    -   搜索请求
    -   搜索结果
    -   默认搜索 & 热搜
    -   搜索建议
-   小黑屋
    -   基本信息
    -   封禁公示
    -   风纪委员及众裁案件相关
        -   风纪委员基本信息
        -   众裁案件基本信息
        -   裁决操作
-   评论区
    -   评论区明细
    -   操作
-   表情
    -   表情及表情包信息
    -   操作
-   实时广播（通讯协议）
    -   视频内广播
-   充电
    -   包月充电
    -   自定义充电
        -   B 币方式充电
        -   微信 & 支付宝方式充电
        -   充电留言
    -   充电列表
-   相簿 (已下线)
    -   基本信息
    -   相簿列表
    -   推荐作者
    -   活动列表
    -   操作
    -   投稿
-   历史记录 & 稍后再看
    -   历史记录
    -   稍后再看
-   收藏夹
    -   基本信息
    -   收藏夹内容
    -   收藏夹操作
-   课程
    -   课程基本信息
    -   已购课程
    -   分区推荐列表
    -   操作
    -   播放 & 下载地址（视频流）
-   直播
    -   直播间基本信息
    -   直播推荐
    -   直播分区
    -   直播间管理
    -   直播间操作
    -   直播视频流
    -   直播信息流
    -   直播红包
    -   直播间表情包
    -   直播间用户实用 API
    -   直播间禁言相关
    -   关注UP直播情况
    -   直播心跳上报
    -   直播间弹幕
    -   直播流水
    -   礼物相关
    -   大航海/粉丝团
    -   直播回放
    -   直播数据
    -   直播投票
-   活动
    -   活动列表
    -   活动主题信息
-   转正答题
    -   查询信息
    -   拉取题目
    -   操作
-   青少年守护
    -   青少年模式
    -   亲子平台
    -   课堂模式
-   B 币钱包
    -   基本信息
    -   B 币充值
    -   贝壳相关
-   哔哩哔哩漫画
    -   用户信息
    -   签到
    -   积分商城
    -   漫画操作
    -   漫画任务操作
    -   漫画赛季
    -   漫读券/已购相关
    -   下载
    -   data.index 解析
    -   获取轻享卡信息
-   哔哩哔哩游戏
-   终端网络查询
    -   基于 IP 的地理位置查询
-   客服中心
    -   客服消息
-   web 端组件
    -   分区当日投稿数
    -   404 页漫画收集
    -   首页横幅头图
    -   分区横幅轮播图
-   APP 端组件
    -   开屏图片 + 恰饭珍贵录像
    -   获取最新 APP 版本
-   个性装扮
    -   APP 主题
    -   主题色
    -   装扮/收藏集

✨鸣谢
---

你们的存在，让社区更美好

📖相关协议基础
--------

HTTP 协议：传送门

JSON 序列格式：传送门

XML 序列格式：传送门

ProtoBuf 序列格式：传送门

💦交流
----

⚠注意：开源社群欢迎交流探讨，**拒绝**咨询、**不支持**合作，**黑产号**一经发现立即拉黑并举报相关 SRC

-   QQ 交流群：邀请链接
-   Telegram 交流群：@bilibili\_API\_collect\_community

🧋发电
----

欢迎来交♂易，大家的支持就是我继续开发的动力！

请可爱的易姐喝杯奶茶

WeChat & Alipay：

OR Aifadian：https://afdian.com/@ShakaiAneE

🔗相关项目推荐
--------

### 库及文档

-   jingyuexing/bilibiliAPI
-   fython/BilibiliAPIDocs
-   czp3009/bilibili-api
-   Vespa314/bilibili-api
-   Pengfei00/bili-utils: bilibili 工具箱
-   lovelyyoshino/Bilibili-Live-API: Bilibili 直播/番剧 API 文档
-   flaribbit/bilibili-manga-spider: Bilibili 漫画爬虫
-   simon300000/bili-api: Bilibili Node.js API
-   iyear/biligo: Bilibili API SDK in Golang
-   bilibili-openplatform/demo: 哔哩哔哩开放平台示例代码库
-   ddiu8081/blive-message-listener: Bilibili-live danmu listener with type. Bilibili 直播间弹幕监听库，支持类型输出。
-   Nemo2011/bilibili-api: 哔哩哔哩常用API调用。支持视频、番剧、用户、频道、音频等功能。工具齐全。
-   CuteReimu/bilibili: 哔哩哔哩API的Go版本SDK

### 成品

-   NullPointerException/AnimePipe: 功能完善的Android流媒体综合客户端，支持Bilibili, Youtube, NicoNico
-   3Shain/Comen: 基于h5的B站直播弹幕姬
-   AncientLysine/BiliLocal: 本地弹幕播放器
-   zyzsdy/biliroku: bilibili 生放送（直播）录制
-   otakustay/danmaku-to-ass: A站B站弹幕转字幕文件
-   bilibili-helper/bilibili-helper-o: 哔哩哔哩 (bilibili.com) 辅助工具，可以下载视频，查询弹幕发送人以及一些十分实用的直播区功能。
-   apachecn/CDNDrive: 基于B站相簿上传的文件分块索引存储器
-   Hsury/BiliDrive: 基于B站相簿上传的文件分块索引存储器
-   Tsuk1ko/bilibili-live-chat: 无后端的仿 YouTube Live Chat 风格的简易 Bilibili 弹幕姬
-   ironmanic/crawler\_target\_users\_good: 搜索bilibili特定视频，为评论 点赞，关注，私信，一体化服务
-   dd-center/DDatElectron: DD@Home 分布式项目, 桌面客户端
-   dd-center/vtbs.moe: B站VTB数据中心
-   the1812/Bilibili-Evolved: 强大的哔哩哔哩增强脚本: 下载视频、音乐、封面、弹幕 / 简化直播间、评论区、首页 / 自定义顶栏、删除广告、夜间模式 / 触屏设备支持
-   xlzy520/bili-short-url: 哔哩哔哩短链生成器
-   zjkwdy/bili\_app\_splash: B站壁纸娘和开屏图自动下载，每天使用Actions自动同步
-   Jannchie/BiliOB: BiliOB观测者是一个观测B站UP主及视频数据变化，并予以分析的Web应用程序
-   biliob233/biliob233.github.io: 无可奉告
-   biliup/biliup: 全自动录播、投稿工具，支持录制直播弹幕，也支持Youtube、twitch直播回放列表自动搬运到B站
-   ddiu8081/bilicli: Bilibili-live danmu dashboard in your terminal.
-   MotooriKashin/Bilibili-Old: 恢复旧版Bilibili页面，为了那些念旧的人。
-   SocialSisterYi/bcut-asr: 使用必剪API的语音字幕识别
-   CzJam/Bili\_Realtime\_Data: Bilibili粉丝与视频实时数据统计
-   kingwingfly/fav: 自动同步bili收藏夹、合集视频到本地的CLI工具（Rust实现，并提供一个文档测试完善的Rust风格的用于构建有状态爬虫的核心库）
-   linyuye/Bilibili\_crawler: 基于bilibili懒加载api爬取b站动态，视频等评论区
-   ouzexi/bilibili-hot-tags: 一个B站热门视频标签检索统计小工具

### 其他

-   kuresaru/geetest-validator: GeeTest 调试器
-   bloomrpc/bloomrpc: GUI Client for GRPC Services
-   grpc/grpc: The C based gRPC (C++, Python, Ruby, Objective-C, PHP, C#)
-   glideapps/quicktype: quicktype generates strongly-typed models and serializers from JSON, JSON Schema, TypeScript, and GraphQL queries, making it a breeze to work with JSON type-safely in many programming languages. 一键生成多种语言的JSON反序列化所需类，以便于快速反序列化，有网页版
-   SessionHu/json-apidoc-gen: Simple CLI tool for generating BAC document template
