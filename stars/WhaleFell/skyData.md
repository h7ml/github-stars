---
project: skyData
stars: 14
description: 光遇官网 光遇博物馆爬虫采集脚本。愿温暖的灵魂终将相遇！
url: https://github.com/WhaleFell/skyData
---

光遇官网——光遇博物馆爬虫脚本
===============

前言
--

> 感恩季 追光季 归属季 凛冬季 魔法季 圣岛季 预言季 很荣幸能陪光遇走到现在，还有那些温柔的人 这一年多 有笑 有泪 不管怎样，我永远不会忘记我在这里度过的时光，开完好友树的，只开了对话的，只加了好友的，甚至是点亮过的小黑，很高兴认识你们，这一路承蒙照顾 真的很爱光遇,祝光遇越来越好，陈老师加油!

运行
--

1.  一定要在 `python3.X` 环境下运行本项目
2.  运行前请安装项目依赖的模块: `pip install -r requriements.txt`
3.  Linux运行:`sudo python3 sky.py`
4.  sudo python3 sky.py # 获取CSV文件
    sudo python3 download.py #下载
    sudo python3 api.py # api模块
    

爬取部分
----

-   1.  **爬取页面--光遇博物馆**
    
    > https://game.163.com/star/sky/index.html
    
-   1.  在脚本目录生成 **skyData {time}.csv** 文件
    
    -   文件的结构:
        
        ```
        title,text,tags,name,picList,time
        标题,文字内容(一些没有),标签,作者名,图片列表,发表时间
        ```
        
-   1.  本脚本 **可以一直爬取到`2019/6/27 2:06:24`的第一条内容** ,标题好像是:
    
    > 与温暖的灵魂相遇
    
-   1.  在我的win10上用Excel读取CSV文件已**不存在中文乱码的问题**
    
    -   关于Python CSV中文乱码问题的解决:
    
    import csv
    import codecs  \# 处理csv乱码
    with codecs.open("XXX.csv".format(new\_time), "w", encoding\="utf\_8\_sig") as cvs\_file:
          writer \= csv.DictWriter(cvs\_file, headers)
          writer.writeheader()  #写表头v
          writer.writerows(Data)  #写入多行字典数据
    
    > ### 如果还是存在中文乱码问题的话请提交`issues`
    

下载部分
----

**2021.2.5** _**已初步实现下载功能**_ 详细请查看download.py

> ### 运行前记得改路径哈！

-   下载结构

```
├─Skydownload
  ├─pic //图片文件夹
    ├─ 图片标签名文件夹
      ├─XXX.jpg
  ├─txt  //文字文件夹
    ├─标题_作者.txt
  ├─video //视频文件夹
    ├─标题.mp4
```

-   **实践** 2020.2.4 自己下载了大约1小时 大概 _**10GB**_ 左右叭

API部分
-----

-   运行:`python3 api.py`
-   获取json信息: **GET POST** `/sky/json/` 返回:
    
    {
      "status": 200, \# 正常返回200 错误返回500
      "data": {
      	"title": "积云中藏有秘密", \# 标题
      	"text": "nan", \# 文字
      	"tag": "游戏截图", \# 标签
      	"time": "2019-07-15 14:06:44", \# 发布日期
      	"pic\_url": "https://kol-fans.fp.ps.netease.com/file/ 5d2c88747f9d2abb9e34d4d5qBIAwTQd02", \# 图片链接
      	"content": "积云中藏有秘密|游戏截图" \# 整理后的文字
      }
    
    **异常返回:**
    
    {
      "status": 500,
      "data": {
        "content": "出现了其他异常 {异常信息}",
        "pic\_url": "https://i.loli.net/2021/02/18/w36CqS2FPkdvcV9.jpg", \# 异常图片
      }
    }
    
-   直接重定向到图片地址: **GET POST** `/sky/pic/`

自动提交shell部分
-----------

> 参见 **auto.sh**

-   Linux 下使用crontab实现 **自动运行**
    
    > 安利一个很好用的crontab 表达式生成工具
    
    sudo apt-get install crontabs
    # 用普通用户执行
    crontab -l # 查看
    crontab -e # 编辑
    # 添加
    30 15 0 \* \* ? \* pi /home/pi/skyData/auto.sh
    

TODO
----

-   添加`crantab`自动运行和自动提交`Git`的`shell` **脚本** 每天自动更新提交到`GitHub`(2020.2.19基本完成 **要开学了 嘤嘤嘤**)
-   添加 **下载列表中的图片功能** ,并把图片按文件夹**归类** (2021.2.5已完成)
-   爬取更多有关`Sky·光遇`的东西 (打算爬取 **光遇手游weibo**)
-   用Python Flask模块开发个 **光遇随机图api**(2021.2.18已完成)

后
-

-   此项目由一个**初中生**开发,仅供**学习用途**
-   如果有什么好的建议也欢迎提出 **Issues** ,也欢迎各位大佬 **Pull resquests** 这个项目.
-   诶呀! 点个 **Star** 再走叭!! mua~ /可爱
