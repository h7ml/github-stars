---
project: gopay
stars: 5215
description: 微信、支付宝、通联支付、拉卡拉、PayPal、Apple 的Go版本SDK。【极简、易用的聚合支付SDK】
url: https://github.com/go-pay/gopay
---

GoPay
=====

### 微信、支付宝、QQ、通联支付、拉卡拉、PayPal、扫呗、Apple支付的 Golang 版本SDK

* * *

一、安装
====

go get github.com/go-pay/gopay

#### 查看 GoPay 版本

版本更新记录

import (
    "github.com/go-pay/gopay"
    "github.com/go-pay/xlog"
)

func main() {
    xlog.Info("GoPay Version: ", gopay.Version)
}

* * *

  

二、文档目录
======

> ### 点击查看不同支付方式的使用文档。方便的话，请留下您认可的小星星，十分感谢！

-   #### 支付宝支付（V3版）
    
-   #### 支付宝支付
    
-   #### 微信支付（V3版）
    
    -   微信商家转账产品升级，目前已支持新版商家转账接口
-   #### 微信支付（V2版，不推荐）
    
-   #### QQ支付
    
-   #### 通联支付
    
-   #### 拉卡拉支付
    
-   #### Paypal支付
    
-   #### Apple支付校验
    
-   #### 扫呗支付
    

* * *

  

三、其他说明
======

-   如需自定义Log输出，New Client 后，调用 `client.SetLogger()` 方法设置自定义Logger，自定义Logger实现 `xlog.XLogger` interface即可。
    
-   各支付方式接入，请仔细查看 `xxx_test.go` 使用方式
    
    -   `gopay/wechat/v3/client_test.go`
    -   `gopay/alipay/v3/client_test.go`
    -   `gopay/alipay/client_test.go`
    -   `gopay/qq/client_test.go`
    -   `gopay/allinpay/client_test.go`
    -   `gopay/lakala/client_test.go`
    -   `gopay/paypal/client_test.go`
    -   `gopay/apple/verify_test.go`
    -   或 examples
-   接入gopay示例项目(可参考接入使用方式)：gopay-platform
    
-   有问题请加微信群 或 关注抖音账号，加入首页粉丝群拉微信群。在此，非常感谢提出宝贵意见和反馈问题的同志们！
    
-   开发过程中，请尽量使用正式环境，1分钱测试法！
    
-   有偿承接技术咨询、开发，如需要加微信联系。
    

  

* * *

赞赏多少是您的心意，感谢支持！
---------------

微信赞赏码：      支付宝赞助码：

* * *

问题沟通（非必要不用加微信）
--------------

> 微信: **85411418**（加个人微信备注 gopay 并关注抖音账号，谢谢）。

* * *

  

鸣谢
--

> GoLand A Go IDE with extended support for JavaScript, TypeScript, and Databases。

特别感谢 JetBrains 为开源项目提供免费的 GoLand 等 IDE 的授权  
  

> Copyright © 2025 JetBrains s.r.o. JetBrains and the JetBrains logo are trademarks of JetBrains s.r.o.
