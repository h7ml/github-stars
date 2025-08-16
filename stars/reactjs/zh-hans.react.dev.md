---
project: zh-hans.react.dev
stars: 961
description: React documentation website in Simplified Chinese
url: https://github.com/reactjs/zh-hans.react.dev
---

React 中文文档
==========

此仓库包含 React 中文文档 的文档及源码，并由官方实时同步。

参与贡献
----

目前，大部分的翻译工作都已经完成。现在主要工作是同步和完善已有翻译。

**参与贡献前，请仔细阅读 React 中文文档译文规范**。

* * *

react.dev
=========

This repo contains the source code and documentation powering react.dev.

Getting started
---------------

### Prerequisites

1.  Git
2.  Node: any version starting with v16.8.0 or greater
3.  Yarn: See Yarn website for installation instructions
4.  A fork of the repo (for any contributions)
5.  A clone of the react.dev repo on your local machine

### Installation

1.  `cd react.dev` to go into the project root
2.  `yarn` to install the website's npm dependencies

### Running locally

1.  `yarn dev` to start the development server (powered by Next.js)
2.  `open http://localhost:3000` to open the site in your favorite browser

Contributing
------------

### Guidelines

The documentation is divided into several sections with a different tone and purpose. If you plan to write more than a few sentences, you might find it helpful to get familiar with the contributing guidelines for the appropriate sections.

### Create a branch

1.  `git checkout main` from any folder in your local `react.dev` repository
2.  `git pull origin main` to ensure you have the latest main code
3.  `git checkout -b the-name-of-my-branch` (replacing `the-name-of-my-branch` with a suitable name) to create a branch

### Make the change

1.  Follow the "Running locally" instructions
2.  Save the files and check in the browser
3.  Changes to React components in `src` will hot-reload
4.  Changes to markdown files in `content` will hot-reload
5.  If working with plugins, you may need to remove the `.cache` directory and restart the server

### Test the change

1.  If possible, test any visual changes in all latest versions of common browsers, on both desktop and mobile.
2.  Run `yarn check-all`. (This will run Prettier, ESLint and validate types.)

### Push it

1.  `git add -A && git commit -m "My message"` (replacing `My message` with a commit message, such as `Fix header logo on Android`) to stage and commit your changes
2.  `git push my-fork-name the-name-of-my-branch`
3.  Go to the react.dev repo and you should see recently pushed branches.
4.  Follow GitHub's instructions.
5.  If possible, include screenshots of visual changes. A preview build is triggered after your changes are pushed to GitHub.

Translation
-----------

If you are interested in translating `react.dev`, please see the current translation efforts here.

License
-------

Content submitted to react.dev is CC-BY-4.0 licensed, as found in the LICENSE-DOCS.md file.
