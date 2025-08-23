---
project: electerm
stars: 12835
description: 📻Terminal/ssh/sftp/ftp/telnet/serialport/RDP/VNC client(linux, mac, win)
url: https://github.com/electerm/electerm
---

中文

electerm
========

Open-sourced terminal/ssh/telnet/serialport/RDP/VNC/sftp/ftp client(linux, mac, win).

Powered by manate

For experienced developers, you may try the web app version running in browser(including mobile device): electerm-web or docker image for electerm-web

Online demo: https://electerm-demo.html5beta.com

Features
--------

-   Works as a terminal/file manager or ssh/sftp/ftp/telnet/serialport/RDP/VNC client
-   Global hotkey to toggle window visibility (similar to guake, default is `ctrl + 2`)
-   Multi platform(linux, mac, win)
-   🇺🇸 🇨🇳 🇧🇷 🇷🇺 🇪🇸 🇫🇷 🇹🇷 🇭🇰 🇯🇵 🇸🇦 🇩🇪 🇰🇷 🇮🇩 🇵🇱 Multi-language support(electerm-locales, contributions/fixes welcome)
-   Double click to directly edit (small) remote files.
-   Auth with publicKey + password.
-   Support Zmodem(rz, sz).
-   Support ssh tunnel.
-   Support Trzsz(trz/tsz), similar to rz/sz, and compatible with tmux.
-   Transparent window(Mac, win).
-   Terminal background image.
-   Global/session proxy.
-   Quick commands
-   UI/terminal theme
-   Sync bookmarks/themes/quick commands to github/gitee secret gist
-   Quick input to one or all terminals.
-   AI assistant integration (supporting DeepSeek, OpenAI, and other AI APIs) to help with command suggestions, script writing, and explaining selected terminal content
-   Command line usage: check wiki

Download
--------

-   Homepage
-   sourceforge
-   github releases

Install
-------

-   For Mac user: `brew install --cask electerm`
-   With snap: `sudo snap install electerm --classic`
-   For some Linux distribution, you can find it from OS default App store(Ubuntu, Deepin, Mint...).
-   For some linux OS, the `rpm`, `deb`, or `snap` release may not work, you can try the `tar.gz` or `.appImage` release.
-   For Windows users, you can install it from windows store, command-line installer winget and scoop is also recommended:

# winget https://github.com/microsoft/winget-cli
winget install electerm.electerm

# scoop https://github.com/lukesampson/scoop
scoop bucket add dorado https://github.com/chawyehsu/dorado
scoop install dorado/electerm

-   Install from Debian repository (for Debian/Ubuntu-based systems) with `apt` command

Check https://electerm-repos.html5beta.com/deb

-   Install from npm

npm i -g electerm

# After installation, it will immediately open for windows and linux,
# For macOS, it will open the drag to install panel

Upgrade
-------

-   Auto upgrade: When a new version is released, you will get an upgrade notification after you start electerm again. You can then click the upgrade button to upgrade.
-   Download: Just download the latest edition, reinstall.
-   Npm: If you install from npm, just run `npm i -g electerm` again.
-   If use Snap or some other distribution system, these systems may provide upgrades.

Themes
------

-   https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/electerm
-   https://github.com/Hope-IT-Works/electerm-theme-termius

Known issues
------------

https://github.com/electerm/electerm/wiki/Know-issues

Troubleshoot
------------

https://github.com/electerm/electerm/wiki/Troubleshoot

Discussion
----------

Discussion board

Support
-------

Would love to hear from you, please tell me what you think, submit an issue, Start a new discussion, create/fix language files or create pull requests, all welcome.

Sponsor this project
--------------------

github sponsor

https://github.com/sponsors/electerm

kofi

https://ko-fi.com/zhaoxudong

wechat donate

Dev
---

# tested in ubuntu20.04+/mac os 10.13+ only
# needs nodejs/npm, suggest using fnm to install nodejs/npm
# with nodejs 22.x

git clone git@github.com:electerm/electerm.git
cd electerm
npm i

# start webpack dev server, requires port 5570
npm start

# in a separate terminal session run app
npm run app

# code format check
npm run lint

# code format fix
npm run fix

Test
----

npm run b
npm run prepare-test
cp .sample.env .env

# edit .env, fill your test host/username/password, may only works in mac OS
npm run test

Test build
----------

# Tested only in ubuntu 16.04 x64+
# Install yarn first(to do yarn autoclean)
# See https://yarnpkg.com/en/docs/install

# Build linux only with -l
npm i
npm run b
./node\_modules/.bin/electron-builder --linux tar.gz
# or replace tar.gz to rpm/deb/AppImage
# check dist/ folder

# build for linux arm/
./node\_modules/.bin/electron-builder --linux --arm64

Video guides
------------

-   bilibili

Change log
----------

Visit Releases.

License
-------

MIT

Star History
------------
