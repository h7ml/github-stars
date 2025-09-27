---
project: freenom
stars: 3337
description: Freenom 域名自动续期。Freenom domain name renews automatically.
url: https://github.com/luolongfei/freenom
---

### Freenom：freenom域名自动续期

Documentation: English version | 中文版

📢 公告

📃 引言

🍭 效果

🎁 事前准备

📪 配置送信功能（支持 邮件送信 / Telegram Bot / 企业微信 / Server 酱 / Bark 等送信方式）

⛵ 通过 Docker Compose 方式部署

🐳 通过 Docker 方式部署（推荐，最简单的部署方式之一）

🧊 通过 Heroku 部署

🚈 通过 Railway 部署

📦 通过 Koyeb 部署（没有自己服务器的用户可使用此方案）

🧪 通过 Mogenius 部署（已不可行）

☁ 通过 各种云函数 部署 （目前各平台已开启收费模式，已放弃支持）

🚧 直接拉取源码部署

📋 赞助名单 Donation List

❤ 赞助 Donation

🪓 信仰

🌚 作者

💖 所有贡献者

📝 TODO List

🍅 本项目的其它语言实现

🎉 鸣谢

🥝 开源协议

### 📢 公告

-   热心网友创建了`Freenom 续期事务局`群组，可供交流、测试、反馈， **加入可直接访问 https://t.me/freenom\_auto\_renew ，或者扫码加入：**

### 📃 引言

众所周知，Freenom是地球上唯一一个提供免费顶级域名的商家，不过需要每年续期，每次续期最多一年。由于我申请了一堆域名，而且不是同一时段申请的， 所以每次续期都觉得折腾，于是就写了这个自动续期的脚本。

### 🍭 效果

无论是续期成败或者程序执行出错，都会收到脚本发出的通知。如果是续期成败相关的通知，通知会包括未续期域名的到期天数等内容。_此处展示的是通知邮件的内容。_

### 🎁 事前准备

-   VPS：随便一台服务器都行，系统推荐`Debian`。`PHP`版本需在`php7.3`及以上，如果有`Docker`环境则可无视这个限制。如果你没有服务器，可参考本文档部署到各种免费环境中。
-   送信邮箱（可选）：为了方便理解又称机器人邮箱，用于发送通知邮件。目前针对`Gmail`、`QQ邮箱`、`163邮箱`以及`Outlook邮箱`，程序会自动判断送信邮箱类型并使用合适的配置。 如果你使用的是其它第三方邮箱或者自建邮件服务，那么请参考 .env.example 文件中与邮件配置相关的注释进行配置。
-   收信邮箱（可选）：用于接收机器人发出的通知邮件。
-   上面的`送信邮箱`和`收信邮箱`是可选项，因为目前程序已支持`邮件送信` / `Telegram Bot` / `企业微信` / `Server 酱` / `Bark`等送信方式，仅当你使用`邮件送信`的时候，`送信邮箱`和`收信邮箱` 才是必须的，其它送信方式所需请参考下面的 配置送信功能 。
-   耐心。

### 📪 配置送信功能

此处会分别介绍`邮件送信` / `Telegram Bot` / `企业微信` / `Server 酱` / `Bark`送信方式的配置方法，以及其所需的资料，你可以任选一种送信方式进行配置，直接跳到对应的文档查看即可。 如果你是 IOS 用户，推荐使用 `Bark` 送信方式，其它平台的用户根据自己喜好选择可接受的送信方式即可。不太推荐使用`Server 酱`送信，`Server 酱`每日送信条数的限制，以及需要开会员才能直接看到送信内容，否则需要跳到 `Server 酱` 网站才能查看内容，都是不推荐的原因。同样的配置完全可以直接使用`企业微信`送信方式，`企业微信`送信直接在普通微信客户端就能看到信件内容。

_快速到文档指定位置：_

邮件送信

Telegram Bot

企业微信

Server 酱

Bark 送信

#### 邮件送信

下面分别介绍`Gmail`、`QQ邮箱`以及`163邮箱`的设置，你只用看自己需要的部分。注意，`QQ邮箱`与`163邮箱`均使用`账户加授权码`的方式登录， `谷歌邮箱`使用`账户加密码`或者`账户加授权码`的方式登录，请知悉。另外还想吐槽一下，国产邮箱你得花一毛钱给邮箱提供方发一条短信才能拿到授权码。

_（点击即可展开或收起）_

设置Gmail  

_推荐打开浏览器隐私模式后再登录 gmail 进行设置，防止当你有多个 gmail 账户时无法跳到正确的设置地址。_

1、在`设置>转发和POP/IMAP`中，勾选

-   对所有邮件启用 POP
-   启用 IMAP

然后保存更改。

2、开启两步验证

参考官方文档：开启两步验证

3、配置使用应用专用密码登录邮箱

参考官方文档：使用应用专用密码登录

**由于 Gmail 已不再支持“不安全的登录方式”，故目前只能使用账户加应用专用密码的方式登录。**

* * *

设置QQ邮箱  

在`设置>账户>POP3/IMAP/SMTP/Exchange/CardDAV/CalDAV服务`下，开启`POP3/SMTP服务`

此时坑爹的QQ邮箱会要求你用手机发送一条短信给腾讯，发送完了点一下`我已发送`

然后你就能看到你的邮箱授权码了，使用邮箱账户加授权码即可登录，记下授权码

* * *

设置163邮箱  

在`设置>POP3/SMTP/IMAP`下，开启`POP3/SMTP服务`和`IMAP/SMTP服务`并保存

现在点击侧边栏的`客户端授权密码`，并获取授权码，你看到画面可能和我不一样，因为我已经获取了授权码，所以只有`重置授权码`按钮，这里自己根据网站提示申请获取授权码，网易和腾讯一样恶心，需要你用手机给它发一条短信才能拿到授权码

163 邮箱送信后，接收方如果没收到可以在垃圾邮件里面找一下。

* * *

上面的动作完成后，在`.env`文件中，将`MAIL_USERNAME`和`MAIL_PASSWORD`设置为你的邮箱和密码（或令牌），将`TO`设置为你的收信邮箱，然后将`MAIL_ENABLE`的值设为`1`以启用邮箱送信功能。

上面介绍了三种邮箱的设置方法，如果你不想使用邮件送信，将根目录下的`.env`文件中的`MAIL_ENABLE`的值改为`0`即可关闭邮件推送方式。

_邮件 送信部分完。_

#### Telegram Bot

有关 【Telegram Bot】 的具体配置步骤请参考 此处

#### 企业微信

有关 【企业微信】 的具体配置步骤请参考 此处

#### Server 酱

有关 【Server 酱】 的具体配置步骤请参考 此处

#### Bark 送信

有关 【Bark 送信】 的具体配置步骤请参考 此处

* * *

_与 配置送信功能 相关的篇幅完。下面开始讲本项目的几种使用方式。推荐使用 Docker 方式，无需纠结环境。_

* * *

### ⛵ 通过 Docker Compose 部署

**注意，目前是 beta 版本，只支持在 amd64 架构的机器上安装，arm 或其它架构的用户请稍安勿躁，等后续更新。或者如果你需要一台服务器，可以考虑** 美国便宜 VPS

#### 1、一键安装 docker 和 docker compose

Debian / Ubuntu（推荐）

apt-get update -y;
apt-get install -y wget vim git make;
wget -qO- get.docker.com | bash;
systemctl start docker;
sudo systemctl enable docker.service;
sudo systemctl enable containerd.service;
docker version;
DOCKER\_COMPOSE\_VER=2.24.3;
DOCKER\_CONFIG=/usr/local/lib/docker;
mkdir -p $DOCKER\_CONFIG/cli-plugins;
curl -SL https://github.com/docker/compose/releases/download/v${DOCKER\_COMPOSE\_VER}/docker-compose-linux-x86\_64 -o $DOCKER\_CONFIG/cli-plugins/docker-compose;
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose;
docker compose version;

CentOS

yum update -y;
yum install -y wget vim make;
wget -qO- get.docker.com | bash;
systemctl start docker;
sudo systemctl enable docker.service;
sudo systemctl enable containerd.service;
docker version;
DOCKER\_COMPOSE\_VER=2.24.3;
DOCKER\_CONFIG=/usr/local/lib/docker;
mkdir -p $DOCKER\_CONFIG/cli-plugins;
curl -SL https://github.com/docker/compose/releases/download/v${DOCKER\_COMPOSE\_VER}/docker-compose-linux-x86\_64 -o $DOCKER\_CONFIG/cli-plugins/docker-compose;
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose;
docker compose version;

#### 2、下载本项目

git clone https://github.com/luolongfei/freenom.git && cd freenom

#### 3、配置

##### 3.1、申请 wit.ai 的 token

3.1.1 访问 https://wit.ai

3.1.2 使用 Facebook 账户登录或者使用邮箱注册账户登录，只需要邮箱就可以注册

3.1.3 前往 https://wit.ai/apps 画面，创建一个新的 app

3.1.4 语言选择 English，名字随意，类型选择私有，创建之

3.1.5 前往 Management > Settings (https://wit.ai/apps//settings) 画面

3.1.6 复制 Client Access Token，下面需要写入 .env 文件中，WIT\_AI\_KEY='你复制的 Client Access Token'

##### 3.2、修改 .env 配置文件

将 .env 配置文件中的内容修改为你自己的配置，如果是从旧版升级，也可以直接把旧版 .env 复制到新版项目根目录，脚本会自动更新它。配置含义参考 .env.example 文件中的注解。

cp .env.example .env;
vim .env;

修改完成后，输入 `:wq` 保存并退出。

#### 4、启动

注意：以下命令均需要在 docker-compose.yml 所在目录执行才有效。

make up

没错，就是这么简单。然后可以执行 `make logs` 查看实时日志。

##### 4.1、常用命令

启动或者更新到最新版

make up

停止

make down

查看实时日志

make logs

清理容器占用的空间

make clear

重启容器

make restart

_通过 docker compose 部署部分结束。_

### 🐳 通过 Docker 部署

_如果你有自己的服务器，这是最推荐的部署方式。_

Docker 仓库地址为： https://hub.docker.com/r/luolongfei/freenom ，同样欢迎 star 。 此镜像支持的架构为`linux/amd64`，`linux/arm64`，`linux/ppc64le`，`linux/s390x`，`linux/386`，`linux/arm/v7`，`linux/arm/v6`， 理论上支持`群晖` 、`威联通`、`树莓派`以及各种类型的`VPS`。

#### 1、安装 Docker

##### 1.1 以 root 用户登录，执行一键脚本安装 Docker

升级源并安装软件（下面两行命令二选一，根据你自己的系统）

Debian / Ubuntu

apt-get update && apt-get install -y wget vim make

CentOS

yum update && yum install -y wget vim make

执行此命令等候自动安装 Docker

wget -qO- get.docker.com | bash

说明：请使用 KVM 架构的 VPS，OpenVZ 架构的 VPS 不支持安装 Docker，另外 CentOS 8 不支持用此脚本来安装 Docker。 更多关于 Docker 安装的内容参考 Docker 官方安装指南 。

##### 1.2 针对 Docker 执行以下命令

启动 Docker 服务

systemctl start docker

查看 Docker 运行状态

systemctl status docker

将 Docker 服务加入开机自启动

systemctl enable docker

#### 2、通过 Docker 部署域名续期脚本

##### 2.1 用 Docker 创建并启动容器

命令如下

docker run -d --name freenom --restart always -v $(pwd):/conf -v $(pwd)/logs:/app/logs luolongfei/freenom

或者，如果你想自定义脚本执行时间，则命令如下

docker run -d --name freenom --restart always -v $(pwd):/conf -v $(pwd)/logs:/app/logs -e RUN\_AT="11:24" luolongfei/freenom

上面这条命令只比上上条命令多了个 `-e RUN_AT="11:24"`，其中`11:24`表示在北京时间每天的 11:24 执行续期任务，你可以自定义这个时间。 这里的`RUN_AT`参数同时也支持 CRON 命令里的时间形式，比如， `-e RUN_AT="9 11 * * *"`，表示每天北京时间 11:09 执行续期任务， 如果你不想每天执行任务，只想隔几天执行，只用修改`RUN_AT`的值即可。

**注意：不推荐自定义脚本执行时间。因为你可能跟很多人定义的是同一个时间点，这样可能导致所有人都是同一时间向 Freenom 的服务器发起请求， 使得 Freenom 无法稳定提供服务。而如果你不自定义时间，程序会自动指定北京时间 06 ~ 23 点全时段随机的一个时间点作为执行时间， 每次重启容器都会自动重新指定。**

点我查看上方 Docker 命令的参数解释  

命令

含义

docker run

开始运行一个容器

\-d 参数

容器以后台运行并输出容器 ID

\--name 参数

给容器分配一个识别符，方便将来的启动，停止，删除等操作

\--restart 参数

配置容器启动类型，always 即为 docker 服务重新启动时自动启动本容器

\-v 参数

挂载卷（volume），冒号后面是容器的路径，冒号前面是宿主机的路径（只支持绝对路径），`$(pwd)`表示当前目录，如果是 Windows 系统，则可用`${PWD}`替换此处的`$(pwd)`

\-e 参数

指定容器中的环境变量

luolongfei/freenom

这是从 docker hub 下载回来的镜像完整路径名

至此，你的自动续期容器就跑起来了，执行`ls -a`后你就可以看到在你的当前目录下，有一个`.env`文件和一个`logs`目录，`logs`目录里面存放的是程序日志， 而`.env`则是配置文件，现在直接执行`vim .env` 将`.env`文件里的所有配置项改为你自己的并保存即可。然后重启容器，如果配置正确的话，便很快可以收到相关邮件。

点我查看 .env 文件中部分配置项的含义  

变量名

含义

默认值

是否必须

备注

FREENOM\_USERNAME

Freenom 账户

\-

是

只支持邮箱账户，如果你是使用第三方社交账户登录的用户，请在 Freenom 管理页面绑定邮箱，绑定后即可使用邮箱账户登录

FREENOM\_PASSWORD

Freenom 密码

\-

是

某些特殊字符可能需要转义，详见`.env`文件内注释

MULTIPLE\_ACCOUNTS

多账户支持

\-

否

多个账户和密码的格式必须是“`<账户1>@<密码1>|<账户2>@<密码2>|<账户3>@<密码3>`”，注意不要省略“<>”符号，否则无法正确匹配。如果设置了多账户，上面的`FREENOM_USERNAME`和`FREENOM_PASSWORD`可不设置

MAIL\_USERNAME

机器人邮箱账户

\-

否

支持`Gmail`、`QQ邮箱`、`163邮箱`以及`Outlook邮箱`

MAIL\_PASSWORD

机器人邮箱密码

\-

否

`Gmail`填应用专用密码，`QQ邮箱`或`163邮箱`填授权码

TO

接收通知的邮箱

\-

否

你自己最常用的邮箱，用来接收机器人邮箱发出的域名相关邮件

MAIL\_ENABLE

是否启用邮件推送功能

`0`

否

`1`：启用  
`0`：不启用  
默认不启用，如果设为`1`，启用邮件推送功能，则上面的`MAIL_USERNAME`、`MAIL_PASSWORD`、`TO`变量变为必填项

TELEGRAM\_CHAT\_ID

你的`chat_id`

\-

否

通过发送`/start`给`@userinfobot`可以获取自己的`id`

TELEGRAM\_BOT\_TOKEN

你的`Telegram bot`的`token`

\-

否

TELEGRAM\_BOT\_ENABLE

是否启用`Telegram Bot`推送功能

`0`

否

`1`：启用  
`0`：不启用  
默认不启用，如果设为`1`，则必须设置上面的`TELEGRAM_CHAT_ID`和`TELEGRAM_BOT_TOKEN`变量

NOTICE\_FREQ

通知频率

`1`

否

`0`：仅当有续期操作的时候  
`1`：每次执行

NEZHA\_SERVER

哪吒探针服务端的 IP 或域名

\-

否

NEZHA\_PORT

哪吒探针服务端的端口

\-

否

NEZHA\_KEY

哪吒探针客户端专用 Key

\-

否

NEZHA\_TLS

哪吒客户SSL/TLS加密

\-

否

`1`：启用  
`0`：不启用

**更多配置项含义，请参考 .env.example 文件中的注释。**

> 如何验证你的配置是否正确呢？

修改并保存`.env`文件后，执行`docker restart freenom`重启容器，等待 5 秒钟左右，然后执行`docker logs freenom`查看输出内容， 观察输出内容中有`执行成功` 字样，则表示配置无误。如果你还来不及配置送信邮箱等内容，可先停用邮件功能。

> 如何升级到最新版或者重新部署呢？

在`.env`所在目录，执行`docker rm -f freenom`删除现有容器，然后再执行 `docker rmi -f luolongfei/freenom` 删除旧的镜像，然后再执行上面的 `docker run -d --name freenom --restart always -v $(pwd):/conf -v $(pwd)/logs:/app/logs luolongfei/freenom` 重新部署即可，这样部署后就是最新的代码了。当然，新版对应的`.env`文件可能有变动，不必担心，程序会自动更新`.env`文件内容，并将已有的配置迁移过去。

一句话操作，即在`.env`文件所在目录下执行以下命令，即可完成更新升级：

docker rm -f freenom && docker rmi -f luolongfei/freenom && docker run -d --name freenom --restart always -v $(pwd):/conf -v $(pwd)/logs:/app/logs luolongfei/freenom

##### 2.2 后期容器管理以及 Docker 常用命令

查看容器在线状态及大小

docker ps -as

查看容器的运行输出日志

docker logs freenom

重新启动容器

docker restart freenom

停止容器的运行

docker stop freenom

移除容器

docker rm -f freenom

查看 docker 容器占用 CPU，内存等信息

docker stats --no-stream

查看 Docker 安装版本等信息

docker version

重启 Docker（非容器）

systemctl restart docker

_有关容器部署的内容结束。_

* * *

### 🧊 通过 Heroku 部署

**Heroku 已于 2022-11-28 停止提供免费服务，所以，忘掉本文吧。官方通告：https://blog.heroku.com/next-chapter**

有关 【通过 Heroku 部署】 的具体操作步骤请参考 此处

* * *

### 🚈 通过 Railway 部署

_Railway 已更新服务条款，每月增加了使用时长限制，新的服务条款导致每月最多只能运行 21 天左右， **除非你验证了信用卡，则没有这个限制** 。详细条款内容参考 此处 。_

有关 【通过 Railway 部署】 的具体操作步骤请参考 此处

* * *

### 📦 通过 Koyeb 部署

_推荐没有自己服务器的用户使用此方案部署。此方案完全免费。_

有关 【通过 Koyeb 部署】 的具体操作步骤请参考 此处

**在看完上行文档的具体内容，并且你确定你行后**，便可点击下方按钮，尝试一键部署：

* * *

### 🧪 通过 Mogenius 部署

已下线免费套餐，不再可用。 #208

* * *

### ☁ 通过各种云函数部署

所有云函数使用的是同一个压缩包，已做兼容处理，下载地址： https://github.com/luolongfei/freenom/releases/download/v0.5.1/freenom\_scf.zip 。本文档会在发布新版的时候同步更新此处的压缩包下载地址，所以不必担心，你看到的下载地址指向的包一定是最新版本。

下载后你将得到一个 zip 文件，将 zip 文件放到你能找到的任意目录，后面我们将以 zip 文件的形式上传到各种云函数。

有关 【通过腾讯云函数部署】 的具体操作步骤请参考 此处

有关 【通过阿里云函数部署】 的具体操作步骤请参考 此处

有关 【通过华为云函数部署】 的具体操作步骤请参考 此处

* * *

### 🚧 直接拉取源码部署

有关 【直接拉取源码部署】 的具体操作步骤请参考 此处

* * *

遇到任何问题或 Bug 欢迎提 issue （请按模板格式提`issue`，以便我快速复现你的问题，否则问题会被忽略）， 如果`Freenom` 改变算法导致此项目失效，请提 issue 告知，我会及时修复，本项目长期维护。 欢迎`star`~

### 📋 赞助名单 Donation List

非常感谢「 这些用户 」对本项目的赞助支持！

### ❤ 赞助 Donation

如果你觉得本项目对你有帮助，请考虑赞助本项目，以激励我投入更多的时间进行维护与开发。 If you find this project helpful, please consider supporting the project going forward. Your support is greatly appreciated.

PayPal: https://www.paypal.me/mybsdc

> Every time you spend money, you're casting a vote for the kind of world you want. -- Anna Lappe

题外话：赞助的时候可以留言，留言内容将被展示在 赞助列表画面 。如果赞助图片未能正常显示，请访问： https://images.llfapp.com/pay.png

**你的`star`或者`赞助`是我长期维护此项目的动力所在，由衷感谢每一位支持者，“每一次你花的钱都是在为你想要的世界投票”。 另外，将本项目推荐给更多的人，也是一种支持的方式，用的人越多更新的动力越足。**

### 🪓 信仰

相信未来，保持“理智”。

> 认真是我们参与这个社会的方式，认真是我们改变这个社会的方式。 ——李志

### 🌚 作者

-   主程序以及框架：@luolongfei
-   英文版文档：@肖阿姨

### 💖 所有贡献者

@anjumrafidofficial

### 📝 TODO List

-   支持交互式安装，免去手动修改配置的繁琐操作
-   支持自动升级
-   多个账户的续期结果通知合并为同一条消息

### 🍅 本项目的其它语言实现

-   https://github.com/PencilNavigator/Freenom-Workers （JavaScript）
-   https://github.com/Oreomeow/freenom-py （Python）

_(更多其它语言欢迎提交 PR 更新此列表)_

### 🎉 鸣谢

-   项目依赖 PHPMailer 、 guzzle 等第三方库
-   本项目 Docker 相关文档有参考 秋水逸冰 的文章
-   @anjumrafidofficial 完善英文版邮件内容

### 🥝 开源协议

MIT
