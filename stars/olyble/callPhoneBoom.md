---
project: callPhoneBoom
stars: 917
description: 最新可用！！！夺命百连呼、电话轰炸、电话攻击(电话轰炸、可代替短信轰炸)、留言攻击工具
url: https://github.com/olyble/callPhoneBoom
---

callPhoneBoom
=============

思路：通过爬取使用「莆田系医院」这一营销组件的企业, 我们可以得到数以万计真实企业的网址。 并通过程序模拟浏览，可以将攻击信息给到这些企业。最终达到「电话攻击」的目的。

声明
--

本项目仅供学习交流使用，勿作商业或非法用途。

所有用户个人行为与本项目无关。

爬取接口
----

感谢xdq2005adam提供的爬取脚本catchad

得益于此脚本，你可以本地运行爬取更多地址放入api.txt中，来增加威力

使用教程
----

1.  下载
    
     $ git clone https://github.com/olyble/callPhoneBoom.git
    
2.  安装 Selenium
    
    $ pip3 install selenium
    
    安装 Selenium 之后，**需要安装对应浏览器的 Driver** ，参见 Selenium 文档 1.3 节。
    
    > Seleium 具体的介绍及使用方法可参见 Selenium 文档。
    
3.  配置
    

在main.py中填入需要轰炸的手机号

使用DrissionPage已合并到main2.只用使用set.py设置环境就可以使用

测试阶段建议大家吧api.txt 里面的网站先只保留几个做个测试再跑，要不然一次性弹出来。 问题一：手机号在哪里 改啊？ 没找到配置文件config.py 跑起来只会打开和关闭网站，并没有输入 电话号码欸。 所以 希望博主大大能够补充一下 运行步骤呢 就差最后一步输入 电话号码卡住了呜呜。 selenium 和浏览器组件弄了好久 感谢博主！！！！ 图片一 图片二

1.  运行程序
    
    $ python3 main.py
    
2.  Enjoy!
    
    运行截图：
    

目录说明
----

TODO
----

1.  使用 PyQt5 实现用户界面。
2.  定时任务。
3.  使用 「HTTP 请求」替代「模拟浏览」。
4.  跳过验证码
5.  封装docker

许可
--

MIT
