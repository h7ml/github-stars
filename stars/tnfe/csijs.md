---
project: csijs
stars: 279
description: CSI.JS是一个特别的前端日志系统，帮你快速重建犯罪现场。
url: https://github.com/tnfe/csijs
---

  

CSI.JS 重建犯罪现场
=============

CSI.JS是一个前端日志系统，它将错误信息记录于本地localStorage中。**无任何依赖**、无入侵性。使用**非常简单**，很容易引入你的系统中，而且不会造成任何影响。 它可以帮你快速重建犯罪现场。  
  

  

#### 无入侵

#### 轻量易用

#### 功能强大

#### 高性能

丢上去不管，我们承诺永不入侵你的业务！

兼容各种系统，不管你使用的是jQuery、angular1/2、React、Vue，都可以使用它

完善的查错机制，截图预览、导出excel、直接上传到后台查看等

文件超小，Gzip 5k对你几乎毫无影响

一、快速开始
------

### 1、npm安装

npm i csijs --save
or
yarn add csijs

### 2、使用

import CSI from 'csijs';

// 示例：自定义上报
const csi \= new CSI({
    feID: '', // 项目id，日志区分项目使用
    report: (lines) \=>  {
        // todo 自定义你的上报逻辑
        console.log('error lins', lines);
    }, 
});

// 如果你想主动上报
csi.report();

二、日志查看
------

查看日志快捷键: Ctrl+6

三、本地开发
------

// 本地开发
npm run start
// 发布环境
npm run build

四、MR 流程
-------

TNTWeb 团队会查看所有的 MR，我们会运行一些代码检查和测试，一经测试通过，我们会接受这次 MR，但不会立即发布外网，会有一些延迟。

当您准备 MR 时，请确保已经完成以下几个步骤:

1.  将主仓库代码 Fork 到自己名下。
2.  基于 `master` 分支创建您的开发分支。
3.  如果您更改了 API(s) 请更新代码及文档。
4.  检查您的代码语法及格式。
5.  提一个 MR 到主仓库的 `master` 分支上。

五、如何加入
------

我们十分期待您的任何贡献，无论是修复错别字、提 Bug 还是提交一个新的特性。

如果您使用过程中发现 Bug，请通过 issues 来提交并描述相关的问题，您也可以在这里查看其它的 issue，通过解决这些 issue 来贡献代码。

如果您是第一次贡献代码，请阅读 CONTRIBUTING 了解我们的贡献流程，并提交 Merge Request 给我们。

六、License
---------

The MIT License (MIT). Please see License File for more information.
