---
project: sharelist
stars: 2706
description: 快速分享 GoogleDrive OneDrive 
url: https://github.com/reruin/sharelist
---

ShareList
=========

ShareList 是一个易用的网盘工具，支持快速挂载 GoogleDrive、OneDrive ，可通过插件扩展功能。  
新版正在开发中，欢迎提交反馈。查看旧版。

文档
--

查看文档

进度
--

-   核心库支持
-   新主题
-   自定义插件开发
-   webdav
-   跨盘转移
-   秒传

支持情况
----

下载

上传

列目录

创建目录

删除

重命名

远程移动

hash

秒传

OneDrive

✓

✓

✓

✓

✓

✓

✓

sha1

x

GoogleDrive

✓

✓

✓

✓

✓

✓

✓

md5

x

Local File

✓

✓

✓

✓

✓

✓

✓

md5/sha1

x

AliyunDrive

✓

✓

✓

✓

✓

✓

✓

sha1

✓

CaiYun

✓

✓

✓

✓

✓

✓

✓

md5

✓

CTCloud

✓

✓

✓

✓

✓

✓

✓

md5

✓

Baidu Netdisk

✓

x

✓

✓

✓

✓

✓

encrypt(md5)

✓

安装
--

```
docker run -d -v /etc/sharelist:/sharelist/cache -p 33001:33001 --name="sharelist" reruin/sharelist:next
```

release下载二进制版。

许可
--

MIT  
Copyright (c) 2018-present, Reruin
