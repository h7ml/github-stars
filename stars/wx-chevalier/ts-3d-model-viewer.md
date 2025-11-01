---
project: ts-3d-model-viewer
stars: 213
description: 整合了 google-model-viewer/WebGL/Three.js/WASM 等一系列 3D 模型（STL/OBJ/GLTF/PLY/STEP/X_T）预览工具，便捷地进行模型预览、生成截图、计算拓扑信息。支持 Blender 进行模型压缩优化，提供了基于 Web 的简单 CAD 在线排版操作。
url: https://github.com/wx-chevalier/ts-3d-model-viewer
---

  

### @m-fe/react-model-viewer

STL 3D 预览  
**Explore the docs »**  
  
View Demo · Report Bug · Request Feature

Introduction
============

整合了 `google-model-viewer` 等一系列 3D 模型预览工具，便捷地进行模型预览、生成截图、计算拓扑信息。

> 模板来自于 m-fe-libs。

Getting Started
===============

To get a local copy up and running follow these simple steps.

Installation
------------

Install NPM packages

npm install @m-fe/react-model-viewer
# or
yarn add @m-fe/react-model-viewer

Usage
-----

### GoogleModelViewer

Add the `<model-viewer>`

```
<script type="module" src="https://unpkg.com/@google/model-viewer/dist/model-viewer.js"></script>
<script nomodule src="https://unpkg.com/@google/model-viewer/dist/model-viewer-legacy.js"></script>
```

import \* as React from "react";

import { GoogleModelViewer } from "@m-fe/react-model-viewer";

export default function Simple() {
  return (
    <div\>
      <GoogleModelViewer
        key\="1"
        type\="gltf"
        src\="https://cdn.glitch.com/36cb8393-65c6-408d-a538-055ada20431b/Astronaut.glb?1542147958948"
      /\>
      <GoogleModelViewer
        key\="2"
        type\="stl"
        src\="https://ufc-assets.oss-cn-shanghai.aliyuncs.com/test/pr2\_head\_pan.stl"
        onTopology\={(m) \=> {
          console.log(m);
        }}
      /\>
    </div\>
  );
}

### WebGLViewer

<WebGLViewer
  key\="33"
  type\="stl"
  src\="/error.stl"
  width\={600}
  height\={400}
  onTopology\={(m) \=> {
    // console.log(m);
  }}
  onZip\={(b) \=> {
    // 执行解压缩
    const modelArray: Uint8Array \= pako.inflate(new Uint8Array(b));
    console.log(modelArray);
  }}
  onError\={(err) \=> {
    console.log(err);
  }}
/>

### WasmViewer

About
=====

Roadmap
-------

See the open issues for a list of proposed features (and known issues).

-   https://github.com/josdirksen/threejs-cookbook/blob/master/06-particles-postprocessing/06.06-explode-geometry-model.html 添加爆炸模式
    
-   支持多个模型组同时加载，支持 OBJ/3MF 等原色渲染
    

Contributing
------------

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

License
-------

Distributed under the MIT License. See `LICENSE` for more information.

Acknowledgements
----------------

-   Awesome-Lists: 📚 Guide to Galaxy, curated, worthy and up-to-date links/reading list for ITCS-Coding/Algorithm/SoftwareArchitecture/AI. 💫 ITCS-编程/算法/软件架构/人工智能等领域的文章/书籍/资料/项目链接精选。
    
-   Awesome-CS-Books: 📚 Awesome CS Books/Series(.pdf by git lfs) Warehouse for Geeks, ProgrammingLanguage, SoftwareEngineering, Web, AI, ServerSideApplication, Infrastructure, FE etc. 💫 优秀计算机科学与技术领域相关的书籍归档。
    
-   UZIP.js #Project#: Simple ZIPping library for Javascript.
    

### Viewer

-   webgl-3d-viewer #Project#
    
-   参考设计：Sketchfab
    
-   xeogl #Project#: xeogl is a data-driven WebGL-based engine created by xeolabs for 3D visualization in the browser without using plugins.
    
-   Foxtrot #Project#: Foxtrot is a fast viewer for STEP files, a standard interchange format for mechanical CAD. It is an experimental project built from the ground up, including new libraries for parsing and triangulation.
    
-   f3d #Project#: A fast and minimalist 3D viewer.
    
-   mayo #Project#: 3D CAD viewer and converter based on Qt + OpenCascade
    
-   Online3DViewer #Project#: A free and open source web solution to visualize and explore 3D models right in your browser.
    

### Optimizer

-   meshoptimizer #Project#: Mesh optimization library that makes meshes smaller and faster to render

### Studio

-   jsketcher #Project#: JS.Sketcher is a parametric 2D and 3D CAD modeler written in pure javascript.
    
-   JSCAD #Project#: JSCAD (formally know as OpenJSCAD) provides a programmer’s approach to develop 3D models. In particular, this functionality is tuned towards creating precise models for 3D printing.
    
-   meshy #Project#: Slicing, measurements, transformations, and visualizations on polygon meshes.
    
-   CascadeStudio #Project#: A Full Live-Scripted CAD Kernel and IDE in the Browser.
    
-   Plasticity #Project#: Plasticity is a 3d modelling software for concept artists. Modelling in Plasticity is quick and efficient due to the unique gizmos, shortcuts, and thoughtful workflow.
    

Copyright & More | 延伸阅读
-----------------------

笔者所有文章遵循知识共享 署名 - 非商业性使用 - 禁止演绎 4.0 国际许可协议，欢迎转载，尊重版权。您还可以前往 NGTE Books 主页浏览包含知识体系、编程语言、软件工程、模式与架构、Web 与大前端、服务端开发实践与工程架构、分布式基础架构、人工智能与深度学习、产品运营与创业等多类目的书籍列表：
