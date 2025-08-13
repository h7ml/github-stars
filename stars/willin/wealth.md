---
project: wealth
stars: 11
description: 一个开源的账本响应式网站系统
url: https://github.com/willin/wealth
---

Wealth
======

> Demo Site: https://wealth.willin.wang

教程说明
----

-   视频教程：https://www.ixigua.com/7232851070488314426
-   文章教程：https://blog.csdn.net/jslygwx/article/details/130657624
-   协助部署及定制化开发： https://afdian.net/item/881e40def1fe11ed889f52540025c377

赞助 Sponsor
----------

如果您对本项目感兴趣，可以通过以下方式支持我：

-   关注我的 Github 账号：@willin
-   参与 爱发电 计划
-   支付宝或微信扫码打赏

Donation ways:

-   Github: https://github.com/sponsors/willin
-   Paypal: https://paypal.me/willinwang
-   Alipay or Wechat Pay: QRCode

许可证 License
-----------

Apache-2.0

* * *

开发 Development
--------------

# init db
npx wrangler d1 migrations apply wealth --local

# optional import data
npx wrangler d1 execute wealth --file /PATH/data.sql --local
