---
project: tarojs-plugin-ssr
stars: 233
description: 让 Taro H5 支持 Pre-rendering、SSR 和 ISR，极致的首屏速度🚀，利于 SEO🔍
url: https://github.com/NervJS/tarojs-plugin-ssr
---

Taro Next.js SSR 插件
===================

让 Taro H5 支持 Pre-rendering、SSR 和 ISR，极致的首屏速度 🚀，利于 SEO 🔍。

> 作为这个项目的创建者，我现在的工作已经和 Taro 开发无关，因而无法为其持续投入必要的精力进行维护。此刻，我正在寻找对此插件感兴趣且愿意进行贡献的热心者。如果你有热情并且对本项目感兴趣，请通过添加微信号：SharpYourMind 与我取得联系。

安装
--

你需要先有一个 Taro 项目，如果你还不知该如何创建一个 Taro 项目，请先从这里开始：Taro 安装及使用。

要安装和设置本插件，请运行：

npm init tarojs-plugin-platform-nextjs

或者，你可以手动安装在你的 Taro 项目中安装**本插件**和 **Next.js**。

npm install next tarojs-plugin-platform-nextjs

并在 Taro 项目的 `config/index.js` 中添加插件。

const config \= {
    plugins: \[
        'tarojs-plugin-platform-nextjs'
    \]
}

使用
--

### 开发环境

npx taro build --type nextjs --watch

### 生产环境

项目必须先使用以下命令进行编译：

npx taro build --type nextjs

启动应用：

npx taro start -p 10086

产出目录下是一个**完整的 Next.js 应用**，你也可直接使用 next 命令启动它：

npx next start dist -p 10086

谁在使用
----

  
**百度健康医美**

  
**携程机票**

主要功能
----

### Pre-rendering - 预渲染

插件默认 Pre-rendering 所有页面。这意味着提前为每个页面生成 HTML，而不是让浏览器端 JavaScript 完成所有工作。预渲染可以带来更好的性能和搜索引擎优化。

示例 - 房贷计算器

> 阅读 Next.js 文档了解更多：Pre-rendering。

### SSR - 服务端渲染

在页面中导出 `getServerSideProps` 函数来使用 SSR 功能，插件将对每个请求使用 `getServerSideProps` 返回的数据预先渲染该页面。

export async function getServerSideProps(context) {
    return {
        props: {} // 将作为页面组件的属性
    }
}

示例 - Data Fetch Demo

> 阅读 Next.js 文档了解更多：getServerSideProps。

### ISR - 增量静态生成

在页面导出 `getStaticProps` 函数并对其添加 `revalidate` 属性来使用 ISR 功能。

ISR 功能允许你单独对某个页面进行增量静态生成，无需重新生成整个网站。使用 ISR，你可以在数百万页面的规模上同时保留静态的好处。

export async function getStaticProps() {
  const res \= await fetch('https://.../posts')
  const posts \= await res.json()

  return {
    props: {
      posts,
    },
    // Next.js 将尝试重新生成页面
    // - 当接受到一个请求
    // - 最多每 10 秒一次
    revalidate: 10 // 单位为秒
  }
}

示例 - GitHub Reactions Demo

> 阅读 Next.js 文档了解更多：Incremental Static Regeneration。

### 自定义 Next.js 配置

可以在项目的 `config` 目录下添加 `next.config.js` 文件来自定义 Next.js 应用的相关配置。

如自定义 H5 应用的基本路径（basePath）：

module.exports \= {
    basePath: '/swan'
}

> 阅读 Next.js 文档了解更多：next.config.js。

注意事项
----

### 功能限制

由于插件基于 Next.js 框架，故受其影响，有以下限制：

1.  仅支持 `browser` 路由模式。
2.  组件级样式必须使用 CSS Module。

### 获取路由参数

Taro 有两种获取路由参数的方式，一种是调用方法 `getCurrentInstance().router.params`，另一种是使用 React Hook `useRouter().params`。

推荐使用 `useRouter` 来获取路由参数，因为它内部直接使用 Next.js 提供的 `useRouter` React Hook 实现，具有很好的一致性。

你仍可以使用 `getCurrentInstance` 方法，大多数情况它都会运行的很好。但明白插件是如何处理该方法，会让你避免遇到一些问题时不知所措。

当你在一个类组件中调用 `getCurrentInstance` 时，在编译阶段插件会在该组件外部使用 Next.js 的 `withRouter` 方法进行包装，让类组件能够响应 Next.js 路由的变化。

+ import {withRouter} from 'next/router'

class MyComponent extends Component {
    $instance = getCurrentInstance()

    render() {
        console.log(this.$instance.router)
        return null
    }
}

\- export default MyComponent
+ export default withRouter(MyComponent)

插件配置
----

该插件支持以下配置项：

const config \= {
    plugins: \[
        \['tarojs-plugin-platform-nextjs', {
            // 当执行 taro build --type nextjs --watch 命令后，是否需要自动执行 next dev 命令
            // 默认为 true
            runNextjs: true,
            // 是否启动后自动打开浏览器
            // 默认为 true
            browser: true,
            // 在插件编译阶段需要复制到 Next.js 中的附加文件
            // 作为示例，比如你本地编写的 postcss 插件目录
            extraFiles: \[
                'postcss-plugins/\*\*'
            \]
        }\]
    \]
}

Taro 组件的 React 实现
-----------------

Taro 官方的 H5 组件库是基于 Stencil 框架开发，为了更好的性能和兼容性，本项目使用完全基于 React 开发的 Taro 组件库 @taror/components。

参与建设
----

十分欢迎大家参与对插件问题的修复和功能的改进，如果你有任何问题，都可以在本项目的 issue 中进行提问！

### 本地编译

使用以下命令在本地编译插件

yarn install

yarn lerna run build

### 架构设计

你可以通过阅读架构设计来了解本插件的工作原理。

### 贡献者

  
**SyMind**

  
**zygoing**

  
**zengshide123**

  
**wpigdry**

License
-------

MIT
