---
project: coupons
stars: 1969
description: 美团饿了吗外卖红包外卖优惠券，先领红包再下单。外卖红包优惠券，cps分成，别人领红包下单，你拿佣金。
url: https://github.com/zwpro/coupons
---

\[新\]微信红包封面领取小程序：https://github.com/zwpro/redCover

### 更新日志 12.26

新增订阅功能

修改 cloudfunctions-aliyun/common/utils/index.js 中的 appid和secret参数，上传代码到云服务器即可

### 更新日志 11-30

新增uniCloud云开发，小程序数据可通过api更改。 （如只需要数据写死在前端，可切换到静态数据分支 no-api）

美团饿了吗CPS红包，别人领红包下单，你拿推广佣金
=========================

### 使用方法

源码为uniapp项目，需下载hbuilder导入项目打包，可编译成h5或小程序(跳转地址为小程序路径)

在线文档

### 常见问题

1.  如何获取美团饿了吗的推广链接

美团联盟：https://union.meituan.com/

饿了么、双十一：https://pub.alimama.com/

​ 2.如何打包成小程序

编译成小程序的话，需要配置coupons里小程序路径

比如跳转饿了么小程序：

```
minapp: {
    appid: 'wxece3a9a4c82f58c9',
    path: 'pages/sharePid/web/index?scene=https://s.click.ele.me/wR9ecuu'
}
```

已上线案例：

如有线上案例或疑问，请提issue
