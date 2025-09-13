---
project: chatgpt-adapter
stars: 1051
description: 集成了openai-api、coze、deepseek、cursor、windsurf、qodo、blackbox、you、grok、bing  绘画 多款AI的聊天逆向接口适配到 OpenAI API 标准接口服务端。
url: https://github.com/bincooo/chatgpt-adapter
---

ChatGPT Adapter
---------------

该服务集成了openai-api、coze、deepseek、cursor、windsurf、blackbox、you、grok、bing 绘画 多款AI的聊天逆向接口适配到 OpenAI API 标准接口服务端。

具体配置请 » 查阅文档 »

支持高速流式输出、支持多轮对话，与ChatGPT接口完全兼容。

使用本项目，可享用以下内容转v1接口：

-   字节coze国际版
-   new bing copilot
-   cursor editor
-   windsurf editor
-   qodo
-   deepseek
-   Chatbot Arena LMSYS
-   you
-   grok
-   huggingface 绘图

### 执行前置

安装中间编译工具

go install ./cmd/iocgo

# or 

make install

### 使用

正常指令附加

# ----- go build ------ #
# 原指令 #
go build ./main.go

# 附加指令 #
go build -toolexec iocgo ./main.go

# ----- go run ------ #
# 原指令 #
go run ./main.go

# 附加指令 #
go run -toolexec iocgo ./main.go

其它`go`指令同理

### 运行本项目三部曲 (linux / macos / window)

make install

make build

./bin/\[os\]/server\[.exe\] -h

### Docker 启动

1.  docker 命令：

docker run -p 8080:8080 -v ./config.yaml:/app/config.yaml ghcr.io/bincooo/chatgpt-adapter:latest

1.  huggingface: Duplicate this Space

### systemctl 自启动配置

\[Unit\]
Description\=ChatGPT adapter
After\=network.target

\[Service\]
Type\=simple
WorkingDirectory\=/your\_work\_dir
ExecStart\=/your\_app --port 7860
Restart\=on-failure

\[Install\]
WantedBy\=multi-user.target

### 其它 ...

看到有不少朋友似乎对逆向爬虫十分感兴趣，那我这里就浅谈一下个人的一点小经验吧

-   爬虫逆向之 ja3 指纹篇
-   爬虫逆向之 new bing copilot篇
-   爬虫逆向之 cursor & windsurf (protobuf+gzip)篇

特别声明
----

> 本仓库发布的程序代码及其中涉及的任何解锁和解密分析脚本，仅用于测试和学习研究，禁止用于商业用途，不能保证其合法性，准确性，完整性和有效性，请根据情况自行判断。
> 
> 本项目内所有资源文件，禁止任何公众号、自媒体进行任何形式的转载、发布。
> 
> 本人对任何脚本/代码/访问资源问题概不负责，包括但不限于由任何脚本错误导致的任何损失或损害。
> 
> 间接使用脚本/代码/访问资源的任何用户，包括但不限于建立VPS或在某些行为违反国家/地区法律或相关法规的情况下进行传播, 本人对于由此引起的任何隐私泄漏或其他后果概不负责。
> 
> 请勿将本仓库的任何内容用于商业或非法目的，否则后果自负。
> 
> 如果任何单位或个人认为该项目的脚本/代码/访问资源可能涉嫌侵犯其权利，则应及时通知并提供身份证明，所有权证明，我们将在收到认证文件后删除相关脚本。
> 
> 任何以任何方式查看此项目的人或直接或间接使用该项目的任何脚本的使用者都应仔细阅读此声明。本人保留随时更改或补充此免责声明的权利。一旦使用并复制了任何相关脚本或Script项目的规则，则视为您已接受此免责声明。
> 
> 您必须在下载后的24小时内从计算机或手机中完全删除以上内容.
> 
> 您使用或者复制了本仓库且本人制作的任何脚本/代码，则视为 已接受 此声明，请仔细阅读!
