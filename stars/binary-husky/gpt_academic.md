---
project: gpt_academic
stars: 69298
description: 为GPT/GLM等LLM大语言模型提供实用化交互接口，特别优化论文阅读/润色/写作体验，模块化设计，支持自定义快捷按钮&函数插件，支持Python和C++等项目剖析&自译解功能，PDF/LaTex论文翻译&总结功能，支持并行问询多种LLM模型，支持chatglm3等本地模型。接入通义千问, deepseekcoder, 讯飞星火, 文心一言, llama2, rwkv, claude2, moss等。
url: https://github.com/binary-husky/gpt_academic
---

Important

`master主分支`最新动态(2025.8.23): Dockerfile构建效率大幅优化 `master主分支`最新动态(2025.7.31): 新GUI前端，Coming Soon

2025.2.2: 三分钟快速接入最强qwen2.5-max视频 2025.2.1: 支持自定义字体 2024.10.10: 突发停电，紧急恢复了提供whl包的文件服务器 2024.5.1: 加入Doc2x翻译PDF论文的功能，查看详情 2024.3.11: 全力支持Qwen、GLM、DeepseekCoder等中文大语言模型！ SoVits语音克隆模块，查看详情 2024.1.17: 安装依赖时，请选择`requirements.txt`中**指定的版本**。 安装命令：`pip install -r requirements.txt`。

  

GPT 学术优化 (GPT Academic)
=======================

  

**如果喜欢这个项目，请给它一个Star；如果您发明了好用的快捷键或插件，欢迎发pull requests！**

If you like this project, please give it a Star. Read this in English | 日本語 | 한국어 | Русский | Français. All translations have been provided by the project itself. To translate this project to arbitrary language with GPT, read and run `multi_language.py` (experimental).  

Note

1.本项目中每个文件的功能都在自译解报告`self_analysis.md`详细说明。随着版本的迭代，您也可以随时自行点击相关函数插件，调用GPT重新生成项目的自我解析报告。常见问题请查阅wiki。

2.本项目兼容并鼓励尝试国内中文大语言基座模型如通义千问，智谱GLM等。支持多个api-key共存，可在配置文件中填写如`API_KEY="openai-key1,openai-key2,azure-key3,api2d-key4"`。需要临时更换`API_KEY`时，在输入区输入临时的`API_KEY`然后回车键提交即可生效。

  
  

功能（⭐= 近期新增功能）

描述

⭐接入新模型

百度千帆与文心一言, 通义千问Qwen，上海AI-Lab书生，讯飞星火，LLaMa2，智谱GLM4，DALLE3, DeepseekCoder

⭐支持mermaid图像渲染

支持让GPT生成流程图、状态转移图、甘特图、饼状图、GitGraph等等（3.7版本）

⭐Arxiv论文精细翻译 (Docker)

\[插件\] 一键以超高质量翻译arxiv论文，目前最好的论文翻译工具

⭐实时语音对话输入

\[插件\] 异步监听音频，自动断句，自动寻找回答时机

⭐虚空终端插件

\[插件\] 能够使用自然语言直接调度本项目其他插件

润色、翻译、代码解释

一键润色、翻译、查找论文语法错误、解释代码

自定义快捷键

支持自定义快捷键

模块化设计

支持自定义强大的插件，插件支持热更新

程序剖析

\[插件\] 一键剖析Python/C/C++/Java/Lua/...项目树 或 自我剖析

读论文、翻译论文

\[插件\] 一键解读latex/pdf论文全文并生成摘要

Latex全文翻译、润色

\[插件\] 一键翻译或润色latex论文

批量注释生成

\[插件\] 一键批量生成函数注释

Markdown中英互译

\[插件\] 看到上面5种语言的README了吗？就是出自他的手笔

PDF论文全文翻译功能

\[插件\] PDF论文提取题目&摘要+翻译全文（多线程）

Arxiv小助手

\[插件\] 输入arxiv文章url即可一键翻译摘要+下载PDF

Latex论文一键校对

\[插件\] 仿Grammarly对Latex文章进行语法、拼写纠错+输出对照PDF

谷歌学术统合小助手

\[插件\] 给定任意谷歌学术搜索页面URL，让gpt帮你写relatedworks

互联网信息聚合+GPT

\[插件\] 一键让GPT从互联网获取信息回答问题，让信息永不过时

公式/图片/表格显示

可以同时显示公式的tex形式和渲染形式，支持公式、代码高亮

启动暗色主题

在浏览器url后面添加`/?__theme=dark`可以切换dark主题

多LLM模型支持

同时被GPT3.5、GPT4、清华ChatGLM2、复旦MOSS伺候的感觉一定会很不错吧？

更多LLM模型接入，支持huggingface部署

加入Newbing接口(新必应)，引入清华Jittorllms支持LLaMA和盘古α

⭐void-terminal pip包

脱离GUI，在Python中直接调用本项目的所有函数插件（开发中）

更多新功能展示 (图像生成等) ……

见本文档结尾处 ……

-   新界面（修改`config.py`中的LAYOUT选项即可实现“左右布局”和“上下布局”的切换）

-   所有按钮都通过读取functional.py动态生成，可随意加自定义功能，解放剪贴板

-   润色/纠错

-   如果输出包含公式，会以tex形式和渲染形式同时显示，方便复制和阅读

-   懒得看项目代码？直接把整个工程炫ChatGPT嘴里

-   多种大语言模型混合调用（ChatGLM + OpenAI-GPT3.5 + GPT4）

  
  

Installation
============

flowchart TD
    A{"安装方法"} --> W1("I 🔑直接运行 (Windows, Linux or MacOS)")
    W1 --> W11\["1 Python pip包管理依赖"\]
    W1 --> W12\["2 Anaconda包管理依赖（推荐⭐）"\]

    A --> W2\["II 🐳使用Docker (Windows, Linux or MacOS)"\]

    W2 --> k1\["1 部署项目全部能力的大镜像（推荐⭐）"\]
    W2 --> k2\["2 仅在线模型（GPT, GLM4等）镜像"\]
    W2 --> k3\["3 在线模型 + Latex的大镜像"\]

    A --> W4\["IV 🚀其他部署方法"\]
    W4 --> C1\["1 Windows/MacOS 一键安装运行脚本（推荐⭐）"\]
    W4 --> C2\["2 Huggingface, Sealos远程部署"\]
    W4 --> C4\["3 其他 ..."\]

Loading

### 安装方法I：直接运行 (Windows, Linux or MacOS)

1.  下载项目
    
    git clone --depth=1 https://github.com/binary-husky/gpt\_academic.git
    cd gpt\_academic
    
2.  配置API\_KEY等变量
    
    在`config.py`中，配置API KEY等变量。特殊网络环境设置方法、Wiki-项目配置说明。
    
    「 程序会优先检查是否存在名为`config_private.py`的私密配置文件，并用其中的配置覆盖`config.py`的同名配置。如您能理解以上读取逻辑，我们强烈建议您在`config.py`同路径下创建一个名为`config_private.py`的新配置文件，并使用`config_private.py`配置项目，从而确保自动更新时不会丢失配置 」。
    
    「 支持通过`环境变量`配置项目，环境变量的书写格式参考`docker-compose.yml`文件或者我们的Wiki页面。配置读取优先级: `环境变量` > `config_private.py` > `config.py` 」。
    
3.  安装依赖
    
    # （选择I: 如熟悉python, python推荐版本 3.9 ~ 3.11）备注：使用官方pip源或者阿里pip源, 临时换源方法：python -m pip install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/
    python -m pip install -r requirements.txt
    
    # （选择II: 使用Anaconda）步骤也是类似的 (https://www.bilibili.com/video/BV1rc411W7Dr)：
    conda create -n gptac\_venv python=3.11    # 创建anaconda环境
    conda activate gptac\_venv                 # 激活anaconda环境
    python -m pip install -r requirements.txt # 这个步骤和pip安装一样的步骤
    
    # （选择III: 使用uv）：
    uv venv --python=3.11   # 创建虚拟环境
    source ./.venv/bin/activate # 激活虚拟环境
    uv pip install --verbose -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/ # 安装依赖
    

如果需要支持清华ChatGLM系列/复旦MOSS/RWKV作为后端，请点击展开此处

【可选步骤】如果需要支持清华ChatGLM系列/复旦MOSS作为后端，需要额外安装更多依赖（前提条件：熟悉Python + 用过Pytorch + 电脑配置够强）：

# 【可选步骤I】支持清华ChatGLM3。清华ChatGLM备注：如果遇到"Call ChatGLM fail 不能正常加载ChatGLM的参数" 错误，参考如下： 1：以上默认安装的为torch+cpu版，使用cuda需要卸载torch重新安装torch+cuda； 2：如因本机配置不够无法加载模型，可以修改request\_llm/bridge\_chatglm.py中的模型精度, 将 AutoTokenizer.from\_pretrained("THUDM/chatglm-6b", trust\_remote\_code=True) 都修改为 AutoTokenizer.from\_pretrained("THUDM/chatglm-6b-int4", trust\_remote\_code=True)
python -m pip install -r request\_llms/requirements\_chatglm.txt

# 【可选步骤II】支持清华ChatGLM4 注意：此模型至少需要24G显存
python -m pip install -r request\_llms/requirements\_chatglm4.txt
# 可使用modelscope下载ChatGLM4模型
# pip install modelscope
# modelscope download --model ZhipuAI/glm-4-9b-chat --local\_dir ./THUDM/glm-4-9b-chat

# 【可选步骤III】支持复旦MOSS
python -m pip install -r request\_llms/requirements\_moss.txt
git clone --depth=1 https://github.com/OpenLMLab/MOSS.git request\_llms/moss  # 注意执行此行代码时，必须处于项目根路径

# 【可选步骤IV】支持RWKV Runner
参考wiki：https://github.com/binary-husky/gpt\_academic/wiki/%E9%80%82%E9%85%8DRWKV-Runner

# 【可选步骤V】确保config.py配置文件的AVAIL\_LLM\_MODELS包含了期望的模型，目前支持的全部模型如下(jittorllms系列目前仅支持docker方案)：
AVAIL\_LLM\_MODELS = \["gpt-3.5-turbo", "api2d-gpt-3.5-turbo", "gpt-4", "api2d-gpt-4", "chatglm", "moss"\] # + \["jittorllms\_rwkv", "jittorllms\_pangualpha", "jittorllms\_llama"\]

# 【可选步骤VI】支持本地模型INT8,INT4量化（这里所指的模型本身不是量化版本，目前deepseek-coder支持，后面测试后会加入更多模型量化选择）
pip install bitsandbyte
# windows用户安装bitsandbytes需要使用下面bitsandbytes-windows-webui
python -m pip install bitsandbytes --prefer-binary --extra-index-url=https://jllllll.github.io/bitsandbytes-windows-webui
pip install -U git+https://github.com/huggingface/transformers.git
pip install -U git+https://github.com/huggingface/accelerate.git
pip install peft

1.  运行
    
    python main.py
    

### 安装方法II：使用Docker

1.  部署项目的全部能力（这个是包含cuda和latex的大型镜像。但如果您网速慢、硬盘小，则不推荐该方法部署完整项目）
    
    # 修改docker-compose.yml，保留方案0并删除其他方案。然后运行：
    docker-compose up
    
2.  仅ChatGPT + GLM4 + 文心一言+spark等在线模型（推荐大多数人选择）
    
    # 修改docker-compose.yml，保留方案1并删除其他方案。然后运行：
    docker-compose up
    

P.S. 如果需要依赖Latex的插件功能，请见Wiki。另外，您也可以直接使用方案4或者方案0获取Latex功能。

1.  ChatGPT + GLM3 + MOSS + LLAMA2 + 通义千问（需要熟悉Nvidia Docker运行时）
    
    # 修改docker-compose.yml，保留方案2并删除其他方案。然后运行：
    docker-compose up
    

### 安装方法III：其他部署方法

1.  **Windows一键运行脚本**。 完全不熟悉python环境的Windows用户可以下载Release中发布的一键运行脚本安装无本地模型的版本。脚本贡献来源：oobabooga。
    
2.  使用第三方API、Azure等、文心一言、星火等，见Wiki页面
    
3.  云服务器远程部署避坑指南。 请访问云服务器远程部署wiki
    
4.  在其他平台部署&二级网址部署
    
    -   使用Sealos一键部署。
    -   使用WSL2（Windows Subsystem for Linux 子系统）。请访问部署wiki-2
    -   如何在二级网址（如`http://localhost/subpath`）下运行。请访问FastAPI运行说明

  
  

Advanced Usage
==============

### I：自定义新的便捷按钮（学术快捷键）

现在已可以通过UI中的`界面外观`菜单中的`自定义菜单`添加新的便捷按钮。如果需要在代码中定义，请使用任意文本编辑器打开`core_functional.py`，添加如下条目即可：

"超级英译中": {
    \# 前缀，会被加在你的输入之前。例如，用来描述你的要求，例如翻译、解释代码、润色等等
    "Prefix": "请翻译把下面一段内容成中文，然后用一个markdown表格逐一解释文中出现的专有名词：\\n\\n",

    \# 后缀，会被加在你的输入之后。例如，配合前缀可以把你的输入内容用引号圈起来。
    "Suffix": "",
},

### II：自定义函数插件

编写强大的函数插件来执行任何你想得到的和想不到的任务。 本项目的插件编写、调试难度很低，只要您具备一定的python基础知识，就可以仿照我们提供的模板实现自己的插件功能。 详情请参考函数插件指南。

  
  

Updates
=======

### I：动态

1.  对话保存功能。在函数插件区调用 `保存当前的对话` 即可将当前对话保存为可读+可复原的html文件， 另外在函数插件区（下拉菜单）调用 `载入对话历史存档` ，即可还原之前的会话。 Tip：不指定文件直接点击 `载入对话历史存档` 可以查看历史html存档缓存。

1.  ⭐Latex/Arxiv论文翻译功能⭐

\===>

1.  虚空终端（从自然语言输入中，理解用户意图+自动调用其他插件）

-   步骤一：输入 “ 请调用插件翻译PDF论文，地址为https://openreview.net/pdf?id=rJl0r3R9KX ”
-   步骤二：点击“虚空终端”

1.  模块化功能设计，简单的接口却能支持强大的功能

1.  译解其他开源项目

1.  装饰live2d的小功能（默认关闭，需要修改`config.py`）

1.  OpenAI图像生成

1.  基于mermaid的流图、脑图绘制

1.  Latex全文校对纠错

\===>

1.  语言、主题切换

### II：版本:

-   version 3.80(TODO): 优化AutoGen插件主题并设计一系列衍生插件
-   version 3.70: 引入Mermaid绘图，实现GPT画脑图等功能
-   version 3.60: 引入AutoGen作为新一代插件的基石
-   version 3.57: 支持GLM3，星火v3，文心一言v4，修复本地模型的并发BUG
-   version 3.56: 支持动态追加基础功能按钮，新汇报PDF汇总页面
-   version 3.55: 重构前端界面，引入悬浮窗口与菜单栏
-   version 3.54: 新增动态代码解释器（Code Interpreter）（待完善）
-   version 3.53: 支持动态选择不同界面主题，提高稳定性&解决多用户冲突问题
-   version 3.50: 使用自然语言调用本项目的所有函数插件（虚空终端），支持插件分类，改进UI，设计新主题
-   version 3.49: 支持百度千帆平台和文心一言
-   version 3.48: 支持阿里达摩院通义千问，上海AI-Lab书生，讯飞星火
-   version 3.46: 支持完全脱手操作的实时语音对话
-   version 3.45: 支持自定义ChatGLM2微调模型
-   version 3.44: 正式支持Azure，优化界面易用性
-   version 3.4: +arxiv论文翻译、latex论文批改功能
-   version 3.3: +互联网信息综合功能
-   version 3.2: 函数插件支持更多参数接口 (保存对话功能, 解读任意语言代码+同时询问任意的LLM组合)
-   version 3.1: 支持同时问询多个gpt模型！支持api2d，支持多个apikey负载均衡
-   version 3.0: 对chatglm和其他小型llm的支持
-   version 2.6: 重构了插件结构，提高了交互性，加入更多插件
-   version 2.5: 自更新，解决总结大工程源代码时文本过长、token溢出的问题
-   version 2.4: 新增PDF全文翻译功能; 新增输入区切换位置的功能
-   version 2.3: 增强多线程交互性
-   version 2.2: 函数插件支持热重载
-   version 2.1: 可折叠式布局
-   version 2.0: 引入模块化函数插件
-   version 1.0: 基础功能

GPT Academic开发者QQ群：`610599535`

-   已知问题
    -   某些浏览器翻译插件干扰此软件前端的运行
    -   官方Gradio目前有很多兼容性问题，请**务必使用`requirement.txt`安装Gradio**

timeline LR
    title GPT-Academic项目发展历程
    section 2.x
        1.0~2.2: 基础功能: 引入模块化函数插件: 可折叠式布局: 函数插件支持热重载
        2.3~2.5: 增强多线程交互性: 新增PDF全文翻译功能: 新增输入区切换位置的功能: 自更新
        2.6: 重构了插件结构: 提高了交互性: 加入更多插件
    section 3.x
        3.0~3.1: 对chatglm支持: 对其他小型llm支持: 支持同时问询多个gpt模型: 支持多个apikey负载均衡
        3.2~3.3: 函数插件支持更多参数接口: 保存对话功能: 解读任意语言代码: 同时询问任意的LLM组合: 互联网信息综合功能
        3.4: 加入arxiv论文翻译: 加入latex论文批改功能
        3.44: 正式支持Azure: 优化界面易用性
        3.46: 自定义ChatGLM2微调模型: 实时语音对话
        3.49: 支持阿里达摩院通义千问: 上海AI-Lab书生: 讯飞星火: 支持百度千帆平台 & 文心一言
        3.50: 虚空终端: 支持插件分类: 改进UI: 设计新主题
        3.53: 动态选择不同界面主题: 提高稳定性: 解决多用户冲突问题
        3.55: 动态代码解释器: 重构前端界面: 引入悬浮窗口与菜单栏
        3.56: 动态追加基础功能按钮: 新汇报PDF汇总页面
        3.57: GLM3, 星火v3: 支持文心一言v4: 修复本地模型的并发BUG
        3.60: 引入AutoGen
        3.70: 引入Mermaid绘图: 实现GPT画脑图等功能
        3.80(TODO): 优化AutoGen插件主题: 设计衍生插件

Loading

### III：主题

可以通过修改`THEME`选项（config.py）变更主题

1.  `Chuanhu-Small-and-Beautiful` 网址

### IV：本项目的开发分支

1.  `master` 分支: 主分支，稳定版
2.  `frontier` 分支: 开发分支，测试版
3.  如何接入其他大模型

### V：参考与学习

```
代码中参考了很多其他优秀项目中的设计，顺序不分先后：

# 清华ChatGLM2-6B:
https://github.com/THUDM/ChatGLM2-6B

# 清华JittorLLMs:
https://github.com/Jittor/JittorLLMs

# ChatPaper:
https://github.com/kaixindelele/ChatPaper

# Edge-GPT:
https://github.com/acheong08/EdgeGPT

# ChuanhuChatGPT:
https://github.com/GaiZhenbiao/ChuanhuChatGPT

# Oobabooga one-click installer:
https://github.com/oobabooga/one-click-installers

# More：
https://github.com/gradio-app/gradio
https://github.com/fghrsh/live2d_demo
```
