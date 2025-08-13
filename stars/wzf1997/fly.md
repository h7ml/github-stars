---
project: fly
stars: 8
description: 基于webpack 5 + lerna  的 可视化学习仓库
url: https://github.com/wzf1997/fly
---

FLY 哥万字长文带你入门 monorepo 多包实践
===========================

前言
==

大家好，我是 Fly 哥， 之前写博客的仓库，还是用的原生的 html 和 js 也没有引入 ts , 和一些工程化的东西， 所以自己从新搭建了一套前端项目架构 基于 lerna + yarn 的 monrepo 的仓库， 主要是后面会学习输出的一些东西， 整个架子先搭建起来。

1.  2d 和 3d 公共 util 的封装
2.  个人 npm 包的发布 **（rollup）**
3.  2d react 项目 搭建\*\*（vite）\*\*
4.  3d react 项目 搭建 **（webpack）**
5.  搭建一套基于**webpack 5** 的 cli

每个项目都有一些特定的依赖， 但是也会有一些相同的依赖。 比如 eslint、 babel 的一些基础配置，或者一些通用的脚本文件。读完本篇文章你可以学到 **从 0 到 1 搭建 monorepo 前端工程化项目** 如下图所示：

为什么使用 monorepo
==============

monorepo 是一种将多个项目代码存储在一个仓库里的软件开发策略（"mono" 来源于希腊语 μόνος 意味单个的，而 "repo"，显而易见地，是 repository 的缩写）。将不同的项目的代码放在同一个代码仓库中，这种「把鸡蛋放在同一个篮子里」的做法可能乍看之下有些奇怪，但实际上，这种代码管理方式有很多好处，无论是世界一流的互联网企业 Google，Facebook，还是社区知名的开源项目团队 Babe、都使用了 monorepo 策略管理他们的代码。 **这是 Taro 的官方源码库：**

至于他的优点如下：

1.  代码重用将变得非常容易：由于所有的项目代码都集中于一个代码仓库，我们将很容易抽离出各个项目共用的业务组件或工具，并通过 TypeScript，Lerna 或其他工具进行代码内引用；
2.  赖管理将变得非常简单， 可以轻松的做到版本依赖管理 和版本号自动升级
3.  发布 npm 包 也很特别简单， 提取公共方法 直接公共包，可以快速发布到 npm 上
4.  还有一个 最大的 优点 就是 **避免重复安装包， 减少的磁盘空间， 降低了构建时间**

这两项好处全部都可以由一个成熟的包管理工具来完成，对前端开发而言，即是 yarn（1.0 以上）或 npm（7.0 以上）通过名为 workspaces 的特性实现的（⚠️ 注意：支持 workspaces 特性的 npm 目前依旧不是 LTS 版本）。

yarn
====

这里的话 我们全局安装 yarn

npm install yarn \-g

然后新建一个文件夹 进入到目录中执行

yarn init

会在项目的根目录生成 package.json

这时候我们在项目根目录

新建 packages 目录

在 package.json 新增下面字段 **workspace**

{
  "name": "yarn-test",
  "version": "1.0.0",
  "private": true,
  "workspaces": \["packages/\*"\],
  "main": "index.js",
  "license": "MIT"
}

表示工作区是 packages 下的所有子目录,

**private: true** 表示项目的根目录 不会被发布出去

假设项目中有 foo 和 bar 两个 package：

```
mono-demo/
|--package.json
|--packages/
|  |--foo/
|  |  |--package.json
|  |--bar/
|  |  |--package.json
```

### **yarn workspace <workspace\_name>**

在指定的 package 中运行指定的命令。

```
# 在foo中添加react，react-dom作为devDependencies
yarn workspace foo add react react-dom --dev

# 移除bar中的lodash依赖
yarn workspace bar remove lodash

# 运行bar中package.json的 scripts.test 命令
yarn workspace bar run test
```

### **yarn workspaces run**

在所有 package 中运行指定的命令，若某个 package 中没有对应的命令则会报错。

```
# 运行所有package（foo、bar）中package.json的 scripts.build 命令
yarn workspaces run build
```

### **yarn workspaces info \[--json\]**

查看项目中的 workspace 依赖树。

例如我的 bar 依赖了 foo，如下：

```
// bar/package.json
{
  "name": "bar",
  "version": "1.0.0",
  "dependencies": {
    "foo": "^1.0.0"
  }
}
```

在项目中的依赖结构是这样的（假设 foo/package.json 的版本匹配 bar 的依赖版本，否则会另外安装一个匹配的 foo）：

```
/package.json
/yarn.lock

/node_modules
/node_modules/foo -> /packages/foo

/packages/foo/package.json
/packages/bar/package.json
```

那么运行`yarn workspaces info`会得到如下输出：

```
yarn workspaces
{
  "bar": {
    "location": "packages/bar",
    "workspaceDependencies": [
      "foo"
    ],
    "mismatchedWorkspaceDependencies": []
  },
  "foo": {
    "location": "packages/foo",
    "workspaceDependencies": [],
    "mismatchedWorkspaceDependencies": []
  }
}
```

比如我的一些依赖是所有 package 通用的 比如 eslint、babel... 我们就使用下面的这个命令 加一个 -W 就可以了

### **yarn <add|remove> -W**

-   \-W: --ignore-workspace-root-check ，允许依赖被安装在 workspace 的根目录

管理根目录的依赖。

```
# 安装eslint作为根目录的devDependencies
yarn add eslint -D -W
```

lerna
=====

\*\*Lerna\*\*是社区主流的 monorepo 管理工具之一，集成了依赖管理、版本发布管理等功能。

使用 Learn 管理的项目的目录结构和 yarn workspace 类似。

我们根目录安装

yarn add lerna \-D \-W

然后执行

npx lerna init

然后项目中就会生成 lerna.json

我们进行下面配置

{
  "packages": \["packages/\*"\],
  "command": {
    "run": {
      "npmClient": "yarn"
    },
    "publish": {
      "ignoreChanges": \["ignored-file", "\*.md"\],
      "message": "chore(release): publish",
      "registry": "https://npm.pkg.github.com"
    }
  },
  "version": "independent",
  "useWorkspaces": true,
  "npmClient": "yarn"
}

这里 同样使用 workspace, 指定项目 使用 yarn 进行包管理

这里有一个很重要的字段 **"version": "independent"**,

这是表示使用 独立模式 Lerna 项目允许维护人员彼此独立地增加包版本。每次发布时，您都会收到有关已更改的每个包的提示，以指定它是补丁、次要、主要还是自定义更改。 独立模式允许您更具体地更新每个包的版本，并且对一组组件有意义。这里搭配 semantic-release 这个 npm 包 感兴趣的可以去了解下。

下面我介绍一些 lerna 的一些命令： 大家可以去github lerna 看的更多

**lerna bootstrap**：等同于 lerna link + yarn install，用于创建符合链接并安装依赖包；

\*\*lerna run：\*\*会像执行一个 for 循环一样，在所有子项目中执行 npm script 脚本，并且，它会非常智能的识别依赖关系，并从根依赖开始执行命令；

**lerna exec**：像 lerna run 一样，会按照依赖顺序执行命令，不同的是，它可以执行任何命令，例如 shell 脚本；

\*\*lerna publish：\*\*发布代码有变动的 package，因此首先您需要在使用 Lerna 前使用 git commit 命令提交代码，好让 Lerna 有一个 baseline；

\*\*lerna add：\*\*将本地或远程的包作为依赖添加至当前的 monorepo 仓库中，该命令让 Lerna 可以识别并追踪包之间的依赖关系，因此非常重要

tsconfig
========

作为一个 ts 项目， 在项目根目录安装 ts

```
yarn add typescript  -D -W
```

首先在项目中生成 tsconfig.json

npx tsc \--init

然后在项目根目录生成 tsconfig.json 这里 划重点 我们把基础的 tsconfig.json 放在这里 ，然后 新建一个项目 生成 tsconfig.json 都是继承根目录的 tsconfig.json 类似于这样

{
  "extends": "../../tsconfig.json",
  "compilerOptions": {
    "target": "es2018",
    "module": "ESNext",
    "outDir": "./dist"
  },
  "include": \["./src/\*\*/\*.ts"\] // \* 匹配0或者多个字符 （不包括目录分割符） \*\*/递归匹配任意子目录
}

这是一个子项目的 tsconfig.json

至于 tsconfig.json 文件 详细配置，你可以自己百度。

Babel
=====

Babel 配置文件合并的方式与 TypeScript 如出一辙，甚至更加简单，我们只需在子项目中的 .babelrc 文件中这样声明即可：

```
{
  "extends": "../.babelrc"
}
```

scripts
=======

我们在全局新建一个 scripts 文件夹 可能 是 shell 文件 也有可能是 ts 文件。 我们都知道 ts 文件 是不能直接执行， 都是先编译成 js 然后再执行， 这也太麻烦了吧。 好在社区已经提供的 **ts-node** 可以允许你直接运行 ts 文件 这东西实现的原理 大概就是

我们可以使用 ts-node + 某个 ts 文件，来直接执行这个 ts 文件，它的原理就是修改了 require hook，也就是 `Module._extensions['.ts']` 来实现的。

在 require hook 里面做 ts 的编译，然后后面直接执行编译后的 js，这样就能达到直接执行 ts 文件的效果。

所以我们重写 `Module._extensions['.ts']` 方法，在里面读取文件内容，然后调用 ts.transpileModule 来把 ts 转成 js，之后调用 Module.\_compile 来处理编译后的 js。

yarn add ts\-node \-D \-W

新建一个 **test.ts** 文件

```
const foo = {
  baz: {
    a: 1,
  },
}
console.log(foo)
```

然后 在 package.json

编写如下脚本：

```
 "test": "ts-node ./scripts/test.ts "
```

然后执行 **yarn test**

其实这个 ts-node 有一个坑 就是 文件引用问题 当你的 ts 脚本文件 引用了当前项目的其他包 可能就会出现 执行报错

我们在 package 新建一个 util 然后 新建了一个 index.ts 文件

const add \= (a: number, b: number) \=> a + b
export default add

然后我在根目录的 tsconfig.json 进行别名配置

 "baseUrl": "./packages", // 根路径 路径映射,
  "paths": {
    "@fly/util": \["./util/index.ts"\]
  }

我们在 脚本 引入 这个加法 函数

import add from '@fly/util'

console.error(add(2, 3))

然后继续执行

会报下面这个错误

大家注意看 我画框的地方，大体就是 由于 我们 ts-node 在执行的过程中， 由于 tsconfig.json 的 "module": "CommonJS", 会将

import add from '@fly/util' 编译成

const add \= require('@fly/util')

由于我们这个是 ts 别名配置 当然找不到 这个模块， 如果你是 webpack 项目的话 ，可以 配置别名 解决， 会进行路径替换，

但是我们在写脚手架的时候，**不可能用到 webpack 就是 node 环境**， 这里我怎么去解决呢

社区也提供了解决方案

大概意思就是： 使用它来加载位置在 tsconfig.json 的路径部分中指定的模块。支持在运行时加载和通过 API 加载。

Typescript 默认模仿模块的 **Node.js 运行时解析策略**。但它也允许使用路径映射，允许指定任意模块路径（不以“/”或“.”开头）并将其映射到文件系统中的物理路径。 typescript 编译器可以从 tsconfig 解析这些路径，因此它可以编译。但是，**如果您尝试使用 node（或 ts-node）执行编译后的文件，它只会在 node\_modules 文件夹中一直查找到文件系统的根目录，因此不会找到 tsconfig 中路径指定的模块** 这句话 很重要， 所以我们刚才的报错，就是这个原因 而这个库 就是帮我们解决的。

```
yarn add tsconfig-paths -D -W
```

如何使用呢

```
ts-node --project customLocation/tsconfig.json -r tsconfig-paths/register "test/**/*.ts"
```

这里的话最好 ts config.json 的 common js 因为我们是在 node 环境

所以我在项目新建一个 tsconfigs 用来 存放不同的 ts 配置 同样继承 根目录

{
  "extends": "../tsconfig",
  "compilerOptions": {
    "module": "CommonJS"
  }
}

执行命令

ts\-node \--project ./tsconfigs/cmj.json \-r tsconfig\-paths/register  ./scripts/test.ts

执行成功 很舒服哇。看到这里觉得有帮助的话 可以帮忙点个赞吧

但是这里还会有个问题 如图：

这其实是 eslint import 的配置 ，如果你配置了的话 安装下面这个 npm

```
yarn  add eslint-import-resolver-typescript -D -W
```

光从名字就可以看出和这个问题极为相关。从项目 README 可以发现，这个 lib 可以在 TypeScript 项目使 eslint-plugin-import 找到正确的 .ts 和 .tsx 文件，也能识别 tsconfig.json 的 path 配置（路径别名 2），甚至 monorepo 这类一个 git 仓库多个项目的工程也支持。

用法也很简单在 eslint 的`"import/resolver":`指向当前配置了 path 的 tsconfig 的路径即可，eslint 就会自动识别就不会报错了。

{
  "plugins": \["import"\],
  "rules": {
    "import/no-unresolved": "error"
  },
  "settings": {
    "import/parsers": {
      // 使用 TypeScript parser
      "@typescript-eslint/parser": \[".ts", ".tsx"\]
    },
    "import/resolver": {
      // 默认使用根目录 tsconfig.json
      "typescript": {
        // 从 <roo/>@types 读取类型定义
        "alwaysTryTypes": true，
      },

      // 使用指定路径 tsconfig.json， <root>/path/to/folder/tsconfig.json
      "typescript": {
        "directory": "./path/to/folder"
      },

      // monorepos 这类多 tsconfig.json

      // 可以用 glob 这类匹配模式
      "typescript": {
        "directory": "./packages/\*/tsconfig.json"
      },

      // 或者数组
      "typescript": {
        "directory": \[
          "./packages/module-a/tsconfig.json",
          "./packages/module-b/tsconfig.json"
        \]
      },

      // 也可以混合使用
      "typescript": {
        "directory": \[
          "./packages/\*/tsconfig.json",
          "./other-packages/\*/tsconfig.json"
        \]
      }
    }
  }
}

上面就是官方的用法， 下面我们就开始 eslint 详细用法吧

eslint
======

对于 eslint 的配置其实我们可以如法炮制，我们项目的根目录 新建 .eslintrc 然后我们每个子项目 同样继承外部的 .eslintrc

好的下面我们开始安装 **eslint**

yarn add eslint \-D \-W

然后我们生成 eslint 的配置文件

npx eslint \--init

由于我们的项目 是基于 React 和 ts 的 所以在选择的按照下面进行选择

这时候在我们的根目录 就会出现\*\*.eslint.yml\*\* 这个配置文件 这里你也可以选择你喜欢的配置文件格式， 个人比较喜欢 YAML 这种方式

env:
  browser: true
  node: true
extends:
  \- plugin:react/recommended
  \- eslint:recommended
  \- airbnb
parser: '@typescript-eslint/parser'
parserOptions:
  ecmaFeatures:
    jsx: true
  ecmaVersion: 2020
  sourceType: module
plugins:
  \- react
  \- '@typescript-eslint'
  \- react\-hooks
rules:

然后就会出现下面这个文件我来一一解读下面每一条的配置文件

env
---

1.  表示你在 eslint 想启用的环境 我们是前端嘛 所以 就是 node 和 browser，官网支持的还是比较多的
    
    extends
    -------
    
    单从字面上去理解就是 继承 其他的配置 可以是 **文件路径 形式的** 或者是 下载的插件包的 这里的话 一般 npm 包的 格式
    
    是下面这样子的
    
    eslint \- config \- packagename
    
    我们在配置的时候 前面的 **eslint-config** 可以省略， 我这使用的是 airbnb 的配置。
    
    或者安装的包的名字 是这样子
    
    eslint \- plugin \- packagename
    
    然后就可以 **eslint-plugin** 可以省略，然后就可以像下面使用
    
    plugin: xxxx / recommended
    
    或者 是子目录下继承根目录的 eslint 例如如下：
    
    extends:  ../../.eslintrc
    
    **当一切准备就绪后，我们的项目目录应该大致呈如下所示的结构：**
    
    .
    ├── package.json
    ├── .eslintrc
    └── packages/
        │   ├── tsconfig.json
        │   ├── .babelrc
        ├── project\_1/
        │   ├── index.js
        │   ├── .eslintrc
        │   ├── .babelrc
        │   ├── tsconfig.json
        │   └── package.json
        └───project\_2/
            ├── index.js
            ├── .eslintrc
            ├── .babelrc
            ├── tsconfig.json
            └── package.json
    
    parser
    ------
    
    ESLint 默认使用Espree作为其解析器, 但是由于我们项目是 ts 文件， 所以安装
    
    yarn add @typescript\-eslint/parser
    
    作用 就是将 TypeScript 转换成与 estree 兼容的形式，以便在 ESLint 中使用。eslint 也是对 AST 进行操作，但是对 TS 是不支持的，所以做一层转换成 js.
    
    ### parserOption
    
    有了解析器肯定就有解析参数
    
    ecmaFeatures: jsx: true // 表示支持jsx 语法 但是React 对 ESLint 无法识别的JSX语法应用特定的语义。如果你正在使用 React 并且想要 React 语义支持，我们建议你用 eslint-plugin-react。
    
    ecmaVersion: 2020 // 默认的js 的版本
    
    sourceType: module // esm 模式
    
    plugins
    -------
    
    正如上面所说，在解析参数配置了支持 jsx 语法， 但是 ESLint 无法识别的 JSX 语法应用特定的语义。如果你正在使用 React 并且想要 React 语义支持，我们建议你用 eslint-plugin-react。这就是所谓的插件 ，这里安装了 react 和 react-hooks 两个插件
    
    yarn add eslint\-plugin\-react  eslint\-plugin\-react\-hooks
    
    然后我们就可以 plugins 进行配置了 同样可以省略 **eslint-plugin**
    

rules
-----

rules 的定义我们一般看到的就是这样子， 具体的配置可以自己查官方列表

\--\-
rules:
  eqeqeq: off
  curly: error
  quotes:
    \- error
    \- double

然后你如果安装了插件

就可以插件名/ 规则 可以对默认的插件配置 进行重写， 比如下面这样子

```
'react-hooks/rules-of-hooks': 2
'react-hooks/exhaustive-deps': 2
```

与 VScode 集成
-----------

```
 "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
  }
```

prettier
========

prettier 的出现其实为了解决代码格式的问题？ 这是 eslint 无法做到的

Prettier 中文的意思是漂亮的、美丽的，是一个流行的代码格式化的工具，我们来看如何结合 ESLint 来使用。首先我们需要安装三个依赖：

安装 npm 包

yarn add prettier eslint\-config\-prettier eslint\-plugin\-prettier  \-D \-W

1.  prettier：prettier 插件的核心代码
    
2.  eslint-config-prettier：解决 ESLint 中的样式规范和 prettier 中样式规范的冲突，以 prettier 的样式规范为准，使 ESLint 中的样式规范自动失效
    
3.  eslint-plugin-prettier：将 prettier 作为 ESLint 规范来使用
    

然后在项目的根目录下创建.prettierrc 文件：

{
    "printWidth": 120,
    "semi": false,
    "trailingComma": "all",
    "singleQuote": true,
    "arrowParens": "always"
}

接着修改.eslintrc.js 文件，引入 prettier：

extends:
  \- plugin:react/recommended
  # \- plugin:import/recommended
  \- eslint:recommended
  \- airbnb
  \- prettier

plugins:
  \- react
  \- '@typescript-eslint'
  \- react\-hooks
  # \- import
  \- prettier

分别在 extends 和 plugins 加入 prettier

husky 和 lint-staged 构建代码工作流
===========================

在这之前我先简单介绍 下 Husky 和 lint-staged 这两个东西 到底是干什么的??

husky
-----

husky 目前是前端工程哈必备的一个工具了， husky 这个 npm 包 说白了就是在 git 提交前 提供一些钩子 hooks 方便你运行一些脚本命令。下面跟着我可以实操一下

yarn add husky \-D \-W

**第二步**：在 packgae.json 中添加 prepare 脚本

```
{
  "scripts": {
    "prepare": "husky install"
  }
}
```

prepare 脚本会在`npm install`（不带参数）之后自动执行。也就是说当我们执行 npm install 安装完项目依赖后会执行 `husky install`命令，该命令会创建.husky/目录并指定该目录为 git hooks 所在的目录。

第三步 添加 git hooks

```
npx husky add .husky/pre-commit "yarn lint-staged"
```

这时候在我们根目录 就会出现 .husky 的目录

然后写入 pre-commit 脚本

#!/bin/sh
. "$(dirname "$0")/\_/husky.sh"

yarn lint-staged

由于我们还没有装 lint-staged ， 直接运行会报错

lint-staged
-----------

yarn add lint\-staged \-D \-W

Lint-staged 用于对 Git 暂存区中的文件执行代码检测, 然后我们同样也可以做一些操作

我们在 package.json 增加如下配置

 "lint-staged": {
    "\*.@(js|ts|tsx)": \[
      "eslint --ext .ts,.tsx,.js --fix",
      "prettier --write",
      "git add"
    \],
    "\*.@(yml|yaml)": \[
      "prettier --parser yaml --write"
    \],
    "\*.md": \[
      "prettier --parser markdown --write"
    \],
    "\*.json": \[
      "prettier --parser json --write"
    \]
  },

我们看下第一个，当匹配到 以 js 或者 ts 或者是 tsx 结尾的文件时候， 这时候我们就可以 结合 之前 的 eslint 和 prettirer 做一些操作

1.  eslint 对这些文件 检测 并自动修复
2.  然后 使用 prettier -- write 进行自动检测
3.  最后添加到 暂存区中

我们 run 一下 看下效果：

你会发现好像已经成功了， 但是最后 还是失败了，因为我在 husky 还加了一个 hook 用于在提交命令前 规范 commit-msg

我们输入下面命令

npx husky add .husky/commit\-msg 'yarn commitlint --edit "$1"'

然后在.husky 的目录 就会出现下面这张图

由于运行了这个脚本 commitlint 这个脚本 但是我们 安装 老样子

yarn  add commitlint  @commitlint/config\-conventional  @commitlint/config\-lerna\-scopes \-D \-W

\*\*@commitlint/config-conventional \*\* 这里会使用默认 angular 团队的提交规范

**@commitlint/config-lerna-scopes** 由于我们是 lerna 多个 packages 主要是用来限制在 packages 里的包 不在的 就会报错，

packages
├── api
├── app
└── web

❯ echo "build(api): change something in api's build" | commitlint
⧗   input: build(api): change something in api's build
✔   found 0 problems, 0 warnings

❯ echo "test(foo): this won't pass" | commitlint
⧗   input: test(foo): this won't pass
✖   scope must be one of \[api, app, web\] \[scope\-enum\]
✖   found 1 problems, 0 warnings

foo 不属于项目中的一个包， 所以 直接 会报错。

在项目的根目录 新建： commitlint.config.js

module.exports \= {
  extends: \['@commitlint/config-conventional', '@commitlint/config-lerna-scopes'\],
}

这样我们提交的时候就会做到我们上面的限制, 项目代码的提交规范 还是很重要的

生成 changelog
============

首先，聊一下什么是 CHANGELOG ，为什么需要 CHANGELOG ？它记录你项目所有的 commit 信息并归类版本，可以快速跳转到该条 commit 记录，甚至可以显示修改人信息一眼发现 bug 的创建者 😂。它能让你方便知道项目里哪个版本做了哪些功能有哪些 bug 等信息。也方便排查 bug，对于提交记录一目了然，不用一个一个去翻去查。

这里我们安装 这个包

yarn  add  standard\-version \-D \-W

这里，就直接用 standard-version 来实现自动生成 CHANGELOG 了。 conventional-changelog 咱们就不聊了，毕竟是它推荐咱们用 standard-version （这都是同一个团队的东西，基于 conventional-changelog 实现的）。

semantic-release 还有这个 进行生成

至于这两个的区别？？ 我们看下

> **semantic-release** 自动化整个包发布工作流程，包括：确定下一个版本号、生成发布说明和发布包。

虽然两者都基于结构化提交消息的相同基础，但标准版本采用不同的方法，为您处理版本控制、更改日志生成和 git 标记，而无需自动推送（到 GitHub）或发布（到 npm 注册表）。使用标准版本只会影响您的本地 git 存储库 - 它根本不会影响远程资源。运行标准版本后，您可以查看发布状态、纠正错误并遵循对您的代码库最有意义的发布策略。 我们认为它们都是很棒的工具，如果对他们的用例有意义，我们鼓励人们使用语义发布而不是标准版本

然后我们在 package.json 新增这脚本

 "release": "standard-version",

为了 让我们的 changeLog 看起来好看一点在项目根目录 新增 **.versionrc.js**

```
module.exports = {
  types: [
    { type: 'feat', section: '✨ Features | 新功能' },
    { type: 'fix', section: '🐛 Bug Fixes | Bug 修复' },
    { type: 'init', section: '🎉 Init | 初始化' },
    { type: 'docs', section: '✏️ Documentation | 文档' },
    { type: 'style', section: '💄 Styles | 风格' },
    { type: 'refactor', section: '♻️ Code Refactoring | 代码重构' },
    { type: 'perf', section: '⚡ Performance Improvements | 性能优化' },
    { type: 'test', section: '✅ Tests | 测试' },
    { type: 'revert', section: '⏪ Revert | 回退' },
    { type: 'build', section: '📦‍ Build System | 打包构建' },
    { type: 'chore', section: '🚀 Chore | 构建/工程依赖/工具' },
    { type: 'ci', section: '👷 Continuous Integration | CI 配置' },
  ],
}
```

然后在 husky 新增 pre-push 脚本

npx husky add .husky/pre\-commit "yarn release"

这样我们在 git push 提交代码的时候 就会自动生成 changelog

参考
==

1.  https://www.zhihu.com/question/318476028/answer/1895685159
2.  https://juejin.cn/post/7036688014206042143
3.  https://juejin.cn/post/6868472838613893127

最后
==

很感谢你能够看完，如果觉得 Fly 哥写的不错的话，可以点个赞 👍🏻 鼓励一下，项目源码 目前在 github 开源， 感兴趣的可以学习一下

或者关注我的公众号 **「「前端图形」」**，获取更多好玩与有趣的图形知识。「如果你也一样对技术热爱，喜欢\*\*「图形、数据可视化、游戏」**📚 并且为之着迷,欢迎加我个人微信**（wzf582344150）\*\***，将会邀请你加入我的\***\*可视化交流学习群\*\*一起面向快乐编程~」 🦄。 **「我是 Fly」**， 目前在某电商公司互动游戏组。在这个互联网技术疯狂快速迭代的时代中,很高兴能和你一起变强！😉 本公众号关注前端数据可视化方面，如 svg、canvas、等等知识。带你领略不一样的前端公众号
