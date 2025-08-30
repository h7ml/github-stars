---
project: archguard
stars: 651
description: ArchGuard is a architecture workbench, also for architecture governance, which can analysis architecture in container, component, code level, create architecure fitness functions, and anaysis system dependencies..
url: https://github.com/archguard/archguard
---

ArchGuard backend
=================

> ArchGuard is an architecture governance tool that can analysis architecture in container, component, code level, database, create architecture fitness functions, and test for architecture rules.

Chinese: ArchGuard 是一个针对于微服务（分布式场景）下的架构工作台/治理工具。它可以帮助架构师、开发人员进行架构自助，自定义架构的洞察、 分析系统间的远程服务依赖情况、数据库依赖、API 依赖等。并根据一些架构治理模型，对现有系统提出改进建议。

-   Document: https://archguard.org/
-   Roadmap: Roadmap
-   Contribute: Contribute to Archguard
-   SubProjects:
    -   ArchGuard Frontend
    -   Chapi source code analysis
    -   ArchGuard Co-mate an AI-powered architecture copilot, design and governance tools.
-   Architecture:

You can use:

-   ArchGuard Library in Maven Central to integrate with your backend.
-   ArchGuard Scanner CLI to scan your codebase, upload to your backend or ArchGuard backend.
-   ArchGuard Gradle Plugin to scan your codebase in CI/CD.
-   ArchGuard Web is the backend of ArchGuard, it provides a RESTful API for frontend.

特性（Features）：

-   **设计态**
    -   架构设计、分析与治理 DSL
    -   Feakin: https://github.com/feakin/fklang
-   **开发态**
    -   架构扫描
        -   扫描配置
        -   插件化规则定制
        -   规则化治理：Code Smell, Test Code Smell, SQL Smell, API Smell, Documentation Smell, etc.
    -   架构可视化
        -   基于 C4 模型的可视化分析
            -   上下文：API 服务地图（API 生产者支持语言：Java、Kotlin、C#，API 消费者支持语言：TypeScript/JavaScript、Kotlin、Java 等）
            -   容器分析。数据库地图（支持 MyBatis、JDBI、JPA）
            -   组件分析
            -   代码分析：支持级别模块、包、类、方法四个级别。
        -   高级分析 + 可视化
            -   系统不稳定性模块分析。
            -   容器间：精准测试/变化分析
    -   架构指标（单体DONE，分布式DOING）
        -   体量维度：过大的组件
        -   耦合维度：枢纽组件，过深调用，循环依赖
        -   内聚维度：霰弹式修改
        -   冗余维度：冗余元素，过度泛化
        -   质量维度：测试保护
    -   代码分析
        -   CLOCO：代码复杂度 #79
        -   SCA 分析
        -   OpenAPI 分析
        -   Architecture analysis
-   **运行态**
    -   APM（TODO）
-   **架构工作台**

Features：

-   **Design State**
    -   Architecture Design, Analysis and Governance DSL
    -   Feakin: https://github.com/feakin/fklang
-   **Development state**
    -   Schema scan
        -   Scan configuration
        -   Plug-in rule customization
        -   Rule-based governance: Code Smell, Test Code Smell, SQL Smell, API Smell, Documentation Smell, etc.
    -   Architecture visualization
        -   Visual analysis based on C4 model
            -   Context: API service map (API producer supported languages: Java, Kotlin, C#, API consumer supported languages: TypeScript/JavaScript, Kotlin, Java, etc.)
            -   Container analysis. Database map (support MyBatis, JDBI, JPA)
            -   Component analysis
            -   Code analysis: supports four levels of modules, packages, classes, and methods.
        -   Advanced Analysis + Visualization
            -   System instability module analysis.
            -   Between containers: precise testing/variation analysis
    -   Architecture metrics (single DONE, distributed DOING)
        -   Volume dimension: oversize components
        -   Coupling dimension: hub components, too deep calls, circular dependencies
        -   Cohesive Dimension: Shotgun Modification
        -   Redundant dimensions: redundant elements, overgeneralization
        -   Quality dimension: test protection
        -   Continuous Integration
    -   External analysis
        -   CLOCO: Code Complexity #79
        -   SCA analysis
        -   OpenAPI analysis
        -   Architecture analysis
-   **Running state**
    -   APM (TODO)
-   **Architecture Workbench**

Screenshots:

Languages parse by Chapi

Features/Languages

Java

Python

Go

Kotlin

TypeScript

C

C#

Scala

C++

http api decl

✅

🆕

🆕

✅

✅

🆕

✅

🆕

🆕

syntax parse

✅

✅

✅

✅

✅

✅

✅

✅

🆕

function call

✅

🆕

✅

✅

✅

arch/package

✅

✅

✅

🆕

✅

✅

real world validate

✅

✅

Custom Backend
--------------

case example:

-   https://github.com/unit-mesh/co-unit by Rust language

use Scanner CLI you can customize your backend. For more detail, see in: ArchGuardHttpClient

HTTP examples:

POST http://127.0.0.1:8765/scanner/:systemId/reporting/class-items

POST http://127.0.0.1:8765/scanner/:systemId/reporting/openapi

POST http://127.0.0.1:8765/scanner/:systemId/reporting/container-services

POST http://127.0.0.1:8765/scanner/:systemId/reporting/datamap-relations

...

### Chat

关注我们：

欢迎加入我们：

（PS：如果群满，请添加微信 `phodal02`，并注明 ArchGuard）

Thanks
------

JetBrains support:

License
-------

This code is distributed under the MIT license. See `LICENSE` in this directory.
