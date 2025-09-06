---
project: WeRoBot
stars: 4660
description: WeRoBot 是一个微信公众号开发框架
url: https://github.com/offu/WeRoBot
---

WeRoBot
=======

WeRoBot 是一个微信公众号开发框架，采用MIT协议发布。

文档在这里： https://werobot.readthedocs.org/zh\_CN/latest/

安装
--

推荐使用 pip 进行安装

pip install werobot

Hello World
-----------

一个非常简单的 Hello World 微信公众号，会对收到的所有文本消息回复 Hello World

import werobot

robot = werobot.WeRoBot(token='tokenhere')

@robot.text
def hello\_world():
    return 'Hello World!'

robot.run()

Credits
-------

### Contributors

Thank you to all the people who have already contributed.
