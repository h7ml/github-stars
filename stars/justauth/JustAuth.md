---
project: JustAuth
stars: 17147
description: 🏆Gitee 最有价值开源项目 🚀:100: 小而全而美的第三方登录开源组件。目前已支持Github、Gitee、微博、钉钉、百度、Coding、腾讯云开发者平台、OSChina、支付宝、QQ、微信、淘宝、Google、Facebook、抖音、领英、小米、微软、今日头条、Teambition、StackOverflow、Pinterest、人人、华为、企业微信、酷家乐、Gitlab、美团、饿了么、推特、飞书、京东、阿里云、喜马拉雅、Amazon、Slack和 Line 等第三方平台的授权登录。 Login, so easy!
url: https://github.com/justauth/JustAuth
---

**Login, so easy.**

* * *

* * *

QQ 群：230017570  
微信群：justauth （备注`justauth`或者`ja`）  
帮助文档：www.justauth.cn

什么是 JustAuth？
-------------

JustAuth，如你所见，它仅仅是一个**第三方授权登录**的**工具类库**，它可以让我们脱离繁琐的第三方登录 SDK，让登录变得**So easy!**

JustAuth 集成了诸如：Github、Gitee、支付宝、新浪微博、微信、Google、Facebook、Twitter、StackOverflow等国内外数十家第三方平台。更多请参考已集成的平台

有哪些特点？
------

1.  **全**：已集成十多家第三方平台（国内外常用的基本都已包含），仍然还在持续扩展中（开发计划）！
2.  **简**：API就是奔着最简单去设计的（见后面`快速开始`），尽量让您用起来没有障碍感！

有哪些功能？
------

-   集成国内外数十家第三方平台，实现快速接入。参考文档
-   自定义 State 缓存，支持各种分布式缓存组件。参考文档
-   自定义 OAuth 平台，更容易适配自有的 OAuth 服务。参考文档
-   自定义 Http 实现，选择权完全交给开发者，不会单独依赖某一具体实现。参考文档
-   自定义 Scope，支持更完善的授权体系。参考文档
-   更多...参考文档

快速开始
----

### 引入依赖

<dependency\>
    <groupId\>me.zhyd.oauth</groupId\>
    <artifactId\>JustAuth</artifactId\>
    <version\>{latest-version}</version\>
</dependency\>

> **latest-version** 可选：
> 
> -   稳定版：
> -   快照版：
> 
> > 注意：快照版本是功能的尝鲜，并不保证稳定性。请勿在生产环境中使用。
> 
> 如何引入快照版本
> 
> JustAuth 的快照版本托管在 ossrh 上，所以要指定下载地址。
> 
> <repositories\>
>     <repository\>
>         <id\>ossrh-snapshot</id\>
>         <url\>https://oss.sonatype.org/content/repositories/snapshots</url\>
>         <snapshots\>
>             <enabled\>true</enabled\>
>         </snapshots\>
>     </repository\>
> </repositories\>
> 
> 如果你想第一时间获取 JustAuth 的最新快照，可以添加下列代码，每次构建时都检查是否有最新的快照（默认每天检查）。
> 
>        <url>https://oss.sonatype.org/content/repositories/snapshots</url>
>         <snapshots>
> +           <updatePolicy>always</updatePolicy>
>             <enabled>true</enabled>
>         </snapshots>

如下**任选一种** HTTP 工具 依赖，_项目内如果已有，请忽略。另外需要特别注意，如果项目中已经引入了低版本的依赖，请先排除低版本依赖后，再引入高版本或者最新版本的依赖_

-   hutool-http
    
    <dependency\>
        <groupId\>cn.hutool</groupId\>
        <artifactId\>hutool-http</artifactId\>
        <version\>5.7.7</version\>
    </dependency\>
    
-   httpclient
    
    <dependency\>
    	<groupId\>org.apache.httpcomponents</groupId\>
      	<artifactId\>httpclient</artifactId\>
      	<version\>4.5.13</version\>
    </dependency\>
    
-   okhttp
    
    <dependency\>
      <groupId\>com.squareup.okhttp3</groupId\>
      <artifactId\>okhttp</artifactId\>
      <version\>4.9.1</version\>
    </dependency\>
    

### 调用api

#### 普通方式

// 创建授权request
AuthRequest authRequest = new AuthGiteeRequest(AuthConfig.builder()
        .clientId("clientId")
        .clientSecret("clientSecret")
        .redirectUri("redirectUri")
        .build());
// 生成授权页面
authRequest.authorize("state");
// 授权登录后会返回code（auth\_code（仅限支付宝））、state，1.8.0版本后，可以用AuthCallback类作为回调接口的参数
// 注：JustAuth默认保存state的时效为3分钟，3分钟内未使用则会自动清除过期的state
authRequest.login(callback);

#### Builder 方式一

静态配置 `AuthConfig`

AuthRequest authRequest = AuthRequestBuilder.builder()
    .source("github")
    .authConfig(AuthConfig.builder()
        .clientId("clientId")
        .clientSecret("clientSecret")
        .redirectUri("redirectUri")
        .build())
    .build();
// 生成授权页面
  authRequest.authorize("state");
// 授权登录后会返回code（auth\_code（仅限支付宝））、state，1.8.0版本后，可以用AuthCallback类作为回调接口的参数
// 注：JustAuth默认保存state的时效为3分钟，3分钟内未使用则会自动清除过期的state
  authRequest.login(callback);

#### Builder 方式二

动态获取并配置 `AuthConfig`

AuthRequest authRequest = AuthRequestBuilder.builder()
    .source("gitee")
    .authConfig((source) -> {
        // 通过 source 动态获取 AuthConfig
        // 此处可以灵活的从 sql 中取配置也可以从配置文件中取配置
        return AuthConfig.builder()
            .clientId("clientId")
            .clientSecret("clientSecret")
            .redirectUri("redirectUri")
            .build();
    })
    .build();
Assert.assertTrue(authRequest instanceof AuthGiteeRequest);
System.out.println(authRequest.authorize(AuthStateUtils.createState()));

#### Builder 方式支持自定义的平台

AuthRequest authRequest = AuthRequestBuilder.builder()
    // 关键点：将自定义实现的 AuthSource 配置上
    .extendSource(AuthExtendSource.values())
    // source 对应 AuthExtendSource 中的枚举 name
    .source("other")
    // ... 其他内容不变，参考上面的示例
    .build();

赞助和支持
-----

感谢以下赞助商的支持：

我要赞助

JustAuth 的用户
------------

有很多公司、组织和个人把 JustAuth 用于学习、研究、生产环境和商业产品中，包括（但不限于）：

怎么没有我？登记

开源推荐
----

-   `JAP` 开源的登录认证中间件: https://gitee.com/fujieid/jap
-   `spring-boot-demo` 深度学习并实战 spring boot 的项目: https://github.com/xkcoding/spring-boot-demo
-   `mica` SpringBoot 微服务高效开发工具集: https://github.com/lets-mica/mica
-   `sureness` 面向restful api的高性能认证鉴权框架：sureness

更多推荐，请参考：JustAuth - 开源推荐

鸣谢
--

-   感谢 JetBrains 提供的免费开源 License：

其他
--

-   CONTRIBUTORS
-   CHANGELOGS
-   PLAN

贡献者列表
-----

Stars 趋势
--------

### Gitee

### Github

### ProductHunt
