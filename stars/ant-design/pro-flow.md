---
project: pro-flow
stars: 337
description: 🪢 A React based Flow Framework, include Flow View and Flow Editor
url: https://github.com/ant-design/pro-flow
---

ProFlow
=======

A Flow Editor Framework base on React-Flow.

  
  

English · 简体中文 · Changelog . Report Bug · Request Feature

Table of contents

#### TOC

-   📦 Installation
    -   Compile with Next.js
-   ✨ Features
-   🔨 Usage
    -   Add Data
    -   Add Interaction
-   🖥 Browser compatibility
-   ⌨️ Local Development
-   🤝 Contributing
-   🛣️ Ecosystem

📦 Installation
---------------

Important

This package is ESM only.

To install `@ant-design/pro-flow`, run the following command:

$ pnpm install @ant-design/pro-flow

### Compile with Next.js

Note

By work correct with Next.js SSR, add `transpilePackages: ['@ant-design/pro-flow']` to `next.config.js`. For example:

const nextConfig \= {
  transpilePackages: \['@ant-design/pro-flow'\],
};

  

✨ Features
----------

Note

ProFlow focuses on quickly setting up a flow node-editor framework. It aims to empower developers to easily create rich, dynamic, and intuitive flow editor interfaces.

**ProFlow is a canvas editor built on react-flow. It has the following features:**

-   💠 **Modern Node Design**: It features modern default nodes and grouped node components, making the interface more intuitive, readable, and user-friendly.
-   🌐 **Out-of-the-box Components**: It supports components such as MiniMap, Inspector, and Loading, providing rich extension capabilities and customization options, allowing users to easily customize the canvas interface.
-   🎨 **Automatic Layout Algorithm**: It comes with the dagre layout algorithm, allowing users to achieve automatic layout effects with just nodes and relationships, making it easy to achieve an aesthetically pleasing presentation of flowcharts.
-   🖱️ **Flowchart Data Manipulation**: It provides the useFlowViewer feature, allowing users to easily manipulate and manage canvas-related data, achieving a personalized interactive experience.
-   🧩 **Custom Nodes and Edges**: It supports the ability to customize nodes, custom edges, and provides additional attributes such as label, zoom, and selectType to meet personalized customization needs.
-   📱 **Mobile-Friendly**: It defaults to providing touchpad interactive canvas logic in figma mode, adapting to mobile operations for a smoother user experience.
-   🎨 **Canvas Editor Capabilities**: It provides out-of-the-box canvas editor capabilities, including rich canvas and node operation functions such as copy-paste, undo-redo, enhancing user operation efficiency and convenience.

  

🔨 Usage
--------

import { FlowView } from '@ant-design/pro-flow';

function App() {
  const { styles } \= useStyles();

  return (
    <div className\={'container'}\>
      <FlowView nodes\={\[\]} edges\={\[\]} />
    </div\>
  );
}

export default App;

### Add Data

export const nodes \= \[
  {
    id: 'a1',
    data: {
      title: 'XXX\_API\_a1',
      logo: 'https://mdn.alipayobjects.com/huamei\_ntgeqc/afts/img/A\*kgyiRKi04eUAAAAAAAAAAAAADvuvAQ/original',
      description: 'XXX\_XXX\_XXX\_API',
    },
  },
  {
    id: 'a2',
    data: {
      title: 'XXX\_API\_a2',
      logo: 'https://mdn.alipayobjects.com/huamei\_ntgeqc/afts/img/A\*kgyiRKi04eUAAAAAAAAAAAAADvuvAQ/original',
      description: 'XXX\_XXX\_XXX\_API',
    },
  },
  {
    id: 'a3',
    data: {
      title: 'XXX\_API\_a3',
      logo: 'https://mdn.alipayobjects.com/huamei\_ntgeqc/afts/img/A\*kgyiRKi04eUAAAAAAAAAAAAADvuvAQ/original',
      description: 'XXX\_XXX\_XXX\_API',
    },
  },
\];
export const edges \= \[
  {
    id: 'a1-a2',
    source: 'a1',
    target: 'a2',
  },
  {
    id: 'a1-a3',
    source: 'a1',
    target: 'a3',
    type: 'radius',
  },
\];

### Add Interaction

import { FlowView } from '@ant-design/pro-flow';
import useStyles from './css/index.style';
import { edges, nodes } from './data';

function App() {
  const { styles } \= useStyles();

  return (
    <div className\={styles.container}\>
      <FlowView nodes\={nodes} edges\={edges} />
    </div\>
  );
}

export default App;

  

🖥 Browser compatibility
------------------------

Note

-   Modern browsers and Internet Explorer 11 (with polyfills)
-   Electron

Edge

last 2 versions

last 2 versions

last 2 versions

last 2 versions

  

⌨️ Local Development
--------------------

You can use Github Codespaces for online development:

Or clone it for local development:

$ git clone https://github.com/ant-design/pro-flow.git
$ cd pro-flow
$ pnpm install
$ pnpm dev

  

🤝 Contributing
---------------

Important

Join our collaborative ecosystem. Your contributions are the heartbeat of our project. Here's how you can be an integral part of our vibrant community:

-   **Integrate and Innovate**: Incorporate Ant Design Pro, umi, and ProFlow into your projects. Your real-world usage and feedback are invaluable to us.
-   **Voice Your Insights**: Encounter a glitch? Have a query? Your perspectives matter. Share them by submitting issues and help us enhance the user experience.
-   **Shape the Future**: Have code enhancements or feature ideas? We invite you to propose pull requests and contribute directly to the evolution of our codebase.

Every contribution, big or small, is celebrated. Join us in our mission to refine and elevate the world of open-source enterprise UI components. 😃

  
  
  

  

🛣️ Ecosystem
-------------

-   **ProComponents** - Designed for Enterprise-Level Application, Use Ant Design like a Pro!.
-   **ProEditor** - The Ultimate Editor UI Framework and Components.
-   **ProFlow** - A Flow Editor Framework base on React-Flow.
-   **ProChat** - Components Library for Quickly Building LLM Chat Interfaces.

  

* * *

#### 📝 License

Copyright © 2023 - present AFX & Ant Digital.  
This project is MIT licensed.
