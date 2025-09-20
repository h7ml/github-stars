---
project: core
stars: 807
description: React and HTML framework for Unity UI & UIToolkit
url: https://github.com/ReactUnity/core
---

React Unity
===========

React Unity is a way to build declarative UI in Unity3D using React. It can be used together with packages like Typescript, redux, i18next, react-router and more. It also supports a subset of CSS features and Flexbox layout system.

Requirements
------------

Node is only used while developing and not required in runtime or after the project is built. Following are the minimum recommended versions. Use latest stable versions when possible.

-   Node 20
-   Unity 2021.3
-   TMPro v3

Installing
----------

**Install via OpenUPM (recommended)**

```
npx openupm-cli add com.reactunity.core com.reactunity.quickjs
```

**Or add using the package manager with the git URL**

```
https://github.com/ReactUnity/core.git#latest
```

Usage
-----

-   Create a canvas and add `ReactRendererUGUI` component to it
-   Run `npx @reactunity/create@latest` in your Unity project root to create a React project
-   Install all dependencies `npm intall` from React project
-   Run `npm run start` from React project
-   Click play in Unity

Visit the documentation on the main website to learn more.

Known Issues
------------

-   Low documentation coverage

> Most of ReactUnity's features are not well documented yet. All questions, bug reports and requests are welcome. You can share them by opening issues or posting them in the Discord server.

Resources and References
------------------------

-   Sample Project
-   React Unity Renderer (npm package)
-   Acknowledgements
