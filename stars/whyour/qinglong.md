---
project: qinglong
stars: 18403
description: 支持 Python3、JavaScript、Shell、Typescript 的定时任务管理平台（Timed task management platform supporting Python3, JavaScript, Shell, Typescript）
url: https://github.com/whyour/qinglong
---

青龙
==

简体中文 | English

支持 Python3、JavaScript、Shell、Typescript 的定时任务管理平台

Timed task management platform supporting Python3, JavaScript, Shell, Typescript

Demo / Issues / Telegram Channel / Buy Me a Coffee

演示 / 反馈 / Telegram 频道 / 打赏开发者

功能
--

-   支持多种脚本语言（python3、javaScript、shell、typescript）
-   支持在线管理脚本、环境变量、配置文件
-   支持在线查看任务日志
-   支持秒级任务设置
-   支持系统级通知
-   支持暗黑模式
-   支持手机端操作

版本
--

### docker

`latest` 镜像是基于 `alpine` 构建，`debian` 镜像是基于 `debian-slim` 构建。如果需要使用 `alpine` 不支持的依赖，建议使用 `debian` 镜像

docker pull whyour/qinglong:latest
docker pull whyour/qinglong:debian

### npm

npm 版本支持 `debian/ubuntu/alpine` 系统，需要自行安装 `node/npm/python3/pip3/pnpm`

npm i @whyour/qinglong

部署
--

查看文档

内置 API
------

查看文档

内置命令
----

查看文档

开发
--

git clone https://github.com/whyour/qinglong.git
cd qinglong
cp .env.example .env
# 推荐使用 pnpm https://pnpm.io/zh/installation
npm install -g pnpm@8.3.1
pnpm install
pnpm start

打开你的浏览器，访问 http://127.0.0.1:5700

链接
--

-   nevinee
-   crontab-ui
-   Ant Design
-   Ant Design Pro
-   Umijs
-   darkreader
-   admin-server

名称来源
----

青龙，又名苍龙，在中国传统文化中是四象之一、天之四灵之一，根据五行学说，它是代表东方的灵兽，为青色的龙，五行属木，代表的季节是春季，八卦主震。苍龙与应龙一样，都是身具羽翼。《张果星宗》称“又有辅翼，方为真龙”。

《后汉书·律历志下》记载：日周于天，一寒一暑，四时备成，万物毕改，摄提迁次，青龙移辰，谓之岁。

在中国二十八宿中，青龙是东方七宿（角、亢、氐、房、心、尾、箕）的总称。 在早期星宿信仰中，祂是最尊贵的天神。 但被道教信仰吸纳入其神系后，神格大跌，道教将其称为“孟章”，在不同的道经中有“帝君”、“圣将”、“神将”和“捕鬼将”等称呼，与白虎监兵神君一起，是道教的护卫天神。
