---
project: SwanLab
stars: 2853
description: ⚡️SwanLab - an open-source, modern-design AI training tracking and visualization tool. Supports Cloud / Self-hosted use. Integrated with PyTorch / Transformers / LLaMA Factory / veRL/ Swift / Ultralytics / MMEngine / Keras etc.
url: https://github.com/SwanHubX/SwanLab
---

一个开源、现代化设计的深度学习训练跟踪与可视化工具  
同时支持云端/离线使用，适配30+主流框架，与你的实验代码轻松集成

🔥SwanLab 在线版 · 📃 文档 · 报告问题 · 建议反馈 · 更新日志 · 基线社区

  

中文 / English / 日本語 / Русский

👋 加入我们的微信群

  

目录
--

-   🌟 最近更新
-   👋🏻 什么是SwanLab
-   📃 在线演示
-   🏁 快速开始
-   💻 自托管
-   🔥 实战案例
-   🎮 硬件记录
-   🚗 框架集成
-   🔌 插件与API
-   🆚 与熟悉的工具的比较
-   👥 社区
-   📃 协议

  

🌟 最近更新
-------

-   2025.10.15：📊折线图配置支持**X轴数据源选择**；侧边栏支持显示表格视图中Pin的列，增强实验数据对齐能力；
    
-   2025.09.22：📊全新UI上线；表格视图支持全局排序和筛选；数据层面统一表格视图与图表视图；
    
-   2025.09.12：🔢支持创建**标量图**，灵活显示实验指标的统计值；组织管理页面大升级，提供更强大的权限控制与项目管理能力；
    
-   2025.08.19：🤔更强大的图表渲染性能与低侵入式加载动画，让研究者更聚焦于实验分析本身；集成优秀的MLX-LM、SpecForge框架，提供更多场景的训练体验；
    
-   2025.08.06：👥**训练轻协作**上线，支持邀请项目协作者，分享项目链接与二维码；工作区支持列表视图，支持显示项目Tags；
    
-   2025.07.29：🚀侧边栏支持**实验筛选、排序**；📊表格视图上线**列控制面板**，能够方便地实现列的隐藏与显示；🔐**多API Key**管理上线，让你的数据更安全；swanlab sync提高了对日志文件完整性的兼容，适配训练崩溃等场景；新图表-PR曲线、ROC曲线、混淆矩阵上线，文档；
    
-   2025.07.17：📊更强大的**折线图配置**，支持灵活配置线型、颜色、粗细、网格、图例位置等；📹支持**swanlab.Video**数据类型，支持记录与可视化GIF格式文件；全局图表仪表盘支持配置Y轴与最大显示实验数；
    
-   2025.07.10：📚更强大的**文本视图**，支持Markdown渲染与方向键切换，可由`swanlab.echarts.table`与`swanlab.Text`创建，Demo
    
-   2025.07.06：🚄支持**resume断点续训**；新插件**文件记录器**；集成ray框架，文档；集成ROLL框架，感谢@PanAndy，文档
    

完整更新日志

-   2025.06.27：📊支持**小折线图局部放大**；支持配置**单个折线图平滑**；大幅改进了图像图表放大后的交互效果；
    
-   2025.06.20：🤗集成accelerate框架，PR，文档，增强分布式训练中的实验记录体验；
    
-   2025.06.18：🐜集成AREAL框架，感谢@xichengpro，PR，文档；🖱支持鼠标Hover到侧边栏实验时，高亮相应曲线；支持跨组对比折线图；支持设置实验名裁剪规则；
    
-   2025.06.11：📊支持 **swanlab.echarts.table** 数据类型，支持纯文本图表展示；支持对分组进行**拉伸交互**，以增大同时显示的图表数量；表格视图增加 **指标最大/最小值** 选项；
    
-   2025.06.08：♻️支持在本地存储完整的实验日志文件，通过 **swanlab sync** 上传本地日志文件到云端/私有化部署端；硬件监控支持**海光DCU**；
    
-   2025.06.01：🏸支持**图表自由拖拽**；支持**ECharts自定义图表**，增加包括柱状图、饼状图、直方图在内的20+图表类型；硬件监控支持**沐曦GPU**；集成 **PaddleNLP** 框架；
    
-   2025.05.25：日志支持记录**标准错误流**，PyTorch Lightning等框架的打印信息可以被更好地记录；硬件监控支持**摩尔线程**；新增运行命令记录安全防护功能，API Key将被自动隐藏；
    
-   2025.05.14：支持**实验Tag**；支持折线图**Log Scale**；支持**分组拖拽**；大幅度优化了大量指标上传的体验；增加`swanlab.OpenApi`开放接口；
    
-   2025.05.09：支持**折线图创建**；配置图表功能增加**数据源选择**功能，支持单张图表显示不同的指标；支持生成**训练项目GitHub徽章**；
    
-   2025.04.23：支持折线图**编辑**，支持自由配置图表的X、Y轴数据范围和标题样式；图表搜索支持**正则表达式**；支持**昆仑芯XPU**的硬件检测与监控；
    
-   2025.04.11：支持折线图**局部区域选取**；支持全局选择仪表盘折线图的step范围；支持一键隐藏全部图表；
    
-   2025.04.08：支持**swanlab.Molecule**数据类型，支持记录与可视化生物化学分子数据；支持保存表格视图中的排序、筛选、列顺序变化状态；
    
-   2025.04.07：我们与 EvalScope 完成了联合集成，现在你可以在EvalScope中使用SwanLab来**评估大模型性能**；
    
-   2025.03.30：支持**swanlab.Settings**方法，支持更精细化的实验行为控制；支持**寒武纪MLU**硬件监控；支持 Slack通知、Discord通知；
    
-   2025.03.21：🎉🤗HuggingFace Transformers已正式集成SwanLab（>=4.50.0版本），#36433；新增 **Object3D图表** ，支持记录与可视化三维点云，文档；硬件监控支持了 GPU显存（MB）、磁盘利用率、网络上下行 的记录；
    
-   2025.03.12：🎉🎉SwanLab**私有化部署版**现已发布！！🔗部署文档；SwanLab 已支持插件扩展，如 邮件通知、飞书通知
    
-   2025.03.09：支持**实验侧边栏拉宽**；新增外显 Git代码 按钮；新增 **sync\_mlflow** 功能，支持与mlflow框架同步实验跟踪；
    
-   2025.03.06：我们与 DiffSynth Studio 完成了联合集成，现在你可以在DiffSynth Studio中使用SwanLab来**跟踪和可视化Diffusion模型文生图/视频实验**，使用指引；
    
-   2025.03.04：新增 **MLFlow转换** 功能，支持将MLFlow实验转换为SwanLab实验，使用指引；
    
-   2025.03.01：新增 **移动实验** 功能，现在可以将实验移动到不同组织的不同项目下了；
    
-   2025.02.24：我们与 EasyR1 完成了联合集成，现在你可以在EasyR1中使用SwanLab来**跟踪和可视化多模态大模型强化学习实验**，使用指引
    
-   2025.02.18：我们与 Swift 完成了联合集成，现在你可以在Swift的CLI/WebUI中使用SwanLab来**跟踪和可视化大模型微调实验**，使用指引。
    
-   2025.02.16：新增 **图表移动分组、创建分组** 功能。
    
-   2025.02.09：我们与 veRL 完成了联合集成，现在你可以在veRL中使用SwanLab来**跟踪和可视化大模型强化学习实验**，使用指引。
    
-   2025.02.05：`swanlab.log`支持嵌套字典 #812，适配Jax框架特性；支持`name`与`notes`参数；
    
-   2025.01.22：新增`sync_tensorboardX`与`sync_tensorboard_torch`功能，支持与此两种TensorBoard框架同步实验跟踪；
    
-   2025.01.17：新增`sync_wandb`功能，文档，支持与Weights & Biases实验跟踪同步；大幅改进了日志渲染性能
    
-   2025.01.11：云端版大幅优化了项目表格的性能，并支持拖拽、排序、筛选等交互
    
-   2025.01.01：新增折线图**持久化平滑**、折线图拖拽式改变大小，优化图表浏览体验
    
-   2024.12.22：我们与 LLaMA Factory 完成了联合集成，现在你可以在LLaMA Factory中使用SwanLab来**跟踪和可视化大模型微调实验**，使用指引。
    
-   2024.12.15：**硬件监控（0.4.0）** 功能上线，支持CPU、NPU（Ascend）、GPU（Nvidia）的系统级信息记录与监控。
    
-   2024.12.06：新增对LightGBM、XGBoost的集成；提高了对日志记录单行长度的限制。
    
-   2024.11.26：环境选项卡-硬件部分支持识别**华为昇腾NPU**与**鲲鹏CPU**；云厂商部分支持识别青云**基石智算**。
    

  

👋🏻 什么是SwanLab
---------------

SwanLab 是一款开源、轻量的 AI 模型训练跟踪与可视化工具，提供了一个跟踪、记录、比较、和协作实验的平台。

SwanLab 面向人工智能研究者，设计了友好的Python API 和漂亮的UI界面，并提供**训练可视化、自动日志记录、超参数记录、实验对比、多人协同**等功能。在SwanLab上，研究者能基于直观的可视化图表发现训练问题，对比多个实验找到研究灵感，并通过**在线网页**的分享与基于组织的**多人协同训练**，打破团队沟通的壁垒，提高组织训练效率。

swanlab-demo.mp4

以下是其核心特性列表：

**1\. 📊 实验指标与超参数跟踪**: 极简的代码嵌入您的机器学习 pipeline，跟踪记录训练关键指标

-   ☁️ 支持**云端**使用（类似Weights & Biases），随时随地查看训练进展。手机看实验的方法
    
-   📝 支持**超参数记录**、**指标总结**、**表格分析**
    
-   🌸 **可视化训练过程**: 通过UI界面对实验跟踪数据进行可视化，可以让训练师直观地看到实验每一步的结果，分析指标走势，判断哪些变化导致了模型效果的提升，从而整体性地提升模型迭代效率。
    
-   **支持的元数据类型**：标量指标、图像、音频、文本、视频、3D点云、生物化学分子、Echarts自定义图表...
    

-   **支持的图表类型**：折线图、媒体图（图像、音频、文本、视频）、3D点云、生物化学分子、柱状图、散点图、箱线图、热力图、饼状图、雷达图、自定义图表...

-   **LLM生成内容可视化组件**：为大语言模型训练场景打造的文本内容可视化图表，支持Markdown渲染

-   **后台自动记录**：日志logging、硬件环境、Git 仓库、Python 环境、Python 库列表、项目运行目录
    
-   **断点续训记录**：支持在训练完成/中断后，补充新的指标数据到同个实验中
    

**2\. ⚡️ 全面的框架集成**: PyTorch、🤗HuggingFace Transformers、PyTorch Lightning、🦙LLaMA Factory、MMDetection、Ultralytics、PaddleDetetion、LightGBM、XGBoost、Keras、Tensorboard、Weights&Biases、OpenAI、Swift、XTuner、Stable Baseline3、Hydra 在内的 **30+** 框架

**3\. 💻 硬件监控**: 支持实时记录与监控CPU、NPU（**昇腾Ascend**）、GPU（**英伟达Nvidia**）、MLU（**寒武纪Cambricon**）、XLU（**昆仑芯Kunlunxin**）、DCU（**海光DCU**）、MetaX GPU（**沐曦XPU**）、Moore Threads GPU（**摩尔线程**）、内存的系统级硬件指标

**4\. 📦 实验管理**: 通过专为训练场景设计的集中式仪表板，通过整体视图速览全局，快速管理多个项目与实验

**5\. 🆚 比较结果**: 通过在线表格与对比图表比较不同实验的超参数和结果，挖掘迭代灵感

**6\. 👥 在线协作**: 您可以与团队进行协作式训练，支持将实验实时同步在一个项目下，您可以在线查看团队的训练记录，基于结果发表看法与建议

**7\. ✉️ 分享结果**: 复制和发送持久的 URL 来共享每个实验，方便地发送给伙伴，或嵌入到在线笔记中

**8\. 💻 支持自托管**: 支持离线环境使用，自托管的社区版同样可以查看仪表盘与管理实验，使用攻略

**9\. 🔌 插件拓展**: 支持通过插件拓展SwanLab的使用场景，比如 飞书通知、Slack通知、CSV记录器等

Important

**收藏项目**，你将从 GitHub 上无延迟地接收所有发布通知～ ⭐️

  

📃 在线演示
-------

来看看 SwanLab 的在线演示：

ResNet50 猫狗分类

Yolov8-COCO128 目标检测

跟踪一个简单的 ResNet50 模型在猫狗数据集上训练的图像分类任务。

使用 Yolov8 在 COCO128 数据集上进行目标检测任务，跟踪训练超参数和指标。

Qwen2 指令微调

LSTM Google 股票预测

跟踪 Qwen2 大语言模型的指令微调训练，完成简单的指令遵循。

使用简单的 LSTM 模型在 Google 股价数据集上训练，实现对未来股价的预测。

ResNeXt101 音频分类

Qwen2-VL COCO数据集微调

从ResNet到ResNeXt在音频分类任务上的渐进式实验过程

基于Qwen2-VL多模态大模型，在COCO2014数据集上进行Lora微调。

EasyR1 多模态LLM RL训练

Qwen2.5-0.5B GRPO训练

使用EasyR1框架进行多模态LLM RL训练

基于Qwen2.5-0.5B模型在GSM8k数据集上进行GRPO训练

更多案例

  

🏁 快速开始
-------

### 1.安装

pip install swanlab

源码安装

如果你想体验最新的特性，可以使用源码安装。

# 方式一
git clone https://github.com/SwanHubX/SwanLab.git
pip install -e .

# 方式二
pip install git+https://github.com/SwanHubX/SwanLab.git

离线看板拓展安装

离线看板文档

pip install 'swanlab\[dashboard\]'

### 2.登录并获取 API Key

1.  免费注册账号
    
2.  登录账号，在用户设置 > API Key 里复制您的 API Key
    
3.  打开终端，输入：
    

swanlab login

出现提示时，输入您的 API Key，按下回车，完成登陆。

### 3.将 SwanLab 与你的代码集成

import swanlab

\# 初始化一个新的swanlab实验
swanlab.init(
    project\="my-first-ml",
    config\={'learning-rate': 0.003},
)

\# 记录指标
for i in range(10):
    swanlab.log({"loss": i, "acc": i})

大功告成！前往SwanLab查看你的第一个 SwanLab 实验。

  

💻 自托管
------

自托管社区版支持离线查看 SwanLab 仪表盘。

### 1\. 使用Docker部署自托管版本

详情请参考：文档

git clone https://github.com/SwanHubX/self-hosted.git
cd self-hosted/docker

中国地区快速安装：

./install.sh

从DockerHub拉取镜像安装：

./install-dockerhub.sh

### 2\. 将实验指定到自托管服务

登录到自托管服务：

swanlab login --host http://localhost:8000

完成登录后，即可将实验记录到自托管服务。

  

🔥 实战案例
-------

**使用SwanLab的优秀教程开源项目：**

-   happy-llm：从零开始的大语言模型原理与实践教程
-   self-llm：《开源大模型食用指南》针对中国宝宝量身打造的基于Linux环境快速微调（全参数/Lora）、部署国内外开源大模型（LLM）/多模态大模型（MLLM）教程
-   unlock-deepseek：DeepSeek 系列工作解读、扩展和复现
-   Qwen3-SmVL: 将SmolVLM2的视觉头与Qwen3-0.6B模型进行了拼接微调
-   OPPO/Agent\_Foundation\_Models: 通过多Agent蒸馏和Agent RL的端到端Agent基础模型。

**使用SwanLab的优秀论文：**

-   Animation Needs Attention: A Holistic Approach to Slides Animation Comprehension with Visual-Language Models
-   Efficient Model Fine-Tuning with LoRA for Biomedical Named Entity Recognition
-   SpectrumWorld: Artificial Intelligence Foundation for Spectroscopy
-   CodeBoost: Boosting Code LLMs by Squeezing Knowledge from Code Snippets with RL

**教程文章：**

-   MNIST手写体识别
-   FashionMNIST服装分类
-   Cifar10图像分类
-   Resnet猫狗分类
-   Yolo目标检测
-   UNet医学影像分割
-   音频分类
-   DQN强化学习-推车倒立摆
-   LSTM Google股票预测
-   BERT文本分类
-   Stable Diffusion文生图微调
-   LLM预训练
-   GLM4指令微调
-   Qwen下游任务训练
-   NER命名实体识别
-   Qwen3医学模型微调
-   Qwen2-VL多模态大模型微调实战
-   GRPO大模型强化学习
-   Qwen3-SmVL-0.6B多模态模型训练
-   LeRobot 具身智能入门
-   GLM-4.5-Air-LoRA 及 SwanLab 可视化记录
-   RAG怎么做？SwanLab文档助手方案开源了

🌟如果你有想收录的教程，欢迎提交PR！

  

🎮 硬件记录
-------

SwanLab会对AI训练过程中所使用的**硬件信息**和**资源使用情况**进行记录，下面是支持情况表格：

硬件

信息记录

资源监控

脚本

英伟达GPU

✅

✅

nvidia.py

昇腾NPU

✅

✅

ascend.py

苹果SOC

✅

✅

apple.py

寒武纪MLU

✅

✅

cambricon.py

昆仑芯XPU

✅

✅

kunlunxin.py

摩尔线程GPU

✅

✅

moorethreads.py

沐曦GPU

✅

✅

metax.py

海光DCU

✅

✅

hygon.py

CPU

✅

✅

cpu.py

内存

✅

✅

memory.py

硬盘

✅

✅

disk.py

网络

✅

✅

network.py

如果你希望记录其他硬件，欢迎提交Issue与PR！

  

🚗 框架集成
-------

将你最喜欢的框架与 SwanLab 结合使用！  
下面是我们已集成的框架列表，欢迎提交 Issue 来反馈你想要集成的框架。

**基础框架**

-   PyTorch
-   MindSpore
-   Keras

**专有/微调框架**

-   PyTorch Lightning
-   HuggingFace Transformers
-   LLaMA Factory
-   Modelscope Swift
-   DiffSynth Studio
-   Sentence Transformers
-   PaddleNLP
-   OpenMind
-   Torchtune
-   XTuner
-   MMEngine
-   FastAI
-   LightGBM
-   XGBoost
-   MLX-LM

**评估框架**

-   EvalScope

**计算机视觉**

-   Ultralytics
-   MMDetection
-   MMSegmentation
-   PaddleDetection
-   PaddleYOLO

**强化学习**

-   Stable Baseline3
-   veRL
-   HuggingFace trl
-   EasyR1
-   AReaL
-   ROLL

**其他框架：**

-   Tensorboard
-   Weights&Biases
-   MLFlow
-   HuggingFace Accelerate
-   Ray
-   Unsloth
-   Hydra
-   Omegaconf
-   OpenAI
-   ZhipuAI

更多集成

  

🔌 插件与API
---------

欢迎通过插件来拓展SwanLab的功能，增强你的实验管理体验！

-   自定义你的插件
-   邮件通知
-   飞书通知
-   钉钉通知
-   企业微信通知
-   Discord通知
-   Slack通知
-   CSV记录器
-   文件记录器

开放接口：

-   OpenAPI

  

🆚 与熟悉的工具的比较
------------

### Tensorboard vs SwanLab

-   **☁️ 支持在线使用**： 通过 SwanLab 可以方便地将训练实验在云端在线同步与保存，便于远程查看训练进展、管理历史项目、分享实验链接、发送实时消息通知、多端看实验等。而 Tensorboard 是一个离线的实验跟踪工具。
    
-   **👥 多人协作**： 在进行多人、跨团队的机器学习协作时，通过 SwanLab 可以轻松管理多人的训练项目、分享实验链接、跨空间交流讨论。而 Tensorboard 主要为个人设计，难以进行多人协作和分享实验。
    
-   **💻 持久、集中的仪表板**： 无论你在何处训练模型，无论是在本地计算机上、在实验室集群还是在公有云的 GPU 实例中，你的结果都会记录到同一个集中式仪表板中。而使用 TensorBoard 需要花费时间从不同的机器复制和管理 TFEvent 文件。
    
-   **💪 更强大的表格**： 通过 SwanLab 表格可以查看、搜索、过滤来自不同实验的结果，可以轻松查看数千个模型版本并找到适合不同任务的最佳性能模型。 TensorBoard 不适用于大型项目。
    

### Weights and Biases vs SwanLab

-   Weights and Biases 是一个必须联网使用的闭源 MLOps 平台
    
-   SwanLab 不仅支持联网使用，也支持开源、免费、自托管的版本
    

  

👥 社区
-----

### 周边仓库

-   self-hosted：私有化部署脚本仓库
-   SwanLab-Docs：官方文档仓库
-   SwanLab-Dashboard：离线看板仓库，存放了由`swanlab watch`打开的轻量离线看板的web代码

### 社区与支持

-   GitHub Issues：使用 SwanLab 时遇到的错误和问题
-   电子邮件支持：反馈关于使用 SwanLab 的问题
-   微信交流群：交流使用 SwanLab 的问题、分享最新的 AI 技术

### SwanLab README 徽章

如果你喜欢在工作中使用 SwanLab，请将 SwanLab 徽章添加到你的 README 中：

、

```
[![](https://raw.githubusercontent.com/SwanHubX/assets/main/badge2.svg)](your experiment url)
[![](https://raw.githubusercontent.com/SwanHubX/assets/main/badge1.svg)](your experiment url)
```

更多设计素材：assets

### 在论文中引用 SwanLab

如果您发现 SwanLab 对您的研究之旅有帮助，请考虑以下列格式引用：

@software{Zeyilin\_SwanLab\_2023,
  author = {Zeyi Lin, Shaohong Chen, Kang Li, Qiushan Jiang, Zirui Cai,  Kaifang Ji and {The SwanLab team}},
  doi = {10.5281/zenodo.11100550},
  license = {Apache-2.0},
  title = {{SwanLab}},
  url = {https://github.com/swanhubx/swanlab},
  year = {2023}
}

### 为 SwanLab 做出贡献

考虑为 SwanLab 做出贡献吗？首先，请花点时间阅读 贡献指南。

同时，我们非常欢迎通过社交媒体、活动和会议的分享来支持 SwanLab，衷心感谢！

  

**Contributors**

  

📃 协议
-----

本仓库遵循 Apache 2.0 License 开源协议

Star History
------------
