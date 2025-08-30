---
project: swiftui-example
stars: 607
description: SwiftUI 示例，技巧和技术集合，帮助我构建应用程序，解决问题以及了解SwiftUI的实际工作方式。
url: https://github.com/jaywcjlove/swiftui-example
---

**SwiftUI 示例、技巧和技术集合**：这个集合旨在帮助您构建应用程序、解决问题，并了解 SwiftUI 的实际工作方式。主要内容来源于 `hackingwithswift.com`，所有示例都是在 macOS Big Sur 系统上运行，基于 Xcode `12.4` 开发。

此外，我还制作了一个 Swift/SwiftUI 速查手册应用，您可以通过速查手册快速查阅资料，边动手开发应用，轻松上手。您可以通过以下链接下载：

🚧 **注意事项：** 这些示例适用于 macOS/iOS 上的 Swift 编程（主要是 macOS），文字解释内容是通过 Google 翻译完成的，英文水平有限，欢迎大家参与修改和完善。部分内容进行了添加或修改，并且有些部分是新增的。如果您对 Swift 语法不熟悉，可以参考 `Swift 语法入门`，而如果对 SwiftUI 不熟悉，提供了一个 `SwiftUI 速查手册` 供您参考。

🚧 **版权声明：** 内容版权归 `hackingwithswift.com` 原作者所有，本站不承担任何法律责任或风险，且不以商业为目的。如果您认为本站的内容侵犯了您的版权，请及时联系我们。同时，本站无法完全保证内容的准确性，使用本站内容所带来的任何风险由用户自行承担。使用本站即表示您已接受本站的使用条款和隐私政策。

为了方便在 Swift 中进行颜色拾取，提供了一个 Web 小工具 UI-Color，此外还提供了一个桌面应用 Palette Genius，该应用汇集了许多颜色，并且包含一个颜色选择转换器。欢迎大家提出改进意见。

`SwiftUI 论坛`

只是讨论 SwiftUI 事物的地方 论坛→。想法来源于 sindresorhus/swiftui

✦ 欢迎下载我的 macOS/iOS 应用程序来支持我，谢谢 ✦

示例目录
----

-   介绍
-   建立一个完整的项目
-   使用静态文本
-   图像形状和媒体
-   视图布局
-   堆栈网格滚动视图
-   用户界面控件
-   响应事件
-   点击和手势
-   状态
-   列表
-   表单
-   容器
-   对话框和菜单
-   切换界面
-   转换视图
-   绘画
-   动画
-   排版视图
-   跨平台-swiftui
-   数据
-   辅助功能
-   工具
-   附录a
-   `速查手册`

介绍
--

简要介绍 SwiftUI 的基础

-   不要惊慌！
-   什么是 SwiftUI?
-   SwiftUI 与 Interface Builder 和 storyboards
-   有关 SwiftUI 的常见问题
-   回答这个大问题：你应该学习 SwiftUI，UIKit，还是两者都学？
-   如何遵循这个快速入门指南？
-   从 UIKit 迁移到 SwiftUI
-   基本模板是什么？
-   贡献

建立一个完整的项目
---------

通过实际的应用程序项目学习 SwiftUI

-   创建一个 `SwiftUI` 项目
-   使用列表构建菜单

使用静态文本
------

整齐地布局文本

-   如何使用 `Text` 视图创建静态标签？
-   如何使用字体，颜色，行距等为文本视图设置样式？
-   如何使用 `multilineTextAlignment()` 调整文本对齐方式？
-   如何在文本视图中设置文本格式？
-   如何在文字中的字母之间增加空格？
-   如何在文字检视中格式化日期？
-   如何使用 `textCase()` 使 `TextField` 大写或小写？
-   如何使用 `Label` 并排显示文本和图标？
-   如何使用 `redacted()` 将内容标记为占位符？
-   如何使用 `privacySensitive()` 将内容标记为私有?
-   如何在文本中呈现 `Markdown` 内容？
-   如何让用户选择文本？

图像，形状和媒体
--------

绘制图标，圆形，渐变等

-   如何使用图像视图绘制图像？
-   如何调整图像适合其空间的展示方式？
-   如何平铺图像？
-   如何使用SF符号渲染图像？
-   如何渲染渐变？
-   如何使用图像和其他视图作为背景？
-   如何显示实体形状？
-   如何同时填充和描边形状？
-   如何使用 `trim()` 绘制实体形状的一部分？
-   什么时候应该使用 `ContainerRelativeShape`？
-   如何使用 `VideoPlayer` 播放电影？
-   如何使用 `SpriteView` 集成 `SpriteKit`？
-   如何从 URL 加载远程图像？
-   如何使用 SF Symbols 获得自定义颜色和透明度？

视图布局
----

布局大小，优先级和间距

-   如何给视图定制 `frame`？
-   如何使用 `padding` 来控制各个视图之间的间距？
-   如何使用 `GeometryReader` 提供相对大小？
-   如何将内容放置在安全区域之外？
-   如何返回不同的视图类型？
-   如何使用 `ForEach` 循环创建视图？
-   如何使用 `layoutPriority()` 控制布局优先级？
-   如何使两个视图具有相同的宽度或高度？
-   如何使用 `foregroundStyle()` 提供视觉结构？

堆栈，网格，滚动视图
----------

以结构化方式定位视图

-   如何使用 `VStack` 和 `HStack` 创建堆栈？
-   如何使用对齐 `alignment` 和间距 `spacing` 自定义堆栈布局？
-   如何使用 `Spacer` 将视图强制移到堆栈中的一侧？
-   如何制作固定尺寸的 `Spacer`？
-   如何使用 `ZStack` 在彼此之上叠加视图？
-   如何使用 `zIndex` 更改视图分层的顺序？
-   如何使用尺寸类创建不同的布局？
-   如何根据大小类在 `HStack` 和 `VStack` 之间自动切换？
-   如何使用 `ScrollView` 添加水平和垂直滚动？
-   如何使用 `ScrollViewReader` 使滚动视图移动到某个位置？
-   如何使用 `ScrollView` 和 `GeometryReader` 创建3D效果(如Cover Flow)？
-   如何使用 `LazyVGrid` 和 `LazyHGrid` 在网格中放置视图？
-   如何使用 `LazyVStack` 和 `LazyHStack` 延迟加载视图？
-   如何使用 `HSplitViews` 创建左中右三栏布局？
-   如何添加视觉效果模糊？

用户界面控件
------

响应交互并控制程序状态

-   使用状态
-   如何创建可点击的按钮？
-   如何禁用 `Button` 和 `NavigationLink` 中的图像的覆盖颜色？
-   如何从 `TextField` 读取文本？
-   如何在 `TextField` 上添加边框？
-   如何将占位符添加到 `TextField`？
-   如何在 `TextField` 中禁用自动更正？
-   如何关闭 `TextField` 的键盘？
-   如何格式化数字的 `TextField`？
-   如何使用 `SecureField` 创建安全的文本字段？
-   如何创建拨动开关？
-   如何创建滑块 `Slider` 并从中读取值？
-   如何创建选择器 `Picker` 并从中读取值？
-   如何创建日期选择器 `DatePicker` 并从中读取值？
-   如何创建分段控件并从中读取值？
-   如何创建步进器 `Stepper` 并从中读取值？
-   如何使用 `labelsHidden()` 隐藏 `Picker`，`Stepper`，`Toggle` 等标签？
-   如何使用文本编辑器创建多行可编辑文本 `TextEditor`？
-   如何让用户使用 `ColorPicker` 选择颜色？
-   如何使用 `ProgressView` 显示任务的进度？
-   如何使用 `ProgressView` 显示不确定的进度？
-   如何显示地图 `Map` 视图？
-   如何在地图 `Map` 视图中显示注释？
-   如何在 `Safari` 中打开 Web 链接？
-   如何设置可编辑文本 `TextEditor` 背景颜色？
-   如何自定义 `TextField`、`SecureField` 和 `TextEditor` 的提交按钮？
-   当用户提交 TextField 时如何执行事件？
-   如何获得突出的边框按钮？

响应事件
----

快捷方式，旋转方式和外观

-   如何使用 `scenePhase` 检测您的应用何时移至背景或前景？
-   如何响应查看生命周期事件：`onAppear()` 和 `onDisappear()` ？
-   如何使用 `keyboardShortcut()` 添加键盘快捷键？
-   如何控制应用启动时显示的视图？
-   应用启动时如何运行代码？
-   如何将 `AppDelegate` 添加到 SwiftUI 应用？
-   如何检测设备旋转？
-   如何在键盘上添加工具栏？
-   显示视图时如何运行异步任务？

点击和手势
-----

滑动，轻击，摇动和其他输入

-   如何在视图中添加手势识别器？
-   如何阅读点击和双击手势？
-   如何使用 `highPriorityGesture()` 强制一个手势先识别另一个手势？
-   如何使用 `simultaneousGesture()` 同时识别两个手势？
-   如何使用 `sequenced(before:)` 创建手势链？
-   如何检测到用户将鼠标悬停在视图上？
-   如何检测摇动手势？
-   如何使用 `contentShape()` 控制视图的可点击区域？
-   如何使用 `allowsHitTesting()` 禁用视图的点击？

状态
--

响应交互并控制程序状态

-   `@ObservedObject`，`@State` 和 `@EnvironmentObject` 有什么区别？
-   如何使用 `@StateObject` 创建和监视外部对象？
-   如何使用 `@ObservedObject` 管理外部对象的状态？
-   如何使用 `@EnvironmentObject` 在视图之间共享数据？
-   如何使用 `objectWillChange` 手动发送状态更新？
-   如何创建常量绑定？
-   如何创建自定义绑定？
-   如何在 `SwiftUI` 中使用计时器？
-   当使用 `onChange()` 改变状态时如何运行一些代码？

列表
--

创建数据滚动表

-   使用列表 `List`
-   如何创建静态物品列表？
-   如何创建动态项目列表？
-   如何让用户从列表中删除行？
-   如何让用户在列表中移动行？
-   如何将 `Section` 添加到列表？
-   如何使用 `EditButton` 启用对列表的编辑？
-   如何使用 `listRowBackground()` 设置列表行的背景色？
-   如何创建分组和插入分组列表？
-   如何创建扩展列表？
-   如何滚动到列表中的特定行？
-   如何允许列表中的行选择？
-   如何使用隐式堆栈？

表单
--

快速有效地获得用户输入

-   使用表单 `Form`
-   基本表格设计
-   将表格分为几个部分
-   表单选择器 `Pickers`
-   启用和禁用表单中的元素
-   显示和隐藏表单行

容器
--

将视图放置在导航控制器等中

-   使用容器
-   如何在导航视图中嵌入视图？
-   如何将栏项目添加到导航视图？
-   如何使用 `TabView` 将视图嵌入选项卡栏中？
-   如何使用 `tabViewStyle()` 创建内容的滚动页面？
-   如何将视图组合 `Group` 在一起？
-   如何隐藏和显示状态栏？
-   如何使用 `DisclosureGroup` 隐藏和显示内容？
-   如何创建工具栏并向其中添加按钮？
-   如何为 `iPadOS` 添加侧边栏？
-   如何隐藏和显示 `NavigationView` 侧边栏？

对话框和菜单
------

发生某些情况时显示模式通知

-   使用简介
-   如何显示 `alert`？
-   如何为 `alert` 按钮添加动作？
-   如何在单个视图中显示多个 `alert`？
-   如何显示动作面板？
-   如何显示上下文菜单？
-   如何使用 `appStoreOverlay()` 推荐另一个应用程序？
-   按下按钮时如何显示菜单？
-   如何让用户从菜单中选择选项？
-   如何更改 macOS 应用中主菜单？
-   如何添加偏好设置界面？

切换界面
----

将您的用户从一个视图移动到另一个视图

-   如何将新视图推送到 `NavigationView` 上？
-   点击列表行时如何推送新视图？
-   如何在 `SwiftUI` 中使用程序化导航？
-   如何使用 `sheets` 呈现新视图？
-   如何使视图自行关闭？
-   如何显示弹出视图？

转换视图
----

剪辑，大小，比例，旋转等

-   如何使用其偏移量调整视图的位置 `offset`？
-   如何为视图周围的填充着色？
-   如何堆叠修改器以创建更高级的效果？
-   如何在视图周围绘制边框？
-   如何在视图内绘制边框？
-   如何创建行军蚂蚁边框动画效果？
-   如何在视图周围绘制阴影？
-   如何裁剪视图，以便仅部分可见？
-   如何旋转视图？
-   如何旋转 3D 视图？
-   如何放大或缩小视图？
-   如何圆角化一个视图？
-   如何调整视图的不透明度？
-   如何调整视图的强调色？
-   如何用一个视图掩盖另一个视图？
-   如何模糊视图？
-   如何将视图融合在一起？
-   如何通过着色，去饱和等来调整视图？
-   使用 `ButtonStyle` 自定义按钮
-   使用 `ProgressViewStyle` 自定义 `ProgressView`
-   使用 `ToggleStyle` 自定义 `Toggle`
-   如何更改 `List` `TextEditor` 等的背景色

绘画
--

使用自定义形状控制渲染

-   SwiftUI 的内置形状
-   如何绘制自定义路径？
-   如何绘制多边形和星星？
-   如何画一个棋盘？

动画
--

通过运动使您的界面栩栩如生

-   如何创建基本动画？
-   如何制作弹簧动画？
-   如何为绑定值的变化制作动画？
-   如何创建显式动画？
-   如何延迟动画？
-   视图出现后如何立即启动动画？
-   如何在一个视图中应用多个动画？
-   如何使用 matchedGeometryEffect() 将动画从一个视图同步到另一个视图？
-   如何通过过渡添加和删除视图？
-   如何创建不对称过渡？
-   如何创建自定义过渡？
-   如何设置文字大小的动画？
-   如何用事务覆盖动画？

排版视图
----

使您的UI结构更易于理解

-   如何创建和组合自定义视图？
-   如何将文本视图结合在一起？
-   如何将视图存储为属性？
-   如何创建自定义修改程序？
-   如何为 `SwiftUI` 包装自定义 `UIView`？
-   如何为 `UIViewRepresentable` 结构创建修饰符？
-   如何将图像插入文本？

跨平台 SwiftUI
-----------

学习让您的应用在任何地方都看起来很棒

-   学习一次，随处应用
-   如何在 `macOS` 上获取半透明列表？
-   如何在 `watchOS` 上制作轮播列表？
-   如何使用 `digitalCrownRotation()` 在 `watchOS` 上读取 `Digital Crown`？

数据
--

通过 `Core Data` 集成和更多功能处理数据

-   在 `SwiftUI` 中使用 `Core Data` 的简介
-   如何配置核心数据以与 `SwiftUI` 一起使用？
-   如何从 `SwiftUI` 视图访问 `Core Data` 管理的对象上下文？
-   如何使用 `@FetchRequest` 创建核心数据获取请求？
-   如何使用 `predicate` 过滤核心数据获取请求？
-   如何从 `SwiftUI` 视图添加 `Core Data` 对象？
-   如何从 `SwiftUI` 视图中删除 `Core Data` 对象？
-   如何限制获取请求中的项目数？
-   如何使用 `FileDocument` 和 `DocumentGroup` 创建基于文档的应用程序？
-   如何使用 `fileExporter()` 导出文件？
-   如何在 `SwiftUI` 中继续 `NSUserActivity`？
-   如何使用 `LocationButton` 读取用户的位置？

辅助功能
----

如何使每个人都能使用您的应用

-   SwiftUI 的可访问性简介
-   如何使用带有自定义字体的动态类型？
-   如何检测“减少运动”辅助功能设置？
-   如何检测暗模式？
-   如何使用装饰性图像减少屏幕阅读器的混乱？
-   如何在请求时减少动画？

工具
--

使用Xcode的帮助构建更好的应用程序

-   如何以不同的动态类型大小预览布局？
-   如何在亮(light)和黑暗(dark)模式下预览布局？
-   如何在不同的设备中预览布局？
-   如何在导航视图中预览布局?
-   如何使用 `Instruments` 来配置您的 SwiftUI 代码并识 `identify` 布局？
-   如何在 `SwiftUI` 中使用 `Touch ID` 和 `Face ID`？
-   如何在 Xcode 中添加创建 `Swift` 包依赖？
-   如何以纵向或横向预览布局？
-   如何查找导致 SwiftUI 视图更新的数据更改？

附录A
---

如何使用每个 SwiftUI 属性包装器

-   了解 Swift 和 SwiftUI 中的属性包装器
-   所有 SwiftUI 属性包装器都进行了解释和比较
-   什么是 `@State` 属性包装器？
-   什么是 `@StateObject` 属性包装器？
-   什么是 `@Published` 属性包装器？
-   什么是 `@ObservedObject` 属性包装器？
-   什么是 `@EnvironmentObject` 属性包装器？
-   什么是 `@Environment` 属性包装器？
-   什么是 `@Binding` 属性包装器？
-   什么是 `@GestureState` 属性包装器？
-   什么是 `@FetchRequest` 属性包装器？
-   什么是 `@AppStorage` 属性包装器？
-   什么是 `@SceneStorage` 属性包装器？
-   什么是 `@ScaledMetric` 属性包装器？
-   什么是 `@UIApplicationDelegateAdaptor` 属性包装器？

工具推荐
----

-   Swift 语法入门
-   Swift 包索引
-   hackingwithswift.com

贡献者
---

一如既往，感谢我们出色的贡献者！

使用 action-contributors 制作。

License
-------

Licensed under the MIT License.
