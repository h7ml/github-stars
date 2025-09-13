---
project: tauri
stars: 96512
description: Build smaller, faster, and more secure desktop and mobile applications with a web frontend.
url: https://github.com/tauri-apps/tauri
---

Introduction
------------

Tauri is a framework for building tiny, blazingly fast binaries for all major desktop platforms. Developers can integrate any front-end framework that compiles to HTML, JS and CSS for building their user interface. The backend of the application is a rust-sourced binary with an API that the front-end can interact with.

The user interface in Tauri apps currently leverages `tao` as a window handling library on macOS, Windows, Linux, Android and iOS. To render your application, Tauri uses WRY, a library which provides a unified interface to the system webview, leveraging WKWebView on macOS & iOS, WebView2 on Windows, WebKitGTK on Linux and Android System WebView on Android.

To learn more about the details of how all of these pieces fit together, please consult this ARCHITECTURE.md document.

Getting Started
---------------

If you are interested in making a tauri app, please visit the documentation website.

The quickest way to get started is to install the prerequisites for your system and create a new project with `create-tauri-app`. For example with `npm`:

npm create tauri-app@latest

Features
--------

The list of Tauri's features includes, but is not limited to:

-   Built-in app bundler to create app bundles in formats like `.app`, `.dmg`, `.deb`, `.rpm`, `.AppImage` and Windows installers like `.exe` (via NSIS) and `.msi` (via WiX).
-   Built-in self updater (desktop only)
-   System tray icons
-   Native notifications
-   Native WebView Protocol (tauri doesn't create a localhost http(s) server to serve the WebView contents)
-   GitHub action for streamlined CI
-   VS Code extension

### Platforms

Tauri currently supports development and distribution on the following platforms:

Platform

Versions

Windows

7 and above

macOS

10.15 and above

Linux

webkit2gtk 4.0 for Tauri v1 (for example Ubuntu 18.04). webkit2gtk 4.1 for Tauri v2 (for example Ubuntu 22.04).

iOS/iPadOS

9 and above

Android

7 and above (currently 8 and above)

Contributing
------------

Before you start working on something, it's best to check if there is an existing issue first. It's also a good idea to stop by the Discord server and confirm with the team if it makes sense or if someone else is already working on it.

Please make sure to read the Contributing Guide before making a pull request.

Thank you to everyone contributing to Tauri!

### Documentation

Documentation in a polyglot system is a tricky proposition. To this end, we prefer to use inline documentation in the Rust & JS source code as much as possible. Check out the hosting repository for the documentation site for further information: https://github.com/tauri-apps/tauri-docs

Partners
--------

For the complete list of sponsors please visit our website and Open Collective.

Organization
------------

Tauri aims to be a sustainable collective based on principles that guide sustainable free and open software communities. To this end it has become a Programme within the Commons Conservancy, and you can contribute financially via Open Collective.

Licenses
--------

Code: (c) 2015 - Present - The Tauri Programme within The Commons Conservancy.

MIT or MIT/Apache 2.0 where applicable.

Logo: CC-BY-NC-ND

-   Original Tauri Logo Designs by Alve Larsson, Daniel Thompson-Yvetot and Guillaume Chau
