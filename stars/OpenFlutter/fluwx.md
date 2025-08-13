---
project: fluwx
stars: 3242
description: Flutter版微信SDK.WeChat SDK for flutter.
url: https://github.com/OpenFlutter/fluwx
---

Fluwx
=====

* * *

中文请移步此处

What's Fluwx
------------

`Fluwx` is flutter plugin for WeChatSDK which allows developers to call  
WeChatSDK native APIs.

> Join QQ Group now: 1003811176

Capability
----------

-   Share images, texts, music and so on to WeChat, including session, favorite and timeline.
-   Payment with WeChat.
-   Get auth code before you login in with WeChat.
-   Launch mini program in WeChat.
-   Subscribe Message.
-   Just open WeChat app.
-   Launch app From wechat link.
-   Open Customer Service

Preparation
-----------

Migrate to V4 now

> Breaking changes ：_Fluwx_ won't request permission(WRITE\_EXTERNAL\_STORAGE) since 4.5.0. That means you will need to handle permission when sharing images, if FileProvider is not supported.

`Fluwx` is good but not God. You'd better read official documents before integrating `Fluwx`. Then you'll understand how to generate Android signature, what's universal link for iOS, how to add URL schema for iOS and so on.

Install
-------

Add the following dependencies in your `pubspec.yaml` file:

`Fluwx` with pay:

dependencies:
  fluwx: ^${latestVersion}

Note

`fluwx` without pay:  
Developers who need to exclude payment for iOS can set `no_pay: true` in pubspec.yaml.  
See the example: example/pubspec.yaml  

Warning

Never forget to replace ^${latestVersion} with an actual version!

Configurations
--------------

`Fluwx` enables multiple configurations in the section `fluwx` of `pubspec.yaml` from v4, you can reference pubspec.yaml for more details.

> For iOS, some configurations, such as url\_scheme，universal\_link, LSApplicationQueriesSchemes, can be configured by `fluwx`, what you need to do is to fill configurations in `pubspec.yaml`

-   app\_id. Recommend. It'll be used to generate scheme on iOS。This is not used to init WeChat SDK so you still need to call `fluwx.registerApi` manually.
    
-   debug\_logging. Optional. Enable logs by setting it `true`.
    
-   flutter\_activity. Optional. This is usually used by cold boot from WeChat on Android. `Fluwx` will try to launch launcher activity if not set.
    
-   universal\_link. Recommend for iOS. It'll be used to generate universal link on your projects.
    
-   scene\_delegate. Optional. Use `AppDelegate` or `SceneDelegate`. See official documents for more details.
    
-   For iOS If you are failing `cannot load such file -- plist` on iOS, please do the following steps:
    

# step.1 install missing dependencies
sudo gem install plist
# step.2 enter iOS folder(example/ios/,ios/)
cd example/ios/
# step.3 execute
pod install

-   On OpenHarmony, to check if WeChat is installed, add the following to the module.json5 in your project

{
  "module": {
    "querySchemes": \[
      "weixin"
    \],
  }
}

Register WxAPI
--------------

Register your app via `fluwx` if necessary.

Fluwx fluwx \= Fluwx();
fluwx.registerApi(appId: "wxd930ea5d5a228f5f",universalLink: "https://your.univerallink.com/link/");

The param `universalLink` only works with iOS. You can read this document to learn how to create universalLink. You can also learn how to add URL schema, how to add `LSApplicationQueriesSchemes` in your iOS project. This is essential.

For Android, you shall know to how generate signature for your app in this page. And you have to understand the difference between debug signature and release signature. Once the signature is incorrect, then you'll get `errCode = -1`.

It' better to register your API as early as possible.

Capability Document
-------------------

-   Basic knowledge
-   Share
-   Payment
-   Auth
-   Launch app from h5
-   Open Customer Service

For more capabilities, you can read the public functions of `fluwx`.

QA
--

These questions maybe help

Donate
------

Buy the writer a cup of coffee。

Subscribe Us On WeChat
----------------------

Star history
------------

LICENSE
-------

```
Copyright 2023 OpenFlutter Project

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.
```
