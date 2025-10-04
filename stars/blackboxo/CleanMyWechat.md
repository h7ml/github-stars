---
project: CleanMyWechat
stars: 4983
description: 自动删除 PC 端微信缓存数据，包括从所有聊天中自动下载的大量文件、视频、图片等数据内容，解放你的空间。
url: https://github.com/blackboxo/CleanMyWechat
---

Clean My PC Wechat
==================

自动删除 PC 端微信自动下载的大量文件、视频、图片等数据内容，解放一年几十 G 的空间占用。

该工具不会删除文字的聊天记录，请放心使用。请给个 **Star** 吧，非常感谢！

**现已经支持 Windows 系统中的所有微信版本。**

国内地址 - 点击下载

Github Release - 点击下载

**碰到无法清理的，请记得勾选第一个选项，勾选后才会清理该账号下的内容。**

特性
--

1.  自动识别微信账号，支持用户选择自定义路径；
2.  同时管理多个账号，保留配置参数，打开即用；
3.  自由设置想要删除的文件类型，包括图片类缓存、文件、图片、视频；
4.  自由设置需要删除的文件的距离时间，默认 365 天；
5.  删除后的文件放置在回收站中，检查后自行清空，防止删错需要的文件；

运行截图
----

微信现状
----

下载两年时间，微信一个软件就占用多达 33.5 G 存储空间。其中大部分都是与自己无关的各大群聊中的文件、视频、图片等内容，且很久以前的文件仍旧存在电脑中。

待改进
---

欢迎 PR！

-   Mac 版本的开发
-   增加企业微信的支持
-   Windows XP/7 系统的支持

其他需求详见 Issue

打包 EXE 方式
---------

pip install -r requirements.txt
pyinstaller -F -i images/icon.ico -w main.py
cp -r images dist/
./dist/main.exe

致谢
--

@mylittlefox：图标及 Banner 设计

@Gears：提供微信 for Windows 版本的文件目录树及测试支持

@SongJee：版本 1.1 的主要开发者，增加进度条，支持多个微信版本，自动识别路径

@LenmoisLemon：版本 2.0 的主要开发者，全新 UI 设计，增加多用户配置

@Louhwz：版本 2.0 的主要开发者，增加多用户支持、多线程删除、自定义路径等

开发者
---

微博：@BlackBoXo

邮箱：bwu18@fudan.edu.cn

Blog：https://www.blackboxo.top/

Star History
------------
