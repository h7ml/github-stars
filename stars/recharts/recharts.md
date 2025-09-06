---
project: recharts
stars: 25866
description: Redefined chart library built with React and D3
url: https://github.com/recharts/recharts
---

Recharts
========

Introduction
------------

Recharts is a **Redefined** chart library built with React and D3.

The main purpose of this library is to help you to write charts in React applications without any pain. Main principles of Recharts are:

1.  **Simply** deploy with React components.
2.  **Native** SVG support, lightweight with minimal dependencies.
3.  **Declarative** components.

Documentation at recharts.org and our storybook

Also see the wiki.

All development is done on the `main` branch. The current latest release and storybook documentation reflects what is on the `release` branch.

Examples
--------

<LineChart width\={400} height\={400} data\={data}\>
  <XAxis dataKey\="name" />
  <Tooltip />
  <CartesianGrid stroke\="#f5f5f5" />
  <Line type\="monotone" dataKey\="uv" stroke\="#ff7300" />
  <Line type\="monotone" dataKey\="pv" stroke\="#387908" />
</LineChart\>

All the components of Recharts are clearly separated. The LineChart is composed of x axis, tooltip, grid, and line items, and each of them is an independent React Component. The clear separation and composition of components is one of the principle Recharts follows.

Installation
------------

### npm

NPM is the easiest and fastest way to get started using Recharts. It is also the recommended installation method when building single-page applications (SPAs). It pairs nicely with a CommonJS module bundler such as Webpack.

# latest stable
$ npm install recharts react-is

`react-is` needs to match the version of your installed `react` package.

### umd

The UMD build is also available on unpkg.com:

<script src\="https://unpkg.com/react/umd/react.production.min.js"\></script\>
<script src\="https://unpkg.com/react-dom/umd/react-dom.production.min.js"\></script\>
<script src\="https://unpkg.com/react-is/umd/react-is.production.min.js"\></script\>
<script src\="https://unpkg.com/recharts/umd/Recharts.min.js"\></script\>

Then you can find the library on `window.Recharts`.

Contributing
------------

Recharts is open source. If you want to contribute to the project, please read the CONTRIBUTING.md to understand how to contribute to the project and DEVELOPING.md to set up your development environment.

Thanks
------

Thanks to Chromatic for providing the visual testing platform that helps us review UI changes and catch visual regressions.

Thanks to JetBrains for providing OSS development license for their IDEs.

License
-------

MIT

Copyright (c) 2015-2024 Recharts Group.
