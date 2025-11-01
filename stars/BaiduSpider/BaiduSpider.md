---
project: BaiduSpider
stars: 1122
description: BaiduSpider，一个爬取百度搜索结果的爬虫，目前支持百度网页搜索，百度图片搜索，百度知道搜索，百度视频搜索，百度资讯搜索，百度文库搜索，百度经验搜索和百度百科搜索。
url: https://github.com/BaiduSpider/BaiduSpider
---

  

### BaiduSpider

一个爬取百度的利器  
简体中文 | **繁體中文** | **English**  
**快速上手 »**  
  
查看示例 · 报告问题 · 请求需求

目录

1.  关于本项目
    -   依赖库
2.  起步
    -   预先条件
    -   安装
3.  简单使用
4.  项目路线图
5.  项目共建
6.  开源协议
7.  联系方式
8.  免责声明
9.  贡献者
10.  致谢

关于本项目
-----

搜索引擎是一个十分强大的工具，如果能让其他工具集成搜索引擎的众多强大功能，那么这些工具必将变得更加强大。但目前我没有找到一个可以精准提取搜索引擎搜索结果的开源爬虫。于是，我便编写了这个爬取百度搜索引擎的项目：BaiduSpider。

BaiduSpider 的独特功能:

-   节省提取数据的时间，对于类似深度学习项目的数据模型建立与训练起到了良好的帮助。
    
-   精准提取数据，并删除广告。
    
-   搜索结果大而全，支持多种搜索类型，支持多种返回类型。
    

当然，没有一个项目是完美的。任何一个项目的发展都需要社区的帮助。你可以通过发布 Issue 或提交 PR 来帮助 BaiduSpider 进步！:smile:

一些比较有帮助的文档或工具将在最后的致谢部分中列出。

### 依赖库

一些 BaiduSpider 使用的主要开源依赖库。

-   BeautifulSoup 4
-   requests

起步
--

为了安装 BaiduSpider，请按照以下几个步骤操作。

### 预先条件

在安装 BaiduSpider 之前，请确保你安装了`Python3.6+`：

$ python --version

若版本小于`3.6.0`，请到Python官网下载并安装 Python。

### 安装

#### 使用`pip`安装

请在命令行中键入：

$ pip install baiduspider

#### 从 GitHub 手动安装

$ git clone git@github.com:BaiduSpider/BaiduSpider.git

# ...

$ python setup.py install

简单使用
----

你可以使用以下代码，通过 BaiduSpider 获取百度的网页搜索结果：

\# 导入BaiduSpider
from baiduspider import BaiduSpider
from pprint import pprint

\# 实例化BaiduSpider
spider \= BaiduSpider()

\# 搜索网页
pprint(spider.search\_web(query\='Python'))

_更多样例和配置，请参照文档_

项目路线图
-----

请参考 Opening Issues 以获取最新的项目规划以及已知问题。

项目共建
----

社区的贡献是开源项目的灵魂所在，也是整个开源社区学习、交流、获得灵感的方式。我们**极力欢迎**任何人参与本项目的开发与维护。

具体参与步骤如下：

1.  Fork 此项目
2.  创建 Feature 分支 (`git checkout -b NewFeatures`)
3.  在每次修改代码后，提交你的更改 (`git commit -m 'Add some AmazingFeature'`)
4.  将更改推送到自己的远程仓库 (`git push origin username/BaiduSpider`)
5.  在 GitHub 上打开你的仓库，根据指引提交 PR

开源协议
----

本项目基于`GPL-V3`开源，详情请参见`LICENSE`。

联系方式
----

samzhangjy - @samzhangjy - samzhang951@outlook.com

项目链接：https://github.com/BaiduSpider/BaiduSpider

免责声明
----

此项目仅作为学习用途，不可商用或用于爬取百度大量数据。此外，本项目使用`GPL-V3`版权协议，意味着涉及（使用）此项目的任何其它项目必须开源且注明出处，并且本项目作者不承担滥用导致的任何法律风险。特此说明，违者后果自负。

贡献者
---

致谢
--

-   BeautifulSoup 4
-   Requests
-   Img Shields
-   Gitmoji
-   Best-README-Template
-   Choose an Open Source License
-   GitHub Pages
