---
project: LiveEventBus
stars: 3959
description: :mailbox_with_mail:EventBus for Android，消息总线，基于LiveData，具有生命周期感知能力，支持Sticky，支持AndroidX，支持跨进程，支持跨APP
url: https://github.com/JeremyLiao/LiveEventBus
---

LiveEventBus
============

LiveEventBus是一款Android消息总线，基于LiveData，具有生命周期感知能力，支持Sticky，支持AndroidX，支持跨进程，支持跨APP

为什么要用LiveEventBus
-----------------

##### 生命周期感知

-   消息随时订阅，自动取消订阅
-   告别消息总线造成的内存泄漏
-   告别生命周期造成的崩溃

##### 范围全覆盖的消息总线解决方案

-   进程内消息发送
-   App内，跨进程消息发送
-   App之间的消息发送

##### 更多特性支持

-   免配置直接使用，懒人最爱
-   支持Sticky粘性消息
-   支持AndroidX
-   支持延迟发送
-   观察者的多种接收模式（全生命周期/激活状态可接受消息）

常用消息总线对比
--------

消息总线

延迟发送

有序接收消息

Sticky

生命周期感知

跨进程/APP

线程分发

EventBus

❌

✅

✅

❌

❌

✅

RxBus

❌

❌

✅

❌

❌

✅

LiveEventBus

✅

✅

✅

✅

✅

❌

#### 想了解更多？请点击：全面了解Android消息总线

使用
--

> 1.8及以上版本全面迁移至maven，同时groupID变为io.github.jeremyliao，1.8以下版本保留JCenter

#### maven

-   非AndroidX

```
implementation 'io.github.jeremyliao:live-event-bus:1.8.0'
```

-   AndroidX

```
implementation 'io.github.jeremyliao:live-event-bus-x:1.8.0'
```

#### JCenter

-   非AndroidX

```
implementation 'com.jeremyliao:live-event-bus:1.7.3'
```

-   AndroidX

```
implementation 'com.jeremyliao:live-event-bus-x:1.7.3'
```

快速开始
----

### 订阅消息

-   以生命周期感知模式订阅消息

LiveEventBus
	.get("some\_key", String.class)
	.observe(this, new Observer<String\>() {
	    @Override
	    public void onChanged(@Nullable String s) {
	    }
	});

-   以Forever模式订阅消息

LiveEventBus
	.get("some\_key", String.class)
	.observeForever(observer);

### 发送消息

-   不定义消息直接发送

LiveEventBus
	.get("some\_key")
	.post(some\_value);

-   先定义消息，再发送消息

```
public class DemoEvent implements LiveEvent {
    public final String content;

    public DemoEvent(String content) {
        this.content = content;
    }
}
```

```
LiveEventBus
        .get(DemoEvent.class)
        .post(new DemoEvent("Hello world"));
```

详细使用文档
------

### 获取Observable

##### 通过name获取Observable

```
Observable<T> get(@NonNull String key, @NonNull Class<T> type)
```

```
Observable<Object> get(@NonNull String key)
```

##### 通过event type获取Observable

```
<T extends LiveEvent> Observable<T> get(@NonNull Class<T> eventType)
```

### 消息发送

##### 进程内发送消息

```
void post(T value)
```

##### App内发送消息，跨进程使用

void postAcrossProcess(T value)

##### App之间发送消息

void postAcrossApp(T value)

##### 进程内发送消息，延迟发送

void postDelay(T value, long delay)

##### 进程内发送消息，延迟发送，带生命周期

```
void postDelay(LifecycleOwner sender, T value, long delay)
```

##### 进程内发送消息，有序发送

void postOrderly(T value)

##### 以广播的形式发送一个消息

-   需要跨进程、跨APP发送消息的时候调用该方法
-   建议尽量使用postAcrossProcess、postAcrossApp

```
void broadcast(T value, boolean foreground, boolean onlyInApp)
```

### 消息订阅

##### 以生命周期感知模式订阅消息

-   具有生命周期感知能力，LifecycleOwner销毁时自动取消订阅，不需要调用removeObserver

```
void observe(@NonNull LifecycleOwner owner, @NonNull Observer<T> observer)
```

##### 以Forever模式订阅和取消订阅消息

-   Forever模式订阅消息，需要调用removeObserver取消订阅

```
void observeForever(@NonNull Observer<T> observer)
```

##### 取消订阅消息

```
void removeObserver(@NonNull Observer<T> observer)
```

##### Sticky模式订阅消息

-   Sticky模式
-   支持在订阅消息的时候设置Sticky模式，这样订阅者可以接收到之前发送的消息。
-   以Sticky模式订阅消息，具有生命周期感知能力，LifecycleOwner销毁时自动取消订阅，不需要调用removeObserver

```
void observeSticky(@NonNull LifecycleOwner owner, @NonNull Observer<T> observer)
```

##### Sticky模式Forever订阅消息

-   Forever模式订阅消息，需要调用removeObserver取消订阅，Sticky模式

```
void observeStickyForever(@NonNull Observer<T> observer)
```

### 跨进程消息

##### 支持对基本数据类型消息的跨进程发送

1.  int
2.  float
3.  long
4.  boolean
5.  double
6.  String

##### 支持Serializable和Parcelable类型消息的跨进程发送

-   提供SerializableProcessor
-   提供ParcelableProcessor

##### 支持Bean类型消息的跨进程发送

-   提供GsonProcessor以Gson方式提供支持
-   需要用注解@IpcConfig指定GsonProcessor：

```
@IpcConfig(processor = GsonProcessor.class)
```

> 1.8及以上版本由于拆分了GsonProcessor，需要引入lebx-processor-gson

-   非AndroidX

```
implementation 'io.github.jeremyliao:leb-processor-gson:x.x.x'
```

-   AndroidX

```
implementation 'io.github.jeremyliao:lebx-processor-gson:x.x.x'
```

##### 支持自定义扩展

-   实现自定义Processor，实现Processor接口
-   用注解@IpcConfig指定自定义Processor

### 老版本文档

-   如果使用1.4.X版本，请参考使用方法
-   如果使用1.3.X及以下版本，请参考使用方法

更多使用场景
------

#### SmartEventBus

SmartEventBus是一个Android平台的消息总线框架，这是一款非常smart的消息总线框架，能让你定制自己的消息总线。 SmartEventBus

#### 在组件化中使用LiveEventBus

android-modular

配置
--

在Application.onCreate方法中配置：

```
LiveEventBus
        .config()
        ...
```

-   **lifecycleObserverAlwaysActive** 配置LifecycleObserver（如Activity）接收消息的模式（默认值true）
    
-   **autoClear** 配置在没有Observer关联的时候是否自动清除LiveEvent以释放内存（默认值false）
    

#### 更多配置信息，请点击：LiveEventBus的配置

混淆规则
----

```
-dontwarn com.jeremyliao.liveeventbus.**
-keep class com.jeremyliao.liveeventbus.** { *; }
-keep class android.arch.lifecycle.** { *; }
-keep class android.arch.core.** { *; }
```

for androidx:

```
-dontwarn com.jeremyliao.liveeventbus.**
-keep class com.jeremyliao.liveeventbus.** { *; }
-keep class androidx.lifecycle.** { *; }
-keep class androidx.arch.core.** { *; }
```

常见问题Q&A
-------

> Issues上最经常被提问的问题

-   Q：收不到消息怎么办？
    
    A：通过Console.getInfo()获取即时的调试信息，主要去观察对应的key下面有没有你关注的Observer（Console的用法）
    
    ```
    *********Event info*********
    Event name: key_test_delay_life
        version: -1
        hasActiveObservers: true
        hasObservers: true
        ActiveCount: 1
        ObserverCount: 1
        Observers: 
            [com.jeremyliao.liveeventbus.core.LiveEventBusCore$ObserverWrapper@992681d=android.arch.lifecycle.ExternalLiveData$ExternalLifecycleBoundObserver@bc258f4]
    ```
    
-   Q：收到重复的消息怎么办？
    
    A：同样通过Console.getInfo()获取即时的调试信息，主要去观察有没有重复注册的Observer（Console的用法）
    
-   Q：JCenter要关闭了，什么时候迁移？
    
    A：1.8及以上版本全面迁移至maven，同时groupID变为io.github.jeremyliao，1.8以下版本保留JCenter
    
-   Q：如何传递List或者Pair<Boolean, Double>这种泛型对象？
    
    A：代码上的写法有两种，供参考：
    
    ```
    LiveEventBus
            .get(KEY_TEST_OBSERVE_FOREVER, List.class)
            .observeForever(new Observer<List>() {
                @Override
                public void onChanged(@Nullable List list) {
                    List<String> stringList = list;
                }
            });
    ```
    
    ```
    Observable<List<String>> observable = LiveEventBus.get(KEY_TEST_OBSERVE_FOREVER);
    observable.observeForever(new Observer<List<String>>() {
        @Override
        public void onChanged(@Nullable List<String> strings) {
        }
    });
    ```
    
-   Q：项目中不用Gson库，如何去掉依赖？
    
    A：使用1.8以上的版本，对gson相关代码进行了拆分
    

> 若问题不能解决，请提issue。

其他分支版本
------

#### AndroidX

-   支持AndroidX
-   同master版本一致

#### classic

-   经典实现版，整个实现就一个java文件
-   只支持激活状态（Started）可以实时收到消息，非激活状态（Stoped）无法实时收到消息，需等到Activity重新变成激活状态，方可收到消息
-   不支持跨进程通信

#### v2

-   v2版，历史版本，已废弃
-   为了解决非激活态不能实时收到消息的问题，采用修改LiveData源码的方式实现

示例和DEMO
-------

文档
--

#### 实现原理

-   LiveEventBus的实现原理可参见作者在美团技术博客上的博文： Android消息总线的演进之路：用LiveDataBus替代RxBus、EventBus
-   该博文是初版LiveEventBus的实现原理，与当前版本的实现可能不一致，仅供参考

质量
--

-   编写了30个测试用例以确保LiveEventBus能够正常运行。
-   具体测试用例参见LiveEventBusTest

版本
--

版本

功能

1.8.x

迁移至maven，拆分gson-converter

1.7.x

优化接口设计，优化实现逻辑，修复一些问题

1.6.x

优化接口设计，优化实现逻辑，修复一些问题

1.5.x

优化接口设计，使用起来更简洁

1.4.x

简化对外暴露的接口，重构核心实现，支持前后台线程调用

1.3.x

支持跨进程、跨APP通信

1.2.x

支持接收消息的模式，支持AndroidX

1.1.x

修复了一些问题

1.0.x

初版，支持基本功能

主要功能提交记录
--------

1.  主要功能完成（Jul 11, 2018）
2.  支持Sticky（Aug 8, 2018）
3.  修复在后台线程PostValue会丢失消息的问题（Aug 9, 2018）
4.  解决发送给Stop状态Observer消息无法及时收到的问题（Aug 18, 2018）
5.  解决了Resumed状态的Activity发生订阅，订阅者会收到订阅之前发布的消息的问题。特别感谢@MelonWXD发现了这个问题（Dec 8，2018）
6.  在removeObserver的时候，检查livedata上有没有observer，没有则删除这个livadata，以减少内存占用。特别感谢@GreenhairTurtle提供的解决方案（Dec 27，2018）
7.  支持设置LifecycleObserver接收消息的模式，支持在整个生命周期实时接收消息和只在激活态实时接收消息两种模式（Jan 22，2019）
8.  支持AndroidX（Mar 8，2019）
9.  支持跨进程、跨APP（Mar 26，2019）
10.  简化对外暴露的接口，重构核心实现，支持前后台线程调用（Apr 4，2019）

其他
--

-   欢迎提Issue与作者交流
-   欢迎提Pull request，帮助 fix bug，增加新的feature，让LiveEventBus变得更强大、更好用

More Open Source by JeremyLiao
------------------------------

1.  InterfaceLoader 史上最好用的Android跨进程接口调用框架件
2.  FastSharedPreferences 一个Android平台的高性能key-value组件
3.  SmartEventBus SmartEventBus是一个Android平台的消息总线框架，这是一款非常smart的消息总线框架，能让你定制自己的消息总线。
4.  android-modular 一套Android组件化的实施方案和支撑框架
5.  DataLoader 一个Android异步数据加载框架，用于Activity打开之前预加载数据，页面启动速度优化利器

更多，请点击

深入学习Android系列，让你精通Android
-------------------------

#### Flutter系列

-   JeremyLiao/flutter-learn
-   alibaba/flutter-go

#### Kotlin系列

-   MindorksOpenSource/from-java-to-kotlin
-   JeremyLiao/kotlin-compare-to-java

#### Gradle系列

-   JeremyLiao/android-gradle-study

#### 算法系列

-   labuladong/fucking-algorithm

#### 测试系列

-   JeremyLiao/jacoco-android-demo

### 招聘|抖音成都招聘|有兴趣的同学可以点进去看一下，谢谢
