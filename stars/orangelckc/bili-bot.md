---
project: bili-bot
stars: 57
description: 哔哩哔哩-直播间管家机器人，主播的最佳助手！
url: https://github.com/orangelckc/bili-bot
---

哔哩哔哩-直播间管家机器人
=============

基于Tauri+vue3+ts+Sqlite 的哔哩哔哩直播间管家机器人

请跳转至Realease页面下载最新版本，进行体验

功能
--

### 机器人功能

-   直播间弹幕监控
-   直播间礼物监控
-   直播间进入监控
-   直播间关注监控
-   直播间点赞监控
-   主播开播/下播监控
-   直播间定时发送欢迎词
-   直播间签到打卡
-   可连接GPT3机器人，使用@进行弹幕提问

### 直播间功能

-   直播预览
-   直播录制
-   直播间弹幕/表情包发送

项目截图
----

项目依赖
----

-   Rust环境: 请自行根据官网步骤安装rust环境
-   Node.js: 用于运行项目
-   ffmpeg: 用于直播录制功能，可选

项目运行
----

1.  安装依赖

npm install

1.  运行项目

npm run tauri dev

-   如果运行报错未找到`dist`文件夹，请先手动对前端进行打包

npm run build

1.  打包项目

npm run tauri build

-   如果需要打包后进行调试，请添加`--debug`参数

npm run tauri build --debug

1.  生成app图标，请自行替换/src-tauri/assets文件夹下的icon图标，任何图片格式均可以

npm run build:icon

其他
--

直播间相关数据存储在本地sqlite数据库中，可自行使用数据库管理工具进行查看

macOS下数据库路径为`/Users/用户名/Library/Application Support/bili-bot/sql.db`

windows下数据库路径为`C:\Users\用户名\AppData\Roaming\bili-bot\sql.db`

#### Contributors
