---
project: code-push-server
stars: 1870
description: CodePush service is hot update services which adapter react-native-code-push and cordova-plugin-code-push - 热更新
url: https://github.com/lisong/code-push-server
---

CodePush Server source
======================

CodePush Server is a CodePush progam server! microsoft CodePush cloud is slow in China, we can use this to build our's. I use qiniu to store the files, because it's simple and quick! Or you can use \[local/s3/oss/tencentcloud\] storage, just modify config.js file, it's simple configure.

Support Storage mode
--------------------

-   local _storage bundle file in local machine_
-   qiniu _storage bundle file in qiniu_
-   s3 _storage bundle file in aws_
-   oss _storage bundle file in aliyun_
-   tencentcloud _storage bundle file in tencentcloud_

正确使用code-push热更新
----------------

-   苹果App允许使用热更新Apple's developer agreement, 为了不影响用户体验，规定必须使用静默更新。 Google Play不能使用静默更新，必须弹框告知用户App有更新。中国的android市场必须采用静默更新（如果弹框提示，App会被“请上传最新版本的二进制应用包”原因驳回）。
-   react-native 不同平台bundle包不一样，在使用code-push-server的时候必须创建不同的应用来区分(eg. CodePushDemo-ios 和 CodePushDemo-android)
-   react-native-code-push只更新资源文件,不会更新java和Objective C，所以npm升级依赖包版本的时候，如果依赖包使用的本地化实现, 这时候必须更改应用版本号(ios修改Info.plist中的CFBundleShortVersionString, android修改build.gradle中的versionName), 然后重新编译app发布到应用商店。
-   推荐使用code-push release-react 命令发布应用，该命令合并了打包和发布命令(eg. code-push release-react CodePushDemo-ios ios -d Production)
-   每次向App Store提交新的版本时，也应该基于该提交版本同时向code-push-server发布一个初始版本。(因为后面每次向code-push-server发布版本时，code-puse-server都会和初始版本比较，生成补丁版本)

### shell login

$ code-push login http://api.code-push.com #登录

### web

访问：http://www.code-push.com

### client eg.

ReactNative CodePushDemo

Cordova CodePushDemo

HOW TO INSTALL code-push-server
-------------------------------

-   docker (recommend)
-   manual operation

DEFAULT ACCOUNT AND PASSWORD
----------------------------

-   account: `admin`
-   password: `123456`

HOW TO USE
----------

-   normal
-   react-native-code-push
-   code-push

ISSUES
------

code-push-server normal solution

An unknown error occurred

modify password

UPDATE TIME LINE
================

-   targetBinaryVersion support
    -   `*`
    -   `1.2.3`
    -   `1.2`/`1.2.*`
    -   `1.2.3 - 1.2.7`
    -   `>=1.2.3 <1.2.7`
    -   `~1.2.3`
    -   `^1.2.3`

Advance Feature
---------------

> use google diff-match-patch calculate text file diff patch

-   support iOS and Android
-   use `"react-native-code-push": "git+https://git@github.com/lisong/react-native-code-push.git"` instead `"react-native-code-push": "x.x.x"` in `package.json`
-   change `apps`.`is_use_diff_text` to `1` in mysql codepush database

License
-------

MIT License read
