---
project: xiaogpt
stars: 6679
description: Play ChatGPT and other LLM with Xiaomi AI Speaker
url: https://github.com/yihong0618/xiaogpt
---

xiaogpt
=======

yihong0618.1635132234935177216.mp4

Play ChatGPT and other LLM with Xiaomi AI Speaker

支持的 AI 类型
---------

-   ChatGPT
-   New Bing
-   ChatGLM
-   Gemini
-   Doubao
-   Moonshot
-   01
-   Llama3
-   通义千问

获取小米音响 DID
----------

系统和 Shell

Linux \*sh

Windows CMD 用户

Windows PowerShell 用户

1、安装包

`pip install miservice_fork`

`pip install miservice_fork`

`pip install miservice_fork`

2、设置变量

`export MI_USER=xxx`  
`export MI_PASS=xxx`

`set MI_USER=xxx`  
`set MI_PASS=xxx`

`$env:MI_USER="xxx"`  
`$env:MI_PASS="xxx"`

3、取得 MI\_DID

`micli list`

`micli list`

`micli list`

4、设置 MI\_DID

`export MI_DID=xxx`

`set MI_DID=xxx`

`$env:MI_DID="xxx"`

-   注意不同 shell 对环境变量的处理是不同的，尤其是 powershell 赋值时，可能需要双引号来包括值。
-   如果获取 did 报错时，请更换一下无线网络，有很大概率解决问题。

一点原理
----

不用 root 使用小爱同学和 ChatGPT 交互折腾记

准备
--

1.  ChatGPT id
2.  小爱音响
3.  能正常联网的环境或 proxy
4.  python3.8+

使用
--

-   `pip install -U --force-reinstall xiaogpt[locked]`
-   参考我 fork 的 MiService 项目 README 并在本地 terminal 跑 `micli list` 拿到你音响的 DID 成功 **别忘了设置 export MI\_DID=xxx** 这个 MI\_DID 用
-   run `xiaogpt --hardware ${your_hardware} --use_chatgpt_api` hardware 你看小爱屁股上有型号，输入进来，如果在屁股上找不到或者型号不对，可以用 `micli mina` 找到型号
-   跑起来之后就可以问小爱同学问题了，“帮我"开头的问题，会发送一份给 ChatGPT 然后小爱同学用 tts 回答
-   如果上面不可用，可以尝试用手机抓包，https://userprofile.mina.mi.com/device\_profile/v2/conversation 找到 cookie 利用 `--cookie '${cookie}'` cookie 别忘了用单引号包裹
-   默认用目前 ubus, 如果你的设备不支持 ubus 可以使用 `--use_command` 来使用 command 来 tts
-   使用 `--mute_xiaoai` 选项，可以快速停掉小爱的回答
-   使用 `--account ${account} --password ${password}`
-   如果有能力可以自行替换唤醒词，也可以去掉唤醒词
-   使用 `--use_chatgpt_api` 的 api 那样可以更流畅的对话，速度特别快，达到了对话的体验，openai api, 命令 `--use_chatgpt_api`
-   如果你遇到了墙需要用 Cloudflare Workers 替换 api\_base 请使用 `--api_base ${url}` 来替换。 **请注意，此处你输入的 api 应该是'`https://xxxx/v1`'的字样，域名需要用引号包裹**
-   `--use_moonshot_api` and other models please refer below
-   可以跟小爱说 `开始持续对话` 自动进入持续对话状态，`结束持续对话` 结束持续对话状态。
-   可以使用 `--tts edge` 来获取更好的 tts 能力
-   可以使用 `--tts fish --fish_api_key <your-fish-key> --fish_voice_key <fish-voice>` 来获取 fish-audio 能力 (如何获取 fish voice 见下)
-   可以使用 `--tts openai` 来获取 openai tts 能力
-   可以使用 `--tts azure --azure_tts_speech_key <your-speech-key>` 来获取 Azure TTS 能力
-   可以使用 `--use_langchain` 替代 `--use_chatgpt_api` 来调用 LangChain（默认 chatgpt）服务，实现上网检索、数学运算..

e.g.

export OPENAI\_API\_KEY=${your\_api\_key}
xiaogpt --hardware LX06 --use\_chatgpt\_api
# or
xiaogpt --hardware LX06 --cookie ${cookie} --use\_chatgpt\_api
# 如果你想直接输入账号密码
xiaogpt --hardware LX06 --account ${your\_xiaomi\_account} --password ${your\_password} --use\_chatgpt\_api
# 如果你想 mute 小米的回答
xiaogpt --hardware LX06  --mute\_xiaoai --use\_chatgpt\_api
# 使用流式响应，获得更快的响应
xiaogpt --hardware LX06  --mute\_xiaoai --stream
# 如果你想使用 google 的 gemini
xiaogpt --hardware LX06  --mute\_xiaoai --use\_gemini --gemini\_key ${gemini\_key}
# 如果你想使用自己的 google gemini 服务
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_gemini --gemini\_key ${gemini\_key} --gemini\_api\_domain ${gemini\_api\_domain}
# 如果你想使用阿里的通义千问
xiaogpt --hardware LX06  --mute\_xiaoai --use\_qwen --qwen\_key ${qwen\_key}
# 如果你想使用 kimi
xiaogpt --hardware LX06  --mute\_xiaoai --use\_moonshot\_api --moonshot\_api\_key ${moonshot\_api\_key}
# 如果你想使用 llama3
xiaogpt --hardware LX06  --mute\_xiaoai --use\_llama --llama\_api\_key ${llama\_api\_key}
# 如果你想使用 01
xiaogpt --hardware LX06  --mute\_xiaoai --use\_yi\_api --ti\_api\_key ${yi\_api\_key}
# 如果你想使用 LangChain+SerpApi 实现上网检索或其他本地服务（目前仅支持 stream 模式）
export OPENAI\_API\_KEY=${your\_api\_key}
export SERPAPI\_API\_KEY=${your\_serpapi\_key}
xiaogpt --hardware Lx06 --use\_langchain --mute\_xiaoai --stream --openai\_key ${your\_api\_key} --serpapi\_api\_key ${your\_serpapi\_key}

使用 git clone 运行

export OPENAI\_API\_KEY=${your\_api\_key}
python3 xiaogpt.py --hardware LX06
# or
python3 xiaogpt.py --hardware LX06 --cookie ${cookie}
# 如果你想直接输入账号密码
python3 xiaogpt.py --hardware LX06 --account ${your\_xiaomi\_account} --password ${your\_password} --use\_chatgpt\_api
# 如果你想 mute 小米的回答
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai
# 使用流式响应，获得更快的响应
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --stream
# 如果你想使用 ChatGLM api
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_glm --glm\_key ${glm\_key}
# 如果你想使用 google 的 gemini
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_gemini --gemini\_key ${gemini\_key}
# 如果你想使用自己的 google gemini 服务
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_gemini --gemini\_key ${gemini\_key} --gemini\_api\_domain ${gemini\_api\_domain}
# 如果你想使用阿里的通义千问
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_qwen --qwen\_key ${qwen\_key}
# 如果你想使用 kimi
xiaogpt --hardware LX06  --mute\_xiaoai --use\_moonshot\_api --moonshot\_api\_key ${moonshot\_api\_key}
# 如果你想使用 01
xiaogpt --hardware LX06  --mute\_xiaoai --use\_yi\_api --ti\_api\_key ${yi\_api\_key}
# 如果你想使用豆包
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_doubao --stream --volc\_access\_key xxxx --volc\_secret\_key xxx
# 如果你想使用 llama3
python3 xiaogpt.py --hardware LX06  --mute\_xiaoai --use\_llama --llama\_api\_key ${llama\_api\_key}
# 如果你想使用 LangChain+SerpApi 实现上网检索或其他本地服务（目前仅支持 stream 模式）
export OPENAI\_API\_KEY=${your\_api\_key}
export SERPAPI\_API\_KEY=${your\_serpapi\_key}
python3 xiaogpt.py --hardware Lx06 --use\_langchain --mute\_xiaoai --stream --openai\_key ${your\_api\_key} --serpapi\_api\_key ${your\_serpapi\_key}

config.yaml
-----------

如果想通过单一配置文件启动也是可以的，可以通过 `--config` 参数指定配置文件，config 文件必须是合法的 Yaml 或 JSON 格式 参数优先级

-   cli args > default > config

python3 xiaogpt.py --config xiao\_config.yaml
# or
xiaogpt --config xiao\_config.yaml

或者

cp xiao\_config.yaml.example xiao\_config.yaml
python3 xiaogpt.py

若要指定 OpenAI 的模型参数，如 model, temporature, top\_p, 请在 config.yaml 中指定：

gpt\_options:
  temperature: 0.9
  top\_p: 0.9

具体参数作用请参考 Open AI API 文档。 ChatGLM 文档

配置项说明
-----

参数

说明

默认值

可选值

hardware

设备型号

account

小爱账户

password

小爱账户密码

openai\_key

openai 的 apikey

moonshot\_api\_key

moonshot kimi 的 apikey

yi\_api\_key

01 wanwu 的 apikey

llama\_api\_key

groq 的 llama3 apikey

serpapi\_api\_key

serpapi 的 key 参考 SerpAPI

glm\_key

chatglm 的 apikey

gemini\_key

gemini 的 apikey 参考

gemini\_api\_domain

gemini 的自定义域名 参考

qwen\_key

qwen 的 apikey 参考

cookie

小爱账户 cookie（如果用上面密码登录可以不填）

mi\_did

设备 did

use\_command

使用 MI command 与小爱交互

`false`

mute\_xiaoai

快速停掉小爱自己的回答

`true`

verbose

是否打印详细日志

`false`

bot

使用的 bot 类型，目前支持 chatgptapi,newbing, qwen, gemini

`chatgptapi`

tts

使用的 TTS 类型

`mi`

`edge`、 `openai`、`azure`、`volc`、`baidu`、`google`、`minimax`

tts\_options

TTS 参数字典，参考 tetos 获取可用参数

prompt

自定义 prompt

`请用100字以内回答`

keyword

自定义请求词列表

`["请"]`

change\_prompt\_keyword

更改提示词触发列表

`["更改提示词"]`

start\_conversation

开始持续对话关键词

`开始持续对话`

end\_conversation

结束持续对话关键词

`结束持续对话`

stream

使用流式响应，获得更快的响应

`true`

proxy

支持 HTTP 代理，传入 http proxy URL

""

gpt\_options

OpenAI API 的参数字典

`{}`

deployment\_id

Azure OpenAI 服务的 deployment ID

参考这个如何找到 deployment\_id

api\_base

如果需要替换默认的 api，或者使用 Azure OpenAI 服务

例如：`https://abc-def.openai.azure.com/`

volc\_access\_key

火山引擎的 access key 请在这里获取

volc\_secret\_key

火山引擎的 secret key 请在这里获取

注意
--

1.  请开启小爱同学的蓝牙
2.  如果要更改提示词和 PROMPT 在代码最上面自行更改
3.  目前已知 LX04、X10A 和 L05B L05C 可能需要使用 `--use_command`，否则可能会出现终端能输出 GPT 的回复但小爱同学不回答 GPT 的情况。这几个型号也只支持小爱原本的 tts.
4.  在 wsl 使用时，需要设置代理为 <http://wls 的 ip:port(vpn 的代理端口)>, 否则会出现连接超时的情况，详情 报错：Error communicating with OpenAI

QA
--

1.  用破解么？不用
2.  你做这玩意也没用啊？确实。。。但是挺好玩的，有用对你来说没用，对我们来说不一定呀
3.  想把它变得更好？PR Issue always welcome.
4.  还有问题？提 Issue 哈哈
5.  Exception: Error https://api2.mina.mi.com/admin/v2/device\_list?master=0&requestId=app\_ios\_xxx: Login failed @KJZH001  
    这是由于小米风控导致，海外地区无法登录大陆的账户，请尝试 cookie 登录 无法抓包的可以在本地部署完毕项目后再用户文件夹`C:\Users\用户名`下面找到.mi.token，然后扔到你无法登录的服务器去  
    若是 linux 则请放到当前用户的 home 文件夹，此时你可以重新执行先前的命令，不出意外即可正常登录（但 cookie 可能会过一段时间失效，需要重新获取）  
    详情请见 #332

视频教程
----

https://www.youtube.com/watch?v=K4YA8YwzOOA

Docker
------

### 常规用法

X86/ARM Docker Image: `yihong0618/xiaogpt`

docker run -e OPENAI\_API\_KEY=<your-openapi-key\> yihong0618/xiaogpt <命令行参数\>

如

docker run -e OPENAI\_API\_KEY=<your-openapi-key\> yihong0618/xiaogpt --account=<your-xiaomi-account\> --password=<your-xiaomi-password\> --hardware=<your-xiaomi-hardware\> --use\_chatgpt\_api

### 使用配置文件

xiaogpt 的配置文件可通过指定 volume /config，以及指定参数--config 来处理，如

docker run -v <your-config-dir\>:/config yihong0618/xiaogpt --config=/config/config.yaml

### 网络使用 host 模型

docker run -v <your-config-dir\>:/config --network=host yihong0618/xiaogpt --config=/config/config.yaml

### 本地编译 Docker Image

 docker build -t xiaogpt .

如果在安装依赖时构建失败或安装缓慢时，可以在构建 Docker 镜像时使用 `--build-arg` 参数来指定国内源地址：

docker build --build-arg PIP\_INDEX\_URL=https://pypi.tuna.tsinghua.edu.cn/simple -t xiaogpt .

如果需要在 Apple M1/M2上编译x86

 docker buildx build --platform=linux/amd64 -t xiaogpt-x86 .

### 第三方 TTS

我们目前支持是三种第三方 TTS：edge/openai/azure/volc/baidu/google

edge-tts 提供了类似微软 tts 的能力 azure-tts 提供了微软 azure tts 的能力 openai-tts 提供了类似 openai tts 的能力 fish-tts 提供了 fish tts 的能力

#### Usage

你可以通过参数 `tts`, 来启用它

tts: edge

For edge 查看更多语言支持，从中选择一个

edge-tts --list-voices

#### 如果你想使用 fish-tts

1.  注册 https://fish.audio/zh-CN/go-api/ 拿到 api key
2.  选择你想要的声音自建声音或者使用热门声音 https://fish.audio/zh-CN/text-to-speech/?modelId=e80ea225770f42f79d50aa98be3cedfc 其中 `e80ea225770f42f79d50aa98be3cedfc` 就声音的 key id
3.  python3 xiaogpt.py --hardware LX06 --account xxxx --password xxxxx --use\_chatgpt\_api --mute\_xiaoai --stream --tts fish --fish\_api\_key xxxxx --fish\_voice\_key xxxxx
4.  或者在 xiao\_config.yaml 中配置

tts: fish 
# TTS 参数字典，参考 https://github.com/frostming/tetos 获取可用参数
tts\_options: {
    "api\_key": "xxxxx",
    "voice": "xxxxxx"
}

#### 在容器中使用 edge-tts/azure-tts/openai-tts/volc/google/baidu/fish

由于 Edge TTS 启动了一个本地的 HTTP 服务，所以需要将容器的端口映射到宿主机上，并且指定本地机器的 hostname:

docker run -v <your-config-dir\>:/config -p 9527:9527 -e XIAOGPT\_HOSTNAME=<your ip\> yihong0618/xiaogpt --config=/config/config.yaml

注意端口必须映射为与容器内一致，XIAOGPT\_HOSTNAME 需要设置为宿主机的 IP 地址，否则小爱无法正常播放语音。

推荐的类似项目
-------

-   XiaoBot -> Go 语言版本的 Fork, 带支持不同平台的 UI
-   MiGPT -> Node.js 版，支持流式响应和长短期记忆

感谢
--

-   xiaomi
-   PDM
-   Tetos TTS 云服务支持
-   @Yonsm 的 MiService
-   @pjq 给了这个项目非常多的帮助
-   @frostming 重构了一些代码，支持了`持续会话功能`

赞赏
--

谢谢就够了
