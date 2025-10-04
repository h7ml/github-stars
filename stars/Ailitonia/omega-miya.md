---
project: omega-miya
stars: 279
description: 基于 nonebot2 的多平台机器人
url: https://github.com/Ailitonia/omega-miya
---

Omega Miya
==========

_基于 Nonebot2 的多平台机器人_

  

功能 & 特点
-------

-   基于异步 SQLAlchemy ORM, 支持多种数据库连接
    -   PostgreSQL
    -   MySQL and MariaDB
    -   SQLite
-   支持多协议端连接, 各协议端权限、订阅等配置相互独立
    -   Console Adapter -> 本机调试
    -   OneBot v11 Adapter -> go-cqhttp / Lagrange.OneBot / NapCatQQ
    -   QQ Adapter -> QQ 开放平台
    -   Telegram Adapter -> Telegram Bot
-   插件管理系统
-   权限控制系统
-   命令冷却系统
-   支持 openai API 接入
-   支持 HTTP 代理

插件
--

-   帮助功能
-   批量发送公告
-   定时消息
-   B站动态订阅
-   B站直播间监控
-   微博用户订阅
-   图站作品预览 (如不能直接访问各图站, 则需要 HTTP 代理)
-   Pixiv用户订阅 (如不能直接访问 Pixiv 主站, 则需要 HTTP 代理)
-   Pixivision特辑订阅 (如不能直接访问 Pixiv 主站, 则需要 HTTP 代理)
-   签到卡片
-   求签
-   词云
-   roll 点抽奖
-   AI 肉鸽故事 / AI 行动检定 (需配置 openai API)
-   塔罗牌
-   翻译插件 (使用腾讯云 API)
-   能不能好好说话 / 这是什么
-   QQ 群复读姬
-   QQ 群反撤回
-   QQ 群随机口球
-   QQ 自动处理加好友和被邀请进群
-   ShindanMaker占卜 (shindanmaker.com / 建议使用 HTTP 代理)
-   搜二次元图搜番剧 (Saucenao API, iqbb, ascii2d 等识图引擎 / 建议使用 HTTP 代理)
-   来点萌图 / 来点涩图 (需要 HTTP 代理, 除非部署在外网 / 图片数据库需要自己导入)
-   表情包制作器
-   今天吃啥
-   自动锤轴姬 (需要 OneBot V11 协议端支持文件发送 API)
-   邮箱插件 (仅支持 IMAP 收件)

如何使用
----

请参考本仓库 Wiki

关于图片数据
------

### 手动导入

如果你不想自己收集图片数据, 可以将 这个图片数据库 导入, 基本都是按我自己口味收集的图片

-   Update 2024.8.31: 更新图片数据库共 21.7 万条图片数据 (仅 `Pixiv` 来源, 包含已失效或画师已删除作品)
-   Update 2022.5.30: 更新图片数据库共 13.1 万条图片数据 (仅 `Pixiv` 来源, 包含已失效或画师已删除作品)
-   Update 2021.8.10: 更新图片数据库共 9.7 万条图片数据 (仅 `Pixiv` 来源, 包含已失效或画师已删除作品)

解压后直接把 `omega_artwork_collection_20240831201102.csv` 导入对应的 `artwork_collection` 表就好了

数据集来源大部分是我的 这个频道, 虽然已经断更很久了...

### 自动导入

目前内置的 `omega_artwork_collection_updater` 插件可以自动从图站收录图片作品, 来源包括 lolicon API, Pixiv 发现及首页推荐, danbooru/konachan/yande.re 的高评分作品

不过上述来源作品以 NSFW 居多, 还是建议导入上面的图库, 里面有很多 SFW 的萌图

### 关于图片分级分类

图片数据的分类分级字段解释如下

#### Classification: 主要体现图片由谁分级以及分级的**可靠性**

-   `Ignored = -2` 可能是由于**XP不符**/低质/敏感话题/广告等因素, 被人工手动审核/标记为忽略该作品, 一般情况下不应当使用分类为此等级的图片
-   `Unknown = -1` 无法确认分类级别, 一般为本地图片或无确切来源的图片
-   `Unclassified = 0` 未分类, 一般为无分级图站作品默认分类级别
-   `AIGenerated = 1` 确认/疑似为 AI 生成作品
-   `Automatic = 2` 由图站分类/图站分级/第三方接口分类, 可能由人工进行分类但不完全可信, 一般可作为应用层插件使用的最低可信级别
-   `Confirmed = 3` 由人工审核/确认为 "人类生成" 的作品, 且分级可信

说白了就是 `Classification = 3` 的才代表本人XP, 其他级别均为未分类/自动爬取/忽略排除, 本人概不负责

#### Rating: 图片分级

-   `Unknown = -1` 未知, 可能为下面任意一种分级的其中之一, 绝对不要直接当作 G-rated 作品使用
-   `General = 0` G-rated content, 任何人随时可观看的, sfw
-   `Sensitive = 1` Ecchi, sexy, suggestive, or mildly erotic, 包含内衣/泳装/部分裸露/暗示性动作等, 涩图, nsfw
-   `Questionable = 2` Softcore erotica, 除了关键之外的明目张胆, 官能作品, nsfw+
-   `Explicit = 3` Hardcore erotica, 限制级作品, R18, nsfw+++

一张图看懂如何获取 Pixiv Cookies
-----------------------

**注意！该 cookie 等同于您账号控制权，请不要泄露给他人！**

**注意！该 cookie 等同于您账号控制权，请不要泄露给他人！**

特别感谢
----

-   **非常可爱的 @喵田弥夜Miya 画的 Logo**
-   Nonebot2
-   go-cqhttp
-   OneBot
-   ZhouShen\_Hime
-   nonebot-plugin-petpet

说点题外话
-----

Omega\_miya 的设计思路显然与 Nonebot 插件间应该尽可能解耦的设计思路相悖。

当然这和 Omega\_miya 最初的用途有关，她本来是用来督促字幕组摸鱼干活的，并且一开始设计的时候继承了初代真正零号 Omega\_miya 的数据库以及设计思路，所以 Omega\_miya 的插件体系是强耦合的，后来随着功能迭代，也就改不过来了。

因此，对于 Omega\_miya 这个项目，我想她可能并不是可以直接拿来就用的，因为她的设计本身就有局限性，这里大概是可以提供某些插件功能上的思路，希望能给其他的开发者带来一些帮助。

欢迎来提各种issue~

Supported by
------------
