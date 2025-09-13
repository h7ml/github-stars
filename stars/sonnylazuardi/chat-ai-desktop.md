---
project: chat-ai-desktop
stars: 2021
description: Unofficial ChatGPT desktop app for Mac & Windows menubar using Tauri & Rust
url: https://github.com/sonnylazuardi/chat-ai-desktop
---

Chat AI Desktop App
===================

Unofficial open source Chat AI desktop app for mac, windows, and linux menubar using tauri & rust.

ssstwitter.com\_1676182720544.mp4

Downloads
=========

-   Windows (4.11 MB)
-   MacOS (3.8 MB)
-   Linux .deb (2.3 MB)
-   Linux .rpm (2.1 MB)

API Mode
--------

I would like to credit open source chatbot UI by @mckaywrigley that made this possible. The desktop app wrapping the forked version here

### Set your API Key

You can visit OpenAI Account to get your own API key, click menu on the top left and input your API Key

FAQ
---

### Is it safe to login with my account in the app?

Yes, it is safe. There is no data transferred in the app (you can check the source). It's just a wrapper for teh popular Chat AI website. If you are still unsure, you can build your own binary and use it.

### I cannot open the MacOS app because developer cannot be verified?

1.  In the Finder on your Mac, locate the chat ai app. Don't use Launchpad to do this. Launchpad doesn't allow you to access the shortcut menu.
2.  Control-click the app icon, then choose Open from the shortcut menu.
3.  Click Open.

https://support.apple.com/en-sg/guide/mac-help/mh40616/mac

Recommended IDE Setup
---------------------

-   VS Code + Tauri + rust-analyzer

Developing
----------

```
yarn
yarn tauri dev
```

Building
--------

```
yarn
yarn tauri build
```
