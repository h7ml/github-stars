---
project: editor
stars: 750
description: Browser-based visual editor for building WebGL, WebGPU, WebXR apps
url: https://github.com/playcanvas/editor
---

PlayCanvas Editor
=================

| User Manual | API Reference | Blog | Forum |

The PlayCanvas Editor is a visual editing environment for building WebGL/WebGPU/WebXR apps. It can be accessed at https://playcanvas.com.

You can see more projects build using the Editor on the PlayCanvas website.

Local Development
-----------------

To initialize a local development environment for the Editor Frontend, ensure you have Node.js 18 or later installed. Follow these steps:

1.  Clone the repository:
    
    git clone https://github.com/playcanvas/editor.git
    cd editor
    
2.  Install dependencies:
    
    npm install
    
3.  Build Editor and start a local web server on port 51000:
    
    npm run develop
    
4.  Append the query parameter `use_local_frontend` to load the development build:
    
    ```
    https://playcanvas.com/editor/project/2535?use_local_frontend
    ```
    

Note

This query parameter is also supported in the code editor and launch page

Library integration testing
---------------------------

The Editor is built on the following open source libraries:

Library

Details

PlayCanvas Engine

Powers the Editor's 3D View and Launch Page

Observer

Data binding and history

PCUI

Front-end component library

PCUI-Graph

PCUI plugin for rendering node-based graphs

Editor API

Public API for Editor automation

To test the integration of these libraries use npm link. Follow these steps:

1.  Create a global link from source
    
    cd <library\>
    npm link
    
2.  Create a link to the global link
    
    cd editor
    npm link <library\>
