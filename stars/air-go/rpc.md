---
project: rpc
stars: 134
description: Go 微服务框架，Router 基于 Gin 和 gRPC Gateway，同时支持 gRPC 和 HTTP，封装各种常用组件，开箱即用，专注业务。
url: https://github.com/air-go/rpc
---

rpc
===

Go 微服务框架，同时支持 gRPC 和 HTTP，封装各种常用组件，开箱即用，专注业务

  

建议反馈
----

如果您对本框架有任何意见或建议，欢迎随时通过以下方式反馈和完善：

1.  提 issues 反馈
2.  通过下方的联系方式直接联系我
3.  提 PR 共同维护  
      
    

联系我
---

QQ群：909211071  
个人QQ：444216978  
微信：AirGo\_\_\_  
  

功能列表
----

✅  多格式配置读取  
✅  服务优雅关闭  
✅  进程结束资源自动回收  
✅  日志抽象和标准字段统一（请求、DB、Redis、RPC）  
✅  DB（ORM）  
✅  Redis  
✅  RabbitMQ  
✅  Kafka  
✅  Apollo配置中心  
✅  cron定时任务  
✅  单机和分布式限流  
✅  分布式缓存（解决缓存穿透、击穿、雪崩）  
✅  分布式链路追踪  
✅  分布式锁  
✅  服务注册  
✅  服务发现  
✅  负载均衡  
✅  通用链接池  
✅  HTTP-RPC 超时传递  
✅  端口多路复用  
✅  gRPC  
✅  Prometheus 监控  
  

后续规划
----

日志收集  
告警  
限流  
熔断  
  

工程目录
----

```
- rpc
  - bootstrap //应用启动
  - client
    - grpc //grpc客户端
    - http //http客户端
  - library //基础组件库，不建议修改
    - app //app
    - apollo //阿波罗
    - cache //分布式缓存
    - config //配置加载
    - cron //任务调度
    - etcd //etcd
    - grpc //grpc封装
    - opentracing //opentracing分布式链路追踪
    - limiter //限流
    - lock //分布式锁
    - logger //日志
    - orm //db orm
    - otel //otel分布式链路追踪
    - pool //通用链接池
    - prometheus //prometheus监控
    - queue //消息队列
    - redis //redis
    - registry //注册中心
    - reliablequeue //可靠消息队列
    - selector //负载均衡器
    - servicer //下游服务
  - mock
    - third //三方单测mock
    - tools //常见mock工具封装
  - server
    - grpc //grpc服务端
    - http //http服务端  
  - third //三方依赖引入
  .gitignore
  Dockerfile
  LICENSE
  Makefile
  README.md
  go.mod
  go.sum
```

  

Example
-------

HTTP  
gRPC  
完整业务架构  

* * *
