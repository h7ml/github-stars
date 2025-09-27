---
project: mirai-api-http
stars: 1675
description: Mirai HTTP API (console) plugin
url: https://github.com/project-mirai/mirai-api-http
---

  

* * *

Mirai 是一个在全平台下运行，提供 QQ Android 和 TIM PC 协议支持的高效率机器人框架

这个项目的名字来源于

京都动画作品《境界的彼方》的栗山未来(Kuriyama **Mirai**)

CRYPTON以初音未来为代表的创作与活动(Magical **Mirai**)

图标以及形象由画师DazeCake绘制

mirai-api-http
==============

Mirai HTTP API (console) plugin

**mirai-api-http插件 提供HTTP API供所有语言使用mirai**

安装`mirai-api-http`
------------------

### 使用 Mirai Console Loader 安装`mirai-api-http`

-   `MCL` 支持自动更新插件，支持设置插件更新频道等功能
-   `2.x` 版本需要切换到 `stable-v2` 的 channel

`./mcl --update-package net.mamoe:mirai-api-http --channel stable-v2 --type plugin`

-   启动 `MCL` 完成自动更新和启动

`./mcl -u`

开始使用
----

1.  编辑`config/net.mamoe.mirai-api-http/setting.yml`配置文件 (没有则自行创建)
2.  启动MCL `./mcl`
3.  如果手动安装则启动 `mirai-console`(不建议)
4.  记录日志中出现的`authKey`

#### setting.yml模板

#\# 配置文件中的值，全为默认值

#\# 启用的 adapter, 内置有 http, ws, reverse-ws, webhook
adapters:
  - http
  - ws

#\# 是否开启认证流程, 若为 true 则建立连接时需要验证 verifyKey
#\# 建议公网连接时开启
enableVerify: true
verifyKey: 1234567890

#\# 开启一些调试信息
debug: false

#\# 是否开启单 session 模式, 若为 true，则自动创建 session 绑定 console 中登录的 bot
#\# 开启后，接口中任何 sessionKey 不需要传递参数
#\# 若 console 中有多个 bot 登录，则行为未定义
#\# 确保 console 中只有一个 bot 登录时启用
singleMode: false

#\# 历史消息的缓存大小
#\# 同时，也是 http adapter 的消息队列容量
cacheSize: 4096

#\# adapter 的单独配置，键名与 adapters 项配置相同
adapterSettings:
  #\# 详情看 http adapter 使用说明 配置
  http:
    host: localhost
    port: 8080
    cors: \["\*"\]
    unreadQueueMaxSize: 100
  
  #\# 详情看 websocket adapter 使用说明 配置
  ws:
    host: localhost
    port: 8080
    reservedSyncId: \-1

Adapter
-------

`mirai-api-http` 提供了多种接口调用方式, 并进行模块化称为 `adapter`

对于较常使用的调用方式, 内置了4种 `adapter`

-   http: 基于轮询的 http 接口
-   ws: websocket server 形式的接口
-   reverse-ws: websocket client 形式的接口
-   webhook: http 回调形式的接口

`adapter` 可以多个同时开启, 请按需启用

Adapter 一览

迁移至 2.x
-------

从 1.x 迁移至 2.x 有不少变动，提供迁移文档参考

可能无法覆盖所有变更

调试API
-----

(2.x 未更新)

更新日志
----

点我查看

文档
--

在线文档

-   **API文档参考**
    -   状态码
    -   获取插件信息
    -   缓存操作
        -   通过messageId获取消息
    -   获取账号信息
        -   获取好友列表
        -   获取群列表
        -   获取群成员列表
        -   获取Bot资料
        -   获取好友资料
        -   获取群成员资料
    -   消息发送与撤回
        -   发送好友消息
        -   发送群消息
        -   发送临时会话消息
        -   发送头像戳一戳消息
        -   撤回消息
    -   账号管理
        -   删除好友
    -   群管理
        -   禁言群成员
        -   解除群成员禁言
        -   移除群成员
        -   退出群聊
        -   全体禁言
        -   解除全体禁言
        -   设置群精华消息
        -   获取群设置
        -   修改群设置
        -   获取群员资料
        -   修改群员资料
    -   事件处理
        -   添加好友申请
        -   用户入群申请
        -   Bot被邀请入群申请
-   **事件类型参考**
    -   Bot自身事件
    -   好友事件
    -   群事件
    -   申请事件
-   **消息类型参考**
