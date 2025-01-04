---
project: Xray-core
stars: 26499
description: Xray, Penetrates Everything. Also the best v2ray-core, with XTLS support. Fully compatible configuration.
url: https://github.com/XTLS/Xray-core
---

Project X
=========

Project X originates from XTLS protocol, providing a set of network tools such as Xray-core and REALITY.

README is open, so feel free to submit your project here.

Donation & NFTs
---------------

-   **ETH/USDT/USDC: `0xDc3Fe44F0f25D13CACb1C4896CD0D321df3146Ee`**
-   **Project X NFT: Announcement of NFTs by Project X**
-   **REALITY NFT: XHTTP: Beyond REALITY**

License
-------

Mozilla Public License Version 2.0

Documentation
-------------

Project X Official Website

Telegram
--------

Project X

Project X Channel

Project VLESS (non-Chinese)

Installation
------------

-   Linux Script
    -   XTLS/Xray-install (**Official**)
    -   tempest (supports `systemd` and OpenRC; Linux-only)
-   Docker
    -   ghcr.io/xtls/xray-core (**Official**)
    -   teddysun/xray
    -   wulabing/xray\_docker
-   Web Panel - **WARNING: Please DO NOT USE plain HTTP panels like 3X-UI**, as they are believed to be bribed by Iran GFW for supporting plain HTTP by default and refused to change (#3884 (comment)), which has already put many users' data security in danger in the past few years. **If you are already using 3X-UI, please switch to the following panels, which are verified to support HTTPS and SSH port forwarding only:**
    -   Marzban
    -   Xray-UI
    -   Hiddify
-   One Click
    -   Xray-REALITY, xray-reality, reality-ezpz
    -   Xray\_bash\_onekey, XTool
    -   v2ray-agent, Xray\_onekey, ProxySU
-   Magisk
    -   Xray4Magisk
    -   Xray\_For\_Magisk
-   Homebrew
    -   `brew install xray`

Usage
-----

-   Example
    -   VLESS-XTLS-uTLS-REALITY
    -   VLESS-TCP-XTLS-Vision
    -   All-in-One-fallbacks-Nginx
-   Xray-examples
    -   XTLS/Xray-examples
    -   chika0801/Xray-examples
    -   lxhao61/integrated-examples
-   Tutorial
    -   XTLS Vision
    -   REALITY (English)
    -   XTLS-Iran-Reality (English)
    -   Xray REALITY with 'steal oneself' (English)
    -   Xray with WireGuard inbound (English)

GUI Clients
-----------

-   OpenWrt
    -   PassWall, PassWall 2
    -   ShadowSocksR Plus+
    -   luci-app-xray (openwrt-xray)
-   Windows
    -   v2rayN
    -   Furious
    -   Invisible Man - Xray
-   Android
    -   v2rayNG
    -   X-flutter
    -   SaeedDev94/Xray
-   iOS & macOS arm64
    -   FoXray
    -   Streisand
-   macOS arm64 & x64
    -   V2rayU
    -   V2RayXS
    -   Furious
    -   FoXray
-   Linux
    -   v2rayA
    -   Furious

Others that support VLESS, XTLS, REALITY, XUDP, PLUX...
-------------------------------------------------------

-   iOS & macOS arm64
    -   Shadowrocket
-   Xray Tools
    -   xray-knife
-   Xray Wrapper
    -   XTLS/libXray
    -   xtlsapi
    -   AndroidLibXrayLite
    -   Xray-core-python
    -   xray-api
-   XrayR
    -   XrayR-release
    -   XrayR-V2Board
-   Clash.Meta
    -   clashN
    -   Clash Meta for Android
-   sing-box

Contributing
------------

Code of Conduct

Credits
-------

-   Xray-core v1.0.0 was forked from v2fly-core 9a03cc5, and we have made & accumulated a huge number of enhancements over time, check the release notes for each version.
-   For third-party projects used in Xray-core, check your local or the latest go.mod.

Compilation
-----------

### Windows (PowerShell)

$env:CGO\_ENABLED\=0
go build \-o xray.exe \-trimpath \-ldflags "\-s -w -buildid=" ./main

### Linux / macOS

CGO\_ENABLED=0 go build -o xray -trimpath -ldflags "\-s -w -buildid=" ./main

### Reproducible Releases

make

Stargazers over time
--------------------
