---
project: vega
stars: 11279
description: A visualization grammar.
url: https://github.com/vega/vega
---

Vega: A Visualization Grammar
=============================

**Vega** is a _visualization grammar_, a declarative format for creating, saving, and sharing interactive visualization designs. With Vega you can describe data visualizations in a JSON format, and generate interactive views using either HTML5 Canvas or SVG.

For documentation, tutorials, and examples, see the Vega website. For a description of changes between Vega 2 and later versions, please refer to the Vega Porting Guide.

Build Instructions
------------------

For a basic setup allowing you to build Vega and run examples:

-   Clone `https://github.com/vega/vega`.
-   Run `yarn` to install dependencies for all packages. If you don't have yarn installed, see https://yarnpkg.com/en/docs/install. We use Yarn workspaces to manage multiple packages within this monorepo.
-   Once installation is complete, run `yarn test` to run test cases, or run `yarn build` to build output files for all packages.
-   After running either `yarn test` or `yarn build`, run `yarn serve` to launch a local web server — your default browser will open and you can browse to the `"test"` folder to view test specifications.

This repository includes the Vega website and documentation in the `docs` folder. To launch the website locally, first run `bundle install` in the `docs` folder to install the necessary Jekyll libraries. Afterwards, use `yarn docs` to build the documentation and launch a local webserver. After launching, you can open `http://127.0.0.1:4000/vega/` to see the website.

Internet Explorer Support
-------------------------

For backwards compatibility, Vega includes a babel-ified IE-compatible version of the code in the `packages/vega/build-es5` directory. Older browser would also require several polyfill libraries:

<script src\="https://cdnjs.cloudflare.com/ajax/libs/babel-polyfill/7.4.4/polyfill.min.js"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/regenerator-runtime@0.13.3/runtime.min.js"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/whatwg-fetch@3.0.0/dist/fetch.umd.min.js"\></script\>

Contributions, Development, and Support
---------------------------------------

Interested in contributing to Vega? Please see our contribution and development guidelines, subject to our code of conduct.

Looking for support, or interested in sharing examples and tips? Post to the Vega discussion forum or join the Vega slack organization! We also have examples available as Observable notebooks.

If you're curious about system performance, see some in-browser benchmarks. Read about future plans in our roadmap.
