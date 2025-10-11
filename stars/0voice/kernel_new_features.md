---
project: kernel_new_features
stars: 1855
description: 一个深挖 Linux 内核的新功能特性，以 io_uring, cgroup, ebpf, llvm 为代表，包含开源项目，代码案例，文章，视频，架构脑图等
url: https://github.com/0voice/kernel_new_features
---

🔰 深挖 Linux 内核的新功能特性，以 io\_uring, cgroup, ebpf, llvm 为代表，包含开源项目，代码案例，文章，视频，架构脑图等
================================================================================

所有数据来源于互联网。所谓取之于互联网，用之于互联网。

如果涉及版权侵犯，请邮件至 wchao\_isvip@163.com ，我们将第一时间处理。

如果您对我们的项目表示赞同与支持，欢迎您 lssues我们，或者邮件 wchao\_isvip@163.com 我们，更加欢迎您 pull requests 加入我们。

感谢您的支持！

🔥 io\_uring
------------

#### —— 2019 年 Linux 5.1 内核首次引入的高性能 异步 I/O 框架，能显著加速 I/O 密集型应用的性能。

### 文档

-   官方文档: Efficient I/O with io\_uring
-   其他文档：
    -   Improved Storage Performance Using the New Linux Kernel I.O Interface
    -   I/O-uring speed the RocksDB & TiKV
    -   The Evolution of File Descriptor Monitoring in Linux
    -   io\_uring-BPF
    -   Enabling Financial-Grade Secure Infrastructure with Confidential Computing
    -   Boosting Compaction in B-Tree Based Key-Value Store by Exploiting Parallel Reads in Flash SSDs
    -   Programming Emerging Storage Interfaces
    -   I/O is faster than the OS
    -   StefanMetzmacher\_sambaxp2021\_multichannel\_io-uring-rev0-presentation
    -   I/O Stack
    -   io\_uring-徐浩-阿里云

### 开源项目

-   axboe/liburing: io\_uring 库，liburing为设置和拆掉 io\_uring 实例，还有一个简化接口不需要（或不想）处理完整内核的应用程序边执行。
-   shuveb/io\_uring-by-example: 一个io\_uring 示例的库
-   bytedance/monoio: 基于io-uring的Rust异步运行时
-   spacejam/rio: Rust io\_uring库，构建在libc上，线程和异步友好，抗误用
-   Iceber/iouring-go: 提供易于使用的异步IO接口io\_uring
-   frevib/io\_uring-echo-server: io\_uring echo server
-   hodgesds/iouring-go: Io\_uring支持go
-   dshulyak/uring: 用于io\_uring框架的Golang库(无CGO)
-   quininer/ritsu: 一个实验性的基于io-uring的异步运行时。
-   shuveb/loti-examples: 源代码示例程序，从主的io\_uring指南
-   xuanyi-fu/xynet: 基于io\_uring和c++ 20协程的网络库
-   KuiBaDB/kbio: 一个基于io\_uring的异步IO框架
-   shuveb/loti: io\_uring教程，例子和参考
-   MarkReedZ/mrloop: C语言使用io\_uring的事件循环
-   tchaloupka/during: dlang io\_uring包装
-   omegacoleman/arkio: 基于异步IO的内核IO库
-   ciconia/awesome-io\_uring: 一个很棒的io\_uring资源、库和工具的分类集合。
-   ddeka0/AsyncIO: 一个用于异步套接字服务器的CPP包装器，使用linux最新的io\_uring API
-   uroni/fuseuring: 使用io\_uring实现一个用户空间Linux fuse服务器
-   yunwei37/co-uring-WebServer: 一个使用io\_uring和cpp20协同程序的c++高性能Web服务器
-   romange/helio: 一个基于io\_uring Linux接口的现代后端开发框架
-   3541/short-circuit: Linux高性能web服务器，基于io\_uring构建。
-   anolis-os-archive/perf-test-for-io\_uring: 一个用于io\_uring性能测试的框架。
-   BlazeWasHere/Cnidus: 基于io\_uring的C语言web框架。
-   AnSpake/osiris: 一个简单的服务器/客户端，使用io\_uring

### 文章

-   io\_uring 高效 IO
-   \[译\] Linux 异步 I\_O 框架 io\_uring：基本原理、程序示例与性能压测（2020）
-   浅析开源项目之io\_uring
-   io\_uring 系统性整理
-   io\_uring（1） – 我们为什么会需要 io\_uring
-   io\_uring（2）- 从创建必要的文件描述符 fd 开始
-   下一代异步 IO io\_uring 技术解密
-   小谈io\_uring
-   智汇华云-新时代IO利器-io\_uring
-   Linux 5.1 的 io\_uring
-   What is io\_uring
-   io\_uring\_setup
-   io\_uring\_enter
-   io\_uring\_register
-   The Low-level io\_uring Interface
-   Submission Queue Polling
-   Efficient IO with io\_uring

### 视频(提取码：1024)

-   Speeding Up VM’s I\_O Sharing Host's io\_uring Queues With Guests by Stefano Garzarella【2020】
-   Asynchronous I\_O and coroutines for smooth data streaming - Björn Fahller - NDC TechTown 2021
-   Guilherme Bernal - Reaching 200k req\_s on a single core with io\_uring - Crystal 1.0 Conference
-   Improved Storage Performance Using the New Linux Kernel I O Interface (SDC 2019)
-   io\_uring- BPF controlled I\_O - Pavel Begunkov
-   io\_uring in QEMU- high-performance disk I\_O for Linux
-   Kernel Recipes 2019 - Faster IO through io\_uring
-   SDC2021- Samba Multi-Channel\_io\_uring Status Update
-   Speeding Up VM’s I\_O Sharing Host's io\_uring Queues With Guests - Stefano Garzarella, Red Hat
-   USENIX ATC '19 - Asynchronous I\_O Stack\_ A Low-latency Kernel I\_O Stack for Ultra-Low Latency SSDs
-   来自阿里云的 Linux 内核 io\_uring 介绍与实践

🔥 cgroup
---------

#### —— 限制、控制与分离一个进程组的资源（如CPU、内存、磁盘输入输出等）。

### 文档

-   官方文档:
    
    -   Control Groups definition, implementation details, examples and API
    -   CPU Accounting Controller; account CPU usage for groups of tasks
    -   documents the cpusets feature; assign CPUs and Mem to a set of tasks
    -   Device Whitelist Controller; description, interface and security
    -   checkpointing; rationale to not use signals, interface
    -   Memory Resource Controller; implementation details
    -   Memory Resource Controller; design, accounting, interface, testing
    -   Resource Counter API
-   其他文档：
    
    -   cgroups介绍
    -   CgroupMemcgMaster
    -   Resource Management
    -   Challenges with the memory resource controller and its performance
    -   Ressource Management in Linux with Control Groups
    -   System Programming for Linux Containers Control Groups (cgroups)
    -   Managing Resources with cgroups
    -   5 years of cgroup v2
    -   Linux’s new unified control group system
    -   cgroups\_intro
    -   red\_hat\_enterprise\_linux-6-resource\_management\_guide-en-us
    -   An introduction to Control Groups (cgroups)
    -   Using Linux Control Groups and Systemd to Manage CPU Time and Memory
    -   An introduction to cgroups and cgroupspy

### 开源项目

-   containerd/cgroups: 用于创建、管理、检查和销毁cgroup。cgroup上设置的资源格式使用这里找到的OCI运行时规范。
-   mhausenblas/cinf: 一个查看命名空间和cgroups的命令行工具
-   flouthoc/vas-quod: 用Rust编写的一个极小的容器运行时
-   poelzi/ulatencyd: 使用cgroups最小化linux系统延迟的守护进程
-   haosdent/jcgroup: jcgroup是JVM上的cgroup包装器。您可以使用这个库来限制线程的CPU共享、磁盘I/O速度、网络带宽等。
-   kinvolk/traceloop: 使用BPF和可重写的环形缓冲区跟踪cgroup中的系统调用
-   tianon/cgroupfs-mount: 挂载cgroupfs (v1)层次结构的简单(过时)脚本，特别是用于Debian打包的结构化脚本
-   francisbouvier/cgroups: 一个库来管理cgroups Linux内核特性
-   bpowers/mstat: 这个工具运行在Linux上，利用cgroups内核API(也被Docker等容器基础设施使用)来记录一组进程随时间的内存使用情况。

### 文章

-   Linux cgroups 概述
-   【译】Control Group v2（cgroupv2 权威指南）（KernelDoc, 2021）
-   How I Used CGroups to Manage System Resources
-   Cgroups控制cpu，内存，io示例
-   Linux Control Groups V1 和 V2 原理和区别
-   Linux资源管理之cgroups简介
-   彻底搞懂容器技术的基石： cgroup
-   深入理解 Linux Cgroup 系列（一）：基本概念
-   深入理解 Linux Cgroup 系列（二）：玩转 CPU
-   深入理解 Linux Cgroup 系列（三）：内存
-   Cgroup - 从CPU资源隔离说起
-   Cgroup - Linux内存资源管理
-   Cgroup - Linux的IO资源隔离
-   Cgroup - Linux的网络资源隔离
-   用 cgroups 管理 cpu 资源
-   用 cgruops 管理进程内存占用
-   用 cgroups 管理进程磁盘 io

### 视频

-   Containers\_ cgroups, Linux kernel namespaces, ufs, Docker, and intro to Kubernetes pods\---提取码: k4hn
-   Understanding and Working with the Cgroups Interface - Michael Anderson, The PTR Group, LLC\---提取码: 54vs
-   Linux Container Primitives- cgroups, namespaces, and more!\---提取码: cjwd
-   Cgroups, namespaces, and beyond\---提取码: at6x
-   Kubernetes On Cgroup v2 - Giuseppe Scrivano, Red Hat\---提取码: 552y
-   Cgroup Slab Memory Controller and Time Namespace - DevConf.CZ 2021\---提取码: gayh
-   Modern Linux Servers with cgroups - Brandon Philips, CoreOS\---提取码: afm1
-   LISA21 - 5 Years of Cgroup v2- The Future of Linux Resource Control\---提取码: ygrv
-   Limit CPU usage on Ubuntu with Systemd cgroups\---提取码: ktva
-   What's new in control groups (cgroups) version 2\---提取码: w2tz

🔥 ebpf
-------

#### —— Linux 内核中顶级子模块

### 文档

-   官方文档:
    
    -   Linux 内核：https://www.kernel.org/doc/Documentation/networking/filter.txt and https://www.kernel.org/doc/html/latest/bpf/#
    -   开发QA: https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/bpf/bpf\_devel\_QA.rst
    -   eBPF-Helpers：https://github.com/iovisor/bpf-docs/blob/master/bpf\_helpers.rst/
-   其他文档：
    
    -   iovisor/bpf-docs: 列出了 eBPF opcode，项目是 iovisor 总结的系列文档、pre。
    -   Advanced\_BPF\_Kernel\_Features\_for\_the\_Container\_Age\_FOSDEM
    -   BPF to eBPF
    -   Calico-eBPF-Dataplane-CNCF-Webinar-Slides
    -   Combining System Visibility and Security Using eBPF
    -   DPDK+eBPF
    -   Experience and Lessons Learned
    -   Fast Packet Processing using eBPF and XDP
    -   Kernel Tracing With eBPF
    -   Kernel analysis using eBPF
    -   Making the Linux TCP stack more extensible with eBPF
    -   Performance Analysis Superpowers with Linux eBPF
    -   Performance Implications of Packet Filtering with Linux eBPF
    -   The Next Linux Superpower eBPF Primer
    -   eBPF - From a Programmer’s Perspective
    -   eBPF In-kernel Virtual Machine & Cloud Computin
    -   eBPF for perfomance analysis and networking
    -   eBPF in CPU Scheduler
    -   eBPF-based Content and Computation-aware Communication for Real-time Edge Computing

### 开源项目

-   cilium/cilium: 用于提供、保护和观察容器工作负载之间的网络连接——云原生，并由革命性的内核技术eBPF提供支持,https://cilium.io/
-   BPF Compiler Collection (BCC): BCC -基于bpf的Linux IO分析、联网、监控等工具
-   bpftrace: Linux eBPF的高级跟踪语言
-   Falco: 一种行为活动监视器，旨在检测应用程序中的异常活动。Falco在ebp的帮助下在Linux内核层对系统进行审计。它通过其他输入流(如容器运行时度量和Kubernetes度量)丰富了收集到的数据，并允许持续监视和检测容器、应用程序、主机和网络活动。
-   Katran: 高性能的四层负载均衡器
-   LLVM Compiler: 一个模块化和可重用的编译器和工具链技术的集合。
-   microsoft/ebpf-for-windows: 运行在Windows上的eBPF实现
-   aquasecurity/libbpfgo: 一个用于Linux ebbpf项目的Go库。
-   aquasecurity/tracee: Linux的运行时安全和取证工具。
-   libbpf/libbpf: libbpf是一个基于C/ c++的库，作为上游Linux内核的一部分进行维护。它包含一个eBPF加载器，它接管处理LLVM生成的eBPF ELF文件，以便将其加载到内核中。
-   libbpf/libbpf-rs: Rust生态系统的最小和固执的epf工具
-   foniod/redbpf: Rust库用于构建和运行BPF/eBPF模块
-   aya-rs/aya: 一个用于Rust编程语言的eBPF库，其构建的重点是开发人员的体验和可操作性。
-   cilium/hubble: 使用eBPF的Kubernetes网络、服务和安全可观测性
-   kubearmor/KubeArmor: 一个云本地运行时安全强制系统，它在系统级别限制容器和节点的行为(如进程执行、文件访问和网络操作)。
-   iovisor/kubectl-trace: 使用kubectl在kubernetes集群上调度bpftrace程序
-   iovisor/ply: 一款基于eBPF的Linux动态跟踪软件。

### 文章

-   什么是 eBPF
-   eBPF详解
-   BPF 和 eBPF 初探
-   Linux 内核监测技术 eBPF
-   eBPF 如何简化服务网格
-   eBPF 用户空间虚拟机实现相关
-   基于 eBPF 实现容器运行时安全
-   深入理解 Cilium 的 eBPF 收发包路径
-   eBPF 概述，第 1 部分：介绍
-   eBPF 概述，第 2 部分：机器和字节码
-   eBPF 概述，第 3 部分：软件开发生态
-   eBPF 概述，第 4 部分：在嵌入式系统运行
-   eBPF 概述，第 5 部分：跟踪用户进程
-   【译】大规模微服务利器：eBPF + KubernetesKubeCon, 2020

### 视频

-   Netflix talks about Extended BPF - A new software type\---提取码: 83sv
-   containers\_ebpf\_kernel\---提取码: hxkt

🔥 llvm
-------

#### —— 模块化、可重用的编译器以及工具链技术的集合

### 文档

-   官方文档:
    -   LLVM: A Compilation Framework for Lifelong Program Analysis & Transformation
    -   Introduction to the LLVM Compiler System
    -   LLVM语言参考手册
    -   LLVM语言参考手册-中文版
    -   入门LLVM核心库
-   用户指南：
    -   使用CMake构建LLVM: 使用CMake构建系统的主要入门指南的附录。
    -   在ARM平台上构建LLVM指南: 关于在ARM上构建和测试LLVM/Clang的注意事项。
    -   如何使用配置文件引导优化构建Clang和LLVM: 使用PGO构建LLVM/Clang的注意事项。
    -   如何为ARM平台交叉编译compiler-rt Builtins: 关于交叉构建和测试ARM的编译器-rt内置函数的注意事项。
    -   如何使用Clang/LLVM交叉编译Clang/LLVM：关于交叉构建和测试LLVM / Clang的注意事项。
    -   使用Microsoft Visual Studio开始使用LLVM系统：Windows上使用Visual Studio的主要入门指南的附录。
    -   LLVM的分析和转换Passes:LLVM中实现的优化和分析列表
    -   当前版本的发布说明:这描述了新功能，已知错误和其他限制。
    -   如何提交LLVM错误报告: 有关正确提交有关您在LLVM系统中遇到的任何错误的信息的说明。
    -   sphinx模板快速入门：使用LLVM测试基础结构的参考手册。
    -   LLVM测试套件基础结构指南：使用LLVM测试基础结构的参考手册。
    -   LLVM测试套件使用指南：描述如何编译和运行测试套件基准测试。
    -   如何构建C，C ++，ObjC和ObjC ++前端：从源代码构建clang前端的说明。
    -   LLVM词典：LLVM中使用的首字母缩略词，术语和概念的定义。
    -   如何将构建配置添加到LLVM Buildbot基础结构:有关将新构建器添加到LLVM buildbot master的说明。
    -   YAML I/O：使用LLVM的YAML I/O库的参考指南。
    -   前端作者的性能提示：前端作者关于如何生成IR的技巧的集合，LLVM能够有效地优化。
    -   Dockerfiles用于构建LLVM的指南：使用随LLVM提供的Dockerfiles的参考。
-   编程文档：
    -   LLVM扩展：LLVM特定的工具和格式扩展LLVM寻求兼容性。
    -   CommandLine 2.0库手册：提供有关使用命令行解析库的信息。
    -   LLVM编码标准：详细介绍了LLVM编码标准，并提供了有关编写高效C ++代码的有用信息。
    -   如何为类层次结构设置LLVM样式的RTTI：如何让`isa<>`，`dyn_cast<>`等可供您的类层次的客户。
    -   扩展LLVM：添加指令，内在函数，类型等：在这里查看如何向LLVM添加指令和内在函数。
    -   libFuzzer - 用于覆盖引导的模糊测试的库：用于编写进程中引导模糊器的库
    -   模糊LLVM库和工具：有关编写和使用Fuzzers查找LLVM中的错误的信息.
    -   Scudo硬化分配器：一个实现安全加固的malloc（）的库。
-   子系统文档
    -   编写LLVM Passes：有关如何编写LLVM转换和分析的信息
    -   编写LLVM后端：有关如何为机器目标编写LLVM后端的信息
    -   LLVM与目标无关的代码生成器：LLVM代码生成器的设计和实现。如果您正在将LLVM重新定位到新架构，设计新的codegen传递或增强现有组件，则非常有用。
    -   机器IR（MIR）格式参考手册：MIR序列化格式的参考手册，用于测试LLVM的代码生成过程。
    -   TableGen：描述了TableGen工具，LLVM代码生成器大量使用它。
    -   LLVM别名分析基础结构：有关如何编写新别名分析实现或如何使用现有分析的信息。
    -   MemorySSA：有关LLVM中的MemorySSA实用程序的信息，以及如何使用它。
    -   使用LLVM进行垃圾收集：接口源语言编译器应该用于编译GC程序。
    -   使用LLVM进行源级别调试：本文档描述了LLVM源代码级调试器背后的设计和理念。
    -   LLVM中的自动矢量化：本文档描述了LLVM中矢量化的当前状态
    -   LLVM中的异常处理：本文档描述了LLVM中异常处理的设计和实现
    -   如何添加一个受约束的浮点内在函数：在LLVM中添加新的约束数学内在时，提供必要的步骤。
    -   LLVM bugpoint工具：设计和使用：自动错误查找器和测试用例减少器描述和使用信息
    -   LLVM Bitcode文件格式：这描述了用于LLVM“bc”文件的文件格式和编码。
    -   支持库：本文档描述了LLVM支持库（lib/Support）以及如何使LLVM源代码可移植
    -   LLVM链接时间优化：设计和实现：本文档描述了LLVM模块间优化器与链接器及其设计之间的接口
    -   LLVM黄金插件：如何在Linux上使用链接时优化来构建程序。
    -   使用GDB调试JIT-ed代码:如何使用GDB调试JITed代码。
    -   MCJIT设计与实施：描述了MCJIT执行引擎的内部工作原理
    -   LLVM分支权重元数据：提供有关分支预测信息的信息。
    -   LLVM块频率术语:提供有关BlockFrequencyInfo 分析过程中使用的术语的信息
    -   LLVM中的分段堆栈:本文档描述了分段堆栈以及它们在LLVM中的使用方式
    -   LLVM的可选丰富的反汇编输出:本文档介绍了可选的丰富反汇编输出语法
    -   如何使用属性：回答有关新属性基础结构的一些问题。
    -   NVPTX后端用户指南：本文档描述了使用NVPTX后端编译GPU内核。
    -   AMDGPU后端用户指南:本文档描述了使用AMDGPU后端编译GPU内核。
    -   LLVM中的堆栈映射和补丁点:LLVM支持将指令地址映射到值的位置并允许修补代码。
    -   在big endian模式下使用ARM NEON指令：LLVM支持在大端ARM目标上生成NEON指令有点不直观。本文档解释了实施和理由。
    -   LLVM代码覆盖映射格式:LLVM代码覆盖映射格式
    -   LLVM中的垃圾收集安全点：这描述了一组垃圾收集支持的实验扩展。
    -   MergeFunctions Pass，它是如何工作的：描述合并优化的函数。
    -   InAlloca属性的设计和使用：inalloca参数属性的描述。
    -   FaultMaps和隐式检查：LLVM支持折叠控制流入错误机器指令。
    -   用clang编译CUDA：LLVM对CUDA的支持。
    -   LLVM中的协同程序:LLVM中的协同程序.
    -   全局指令选择：这描述了原型指令选择替换GlobalISel
    -   XRay仪表：有关如何在LLVM中使用XRay的高级文档。
    -   使用XRay进行调试：如何使用XRay调试应用程序的示例。
    -   Microsoft PDB文件格式：Microsoft PDB（程序数据库）文件格式的详细说明。
    -   控制流程验证工具设计文档：控制流完整性验证工具的说明
    -   投机负荷强化：Spectre v1的推测负载强化缓解的描述
    -   堆栈安全分析：本文档描述了局部变量的堆栈安全性分析的设计。

### LLVM命令指南

#### 基本命令

命令

说明

llvm-as

LLVM汇编器

llvm-dis

LLVM反汇编器

opt

LLVM优化器

llc

LLVM静态编译器

lli

LLVM字节码解释器

llvm-link

LLVM字节码连接器

llvm-lib

LLVM的与lib.exe兼用的库工具

llvm-lipo

用于处理通用二进制文件的LLVM工具

llvm-config

打印LLVM编译选项

llvm-cxxmap

Mangled name重映射工具

llvm-diff

LLVM 结构”diff”

llvm-cov

发出覆盖信息

llvm-profdata

配置数据工具

llvm-stress

生成随机的.ll文件

llvm-symbolizer

将地址转换为源代码中的位置

llvm-dwarfdump

转储并检验DWARF调试信息

dsymutil

操作存档文件中的DWARF调试符号文件

llvm-mca

LLVM机器码分析器

llvm-readobj

LLVM目标文件分析器

#### GNU bintils替代命令

命令

说明

llvm-addr2line

addr2line的替代品

llvm-ar

LLVM归档器

llvm-cxxfilt

LLVM符合名称分析器

llvm-nm

列出LLVM字节码和目标文件中的符号表

llvm-objcopy

目标文件复制和编辑工具

llvm-objdump

LLVM目标文件转储器

llvm-ranlib

库存档索引生成工具

llvm-readelf

GNU风格的LLVM对象读取器

llvm-size

打印目标文件尺寸信息

llvm-strings

打印目标文件中的字符串

llvm-strip

目标文件去除调试信息工具

#### 调试工具

命令

说明

bugpoint

自动测试用例缩减工具

llvm-extract

从LLVM模块中提取函数

llvm-bcanalyzer

LLVM字节码分析器

#### 开发工具

命令

说明

FileCheck

灵活的模式匹配文件验证程序

tblgen

目标描述到C++代码生成器

lit

LLVM集成测试仪

llvm-build

LLVM项目构建实用程序

llvm-exegesis

LLVM机器指令基准

llvm-pdbutil

PDB文件取证和诊断

llvm-locstats

计算DWARF调试位置的统计信息

### 开源项目

-   emscripten-core/emscripten: Emscripten:一个llvm到webassembly的编译器
-   tinygo-org/tinygo: 微控制器、WebAssembly (WASM/WASI)和命令行工具。基于LLVM。
-   numba/numba: 使用LLVM支持NumPy动态Python编译器
-   avast/retdec: RetDec是一个基于LLVM的可重定向机器码反编译器。
-   lifting-bits/mcsema: 将x86、amd64、aarch64、sparc32和sparc64程序二进制代码提升到LLVM位码的框架
-   microsoft/DirectXShaderCompiler: 这个repo托管了DirectX Shader编译器的源代码，它是基于LLVM/Clang的。
-   andreasfertig/cppinsights: c++洞察力——用编译器的眼光看你的源代码
-   google/souper: LLVM IR的超优化器
-   HikariObfuscator/Hikari: LLVM模糊处理
-   dotnet/llilc:这个repo包含LLILC，一个基于LLVM的。net Core编译器。它包括一组跨平台的。net代码生成工具，可以将MSIL字节码编译成LLVM支持的平台。
-   banach-space/llvm-tutor: 用于教学和学习的树外LLVM通行证的集合
-   numba/llvmlite: 用于编写JIT编译器的轻量级LLVM python绑定
-   yrnkrn/zapcc: zapcc是一个基于clang的缓存c++编译器，旨在执行更快的编译
-   go-llvm/llgo: 基于llvm的编译器
-   eliben/llvm-clang-samples: unmaintenance:使用LLVM和Clang编译库和工具的例子

### 文章

-   LLVM 入门篇
-   LLVM-Clang入门
-   LLVM编译器框架介绍
-   Llvm编译的基本概念和流程
-   后端技术的重用：LLVM不仅仅让你高效
-   编译优化｜LLVM代码生成技术详解及在数据库中的应用
-   编译器及底层名词解释

### 视频

-   How LLVM & Clang work\---提取码: 225f
-   2021 LLVM Dev Mtg “Otter- Tracing & Visualizing OpenMP Programs as DAGs Through LLVM's OMPT...”\---提取码: d2k2
-   2021 LLVM Dev Mtg “Navigating Exotic SIMD Lands with an LLVM Guide”\---提取码: 5v6s
-   2019 LLVM Developers’ Meeting- E. Christopher & J. Doerfert “Introduction to LLVM”\---提取码: 8u6e
-   2019 LLVM Developers’ Meeting- S. Haastregt & A. Stulova “An overview of Clang ”\---提取码: r6ct
-   P. Goldsborough “clang-useful- Building useful tools with LLVM and clang for fun and profit\---提取码: xemt
