---
project: NestedScrollLayout
stars: 157
description: 支持嵌套滚动的布局
url: https://github.com/getActivity/NestedScrollLayout
---

嵌套滚动布局
======

-   项目地址：Github
    
-   可以扫码下载 Demo 进行演示或者测试，如果扫码下载不了的，点击此处可直接下载
    

-   众所周知，WebView、LinearLayout、FrameLayout、RelativeLayout 是不支持 NestedScroll（嵌套滚动）特性的，于是就有了这个库，专门解决这一问题

#### 集成步骤

-   如果你的项目 Gradle 配置是在 `7.0` 以下，需要在 `build.gradle` 文件中加入

allprojects {
    repositories {
        // JitPack 远程仓库：https://jitpack.io
        maven { url 'https://jitpack.io' }
    }
}

-   如果你的 Gradle 配置是 `7.0` 及以上，则需要在 `settings.gradle` 文件中加入

dependencyResolutionManagement {
    repositories {
        // JitPack 远程仓库：https://jitpack.io
        maven { url 'https://jitpack.io' }
    }
}

-   配置完远程仓库后，在项目 app 模块下的 `build.gradle` 文件中加入远程依赖

android {
    // 支持 JDK 1.8 及以上
    compileOptions {
        targetCompatibility JavaVersion.VERSION\_1\_8
        sourceCompatibility JavaVersion.VERSION\_1\_8
    }
}

dependencies {
    // 嵌套滚动布局：https://github.com/getActivity/NestedScrollLayout
    implementation 'com.github.getActivity:NestedScrollLayout:2.0'
}

#### AndroidX 兼容

-   如果项目是基于 **AndroidX** 包，请在项目 `gradle.properties` 文件中加入

```
# 表示将第三方库迁移到 AndroidX
android.enableJetifier = true
```

-   如果项目是基于 **Support** 包则不需要加入此配置

#### 框架用法

-   NestedScrollWebView

<com.hjq.nested.scroll.layout.NestedScrollWebView
    xmlns:android\="http://schemas.android.com/apk/res/android"
    android:layout\_width\="match\_parent"
    android:layout\_height\="match\_parent" />

-   NestedScrollFrameLayout

<com.hjq.nested.scroll.layout.NestedScrollFrameLayout
    android:layout\_width\="match\_parent"
    android:layout\_height\="match\_parent"\>
    
</com.hjq.nested.scroll.layout.NestedScrollFrameLayout>

-   NestedScrollLinearLayout

<?xml version\="1.0" encoding\="utf-8"?>
<com.hjq.nested.scroll.layout.NestedScrollLinearLayout
    android:layout\_width\="match\_parent"
    android:layout\_height\="match\_parent"
    android:orientation\="vertical"\>

</com.hjq.nested.scroll.layout.NestedScrollLinearLayout>

-   NestedScrollRelativeLayout

<?xml version\="1.0" encoding\="utf-8"?>
<com.hjq.nested.scroll.layout.NestedScrollRelativeLayout
    android:layout\_width\="match\_parent"
    android:layout\_height\="match\_parent"\>

</com.hjq.nested.scroll.layout.NestedScrollRelativeLayout>

-   NestedScrollViewPager

<com.hjq.nested.scroll.layout.NestedScrollViewPager
    android:layout\_width\="match\_parent"
    android:layout\_height\="match\_parent"
    app:layout\_behavior\="@string/appbar\_scrolling\_view\_behavior" />

#### 开源项目列表

-   安卓技术中台：AndroidProject
    
-   安卓技术中台 Kt 版：AndroidProject-Kotlin
    
-   权限框架：XXPermissions
    
-   吐司框架：Toaster
    
-   网络框架：EasyHttp
    
-   标题栏框架：TitleBar
    
-   悬浮窗框架：EasyWindow
    
-   Shape 框架：ShapeView
    
-   语种切换框架：MultiLanguages
    
-   Gson 解析容错：GsonFactory
    
-   日志查看框架：Logcat
    
-   Android 版本适配：AndroidVersionAdapter
    
-   Android 代码规范：AndroidCodeStandard
    
-   Android 资源大汇总：AndroidIndex
    
-   Android 开源排行榜：AndroidGithubBoss
    
-   Studio 精品插件：StudioPlugins
    
-   表情包大集合：EmojiPackage
    
-   AI 资源大汇总：AiIndex
    
-   省市区 Json 数据：ProvinceJson
    
-   Markdown 语法文档：MarkdownDoc
    

#### 微信公众号：Android轮子哥

#### Android 技术 Q 群：10047167

#### 如果您觉得我的开源库帮你节省了大量的开发时间，请扫描下方的二维码随意打赏，要是能打赏个 10.24 🐵就太👍了。您的支持将鼓励我继续创作（点击查看捐赠列表）

#### 广告区

-   我现在任腾讯云服务器推广大使，大家如果有购买服务器的需求，可以通过下面的链接购买

【腾讯云】云服务器、云数据库、COS、CDN、短信等云产品特惠热卖中

【腾讯云】中小企业福利专场，多款刚需产品，满足企业通用场景需求

License
-------

```
Copyright 2018 Huang JinQun

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
