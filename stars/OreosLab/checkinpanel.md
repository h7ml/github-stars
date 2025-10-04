---
project: checkinpanel
stars: 1427
description: 一个主要运行在 𝐞𝐥𝐞𝐜𝐕𝟐𝐏 或 𝐪𝐢𝐧𝐠𝐥𝐨𝐧𝐠 等定时面板，同时支持系统运行环境的签到项目（环境：𝑷𝒚𝒕𝒉𝒐𝒏 3.8+ / 𝑵𝒐𝒅𝒆.𝒋𝒔 10+ / 𝑩𝒂𝒔𝒉 4+ / 𝑶𝒑𝒆𝒏𝑱𝑫𝑲8 / 𝑷𝒆𝒓𝒍5）
url: https://github.com/OreosLab/checkinpanel
---

定时面板上的签到盒
=========

简介
--

> 一个主要运行在 𝐞𝐥𝐞𝐜𝐕𝟐𝐏 或 𝐪𝐢𝐧𝐠𝐥𝐨𝐧𝐠 等定时面板，同时支持系统运行环境的签到项目
> 
> 环境：𝑷𝒚𝒕𝒉𝒐𝒏 3.8+ / 𝑵𝒐𝒅𝒆.𝒋𝒔 10+ / 𝑩𝒂𝒔𝒉 4+ / 𝑶𝒑𝒆𝒏𝑱𝑫𝑲8 / 𝑷𝒆𝒓𝒍5

注意
--

不回答任何关于依赖安装失败的问题，包括且不限于 pip 无法找到 tomli 依赖等，请仔细阅读项目 README

特别声明
----

-   本仓库发布的脚本及其中涉及的任何解锁和解密分析脚本，仅用于测试和学习研究，禁止用于商业用途，不能保证其合法性、准确性、完整性和有效性，请根据情况自行判断。
    
-   本项目内所有资源文件，禁止任何公众号、自媒体进行任何形式的转载、发布。
    
-   本人对任何脚本问题概不负责，包括但不限于由任何脚本错误导致的任何损失或损害。
    
-   间接使用脚本的任何用户，包括但不限于建立 VPS 或在某些行为违反国家/地区法律或相关法规的情况下进行传播，本人对于由此引起的任何隐私泄漏或其他后果概不负责。
    
-   请勿将本仓库的任何内容用于商业或非法目的，否则后果自负。
    
-   如果任何单位或个人认为该项目的脚本可能涉嫌侵犯其权利，则应及时通知并提供身份证明、所有权证明，我们将在收到认证文件后删除相关脚本。
    
-   任何以任何方式查看此项目的人或直接或间接使用该项目的任何脚本的使用者都应仔细阅读此声明。本人保留随时更改或补充此免责声明的权利。一旦使用并复制了任何相关脚本或 checkinpanel 项目的规则，则视为您已接受此免责声明。
    

**您必须在下载后的 24 小时内从计算机或手机中完全删除以上内容**

> _**您使用或者复制了本仓库且本人制作的任何脚本，则视为 `已接受` 此声明，请仔细阅读**_

𝐞𝐥𝐞𝐜𝐕𝟐𝐏 使用方法
-------------------

### 1\. 添加任务

TASK -> 添加订阅任务 -> 修改名称、更新方式、任务 -> 获取内容 -> 全部添加

名称：签到项目

同名任务更新方式： `替换`

任务：

```
https://raw.githubusercontent.com/OreosLab/checkinpanel/master/dailycheckin.json
```

### 2\. 抓包配置

下载 check.sample.toml，根据注释说明进行抓包并配置

### 3\. 上传配置

将 `check.sample.toml` 重命名为 `check.toml` 后放入 `script/Lists` 文件夹

-   OVERVIEW -> EFSS 文件管理界面 -> 是否开启 EFSS 功能：开启 -> 目录：`./script/Lists` -> 选择文件：`check.toml` -> 开始上传
    
-   elecV2P 3.4.6 已支持在线编辑，右键文件即可
    

### 4\. 配置通知

#### 4.1 JSMANAGE -> store/cookie 常量储存管理填写通知环境变量

变量 / key

描述

支持语言

参考 / value

HITOKOTO

一言

PY

true 为开启，false 为关闭，默认关闭

BARK\_PUSH

bark 设备码

JS PY

BARK 推送使用，填写 URL 即可，例如： `https://api.day.app/DxHcxxxxxRxxxxxxcm`

BARK\_ARCHIVE

\* bark 存档

PY

是否存档

BARK\_GROUP

\* bark 消息分组

JS PY

消息分组

BARK\_SOUND

\* bark 声音

JS PY

例如： `choo` ，具体值 bark-推送铃声-查看所有铃声

CONSOLE

控制台输出

PY

true 为开启，false 为关闭，默认关闭

DD\_BOT\_SECRET

钉钉机器人

JS PY SH

钉钉推送官方文档密钥，机器人安全设置页面，加签一栏下面显示的 `SEC` 开头的字符串，注：填写了 `DD_BOT_TOKEN` 和 `DD_BOT_SECRET` ，钉钉机器人安全设置只需勾选 `加签` 即可，其他选项不要勾选

DD\_BOT\_TOKEN

钉钉机器人

JS PY SH

钉钉推送官方文档，只需 `https://oapi.dingtalk.com/robot/send?access_token=XXX` 等于符号后面的 `XXX`

FSKEY

飞书

PY

飞书官方文档，只需 `https://open.feishu.cn/open-apis/bot/v2/hook/xxxxxx` 的 `xxxxxx` 部分

GOBOT\_URL

go-cqhttp

JS PY

例如：推送到个人QQ： `http://127.0.0.1/send_private_msg` 群： `http://127.0.0.1/send_group_msg`

GOBOT\_QQ

go-cqhttp 的推送群或者用户

JS PY

`GOBOT_URL` 设置 `/send_private_msg` 时填入 `user_id=个人QQ` ； `/send_group_msg` 时填入 `group_id=QQ群`

GOBOT\_TOKEN

\* go-cqhttp 的 access\_token

JS PY

go-cqhttp 文件设置的访问密钥

IGOT\_PUSH\_TOKEN

iGot 聚合推送

JS PY

参考文档，支持多方式推送

PUSH\_KEY

server 酱

JS PY SH

server 酱推送官方文档，JS 和 PY 推送兼容新旧版本

PUSH\_TURBO\_KEY

server 酱 Turbo 版

SH

server 酱 TURBO 推送官方文档，仅支持 SH

PUSH\_PLUS\_TOKEN

pushplus 用户令牌

JS PY SH

可直接加到请求地址后，如： `http://www.pushplus.plus/send/{token}` 官方文档

PUSH\_PLUS\_USER

\* pushplus 群组编码

JS PY

一对多推送下面 -> 您的群组（如无则新建） -> 群组编码 1. 需订阅者扫描二维码 2. 如果您是创建群组所属人，也需点击“查看二维码”扫描绑定，否则不能接受群组消息推送

QMSG\_KEY

qmsg 酱

JS PY SH

qmsg 酱推送官方文档，填写 `KEY` 代码即可

QMSG\_TYPE

\* qmsg 酱推送类型

JS PY

qmsg 酱推送官方文档，如果需要推送到群填写 `group` ，其他的都推送到 QQ

QYWX\_AM

企业微信应用

JS PY

参考文档，依次填入 corpid, corpsecret, touser(注：多个成员ID使用 | 隔开), agentid, media\_id(选填，不填默认文本消息类型)

QYWX\_KEY

企业微信机器人

JS PY

官方文档，只需 `https://qyapi.weixin.qq.com/cgi-bin/webhook/send?key=693a91f6-7xxx-4bc4-97a0-0ec2sifa5aaa` key= 后面部分

SRE\_TOKEN

push.jwks123.com

SH

官网关注公众号后再次点击获取令牌

TG\_BOT\_TOKEN

tg 机器人

JS PY SH

申请 @BotFather 的 Token，如 `10xxx4:AAFcqxxxxgER5uw`

TG\_USER\_ID

tg 机器人

JS PY SH

给 @getidsbot 发送 /start 获取到的纯数字 ID，如 `1434078534`

TG\_API\_HOST

\* tg 代理 api

JS PY

Telegram api 自建的反向代理地址 例子：反向代理地址 `http://aaa.bbb.ccc` 则填写 aaa.bbb.ccc 简略搭建教程

TG\_PROXY\_AUTH

\* tg 代理认证参数

JS

username:password，如 `Oreo:123456` ，`TG_PROXY_HOST` 中填了可不填

TG\_PROXY\_HOST

\* tg 机器人代理 IP 地址

JS PY

代理类型为 http，比如您代理是 `http://127.0.0.1:1080` ，则填写 `127.0.0.1` ，有密码例子: `username:password@127.0.0.1`

TG\_PROXY\_PORT

\* tg 机器人代理端口

JS PY

代理端口号，代理类型为 http，比如您代理是 `http://127.0.0.1:1080` ，则填写 `1080`

_\* 表示选填_

#### 4.2 另一种通知配置方式（当和 4.1 中值重复时，以 4.1 值为准）

下载项目中的推送配置文件到**配置文件夹**，按照上述说明修改配置文件中的值并改名为 `notify.toml` ，你可以**自由地删除**该文件中某些不需要的值（注意语法）。

使用了配置文件后，你可以将配置文件放在持久化位置，不受脚本更新、重置容器的影响。

如果想自定义配置文件的位置和文件名，请设置通知环境变量 `NOTIFY_CONFIG_PATH` ， 例如 `/usr/local/app/script/notify.toml` 。建议保持 `toml` 的后缀，防止编辑器的误解。

关于 toml 的语法参考：

-   toml-lang/toml
-   中文知乎介绍
-   TOML 教程中文版

#### 4.3 通知说明

本通知调用了项目中的 𝒏𝒐𝒕𝒊𝒇𝒚\_𝒎𝒕𝒓.𝒑𝒚 。如果你想在**你自己的项目中**使用这个通知脚本，将它拷贝并调用对应的通知函数即可。

在非容器环境中，通知环境变量使用 系统的环境变量 或者 **你通过 `NOTIFY_CONFIG_PATH` 环境变量指定的配置文件** 进行配置。

特别的，如果你想要创建一个基于 python 的 elecV2P 或者 qinglong 项目，并有意愿使用 `toml` 文件，那么强烈建议你拷贝此文件，如此可以大幅度降低用户脚本的配置难度和升级难度。

如果只希望使用 `json` 模块和单纯获取环境变量方法，那么可以拷贝 𝒏𝒐𝒕𝒊𝒇𝒚\_𝒎𝒕𝒓\_𝒆𝒏𝒗.𝒑𝒚。

### 5\. 检查依赖

-   运行 `签到依赖` 任务后的日志
    
-   如果任务列表安装不成功，参考 #12
    

𝐪𝐢𝐧𝐠𝐥𝐨𝐧𝐠 使用方法
---------------------

### 1\. ssh 进入容器

docker exec -it qinglong bash

修改 `qinglong` 为你的青龙容器名称

### 2\. 拉取仓库

**解决 Shell 脚本无法拉取问题**：将以下代码在 `config.sh` 相应位置替换

#\# ql repo命令拉取脚本时需要拉取的文件后缀，直接写文件后缀名即可
RepoFileExtensions="js pl py sh ts"

可添加定时任务，名称、时间自定

ql repo https://github.com/OreosLab/checkinpanel.git "api\_|ck\_|ins\_" "^checkin" "^notify|^utils|cpm" "master"

### 3\. 安装依赖

-   **运行 `签到依赖` 任务**
    
    -   截图
-   依赖持久化配置
    
    -   `签到依赖` 任务保持定时运行即可

### 4\. 拷贝文件

cp /ql/repo/OreosLab\_checkinpanel\_master/check.sample.toml /ql/config/check.toml

_通知配置文件（可选）_

cp /ql/repo/OreosLab\_checkinpanel\_master/notify.sample.toml /ql/config/notify.toml

### 5\. 配置通知

参见上文中的配置通知

特别的：

-   **如果你已经配置了 `config.sh`， 那么你可以不需要做任何改变。**
-   如果使用环境变量，请在 qinglong 面板中配置。
-   如果使用配置文件，请修改 `/ql/config/notify.toml` 文件。
-   当然你也可以在 qinglong 面板中配置 `NOTIFY_CONFIG_PATH` 环境变量为配置文件指定其他位置。

### 6\. 抓包配置

不出意外的话可以在青龙面板的配置文件下找到 `check.toml` 文件

根据注释说明进行抓包并配置

补充说明
----

### 1\. **添加了葫芦侠的签到配置**

参数说明： `HLX.username` ：用户名 `HLX.password` ：密码的 MD5 32 位小写加密生成

### 2\. **添加了网易云游戏的签到配置**

官网

参数说明： `GAME163.authorization`

登录后抓取签到请求（一般请求的请求头也有这个字段）

### 3\. **Shell 脚本配置**

-   目前 Shell 脚本只有一个 SSPanel 签到，如需使用请参考 `env.sample` 配置 `.env` 后放入 `script/Lists` 或 `/ql/config` 文件夹
-   支持自定义配置文件路径
    -   环境变量 / store KEY 名称：`ENV_PATH`
    -   参考值 / VALUE：`/usr/local/app/script/.env`

### 4\. **添加了欢太商城的签到配置**

-   欢太商城 HttpCanary 抓包教程
-   部分域名屏蔽境外 IP 访问，所以本项目不适于在 非中国 IP 代理网络下 / Github Actions / 境外 VPS 上运行！
-   从未在欢太商城做过任务，请先手动进入任务中心完成一下任务再使用，否则可能无法获取到任务列表数据导致出错！@YYplus

### 5\. **添加了时光相册的签到配置**

### 6\. **EUserv 在未开启登录验证时有效**

-   True Captcha
    
-   如图注册账号后获取 `userid` 和 `apikey`
    

其他说明
----

1.  请自行修改执行时间。
    
2.  elecV2P 运行 `手动更新` 任务可强制同步本仓库。
    
3.  大部分脚本移植于 Sitoi，Sitoi 于 2021 年 9 月 3 日 dailycheckin-0.1.7 版本适配了青龙，使用教程与本仓库教程不相同，切勿使用本仓库 checkinpanel 的同时去问大佬。
    
4.  2021 年 9 月 13 日起不再更新 `.json` 后缀的配置文件。
    
5.  2021 年 9 月 23 日起重新初始化项目，原本文件移到这里，上述仓库不再进行更新，期望稳定的用户可以切换到上述仓库。
    
6.  2021 年 11 月 17 日起由 `JSON5` 配置转为更为友好的 `TOML` 配置。
    

计划说明
----

-   𝑷𝒚𝒕𝒉𝒐𝒏 | **api** | LeetCode 每日一题 | 每日一句 | 天气预报 | 每日新闻 | 爱企查e卡监控 | Hax 监控 | RSS 订阅
-   𝑷𝒚𝒕𝒉𝒐𝒏 | **多账号** | AcFun | 百度搜索资源平台 | Bilibili | 天翼云盘 | CSDN | 多看阅读 | 恩山论坛 | Fa米家 | 网易云游戏 | 葫芦侠 | 爱奇艺 | 全民K歌 | MEIZU 社区 | 芒果 TV | 小米运动 | 网易云音乐 | 一加手机社区官方论坛 | 哔咔漫画 | 吾爱破解 | 什么值得买 | 百度贴吧 | V2EX | 腾讯视频 | 微博 | 联通沃邮箱 | 哔咔网单 | 王者营地 | 有道云笔记 | 智友邦 | 机场签到 | 欢太商城 | NGA | 掘金 | GLaDOS | HiFiNi | 时光相册 | 联通营业厅 | 无忧行 | FreeNom | EUserv | Site | SF 轻小说 | 在线工具 | CCAVA | 企鹅电竞 | 联想乐云 | WPS | HOSTLOC | Epic | Hax 续期提醒
-   𝑺𝒉𝒆𝒍𝒍 | **多账号** | SSPanel 签到 | 国内加速
-   𝑱𝒂𝒗𝒂𝑺𝒄𝒓𝒊𝒑𝒕 | **多账号** | 什么值得买任务版 | 爱企查 | 网易蜗牛读书 | 联想商城
-   𝑱𝒂𝒗𝒂 | Bilibili 助手
-   𝑷𝒆𝒓𝒍 | JSON5toTOML 工具

### 项目完成情况

-   多账号补全
-   配置文件由严格的 `.json` 向支持注释的 `.json5` 过渡，再向更友好的 `.toml` 过渡
-   更多环境适配
-   配置文件支持自定义路径
-   通知多线程
-   通知输出优化
-   通知方式增加，如飞书
-   Shell 消息推送、环境检查单列
-   项目重新初始化，更新日志规范化
-   依赖安装重构
-   cron 随机
-   任务多合一执行
-   CK 检测判断是否跳出

### 测试情况

状态

名称

✅

国内加速 | Hax 监控 | LeetCode 每日一题 | 每日一句 | 天气预报 | 每日新闻 | RSS 订阅 | 机场签到 | 爱企查 | 百度搜索资源平台 | Bilibili | Bilibili 助手 | CCAVA | 天翼云盘 | CSDN | 网易蜗牛读书 | 多看阅读 | 恩山论坛 | EUserv | 时光相册 | Fa米家 | FreeNom | GLaDOS | 网易云游戏 | HiFiNi | 葫芦侠 | HOSTLOC | JSON5toTOML 工具 | 掘金 | 全民K歌 | 联想商城 | MEIZU 社区 | 小米运动 | NGA | 一加手机社区官方论坛 | 吾爱破解 | Site | 什么值得买 | 什么值得买任务版 | SSPanel 签到 | 百度贴吧 | 在线工具 | V2EX | 微博 | WPS | 王者营地 | 有道云笔记

❔

哔咔漫画 | 哔咔网单 | 智友邦

❌

致谢
--

@𝐰𝐞𝐧𝐦𝐨𝐮𝐱 --------------- 𝗰𝗵𝗲𝗰𝗸𝗯𝗼𝘅

@𝐒𝐢𝐭𝐨𝐢 -------------------- 𝗱𝗮𝗶𝗹𝘆𝗰𝗵𝗲𝗰𝗸𝗶𝗻

@𝐲𝐮𝐱𝐢𝐚𝐧𝟏𝟓𝟖 ----------- 𝗾𝗹-𝗰𝗵𝗲𝗰𝗸𝗯𝗼𝘅

@𝐢𝐬𝐞𝐜𝐫𝐞𝐭 --------------- 𝗦𝗦𝗣𝗮𝗻𝗲𝗹 𝗦𝗵𝗲𝗹𝗹

@𝐡𝐰𝐤𝐱𝐤 ----------------------- 𝗛𝗲𝘆𝗧𝗮𝗽

@𝐥𝐮𝐦𝐢𝐧𝐨𝐥𝐞𝐨𝐧 ---- 𝗲𝗽𝗶𝗰𝗴𝗮𝗺𝗲𝘀-𝗰𝗹𝗮𝗶𝗺𝗲𝗿

@𝑶𝒕𝒉𝒆𝒓𝒔 -------------- 𝔰𝔠𝔯𝔦𝔭𝔱 𝔠𝔬𝔪𝔪𝔢𝔫𝔱𝔰

历史 Star 数
---------
