---
project: next
stars: 4653
description: 🦍 A configurable component library for web built on React. 
url: https://github.com/alibaba-fusion/next
---

English | 简体中文

An enterprise-class UI solution for backend system, aimed at settling the problems like cooperation between designers and front-developers, consistency of product experience and development efficiency.

* * *

You can customize your own DesignSystem via Collaboration Platform.💖 Designers will receive design materials by Fusion Cool - an easy to use plugin on sketch. Developers will get code fragment on IceWorks. At the same time, the consistency between code and visual manuscript is guaranteed. 😍

🤔 Why use
==========

`@alifd/next` usually used with Fusion Design to improving designer-developer collaboration and development efficiency. Designer can customize the UI of components and release an npm theme package. Developer can use this theme package directly, and don't need to care about the UI refactoring. It saves the workload of reductive degree review repeatedly with designers, and greatly improves the development efficiency.

💻 Browser Compatibility
========================

✔

✔

✔

9+ ✔

✔

✔

✔

🚀 Quick Start
==============

🛠 Install
----------

### 1.Use NPM ( Recommend )

```
npm install @alifd/next --save
```

### 2.Import in Browser

Use the script and link tags in the browser to directly import the file and use the global variable Next. We provide files such as next.js/next.min.js and next.css/next.min.css in the `@alifd/next/dist` directory in the npm package, or via unpkg Download it.

<link rel\="stylesheet" href\="https://unpkg.com/@alifd/next/dist/next.css" />

<script src\="https://unpkg.com/@alifd/next/dist/next.js"\></script\>

// The above ways import latest @alifd/next, we recommend you specify version.
<script src\="https://unpkg.com/@alifd/next@1.8.6/dist/next.min.js"\></script\>

// Or import as your own static resource
<script src\="../build/public/@alifd/next.js"\></script\>

☔️ Dependencies
---------------

-   `@alifd/next` is based on `react@16` development and is currently not compatible with versions below `react@16`. react/react-dom is used as peerDependencies, which requires the user to manually install or import it.
-   `@alifd/next` use moment library to implement date-time related component. moment is also used as peerDependencies, which requires the user to manually install or import it.

🎯 Import
---------

### Import All

import '@alifd/next/dist/next.css';
// import '@alifd/next/index.scss';

import { Button, Input } from '@alifd/next';

### Import module with plugin

#### 1\. Import module manually

import Button from '@alifd/next/lib/button';
import '@alifd/next/lib/button/style';

#### 2\. Use with babel-plugin-import ( Recommend )

// webpack babel loader option or .babelrc
{
    // ...
    plugins: \[
        \[
            'import',
            {
                libraryName: '@alifd/next',
                style: true,
            },
        \],
    \];
}

It will transform code as below

import { Button } from '@alifd/next';

To

import Button from '@alifd/next/lib/button';
import '@alifd/next/lib/button/style';

🔗 Advanced
-----------

-   Use with Theme Package
-   Internationalization
-   Deploy Font File

🌈 Contributing
---------------

Use Gitpod, a free online dev environment for GitHub.

Or clone locally:

-   Contributing

📣 Join Group
-------------

Use Dingtalk App scan the Qrcode to join in _Dingtalk Group_ :
