---
project: wechat_kit
stars: 761
description: Flutter 版微信登录/分享/支付 SDK
url: https://github.com/RxReader/wechat_kit
---

wechat\_kit
===========

Flutter 版微信登录/分享/支付 SDK。

若需使用 API 接口方法，请使用 wechat\_kit\_extension 。

相关工具
----

-   Flutter版微信SDK
-   Flutter版腾讯(QQ)SDK
-   Flutter版新浪微博SDK
-   Flutter版支付宝SDK
-   Flutter版深度链接
-   Flutter版walle渠道打包工具

Dart/Flutter Pub 私服
-------------------

-   simple\_pub\_server

相关文档
----

-   微信开放平台
-   微信登录
-   扫码登录
-   微信支付
-   Universal Links

开始使用
----

### Android

```
# 不需要做任何额外接入工作
# 混淆已打入 Library，随 Library 引用，自动添加到 apk 打包混淆
```

-   获取 Android 签名信息

// android/app/build.gradle
// 1. 执行 flutter run/build ，即可获得签名信息
// 2. shell 执行 pushd android && ./gradlew :app:${variant}SigningConfig && popd (variant: debug/release/profile、flavorDebug/flavorRelease/flavorProfile)，即可获得签名信息
apply from: "${project(":wechat\_kit").projectDir}/key-store.gradle"
// 或
apply from: project(":wechat\_kit").file("key-store.gradle")

\--- KeyStore ---
Alias name: dev
Creation date: Fri May 24 17:26:21 CST 2019
Owner: CN=lin
Issuer: CN=lin
Serial number: 77dcb7d8
Valid from: Fri May 24 17:26:21 CST 2019 until: Sun Apr 30 17:26:21 CST 2119
Certificate fingerprints:
MD5: 28:42:41:30:A4:41:6D:51:9E:00:94:66:51:D5:3A:46
SHA1: C9:A9:3A:28:6D:1A:8A:0A:F1:5A:DB:76:45:97:6F:C6:30:8A:FA:B9
SHA256: EA:3A:9B:EE:3C:8B:6C:96:31:5F:B9:09:52:58:52:05:75:E2:2A:6D:5A:C2:C0:7F:07:4F:EA:90:31:DB:58:D8
Certificate digest:
MD5: 28424130a4416d519e00946651d53a46
SHA1: c9a93a286d1a8a0af15adb7645976fc6308afab9
SHA256: ea3a9bee3c8b6c96315fb9095258520575e22a6d5ac2c07f074fea9031db58d8
+ Certificate Third-part:
+ Wechat/Weibo/Alipay MD5 HEX: 28424130a4416d519e00946651d53a46
+ Firebase SHA1 HEX: C9:A9:3A:28:6D:1A:8A:0A:F1:5A:DB:76:45:97:6F:C6:30:8A:FA:B9
+ Facebook SHA1 BASE64: yak6KG0aigrxWtt2RZdvxjCK+rk=
\--- KeyStore ---

### iOS

> 暂不支持 SceneDelegate，详见文档 微信-iOS接入指南

```
# 不需要做任何额外接入工作
# 配置已集成到脚本里
```

-   Universal Links

apple-app-site-association - 通过 https://${your applinks domain}/.well-known/apple-app-site-association 链接可访问

示例:

https://${your applinks domain}/universal\_link/${example\_app}/wechat/

{
  "applinks": {
    "apps": \[\],
    "details": \[
      {
        "appID": "${your team id}.${your app bundle id}",
        "paths": \[
          "/universal\_link/${example\_app}/wechat/\*"
        \]
      }
    \]
  }
}

> ⚠️ 很多 SDK 都会用到 universal\_link，可为不同 SDK 分配不同的 path 以作区分

### OpenHarmony / HarmonyOS

> 当前 OpenHarmony 的微信 SDK 仅支持部分 API, 使用过程中请自行查阅文档

为了检查是否安装了微信，请在项目的 module.json5 文件中添加以下 scheme

{
  "module": {
    "querySchemes": \[
      "weixin"
    \],
  }
}

### Flutter

-   配置

dependencies:
  wechat\_kit: ^${latestTag}
#  wechat\_kit:
#    git:
#      url: https://github.com/RxReader/wechat\_kit.git

wechat\_kit:
#  ios: no\_pay # 默认 pay
  app\_id: ${your wechat app id}
  universal\_link: https://${your applinks domain}/universal\_link/${example\_app}/wechat/

若需要不包含支付的 iOS SDK

wechat\_kit:
+  ios: no\_pay # 默认 pay

-   安装（仅iOS）

# step.1 安装必要依赖
sudo gem install plist
# step.2 切换工作目录，插件里为 example/ios/，普通项目为 ios/
cd example/ios/
# step.3 执行脚本
pod install

示例
--

示例

Star History
------------
