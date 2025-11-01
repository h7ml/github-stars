---
project: finclip-ios-demo
stars: 333
description: 小程序容器 FinClip 苹果运行环境，让小程序在苹果应用中无缝运行  / iOS DEMO for FinClip
url: https://github.com/finogeeks/finclip-ios-demo
---

**FinClip iOS DEMO**  

本项目提供在 iOS 环境中运行小程序的 DEMO 样例

👉 https://www.finclip.com/ 👈

官方网站 | 示例小程序 | 开发文档 | 部署指南 | SDK 集成指南 | API 列表 | 组件列表 | 隐私承诺

* * *

🤔 FinClip 是什么?
---------------

有没有**想过**，开发好的微信小程序能放在自己的 APP 里直接运行，只需要开发一次小程序，就能在不同的应用中打开它，是不是很不可思议？

有没有**试过**，在自己的 APP 中引入一个 SDK ，应用中不仅可以打开小程序，还能自定义小程序接口，修改小程序样式，是不是觉得更不可思议？

这就是 FinClip ，就是有这么多不可思议！

⚙️ 操作步骤
-------

### 第一步 修改 Podfile 文件，增加 FinApplet 依赖

```
source 'https://github.com/CocoaPods/Specs.git'
pod 'FinApplet'
```

### 第二步 完成SDK初始化

在工程的 `AppDelegate` 中的以下方法中，调用 SDK 的初始化方法。

\- (BOOL)application:(UIApplication \*)application didFinishLaunchingWithOptions:(NSDictionary \*)launchOptions {
	
	// 需要添加至App中的代码--start
    NSMutableArray \*storeArrayM = \[NSMutableArray array\];
    FATStoreConfig \*storeConfig = \[\[FATStoreConfig alloc\] init\];
    storeConfig.sdkKey = @"您的sdkKey信息";
    storeConfig.sdkSecret = @"您的sdkSecret信息";
    storeConfig.apiServer = @"服务器域名";
    storeConfig.apmServer = @"apm统计事件的域名";
    \[storeArrayM addObject:storeConfig\];
    
    FATConfig \*config = \[FATConfig configWithStoreConfigs:storeArrayM\];
    \[\[FATClient sharedClient\] initWithConfig:config error:nil\];
    // 需要添加至App中的代码--end
    
    return YES;
}

### 第三步打开小程序

NSString \*appId = @"小程序id";
// 打开小程序
\[\[FATClient sharedClient\] startRemoteApplet:appId startParams:nil InParentViewController:self completion:^(BOOL result, NSError \*error) {
    NSLog(@"result:%d\---error:%@", result, error);
}\];

-   **SDK KEY** 和 **SDK SECRET** 可以从 FinClip 获取，点 这里 注册账号；
-   进入平台后，在「应用管理」页面添加你自己的包名后，点击「复制」即可获得 key\\secret\\apisever 字段；
-   **apiServer** 和 **apiPrefix** 是固定字段，请直接参考本 DEMO ；
-   **小程序 ID** 是管理后台上架的小程序 APP ID，需要在「小程序管理」中创建并在「应用管理」中关联；

> 小程序 ID 与 微信小程序ID 不一样哦！（这里是特指 FinClip 平台的 ID ）

📋 集成文档
-------

点击这里 查看 iOS 快速集成文档

🔗 常用链接
-------

以下内容是您在 FinClip 进行开发与体验时，常见的问题与指引信息

-   FinClip 官网
-   示例小程序
-   文档中心
-   SDK 部署指南
-   小程序代码结构
-   iOS 集成指引
-   Android 集成指引
-   Flutter 集成指引

☎️ 联系我们
-------

微信扫描下面二维码，关注官方公众号 **「凡泰极客」**，获取更多精彩内容。  

微信扫描下面二维码，加入官方微信交流群，获取更多精彩内容。  

Stargazers
----------

Forkers
-------
