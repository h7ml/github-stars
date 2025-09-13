---
project: BWmelonApi
stars: 62
description: 一个基于Express框架的api接口，包括短网址生成、短网址还原、二维码生成、二维码识别解析、网站标题获取、ICP备案查询、网易云音乐解析、QQ信息获取、一言、必应每日一图。
url: https://github.com/BWmelon/BWmelonApi
---

﻿﻿﻿﻿## 说明 一个基于Express框架的api接口，包括短网址生成、短网址还原、二维码生成、二维码识别解析、网站标题获取、ICP备案查询、网易云音乐解析、QQ信息获取、一言、必应每日一图。

数据库为MongoDB。

演示网站：https://api.no0a.cn/
-------------------------

首页截图：
-----

使用
--

```
#安装依赖
$ npm install

#启动项目，默认端口为3000
$ npm start
```

TODO
----

-   前台文档页面
-   接口使用次数统计
-   接口调用频率限制
-   ip黑名单
-   后台自定义接口的开启与关闭
-   加入更多接口

接口文档
----

### 短网址生成

接口：

`http://127.0.0.1:3000/api/tinyurl/urlcn/?longurl=`

`http://127.0.0.1:3000/api/tinyurl/tcn/?longurl=`

示例：

`http://127.0.0.1:3000/api/tinyurl/urlcn/?longurl=http://api.no0a.cn`

返回：

```
{
    "status": 1,
    "tinyurl": "https://url.cn/5fpMHji"
}
```

### 短网址还原

接口：

`http://127.0.0.1:3000/api/longurl/query?tinyurl=`

示例：

`http://127.0.0.1:3000/api/longurl/query?tinyurl=https://t.cn/AiYNrqef`

返回：

```
{
    "status": 1,
    "longurl": "http://api.no0a.cn/"
}
```

### 二维码生成

接口：

`http://127.0.0.1:3000/api/qrcode/query?url=`

示例：

`http://127.0.0.1:3000/api/qrcode/query?url=http://api.no0a.cn`

返回：

```
直接返回png格式的二维码
```

### 二维码识别解析

接口：

`http://127.0.0.1:3000/api/qrdecode/query?imgurl=`

示例：

`http://127.0.0.1:3000/api/qrdecode/query?imgurl=https://imgs.bwmelon.com/20190803222039.png`

返回：

```
{
    "status": 1,
    "qrurl": "https://i.qianbao.qq.com/wallet/sqrcode.htm?m=tenpay&f=wallet&a=1&ac=CAEQl4jHtQUYz93y6AU%3D_xxx_sign&u=1454490647&n=%E6%89%93%EF%BC%8C%E6%89%93%E4%B8%AA%E5%A4%A7%E8%A5%BF%E7%93%9C%E3%80%80"
}
```

### 网站标题获取

接口：

`http://127.0.0.1:3000/api/sitetitle/query?url=`

示例：

`http://127.0.0.1:3000/api/sitetitle/query?url=https://qr.no0a.cn`

返回：

```
{
    "status": 1,
    "title": "大西瓜三合一收款码"
}
```

### ICP备案查询

接口：

`http://127.0.0.1:3000/api/icp/query?domain=`

示例：

`http://127.0.0.1:3000/api/icp/query?domain=qq.com`

返回：

```
{
    "status": 1,
    "info": {
        "name": "深圳市腾讯计算机系统有限公司",
        "properties": "企业",
        "icp": "粤B2-20090059-5",
        "title": "腾讯网",
        "people": "--",
        "time": "2019/8/1 0:00:00"
    }
}
```

### 网易云音乐解析

接口：

`搜索：https://api.no0a.cn/api/cloudmusic/search/key`

`解析：https://api.no0a.cn/api/cloudmusic/url/id`

`信息：https://api.no0a.cn/api/cloudmusic/info/id`

`歌词：https://api.no0a.cn/api/cloudmusic/lyric/id`

`歌单：https://api.no0a.cn/api/cloudmusic/playlist/id`

示例：

`搜索：https://api.no0a.cn/api/cloudmusic/search/偏爱`

`解析：https://api.no0a.cn/api/cloudmusic/url/86369`

`信息：https://api.no0a.cn/api/cloudmusic/info/86369`

`歌词：https://api.no0a.cn/api/cloudmusic/lyric/86369`

`歌单：https://api.no0a.cn/api/cloudmusic/playlist/2796626278`

返回：

```
{
    "status": 1,
    "results": [
        {
            "name": "偏爱",
            "id": 86369,
            "artist": [
                {
                    "name": "张芸京"
                }
            ]
        },
        {
            "name": "偏爱",
            "id": 328076,
            "artist": [
                {
                    "name": "张芸京"
                }
            ]
        },
        {
            "name": "此生不换",
            "id": 86363,
            "artist": [
                {
                    "name": "青鸟飞鱼"
                }
            ]
        }
    ]
}
```

```
{
    "status": 1,
    "musicurl": "http://m8.music.126.net/20190810162950/cb941dff97550a297f9888cb96251ec0/ymusic/2f43/79c5/bd3c/7fe89e927098b086e99223a996189cba.mp3"
}
```

```
{
    "status": 1,
    "musicinfo": {
        "name": "偏爱",
        "artist": [
            {
                "name": "张芸京"
            }
        ]
    }
}
```

```
{
    "status": 1,
    "musiclyric": "[by:Kyu9n]\n[00:00.000] 作曲 : 陈伟\n[00:01.000] 作词 : 葛大为\n[00:15.50]把昨天都作废\n[00:18.91]现在你在我眼前\n[00:22.69]我想爱 请给我机会\n[00:29.19]如果我错了也承担\n[00:33.07]认定你就是答案\n[00:37.76]我不怕谁嘲笑我极端\n[00:42.07]\n[00:42.92]相信自己的直觉\n[00:46.78]顽固的人不喊累\n[00:50.27]爱上你 我不撤退\n[00:55.19]\n[00:55.70]我说过 我不闪躲\n[00:59.12]我非要这么做\n[01:01.83]讲不听 也偏要爱\n[01:04.27]更努力爱 让你明白\n[01:09.37]没有别条路能走\n[01:12.58]你决定要不要陪我\n[01:15.50]讲不听 偏爱\n[01:17.22]靠我感觉爱\n[01:18.94]等你的依赖\n[01:21.90]对你偏爱\n[01:29.18]痛也很愉快\n[01:36.06]\n[01:37.82]把昨天都作废\n[01:41.20]现在你在我眼前\n[01:44.91]我想爱 请给我机会\n[01:51.49]如果我错了也承担\n[01:55.40]认定你就是答案\n[02:00.14]我不怕谁嘲笑我极端\n[02:04.37]\n[02:05.18]相信自己的直觉\n[02:09.05]顽固的人不喊累\n[02:12.54]爱上你 我不撤退\n[02:17.59]\n[02:18.01]我说过 我不闪躲\n[02:21.44]我非要这么做\n[02:24.09]讲不听 也偏要爱\n[02:26.55]更努力爱 让你明白\n[02:31.79]没有别条路能走\n[02:34.77]你决定要不要陪我\n[02:37.80]讲不听 偏爱\n[02:39.54]靠我感觉爱\n[02:41.20]等你的依赖\n[02:44.04]\n[02:44.22]不后悔 有把握\n[02:47.12]我不闪躲 我非要这么做\n[02:51.46]讲不听 也偏要爱\n[02:53.92]更努力爱 让你明白\n[02:59.16]没有别条路能走\n[03:02.17]你决定要不要陪我\n[03:05.22]讲不听 偏爱\n[03:06.95]靠我感觉爱\n[03:08.74]等你的依赖\n[03:11.64]对你偏爱 爱\n[03:18.91]痛也很愉快\n[03:26.57]\n"
}
```

```
{
    "status": 1,
    "results": [
        {
            "name": "カノン",
            "id": 4894309,
            "artist": [
                {
                    "name": "DJ Okawari"
                }
            ]
        },
        {
            "name": "Adagio for Summer Wind",
            "id": 760037,
            "artist": [
                {
                    "name": "清水準一"
                }
            ]
        },
        {
            "name": "やわらかな光",
            "id": 28287132,
            "artist": [
                {
                    "name": "やまだ豊"
                }
            ]
        },
        {
            "name": "一弯明月",
            "id": 362446,
            "artist": [
                {
                    "name": "陈嘉玲"
                }
            ]
        }
    ]
}
```

### QQ信息获取

接口：

`http://127.0.0.1:3000/api/qqinfo/qq`

示例：

`http://127.0.0.1:3000/api/qqinfo/10001`

返回：

```
{
    "status": 1,
    "qqinfo": {
        "nickname": "pony",
        "qqavatar": "http://q1.qlogo.cn/g?b=qq&s=640&nk=10001"
    }
}
```

### 一言

接口：

`http://127.0.0.1:3000/api/onenote/query`

示例：

`http://127.0.0.1:3000/api/onenote/query`

返回：

```
{
    "status": 1,
    "onenote": "你说你会爱我一辈子，我真傻，居然忘了问是这辈子还是下辈子。"
}
```

### 必应每日一图

接口：

`http://127.0.0.1:3000/api/bing/day` day为时间，0表示当天，1-7表示过去的1-7天，最多为过去7天

示例：

`http://127.0.0.1:3000/api/bing/0`

`http://127.0.0.1:3000/api/bing/1`

`http://127.0.0.1:3000/api/bing/3`

`http://127.0.0.1:3000/api/bing/7`

返回：

```
    "status": 1,
    "bing": {
        "url": "http://s.cn.bing.net/th?id=OHR.UhuRLP_ZH-CN5421658032_1920x1080.jpg&rf=LaDigue_1920x1080.jpg&pid=hp",
        "copyright": "野花草甸上的一只欧亚雕鸮，德国莱茵兰-普法尔茨 (© Rosl Roessner/Minden Pictures)"
    }
}
```

宝塔安装教程
------

https://www.bwmelon.com/archives/27/
