---
project: pushNotifications
stars: 3
description: 基于github action的消息推送 | Message push based on github action
url: https://github.com/dext7r/pushNotifications
---

pushNotifications
=================

pushNotifications
=================

pushNotifications 是基于push-all-in-one 封装的github action版本。也可使用 @dext7r/push-notifications,在node环境下使用

action
------

### 新建一个workflow文件

name: Push Notifications

on:
push:
  branches:
    - main

jobs:
push-notifications:
  runs-on: ubuntu-latest

  steps:
  - name: Checkout code
    uses: actions/checkout@v2

  - name: Run Push Notifications action
    uses: dext7r/pushNotifications
    with:
      TYPE: ${{ secrets.TYPE }}
      TITLE: ${{ secrets.TITLE }}
      DESP: ${{ secrets.DESP }}
      SCTKEY: ${{ secrets.SCTKEY }}
      ACCESS\_TOKEN: ${{ secrets.ACCESS\_TOKEN }}
      SECRET: ${{ secrets.SECRET }}
      WX\_ROBOT\_KEY: ${{ secrets.WX\_ROBOT\_KEY }}
      MSG\_TYPE: ${{ secrets.MSG\_TYPE }}
      EMAIL\_TYPE: ${{ secrets.EMAIL\_TYPE }}
      EMAIL\_TO\_ADDRESS: ${{ secrets.EMAIL\_TO\_ADDRESS }}
      EMAIL\_AUTH\_USER: ${{ secrets.EMAIL\_AUTH\_USER }}
      EMAIL\_AUTH\_PASS: ${{ secrets.EMAIL\_AUTH\_PASS }}
      EMAIL\_HOST: ${{ secrets.EMAIL\_HOST }}
      EMAIL\_PORT: ${{ secrets.EMAIL\_PORT }}
      WX\_APP\_CORPID: ${{ secrets.WX\_APP\_CORPID }}
      WX\_APP\_AGENTID: ${{ secrets.WX\_APP\_AGENTID }}
      WX\_APP\_SECRET: ${{ secrets.WX\_APP\_SECRET }}
      WX\_APP\_USERID: ${{ secrets.WX\_APP\_USERID }}
      PUSH\_PLUS\_TOKEN: ${{ secrets.PUSH\_PLUS\_TOKEN }}
      TEMPLATE\_TYPE: ${{ secrets.TEMPLATE\_TYPE }}
      CHANNEL\_TYPE: ${{ secrets.CHANNEL\_TYPE }}
      I\_GOT\_KEY: ${{ secrets.I\_GOT\_KEY }}
      QMSG\_KEY: ${{ secrets.QMSG\_KEY }}
      QMSG\_QQ: ${{ secrets.QMSG\_QQ }}
      QMSG\_PUSH\_TYPE: ${{ secrets.QMSG\_PUSH\_TYPE }}
      XI\_ZHI\_KEY: ${{ secrets.XI\_ZHI\_KEY }}
      PUSH\_DEER\_PUSH\_KEY: ${{ secrets.PUSH\_DEER\_PUSH\_KEY }}
      PUSH\_DEER\_ENDPOINT: ${{ secrets.PUSH\_DEER\_ENDPOINT }}
      PUSH\_DEER\_PUSH\_TYPE: ${{ secrets.PUSH\_DEER\_PUSH\_TYPE }}
      DISCORD\_WEBHOOK: ${{ secrets.DISCORD\_WEBHOOK }}
      DISCORD\_USERNAME: ${{ secrets.DISCORD\_USERNAME }}
      TELEGRAM\_BOT\_TOKEN: ${{ secrets.TELEGRAM\_BOT\_TOKEN }}
      TELEGRAM\_CHAT\_ID: ${{ secrets.TELEGRAM\_CHAT\_ID }}
      TELEGRAM\_SEND\_SILENTLY: ${{ secrets.TELEGRAM\_SEND\_SILENTLY }}
      TELEGRAM\_PROTECT\_CONTENT: ${{ secrets.TELEGRAM\_PROTECT\_CONTENT }}
      TELEGRAM\_MESSAGE\_THREAD\_ID: ${{ secrets.TELEGRAM\_MESSAGE\_THREAD\_ID }}
      ONE\_BOT\_BASE\_URL: ${{ secrets.ONE\_BOT\_BASE\_URL }}
      ONE\_BOT\_ACCESS\_TOKEN: ${{ secrets.ONE\_BOT\_ACCESS\_TOKEN }}
      ONE\_BOT\_MSG\_TYPE: ${{ secrets.ONE\_BOT\_MSG\_TYPE }}
      ONE\_BOT\_RECIEVER\_ID: ${{ secrets.ONE\_BOT\_RECIEVER\_ID }}

参数
--

变量名

描述

可选值

默认值

必填

TYPE

通知类型

ServerChanTurbo, Dingtalk, CustomEmail, WechatRobot, WechatApp, PushPlus, IGot, Qmsg, XiZhi, PushDeer, Discord, Telegram, OneBot

无

是

TITLE

通知标题

任意字符串

无

是

DESP

通知内容

任意字符串

无

是

SCTKEY

Server酱的SCKEY

字符串

无

否

ACCESS\_TOKEN

推送服务的ACCESS\_TOKEN

字符串

无

否

SECRET

推送服务的SECRET

字符串

无

否

WX\_ROBOT\_KEY

微信机器人的KEY

字符串

无

否

MSG\_TYPE

微信机器人的消息类型

所有消息类型

无

否

EMAIL\_TYPE

邮件通知类型

所有邮件类型

无

否

EMAIL\_TO\_ADDRESS

邮件接收地址

有效邮箱地址

无

否

EMAIL\_AUTH\_USER

邮件发送者邮箱

有效邮箱地址

无

否

EMAIL\_AUTH\_PASS

邮件发送者授权密码

字符串

无

否

EMAIL\_HOST

邮件发送者邮箱服务器

有效域名

无

否

EMAIL\_PORT

邮件发送者邮箱端口

数字

无

否

WX\_APP\_CORPID

企业微信的CORPID

字符串

无

否

WX\_APP\_AGENTID

企业微信的AGENTID

数字

无

否

WX\_APP\_SECRET

企业微信的SECRET

字符串

无

否

WX\_APP\_USERID

企业微信的USERID

字符串

无

否

PUSH\_PLUS\_TOKEN

PUSH\_PLUS的TOKEN

字符串

无

否

TEMPLATE\_TYPE

钉钉机器人的模板类型

所有模板类型

无

否

CHANNEL\_TYPE

钉钉机器人的通道类型

所有通道类型

无

否

I\_GOT\_KEY

iGot的KEY

字符串

无

否

QMSG\_KEY

Qmsg的KEY

字符串

无

否

QMSG\_QQ

Qmsg的QQ

字符串

无

否

QMSG\_PUSH\_TYPE

Qmsg的推送类型

所有推送类型

无

否

XI\_ZHI\_KEY

喜知的KEY

字符串

无

否

PUSH\_DEER\_PUSH\_KEY

PushDeer的PUSH\_KEY

字符串

无

否

PUSH\_DEER\_ENDPOINT

PushDeer的ENDPOINT

字符串

无

否

PUSH\_DEER\_PUSH\_TYPE

PushDeer的推送类型

所有推送类型

无

否

DISCORD\_WEBHOOK

Discord的WEBHOOK

字符串

无

否

DISCORD\_USERNAME

Discord的用户名

字符串

无

否

TELEGRAM\_BOT\_TOKEN

Telegram的BOT\_TOKEN

字符串

无

否

TELEGRAM\_CHAT\_ID

Telegram的CHAT\_ID

数字

无

否

TELEGRAM\_SEND\_SILENTLY

Telegram的是否静默发送

true或false

false

否

TELEGRAM\_PROTECT\_CONTENT

Telegram的是否保护内容

true或false

false

否

TELEGRAM\_MESSAGE\_THREAD\_ID

Telegram的消息线程ID

字符串

无

否

ONE\_BOT\_BASE\_URL

OneBot的BASE\_URL

字符串

无

否

ONE\_BOT\_ACCESS\_TOKEN

OneBot的ACCESS\_TOKEN

字符串

无

否

ONE\_BOT\_MSG\_TYPE

OneBot的消息类型

所有消息类型

无

否

ONE\_BOT\_RECIEVER\_ID

OneBot的接收者ID

数字

无

否
