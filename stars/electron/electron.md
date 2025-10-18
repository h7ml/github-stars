---
project: electron
stars: 118710
description: :electron: Build cross-platform desktop apps with JavaScript, HTML, and CSS
url: https://github.com/electron/electron
---

📝 Available Translations: 🇨🇳 🇧🇷 🇪🇸 🇯🇵 🇷🇺 🇫🇷 🇺🇸 🇩🇪. View these docs in other languages on our Crowdin project.

The Electron framework lets you write cross-platform desktop applications using JavaScript, HTML and CSS. It is based on Node.js and Chromium and is used by the Visual Studio Code and many other apps.

Follow @electronjs on Twitter for important announcements.

This project adheres to the Contributor Covenant code of conduct. By participating, you are expected to uphold this code. Please report unacceptable behavior to coc@electronjs.org.

Installation
------------

To install prebuilt Electron binaries, use `npm`. The preferred method is to install Electron as a development dependency in your app:

npm install electron --save-dev

For more installation options and troubleshooting tips, see installation. For info on how to manage Electron versions in your apps, see Electron versioning.

Platform support
----------------

Each Electron release provides binaries for macOS, Windows, and Linux.

-   macOS (Big Sur and up): Electron provides 64-bit Intel and Apple Silicon / ARM binaries for macOS.
-   Windows (Windows 10 and up): Electron provides `ia32` (`x86`), `x64` (`amd64`), and `arm64` binaries for Windows. Windows on ARM support was added in Electron 5.0.8. Support for Windows 7, 8 and 8.1 was removed in Electron 23, in line with Chromium's Windows deprecation policy.
-   Linux: The prebuilt binaries of Electron are built on Ubuntu 20.04. They have also been verified to work on:
    -   Ubuntu 18.04 and newer
    -   Fedora 32 and newer
    -   Debian 10 and newer

Electron Fiddle
---------------

Use `Electron Fiddle` to build, run, and package small Electron experiments, to see code examples for all of Electron's APIs, and to try out different versions of Electron. It's designed to make the start of your journey with Electron easier.

Resources for learning Electron
-------------------------------

-   electronjs.org/docs - All of Electron's documentation
-   electron/fiddle - A tool to build, run, and package small Electron experiments
-   electronjs.org/community#boilerplates - Sample starter apps created by the community

Programmatic usage
------------------

Most people use Electron from the command line, but if you require `electron` inside your **Node app** (not your Electron app) it will return the file path to the binary. Use this to spawn Electron from Node scripts:

const electron \= require('electron')
const proc \= require('node:child\_process')

// will print something similar to /Users/maf/.../Electron
console.log(electron)

// spawn Electron
const child \= proc.spawn(electron)

### Mirrors

-   China

See the Advanced Installation Instructions to learn how to use a custom mirror.

Documentation translations
--------------------------

We crowdsource translations for our documentation via Crowdin. We currently accept translations for Chinese (Simplified), French, German, Japanese, Portuguese, Russian, and Spanish.

Contributing
------------

If you are interested in reporting/fixing issues and contributing directly to the code base, please see CONTRIBUTING.md for more information on what we're looking for and how to get started.

Community
---------

Info on reporting bugs, getting help, finding third-party tools and sample apps, and more can be found on the Community page.

License
-------

MIT

When using Electron logos, make sure to follow OpenJS Foundation Trademark Policy.
