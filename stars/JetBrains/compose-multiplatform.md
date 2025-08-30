---
project: compose-multiplatform
stars: 18093
description: Compose Multiplatform, a modern UI framework for Kotlin that makes building performant and beautiful user interfaces easy and enjoyable.
url: https://github.com/JetBrains/compose-multiplatform
---

Compose Multiplatform is a declarative framework for sharing UI code across multiple platforms with Kotlin. It is based on Jetpack Compose and developed by JetBrains and open-source contributors.

You can choose the platforms across which to share your UI code using Compose Multiplatform:

-   iOS
-   Android
-   Desktop (Windows, MacOS, and Linux)
-   Web (Alpha)

For example, you can share UIs between iOS and Android or Windows and MacOS.

iOS
---

Compose Multiplatform shares most of its API with Jetpack Compose, the Android UI framework developed by Google. You can use the same APIs to build user interfaces for both Android and iOS.

Since Compose is built on top of Kotlin Multiplatform, you can easily access native APIs, such as the Camera API, and embed complex native UI views, such as MKMapView.

**Get started with Compose Multiplatform**

Android
-------

When Android is one of your targets, you get the same experience for Android as if you were developing an Android app using Jetpack Compose.

**Get started with Compose Multiplatform**

Desktop
-------

Compose Multiplatform targets the JVM and supports high-performance hardware-accelerated UI rendering on all major desktop platforms – macOS, Windows, and Linux.

It has desktop extensions for menus, keyboard shortcuts, window manipulation, and notification management.

**Get started with Compose Multiplatform**

Web
---

> Web support is in Alpha. It may change incompatibly and require manual migration in the future. We would appreciate your feedback on it in the public Slack channel #compose-web. If you face any issues, please report them on YouTrack.

You can experiment with sharing your mobile or desktop UIs with the web. Compose for Web is based on Kotlin/Wasm, the newest target for Kotlin Multiplatform projects. It allows Kotlin developers to run their code in the browser with all the benefits that WebAssembly has to offer, such as good and predictable performance for your applications.

**Get started with Compose for Web**

Libraries
---------

### Compose HTML

Compose HTML is a library targeting Kotlin/JS that provides Composable building blocks for creating web user interfaces with HTML and CSS.

> Note that Compose HTML is not a multiplatform library. It can be used only with Kotlin/JS.

Learn more
----------

-   FAQ
-   Samples
-   Tutorials
-   Compatibility and versioning
-   Changelog

Get help
--------

There are dedicated public Slack channels for #compose-ios, #compose-desktop and #compose-web, as well as the general #compose channel.

If you encounter any issues, please report them on YouTrack.
