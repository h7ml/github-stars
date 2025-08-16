---
project: fingerprint-chromium
stars: 1094
description: An open source fingerprint browser based on Ungoogled Chromium. 指纹浏览器 隐私浏览器
url: https://github.com/adryfish/fingerprint-chromium
---

fingerprint-chromium
====================

中文文档

_A fingerprint browser based on `Ungoogled Chromium`._

Installation and Usage
----------------------

### Download

Please download the version suitable for your system from the links below. Each major version of Chromium is compiled into a corresponding release. Choose the appropriate version for your operating system:

**Version**

**Source Code**

**Windows**

**Linux**

**MacOS**

**Chrome 138**

Released with Chrome 139

Installer  
ZIP

138.0.7204.183-1\_linux.tar.xz

**Chrome 136**

136.0.7103.113

Installer  
ZIP

136.0.7103.113-1\_linux.tar.xz

136.0.7103.113-1.1\_macos.dmg

**Chrome 135**

135.0.7049.95

Installer  
ZIP

135.0.7049.95-1\_linux.tar.xz

135.0.7049.95-1.1\_macos.dmg

**Chrome 134**

134.0.6998.165

Installer  
ZIP

134.0.6998.165-1\_linux.tar.xz

**Chrome 133**

133.0.6943.126

Installer  
ZIP

133.0.6943.126-1\_linux.tar.xz

**Chrome 132**

132.0.6834.159

Installer  
ZIP

132.0.6834.159-1\_linux.tar.xz

132.0.6834.110-1.1\_macos.dmg

For chinese users, you can download via cloud storage

Quark: https://pan.quark.cn/s/9bb65af874fb

* * *

You can find the compiled versions for each major Chromium release on the GitHub Release page. Download the appropriate file for your platform.

### Build from Source

**SOURCE CODE IS AVAILABLE IN THE GITHUB REPOSITORY TAGS, NOT IN THE MAIN BRANCH!**

To maintain the integrity of this free and open source project, we've adopted a delayed source code release policy:

-   **Current Version**: Compiled binaries are immediately available for all users
-   **Source Code**: patch files will be released when the next version is published (typically one month later)

This approach helps prevent unauthorized repackaging and profiteering from our work while maintaining our open source commitment.

Once the source code is released, you can build by referring to the `ungoogled-chromium` documentation. Simply replace the `ungoogled-chromium` submodule URL with the `fingerprint-browser` repository URL.

📢 Advertisement for Chinese Users
----------------------------------

**🌟 EasyChat - Claude Mirror Site**

Access Claude's AI services seamlessly:

-   🆓 **Free to Use**: No registration required, one click to use
-   🌐 **Direct Access**: Optimized for stable China access
-   👥 **Shared Membership**: Use Claude Team features without account ban risks

🔗 **Visit now**: https://easychat.top

**🛠️ Flapcode**

A one-stop solution designed for users who need Claude Code but prefer not to self-host.

**Core Advantages:**

-   🌐 **Direct China Access**: Access full Claude Code functionality at high speed without VPN
-   🤝 **Full Max Account**: Enjoy complete model experience without usage limitations
-   💰 **Simple & Transparent Billing**: Same pricing as official API, daily usage updates
-   🔒 **Safe & Reliable**: Professional ops team ensures service stability, letting you focus on development

🔗 **Visit now**: https://flapcode.com

Features
--------

### Fingerprint Support

You can use creepjs and browserleaks to test fingerprint modification effects.

-   **User-Agent**: Modify the browser's `navigator.userAgent`, `navigator.platform`, `navigator.userAgentData` and `Client Hints` information.
-   **Operating System**
-   **Audio**
-   **Plugins**: After removal in version 133+, the browser returns a fixed plugin list.
-   **CPU Cores**
-   **Memory**
-   **WebGL Image**
-   **WebGL Metadata**: Modify GPU vendor and graphics card model (currently only supports Linux).
-   **Fonts**
-   **Canvas Image**
-   **Canvas Text**
-   **ClientRects**
-   **WebRTC**
-   **Language Support**
-   **Timezone Support**

### Automation Support

**Optimized for automation scenarios, offering the following features:**

1.  **Fake Shadow DOM Support**  
    Adds the `fakeShadowRoot` property, equivalent to the `shadowRoot` property, enabling access to Closed Shadow Root for easier automation handling.
    
2.  **Avoid CDP Detection**  
    Prevents Chrome DevTools Protocol (CDP) detection when invoking `Runtime.enable`, enhancing stealthiness for automation tools.
    
3.  **Webdriver**  
    Sets `navigator.webdriver` to false to avoid detection of automation tools.
    
4.  **Headless**  
    Only changes `User-Agent` from `HeadlessChrome` to `Chrome`. Other headless characteristics remain unchanged, use with caution.
    

### Enabling Fingerprint Features with Command Line Arguments

You can enable or customize fingerprinting and privacy protection features by passing command line arguments when launching the browser:

**Command Line Argument**

**Description**

**Examples**

**`--fingerprint`**

Specifies the fingerprint seed. When enabled, most fingerprinting features take effect

32-bit integer

**`--fingerprint-platform`**

Specifies the operating system type

`windows`, `linux`, `macos`

**`--fingerprint-platform-version`**

Specifies the operating system version

Uses default version if not specified

**`--fingerprint-brand`**

Specifies the browser brand in `User-Agent` and `User-Agent Data`

Chrome, Edge, Opera, Vivaldi (default is Chrome)

**`--fingerprint-brand-version`**

Specifies the version number for the browser brand

Uses default version if not specified

**`--fingerprint-hardware-concurrency`**

Specifies the number of CPU cores

Integer value (randomly generated from fingerprint seed if not provided)

**`--disable-non-proxied-udp`**

Specifies WebRTC policy, by default non-proxied UDP connections are disabled

Recommended to keep default setting

**`--lang`**

Sets the browser language

Language code (e.g., `en-US`)

**`--accept-lang`**

Sets the languages accepted by the browser

Language codes (e.g., `en-US,en`)

**`--timezone`**

timezone

Timezone (e.g., `Asia/Shanghai`, `UTC`)

**`--proxy-server`**

proxy server

`http`, `socks` proxy (password authentication not supported)

### **New User-Agent Customization Command Line Arguments**

Chrome 131 introduces two new command line arguments for advanced customization of `User-Agent` and `User-Agent Data`:

-   **`--fingerprint-brand`**
    
    -   Specifies the browser brand used in `User-Agent` and `User-Agent Data`.
    -   Supported values: `Chrome`, `Edge`, `Opera`, `Vivaldi`, or custom brand names.
-   **`--fingerprint-brand-version`**
    
    -   Specifies the version number for the specified brand.
    -   Default values: `Chrome`, `Edge`, `Opera`, `Vivaldi` all provide default versions, custom versions can also be passed.

These arguments enhance browser environment simulation capabilities, suitable for automation and testing scenarios. If `--fingerprint-brand` is not specified, the default brand will be used.

Usage Examples
--------------

Here are command line examples for several common use cases:

### Basic Usage

./chrome --fingerprint=1000 --user-data-dir=/tmp/chromium/1000 --timezone="America/Los\_Angeles" --proxy-server="your\_proxy\_server\_address"

### Customizing User-Agent

chrome.exe --fingerprint=2023 --fingerprint-platform=macos --fingerprint-platform-version="15.2.0" --fingerprint-brand="Edge"  --user-data-dir=%TEMP%\\chromium

### Fingerprint Testing

Testing Platform

Status

**CreepJS**

✔️ 51.5%.

**BrowserScan**

✔️ 100%. Pass all detections.

**BrowserLeaks**

✔️ Supports multiple fingerprint leak detection

**Cloudflare**

✔️

‣ Turnstile

✔️

User Communication
------------------

Scan the QR code to join the QQ group to communicate with other users.

If you need Chrome customization development services or are looking for custom development opportunities, the group owner can help connect you with relevant resources:

Credits
-------

-   Ungoogled Chromium

License
-------

BSD-3-clause. See LICENSE
