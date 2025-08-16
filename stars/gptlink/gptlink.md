---
project: gptlink
stars: 2656
description: 10分钟搭建可免费商用的AI对话环境，搭建简单，包含用户，订单，任务，付费等功能
url: https://github.com/gptlink/gptlink
---

GPTLink
=======

只需简单几步，即可快速搭建可用的 AI对话 站点。

体验地址 · 演示图片 · 反馈 · 微信加群

商务合作 · 关注公众号 · 打赏开发者

功能概览
----

-   支持 Docker 部署
-   开箱即用的控制台
-   完美适配移动端
-   自定义付费套餐
-   一键导出对话
-   任务拉新获客

开始使用
----

1.  项目基于 PHP (Hyperf) + Vue 开发，推荐使用 Docker 进行部署；
2.  准备好一个 API Key，推荐使用 GPTLINK Key；
    -   GPTLINK Key ，注册完成之后进入个人中心申请开发者后获取 API Key，过程非常简单，无需审核，接口无需代理；
    -   OpenAi 官方 Key；
3.  微信相关应用（非必须）
    -   微信网站应用
    -   微信公众号
    -   微信支付

项目仓库
----

-   前端源码： https://github.com/gptlink/gptlink-web
-   部署脚本： https://github.com/gptlink/gptlink-deploy
-   管理端源码： 新版开发中，敬请期待

项目配置
----

项目提供有限的权限控制功能，项目配置文件位于 `gptserver/.env`，如诺不存在此文件，将 `gptserver/.env.example` 更名为 `.env` 作为配置项进行使用，详细的配置说明 点此查看

部署
--

项目支持多种部署方式，部署文档参考：点此查看

-   PHP 环境部署
-   Docker 部署
-   Docker Compose 部署
-   ...

### 访问

**项目访问**

-   对话端 访问 `http://域名或IP` 进入对话页面
-   管理端 访问 `http://域名或IP/admin` 进入管理页

管理员账号密码为配置项设置的 `ADMIN_USERNAME` 与 `ADMIN_USERNAME`，如不传入，默认账号密码为 `admin` `admin888`

**API 文档地址：**

-   用户端 API 文档访问 `/api/docs/default`
-   管理端 API 文档访问 `/api/docs/admin`

版本计划
----

-   前端开源
-   管理端开源
-   账号密码登录
-   线下收款配置
-   兑换码
-   AI 生图
-   分销
-   统计视图

参与贡献
----

我们深知这不是一个完美的产品，但是它只是一个开始，欢迎加入我们一起完善！:heart: 请参阅 贡献指南

特别鸣谢
----

-   @overtrue
-   @Lainy0307

疑难解答
----

常见问题汇总：点击查看

微信交流群
-----

开源协议
----

Apache License Version 2.0 see http://www.apache.org/licenses/LICENSE-2.0.html
