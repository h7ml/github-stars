---
project: san-devtools
stars: 82
description: Browser developer tools extension for debugging San.
url: https://github.com/baidu/san-devtools
---

San DevTools
============

Development tool for debugging San.js applications.

It is exists both as a browser extension and as a common line tool(works with other environments including Safari, IE, San Native and Electron.)

🎉 Features
-----------

-   Provide local server command, support remote debugging.
-   Built in Chrome Devtools for remote debug mobile page.
-   Provide Chrome Extension.
-   Support `San Native` debugging (waiting for release).

📦 Installation
---------------

### standalone

The standalone version exists as a command line tool, and install from NPM or Yarn.

npm i -g san-devtools 
# OR
yarn global add san-devtools

### chrome extension

Get the Chrome Extension

OR

Navigate to chrome://extensions in Chrome/Chromium to load the unpacked extension from dist directory.

📖 Document
-----------

中文文档

🤝 Quick Start
--------------

### standalone

**First:** Start debugging server, and will auto open the remote inspector.

sand # short for san-devtools
# OR
san-devtools

**Second:** Add `ws-backend.js` to the top of the debugging page（before san.js).

**Third:** Open the debugging page, and inspector page will auto connected.

### chrome extension

Open the debugging page and san-devtools plugin will show the San version, then open the chrome devtool and will see the San tab.

#### sand options

-   \--open, -o: Open browser when server start(default: true)
-   \--port, -p: Port to use (default: 8899)
-   \--address, -a: Address to use
-   \--version, -v: Show version number
-   \--help, -h: Show help

🍻 Companions
-------------

-   san-devtools - Chrome DevTools extension
-   san-router - SPA Router
-   san-store - Application States Management
-   san-update - Immutable Data Update
-   san-factory - Component register and instantiation
-   santd - Components Library following the Ant Design specification
-   san-mui - Material Design Components Library
-   san-xui - A Set of SAN UI Components that widely used on Baidu Cloud Console
-   drei - VSCode extension for SAN
-   san-cli - A CLI tooling based on SAN for rapid development
-   san-test-utils - The unit testing utility library for SAN
-   san-loader - Webpack loader for single-file SAN components
-   san-hot-loader - Webpack loader for SAN components HMR

☀️ License
----------

MIT
