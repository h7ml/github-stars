---
project: mini-react
stars: 635
description: 手写react、react-dom、react reconciler主流程源码，加深对react源码的理解。包括fiber，合成事件，hooks实现原理，dom diff，reconciliation，scheduler等
url: https://github.com/lizuncong/mini-react
---

> 如果对 react 源码感兴趣的朋友，可以从下面的 TODO 待办项中找一项，以此为发力点解析 React 源码。如果有什么好的外文需要翻译，也可以加到 TODO 中。或者觉得什么文章好，也欢迎提 PR 收录进来。希望能一起对文章质量把关，一起共建社区最好的 react 源码生态环境。

### 目录划分

-   docs。react 相关知识文档&源码剖析目录
-   react。手写 react 源码目录，对应的官方 react 版本为 17.0.1
-   react-dom。手写 react-dom 源码目录，对应的官方 react-dom 版本为 17.0.1
-   react-reconciler。手写 react-reconciler 源码目录，对应的官方 react-reconciler 版本为 17.0.1

### React 源码系列文档(基于 React17.0.1 版本)

-   提高 React 源码 debug 体验舒适度的一些奇淫技巧
    
-   React 工作原理
    
    对理解 react 工作原理有很大的启发作用
    
    -   手把手开发极简 Fiber 版本的 React
        
    -   Fiber 内部：React 中新的协调算法的深入概述
        
    -   React 中 state 和 props 更新的深入讲解
        
    -   React 是如何防止 XSS 攻击的，论$$typeof 的作用
        
    -   【TODO】类组件和函数组件最大的区别
        
    -   【TODO】组件名称首字母为啥一定要大写
        
    -   深入概述 React 初次渲染及状态更新主流程
        
    -   React17 与 React18 源码之间的差别
        
-   React 合成事件原理
    
    -   JavaScript 事件基础
    -   React 合成事件与原生事件的执行顺序，React17 以后合成事件有哪些变更
    -   极简版合成事件
    -   React 源码中合成事件的实现过程
    -   React 合成事件源码中浏览器兼容相关 API 收录
    -   【TODO】React 如何实现 mouseenter 和 mouseleave 事件代理
-   Hooks
    
    -   React.useReducer 原理及源码主流程
    -   从源码的角度分析 useLayoutEffect 及 useEffect 的区别
    -   彻底搞懂函数组件 hook 链表
-   Class Component
    
    -   React 批量&同步更新场景
    -   Class Component setState 主流程及源码，类组件与函数组件对应的 fiber.memoizedState 的区别
    -   React 批量&同步更新原理及主流程源码
-   Reconciler
    
    -   Dom Diff 算法简介
    -   单节点 Dom Diff 算法简介
    -   多节点 Dom Diff 算法及 Commit 阶段节点移动插入更新删除等源码剖析
    -   构建副作用链表算法，为什么 React 不采用数组保存具有副作用的 Fiber 节点？
    -   Dom diff 所有场景介绍
-   Fiber
    
    -   updateQueue 在不同类型的 Fiber 节点的含义
    -   盘点 fiber 中常见的副作用标志 flags
    -   33 张图爆肝介绍 Fiber 双缓冲树机制
    -   Ref 原理及源码解析
-   Hydrate 服务端渲染
    
    -   React Hydrate 原理及源码剖析
-   异常捕获
    
    -   全网最详细的 React 异常捕获机制及源码，为什么在开发环境下，React 不使用 try catch，而是自己模拟了 try catch 的效果？
-   React Context 设计哲学
    
    -   手撕 React Context 源码设计哲学
-   React Scheduler
    
    -   【手写 Scheduler 源码系列文章第一篇】哪些 API 适合用于调度任务。介绍`requestAnimationFrame`、`requestIdleCallback`、`setTimeout`、`MessageChannel`、`MutationObserver`等基础用法及特性，看看哪些 API 会适合任务调度
    -   【手写 Scheduler 源码系列文章第二篇】scheduler 用法详解
    -   【手写 Scheduler 源码系列文章第三篇】scheduler 原理及源码手写。介绍任务切片、时间切片原理、为什么使用 Message Channel 而不是 setTimeout 等调度任务？
    -   【手写 Scheduler 源码系列文章第四篇】scheduer 优先级调度原理及源码手写
    -   【手写 Scheduler 源码系列文章第五篇】scheduer 延迟任务原理及源码手写
    -   【手写 Scheduler 源码系列文章终章】scheduler 核心源码精讲
-   lane 模型
    
    在看 lane 模型前，请先确保已经熟悉 React Scheduler 任务调度原理及用法
    

### 参考链接

-   React 作者 Dan Abramov 的博客
-   Fiber 内部：深入概述 React 中新的协调算法
-   medium.com

Star History
------------

### 关于作者

实干家，不贩卖焦虑，不写水文不吹水。业余时间会根据兴趣看些框架源码，有时间就写写文章。有兴趣的网友可以扫码加个好友一起聊聊人生(备注 react 源码)

如果觉得写得好，点个 star 或者 follow 满足一下男人的虚荣心。心情好的话同时有点小钱，也可以请我喝个小茶开心一下。写得差的话就轻点喷，我会连夜改，真的
