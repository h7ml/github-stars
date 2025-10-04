---
project: MNBVC
stars: 3991
description: MNBVC(Massive Never-ending BT Vast Chinese corpus)超大规模中文语料集。对标chatGPT训练的40T数据。MNBVC数据集不但包括主流文化，也包括各个小众文化甚至火星文的数据。MNBVC数据集包括新闻、作文、小说、书籍、杂志、论文、台词、帖子、wiki、古诗、歌词、商品介绍、笑话、糗事、聊天记录等一切形式的纯文本中文数据。
url: https://github.com/esbatmop/MNBVC
---

MNBVC(Massive Never-ending BT Vast Chinese corpus)超大规模中文语料集
===========================================================

请媒体朋友们不要报道我们，让我们有更长久的时间可以收集整理数据。我们最怕捧杀了，您让我们保持低调，就是对中文算法圈做了大的贡献！
----------------------------------------------------------------

中文互联网上最古老最神秘(没有之一)的MOP里屋社区于2023.1.1庄重宣布:

**在英明神武的猫扑管子带领下，决心发挥社区所长(哪都长)，帮助开源社区长期更新一份最大的中文互联网语料集**

MNBVC语料集 不但包括主流文化，也包括各个小众文化甚至火星文的数据。MNBVC数据集包括新闻、作文、小说、书籍、杂志、论文、台词、帖子、wiki、古诗、歌词、商品介绍、笑话、糗事、聊天记录等一切形式的纯文本中文数据。数据均来源于互联网收集。

### 进度

目前总数据量59703GB，目标是达到253T数据，目前进度23.5%。

### 数据说明

压缩包密码为253874

压缩包内中文语料包括txt、json、jsonl和parquet（多模态专用）格式，最终会统一到jsonl和parquet格式。

压缩包根目录的links.txt里有每个子文件夹数据来源的url

每个子文件夹内有一张png格式的图片，是数据来源的网页截图

收录的数据将去掉大于等于8位的数字串进行脱敏

压缩包内数据只做了粗加工,例如html&xml转txt、csv&tsv转json等

### 索引和分类

我们没有能力对数据来源进行版权审核。虽然本数据集包括了数据来源信息，但为了长而持久的提供数据集的更新和下载，为了尽量避免版权争议，本数据集不提供压缩包内数据的索引和分类。并恳请大家克制住自己的分享欲，不要讨论压缩包的索引及所包含具体内容的信息。请大家更多的关注大数据量语料本身的应用，拜托大家低调的使用数据。

### huggingface

清洗完成的分类数据将陆续放到：https://huggingface.co/datasets/liwu/MNBVC

### 一人行快，众人行远（摇人加速 发送邮件 MNBVC@253874.net）

各个小组长反映，数据清洗的苦力代码工作比较多，技术落地有点慢，希望有大量时间的同学来帮忙，会用python就行，有人手把手指导。请来帮忙的同学先阅读项目的三条红线。

-   OCR转码小组（被GPT4逼成了包含文字-图片的多模态语料组，增加编制），目前5人，缺5人（需有CV、NLP算法背景，想用nlp辅助ocr转码，有业内此领域顶尖大佬带队指导）
-   问答语料小组，目前3人，缺4人（目前全是写python代码对齐问答项并人肉检查的苦力活，后面想利用算法模型做自动对齐）
-   语料增强小组，目前3人，缺2人（想利用nlp补全缺字的语料，并进行文本质量检测等）
-   代码语料小组和平行语料小组还缺几个打杂（后面由组长来决定到底干嘛）
-   待建古文研究小组（研究地方志等古籍的转码，语料很多，难度很大）
-   待建测试组（请测试同学加入，帮助我们提升数据质量，希望本组同学可以研究用llm直接生成测试用例和测试代码）

即使没空帮助项目做开发，也可以通过参加 (语料元气弹) 项目，随手上传语料文档，来参与MNBVC语料集的建设。

### 中文大语料清洗工具

为处理大规模的中文语料，MNBVC项目组的同学在现有开源软件基础上做了优化，提供了更高效的版本:

-   更快速且准确的中文编码检测工具：charset\_mnbvc
-   将txt批量转成jsonl并挑出段落重复度高的文件：deduplication\_mnbvc
-   从多层目录中按关键词采样一定数量的文件并保留目录结构：scan\_copy\_files\_mnbvc
-   将MNBVC语料格式统一的格式检查工具：DataCheck\_MNBVC
-   数据清洗示例及工具：DataClean-MNBVC

### 代码仓库爬虫工具

现有各个开源代码语料集都有很严重的人为过滤现象，这让追赶chatGPT变得更为困难。为避免重复劳动，提供经过MNBVC大规模验证后的代码仓库爬虫代码。

-   爬取github代码仓库meta信息：publicRepos\_mnbvc
-   爬取github代码仓库最新版本代码：github\_downloader\_mnbvc
-   爬取notabug代码仓库：notabug\_download\_mnbvc
-   爬取bitbucket代码仓库：bitbucket\_crawl\_mnbvc
-   将代码转为语料：githubcode\_extractor\_mnbvc
-   爬取commit记录：get\_github\_commit\_mnbvc

### 多模态处理工具

-   PDF元信息抽取工具：pdf\_meta\_data\_mnbvc
-   PDF解析规则工具：mmdp\_mnbvc
-   第一版的pdf转txt工具：pdf2txt\_mnbvc
-   Arxiv文档解析工具：Arxiv\_mllm\_mnbvc
-   Arxiv图文对处理工具：ARXIV\_IMAGE2CAPTION\_mnbvc
-   将PDF文件转换为JSON和Markdown格式的工具：docling\_parse\_mnbvc
-   将文本文件转化为parquet格式：mm\_template\_mnbvc

### 各种清洗代码

-   wikihow清洗代码：WikiHowQAExtractor-mnbvc
-   中国外交部发言清洗代码：QA\_with\_reporters\_from\_the\_Ministry\_of\_Foreign\_Affair\_mnbvc
-   各类数学题清洗代码：Math\_mnbvc
-   stackexchange的清洗代码：stackexchange\_mnbvc
-   平行语料的清洗代码：parallel\_corpus\_mnbvc
-   试卷的清洗代码：Exam-Question-Bank-Dataset-zh\_mnbvc
-   裁判文书网的清洗代码：MNBVC-judgment
-   剧本杀的清洗代码：MNBVC-pdf-extract
-   DocLayNet的清洗代码：DocLayNetPlus\_mnbvc

### 其他小工具

-   chinarxiv的爬虫：chinaxivCrawler\_mnbvc
-   从warc中提取文件：warc\_extractor\_mnbvc
-   psyarxiv、chemrxiv、biorxiv、medrxiv的爬虫：xxarxiv\_mnbvc
-   wipo的爬虫：wipo\_mnbvc

### 语料集下载信息(每个压缩包都会随着清洗进度更新):

1.通过p2p微力同步全部压缩包并接收更新  
建议关闭tcp穿透、关闭udp传输的微力设置。如不关闭，微力有可能堵塞路由器（同时也许传输速度更快）

> 微力密钥part1: B4MVPVJTK3DOOAOPVLJ3E7TA7RWW4J2ZEAXJRMRSRHSBPDB7OAFHUQ  
> 微力直达链接part1 注：此part1需占磁盘空间10T+，如需要更小分块的链接，请看：锐意新计划

> 微力密钥part2: B4FQSD525XQQDY6XNO7JZ6BM2EIKAUTVPLLVX6N52HIWBZ7G72R7EQ  
> 微力直达链接part2

2.通过百度网盘下载：第一部分、第二部分

### Citation

Please cite the repo if you use the data or code in this repo.

```
@misc{mnbvc,
  author = {{MOP-LIWU Community} and {MNBVC Team}},
  title = {MNBVC: Massive Never-ending BT Vast Chinese corpus},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/esbatmop/MNBVC}},
}
```
