---
project: WuKongIM
stars: 4333
description: More than just IM 不只是即时通讯( IM )
url: https://github.com/WuKongIM/WuKongIM
---

悟空IM（让信息传递更简单）
--------------

10(2015)年积累，沉淀出来的高性能通用通讯服务，支持即时通讯，站内/系统消息，消息中台，物联网通讯，音视频信令，直播弹幕，客服系统，AI通讯，即时社区等场景。

`本项目需要在go1.20.0或以上环境编译`

`不再支持Windows系统`

分布式IM重要特性： 故障自动转移，去中心化设计，节点之间数据互备，支持集群快速自动扩容，代理节点机制

涉及到的知识点： 自定义协议， 分布式Raft（魔改pull模式），多组Raft（魔改pull模式），关系数据库底层原理，分布式数据库设计， Reactors设计，独创分布式多层领导机制 等等

English

-   **官网**: https://githubim.com
-   **通讯协议1**: WuKongIM二进制协议
-   **通讯协议2**: WuKongIM JSON协议(仅Websocket)
-   **提问**: https://github.com/WuKongIM/WuKongIM/issues
-   **文档**: https://githubim.com
-   **架构文档**: https://deepwiki.com/WuKongIM/WuKongIM

架构图
---

视频演示
----

故障转移演示

AI演示

演示
--

**聊天Demo**

web聊天场景演示： http://imdemo.githubim.com

后端监控演示： http://monitor.githubim.com/web

测试报告： https://githubim.com/server/advance/stressSingleReport.html

吹个牛
---

开源中唯一`去中心化`的分布式IM

开源中唯一单机发送并发超`20万`的IM

开源中唯一内置自研分布式存储的IM

开源中唯一不依赖任何中间件的分布式IM

特点
--

🎦**独特性**

群成员无上限，轻松支持10万人群聊，消息可永久存储。

📚**资源消耗低**

自研二进制协议，心跳包只有1字节，省流量，省电量，传输更迅速。

🔐**安全性**

消息通道和消息内容全程加密，防中间人攻击和窜改消息内容，服务端数据实时备份，数据不丢失。

🚀 **性能**

基于pebble kv数据库，研发了针对于IM这种服务的特有分布式数据库，省了其他数据库为了通用性而带来的性能损耗， 因为存储快，所以消息快。

🔥**高可用**

通过魔改raft分布式协议，实现了自动容灾，一台机器宕机，另一台机器自动接管，对外无感知。

去中心化，无单点，无中心节点，每个节点都是独立且平等的，都可以提供服务。

扩容方便，只需增加机器，不需要停机，不需要迁移数据，自动按策略分配数据。

0⃣️ **易用性**

不依赖任何第三方中间件，部署简单，一条命令即可启动。

采用频道订阅发布的设计理念，容易理解，容易上手。

与Redis一样简单，Kafka一样高性能，MySQL一样可靠

🌲**技术支持**

官方团队提供技术支持，提供技术文档，提供技术交流群，提供issue反馈。

功能特性
----

-   支持自定义消息
-   支持订阅/发布者模式
-   支持个人/群聊/客服/社区资讯频道
-   支持频道黑名单
-   支持频道白名单
-   支持消息永久漫游，换设备登录，消息不丢失
-   支持在线状态，支持同账号多设备同时在线
-   支持多设备消息实时同步
-   支持用户最近会话列表服务端维护
-   支持指令消息
-   支持离线指令接口
-   支持Webhook，轻松对接自己的业务系统
-   支持Datasource，无缝对接自己的业务系统数据源
-   支持Websocket连接
-   支持TLS 1.3
-   支持proxyproto协议
-   支持JSON协议通讯
-   支持Prometheus监控
-   监控系统开发
-   支持流式消息，类似chatgpt的结果输出流
-   支持分布式
    -   去中心化设计，任意一个节点宕机，集群自动修复
    -   集群节点之间数据互备，任意一个节点损害，不影响数据完整性
    -   支持集群快速自动扩容

快速部署体验
------

git clone https://github.com/WuKongIM/WuKongIM.git

cd WuKongIM/docker/cluster

sudo docker compose up -d

后台管理系统： http://127.0.0.1:15300/web

聊天演示地址：http://127.0.0.1:15172/login

源码开发
----

### 单机

go run main.go

(或 go run main.go --config config/wk.yaml)

### 分布式

# 启动第一个节点
go run main.go --config  ./exampleconfig/cluster1.yaml

# 启动第二个节点
go run main.go --config  ./exampleconfig/cluster2.yaml

# 启动第三个节点
go run main.go --config  ./exampleconfig/cluster3.yaml

### 访问

后台管理系统： http://127.0.0.1:5300/web

聊天演示地址：http://127.0.0.1:5172/chatdemo

### 客户端使用

import { WKIM, WKIMChannelType, WKIMEvent } from 'easyjssdk';

// 1. 初始化
const im \= WKIM.init("ws://your-wukongim-server.com:5200", {
    uid: "your\_user\_id", // 当前连接的用户uid
    token: "your\_auth\_token" // 当前连接用户的认证token（默认不需要认证，如果开启了需要填写）
});

// 2. 监听
im.on(WKIMEvent.Connect, () \=> {
    console.log("IM Connected!");
    //  发送消息
    const result \= await im.send("target user",WKIMChannelType.Person,{ type: "text", content: "Hello from EasyJSSDK!" })
});

// 监听接收消息事件
im.on(WKIMEvent.Message, (message) \=> {
    console.log("Received:", message);
});

// 监听错误事件
im.on(WKIMEvent.Error, (error) \=> {
    console.error("IM Error:", error);
});

// 3. 连接
await im.connect()

正式部署
----

请参考部署文档

配套SDK源码和Demo
------------

项目名

Github地址

Example

文档

说明

WuKongIM

Github

无

文档     

悟空IM通讯端，负责长连接维护，消息投递等等

WuKongIMAndroidSDK

Github

Example

文档

悟空IM的Android SDK

WuKongIMiOSSDK

Github

Example

文档

悟空IM的iOS SDK

WuKongIMUniappSDK

Github

Example

文档

悟空IM的 Uniapp SDK

WuKongIMJSSDK

Github

Example

文档

悟空IM的 JS SDK

WuKongIMFlutterSDK

Github

Example

文档

悟空IM的 Flutter SDK

WuKongIMReactNativeDemo

Github

无

无

悟空IM的 React Native Demo(由贡献者 wengqianshan 提供)

WuKongIMHarmonyOSSDK

Github

Example

文档

WuKongIM的纯血鸿蒙OS SDK

节点故障转移演示
--------

后台截图
----

Star
----

我们团队一直致力于即时通讯的研发，需要您的鼓励，如果您觉得本项目对您有帮助，欢迎点个star，您的支持是我们最大的动力。

案例展示
----

**项目名**

TangSengDaoDao

**开源地址**

https://github.com/TangSengDaoDao/TangSengDaoDaoServer

**截图**

Wechat
------

如果有需要，加我拉你进群，微信号：wukongimgo

License
-------

WuKongIM is licensed under the Apache License 2.0.
