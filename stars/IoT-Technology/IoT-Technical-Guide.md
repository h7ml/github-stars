---
project: IoT-Technical-Guide
stars: 4400
description: :honeybee: IoT Technical Guide --- 从零搭建高性能物联网平台及物联网解决方案和Thingsboard源码分析 :sparkles: :sparkles: :sparkles: (IoT Platform, SaaS, MQTT, CoAP, HTTP, Modbus, OPC, WebSocket, 物模型，Protobuf, PostgreSQL, MongoDB, Spring Security, OAuth2, RuleEngine, Kafka, Docker)
url: https://github.com/IoT-Technology/IoT-Technical-Guide
---

交流群
===

扫码如下**二维码**。回复【物联网技术指南】关键字。

可以添加帅气而又风趣的我为好友，并拉你进一个学习交流**装逼群**。

物联网技术学习指南
=========

基于物联网场景和技术的入门和深度学习教程。

物联网相较于电商、支付和金融等是一个全新的行业。但是物联网又是一个高速发展的行业，很多人想要从事这个行业，但是不得其法，于是诞生了此教程。

市面上的物联网技术文章很少，且文章的质量都较为粗浅和不成体系。对于很多开发者来说，入门即是其对某个技术栈的最终理解，一方面是开发者“比较懒”，另一方面是文章作者把物联网技术写的太浅，又或者不够全面。

-   整理了物联网学习资源和书籍，涉及计算机网络、算法和书籍结构、框架、数据存储等每个细节的知识。
    
-   在学习基础知识的同时，我想要你了解物联网开发常见的~~**黑话**~~专业术语，例如数字孪生、设备影子、通信相关的术语名词、蓝牙、Zigbee、CoAP、MQTT协议等。
    
-   在带你学会MQTT v3.1、v3.1.1和v5.0协议的同时，我还想告诉你当前流行和好用的MQTT 客户端工具和不同语言的MQTT Client依赖包，最后以实战的方式带你实现一个单机百万的MQTT Broker。
    
-   学习上面的知识后，我相信你对物联网有所了解了，我允许你叉着腰**骄傲**一下，接下来我会带你学习从零搭建高性能IoT平台所需要的技术栈、包括架构设计、MQTT Broker搭建、CoAP服务搭建、消息削峰、数据模型设计和数据库选型等。
    
-   最好我带你编译和学习当前GitHub上最流行的开源物联网平台-Thingsboard, 其在GitHub上点赞超过1w+, 学习前沿的物联网理念和知识，如果你有二次开发的需求，也可沟通联系我欧！一起探讨学习！
    
-   ...
    
    让我们一起愉快的挖坑，挖深坑，哇哈哈。
    

Part1 物联网基石和学习之路
----------------

### Part1-1『 物联网学习书籍和资源 』

-   计算机网络篇
    
    -   《TCP/IP详情 卷1: 协议》
        
    -   《TCP/IP详情 卷2: 实现》
        
    -   《TCP/IP详情 卷3: TCP事务协议、HTTP、NNTP和UNIX域协议》
        
    -   《图解TCP/IP (第5版)》
        
    -   《图解HTTP》
        
-   算法和数据结构篇
    
    -   《我的第一本算法书》
        
    -   《算法导论 (第四版))》
        
-   Java基础
    
    -   《Head First Java》
        
    -   《Effective Java 中文版》
        
    -   《Java并发编程实战》
        
-   Spring及SpringBoot系列
    
    -   《Spring 实战 (第四版)》
        
    -   《Spring Boot揭秘》
        
-   数据存储篇
    
    -   《MySQL必知必会》
        
    -   《高性能MySQL》
        
    -   《MongoDB实战》
        
    -   《PostgreSQL实战》
        
-   缓存篇
    
    -   《Redis 开发与运维》
        
    -   《Redis深入历险：核心原理与应用实战》
        
-   消息队列篇
    
    -   《Kafka权威指南》
        
    -   《Apache Kafka源码剖析》
        
-   通讯框架篇
    
    -   《Netty实战》
        
    -   《Netty实践学习案例》
        
-   Docker&Kubernetes篇
    
    -   《第一本Docker书》
        
    -   《深入剖析Kubernetes 52讲》
        

### Part1-2『 物联网内功和基础知识 』

-   基础篇
    
    -   《女朋友问: 你知道蓝牙耳机的原理吗？》
    -   《直呼: 太细了!拿捏🤏Zigbee协议》
-   物联网概念篇
    
    -   《通信相关的术语名词》
    -   《数字孪生&设备影子》
-   设备配网篇
    
    -   《WIFI设备-EZ配网》
    -   《WIFI设备-AP3.0配网》
-   CoAP协议
    
    -   《第一章 - 简介》
    -   《第二章 - 受限应用协议CoAP》
    -   《第三章 - 消息格式》
    -   《第四章 - 消息传递》
    -   《第五章 - 请求/响应的语义》
    -   《第六章 - CoAP URI》
    -   《第七章 - 发现》
    -   《第八章 - 多播CoAP》
    -   《第九章 - 安全CoAP》
    -   《第十章 - CoAP和HTTP的跨协议代理》
    -   《第十章 - 发现》
    -   《第十二章 - 互联网地址分配注意事项（IANA Considerations）》
-   BACnet协议(楼宇自动化与控制网络)篇
    
    -   《认识BACnet-第1部分-什么是BACnet?》
    -   《认识BACnet-第2部分-设备模型》
    -   《认识BACnet-第3部分-网络类型》
    -   《认识BACnet-第4部分-服务》
    -   《认识BACnet-第5部分-互操作领域》
    -   《认识BACnet-第6部分-BIBBS》

Part2.『 MQTT学习指南三重境 』
---------------------

### Part2-1『 一重境之求索：MQTT客户端工具和依赖包 』

-   《MQTT客户端桌面工具:school\_satchel:》
    
    -   《MQTT.js: JavaScript 编写，用于 node.js 和浏览器》
    -   《MQTT X: 跨平台 MQTT桌面客户端》
    -   《MQTT CLI: 有用的MQTT CLI命令行界面》
    -   《MQTT fx: 基于JavaFx的MQTT客户端》
-   《MQTT客户端库:hammer:》
    
    -   《hivemq-mqtt-client: 高性能 Java 客户端库》
    -   《paho.mqtt.java: Eclipse Java 客户端库》
    -   《Paho.mqtt.golang: Eclipse Go 客户端库》
    -   《MQTT.js: JavaScript 编写，用于 node.js 和浏览器》
    -   《paho.mqtt.python: Eclipse Python 客户端库》
    -   《paho.mqtt.c: Eclipse C 客户端库》

### Part2-2『 二重境之实干：自研MQTT Broker，直通百万并发客户端 』

-   待补充

### Part2-3『 三重境之感悟：MQTT v3.1/v3.1.1中文协议文档 』

-   《第一章 - 介绍》
    
-   《第二章 MQTT控制报文格式 MQTT Control Packet format》
    
-   《第三章 - MQTT控制报文》
    
    -   《3.1 CONNECT - 连接服务端》
    -   《3.2 CONNACK – 确认连接请求》
    -   《3.3 PUBLISH – 发布消息》
    -   《3.4 PUBACK – 发布确认》
    -   《3.5 PUBREC – 发布收到（QoS 2，第一步）》
    -   《3.6 PUBREL – 发布释放（QoS 2，第二步）》
    -   《3.7 PUBCOMP – 发布完成（QoS 2，第三步）》
    -   《3.8 SUBSCRIBE - 订阅主题》
    -   《3.9 SUBACK - 订阅确认》
    -   《3.10 UNSUBSCRIBE – 取消订阅》
    -   《3.11 UNSUBACK – 取消订阅确认》
    -   《3.12 PINGREQ – 心跳请求》
    -   《3.13 PINGRESP – 心跳响应》
    -   《3.14 DISCONNECT –断开连接》
-   第四章 – 操作行为
    
-   第五章 – 安全
    
-   第六章 – 使用WebSocket
    
-   第七章 – 一致性目标
    
-   附录B - 强制性规范声明
    

### Part2-4『 三重境之感悟: MQTT v5.0中文协议文档』

-   《第一章 - 介绍》
    
-   《第二章 MQTT控制报文格式 MQTT Control Packet format》
    
-   《第三章 - MQTT控制报文》
    
    -   《3.1 CONNECT - 连接服务端》
    -   《3.2 CONNACK – 确认连接请求》
    -   《3.3 PUBLISH – 发布消息》
    -   《3.4 PUBACK – 发布确认》
    -   《3.5 PUBREC – 发布收到（QoS 2，第一步）》
    -   《3.6 PUBREL – 发布释放（QoS 2，第二步）》
    -   《3.7 PUBCOMP – 发布完成（QoS 2，第三步）》
    -   《3.8 SUBSCRIBE - 订阅主题》
    -   《3.9 SUBACK - 订阅确认》
    -   《3.10 UNSUBSCRIBE – 取消订阅》
    -   《3.11 UNSUBACK – 取消订阅确认》
    -   《3.12 PINGREQ – 心跳请求》
    -   《3.13 PINGRESP – 心跳响应》
    -   《3.14 DISCONNECT – 断开连接》
    -   《3.15 AUTH – 认证交换》
-   第四章 – 操作行为
    
-   第五章 – 安全
    
-   第六章 – 使用WebSocket
    
-   第七章 – 一致性目标
    
-   附录B - 强制性规范声明
    
-   附录C - MQTT v5.0新特性总结 (非规范)
    

Part3.『 从零搭建高性能IoT平台 』
----------------------

-   预习篇
    
    -   《新基建和5G风口下的物联网平台》
        
    -   《理解SaaS多租户应用的架构和设计》
        
-   设备接入篇
    
    -   《白话MQTT基础知识和入门》
        
    -   《实现百万并发MQTT服务端》
        
    -   《初识CoAP并抓住它的"心"》
        
    -   《100行代码快速搭建功能完备的CoAP服务》
        
    -   《重新认识HTTP协议并管理设备》
        
    -   《实践案例: 车载终端设备的数据解析》
        
-   边缘计算篇
    
    -   《工业领域下的Modbus网关设备》
        
    -   《工业领域下的OPC-UA网关设备》
        
-   设备、接口认证和安全篇
    
    -   Spring Security能量
        
        -   《什么是JWT(JSON Web Token)?》
            
        -   《Spring Boot Security + JWT》
            
        -   《Spring Boot Security + JWT + MySQL》
            
    -   下一代安全实践OAuth2
        
        -   《OAuth2.0 最简单的指南》
-   实时显示篇
    
    -   《WebSocket技术魔法》
-   数据交换和序列化篇
    
    -   《设备的语言-物模型》
        
    -   《平台无关并具有扩展性的gRPC下的ProtoBuf》
        
-   存储和查询篇
    
    -   《PostgreSQL碰撞IoT》
        
    -   《MongoDB在IoT中的应用》
        
-   流处理和消息队列篇
    
    -   《简单实现一个消息队列》
        
    -   《广受好评的Kafka》
        
    -   《从未缺席的RabbitMQ》
        
-   规则引擎篇
    
    -   《规则引擎在IoT的重要性》
        
    -   《Easy-Rules规则引擎在IoT的使用》
        
    -   《带你走进ThingsBoard规则引擎的实现原理》
        
    -   《阿里云物联网平台规则引擎的面纱》
        
-   Docker和k8s篇
    
    -   《Docker在IoT技术领域的应用》
        
    -   《DevOps的领头羊-Kubernetes》
        

Part4.『 Thingsboard源码解析 』
-------------------------

-   准备篇
    -   《物联网时代-Thingsboard源码分析-调试环境搭建》
    -   《物联网时代-Thingsboard源码分析-项目结构说明》
-   设备连接协议篇
    -   《MQTT设备连接协议-上》
    -   《MQTT设备连接协议-下》
    -   《CoAP设备连接协议》
    -   《HTTP设备连接协议》
-   存储和查询篇
    -   《数据模型之用户相关表结构设计》
    -   《数据模型之设备相关表结构设计》
    -   《数据模型之规则引擎相关表结构设计》
    -   《领略Spring Data JPA在Thingsboard的使用》
-   网关篇
    -   《网关之Modbus》
    -   《网关之OPC-UA》
-   实时显示篇
    -   《实时显示之WebSocket》
-   数据交换和序列化篇
    -   《数据交换和序列化篇之JSON》
    -   《数据交换和序列化篇之ProtoBuf》
-   设备、接口认证和安全篇
    -   《Spring Security在接口的使用》
    -   《紧跟安全前沿OAuth2》
-   流处理和消息队列篇
    -   《流处理和消息队列篇之Kafka》
    -   《流处理和消息队列篇之RabbitMQ》
-   规则引擎篇
    -   《Rule Engine解放你的双手》
-   Docker和kubernetes篇
    -   《Docker和IoT的碰撞》
    -   《让人惊叹的Kubernetes》
-   设计模式篇
    -   《一文看尽命令模式》
