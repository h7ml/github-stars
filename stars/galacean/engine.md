---
project: engine
stars: 5276
description: A typescript interactive engine, support 2D, 3D, animation, physics, built on WebGL and glTF.
url: https://github.com/galacean/engine
---

Galacean Engine
===============

Galacean Engine is a high-performance, real-time interactive engine designed primarily for web and mobile platforms. It employs a component system architecture and emphasizes ease of use and lightweight design. Developers can create projects using either editor or pure code.

Features
--------

-   🖥  **Platform** - Support HTML5 and wechat minigame
-   🔮  **Graphics** - Advanced 2D + 3D graphics engine
-   🏃  **Animation** - Powerful animation system
-   🧱  **Physics** - Powerful and easy-to-use physical features
-   🎨  **GUI** - Flexible UI system with drag-and-drop and dynamic interactions
-   👆  **Input** - Easy-to-use interactive capabilities
-   📑  **Scripts** - Use TypeScript to write logic efficiently

Usage
-----

### Using Editor

We recommend using **Editor** for a streamlined workflow that enables seamless integration between artists and developers. Its intuitive visual tools allow artists to quickly create scenes and enable developers to write custom logic, with convenient platform export. You can even create projects based on pre-built case templates.

### Using Pure Code

If you want to build your project using pure code via runtime, install the engine from npm:

npm install @galacean/engine

Create a simple scene:

import { BlinnPhongMaterial, Camera, DirectLight, MeshRenderer, WebGLEngine, PrimitiveMesh } from "@galacean/engine";

// Create engine by passing in the HTMLCanvasElement id and adjust canvas size
const engine \= await WebGLEngine.create({ canvas: "canvas-id" });
engine.canvas.resizeByClientSize();

// Get scene and create root entity
const scene \= engine.sceneManager.activeScene;
const rootEntity \= scene.createRootEntity("Root");

// Create light
const lightEntity \= rootEntity.createChild("Light");
const directLight \= lightEntity.addComponent(DirectLight);
lightEntity.transform.setRotation(\-45, \-45, 0);
directLight.intensity \= 0.4;

// Create camera
const cameraEntity \= rootEntity.createChild("Camera");
cameraEntity.addComponent(Camera);
cameraEntity.transform.setPosition(0, 0, 12);

// Create sphere
const meshEntity \= rootEntity.createChild("Sphere");
const meshRenderer \= meshEntity.addComponent(MeshRenderer);
const material \= new BlinnPhongMaterial(engine);
meshRenderer.setMaterial(material);
meshRenderer.mesh \= PrimitiveMesh.createSphere(engine, 1);

// Run engine
engine.run();

Contributing
------------

This repository contains the runtime's source code and documentation. Everyone is welcome to contribute—whether you find a bug, have a feature request, or want to tackle a task from our roadmap, please get in touch.

Make sure to read the Contributing Guide / 贡献指南 before submitting changes.

Clone
-----

Prerequisites:

-   git-lfs (Install by official website)

Clone this repository:

git clone git@github.com:galacean/engine.git

Build
-----

Prerequisites:

-   Node.js v15.0.0+ and NPM (Install by official website)
-   PNPM (Install globally by `npm install -g pnpm`)

In the folder where you have cloned the repository, install the build dependencies using pnpm:

pnpm install

Then, to build the source, using npm:

npm run b:all

Links
-----

-   Official Site
-   Editor
-   Documentation

License
-------

The engine is released under the MIT license. See LICENSE file.
