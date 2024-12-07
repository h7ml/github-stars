---
project: pixijs
stars: 44085
description: The HTML5 Creation Engine: Create beautiful digital content with the fastest, most flexible 2D WebGL renderer.
url: https://github.com/pixijs/pixijs
---

PixiJS — The HTML5 Creation Engine
==================================

This project aims to provide a fast, lightweight 2D library that works across all devices. The PixiJS renderer allows everyone to enjoy the power of hardware acceleration without prior knowledge of WebGL. Also, it's fast. Really fast.

If you want to keep up to date with the latest PixiJS news then feel free to follow us on Twitter @PixiJS and we will keep you posted! You can also check back on our site as any breakthroughs will be posted up there too!

**We are now a part of the Open Collective and with your support you can help us make PixiJS even better. To make a donation, simply click the button below and we'll love you forever!**

### What to Use PixiJS for and When to Use It

PixiJS is a rendering library that will allow you to create rich, interactive graphics and cross-platform applications and games without having to dive into the WebGL API or deal with browser and device compatibility.

PixiJS supports WebGPU with fallback support for WebGL. As a library, PixiJS is a fantastic tool for authoring interactive content. Use it for your graphics-rich, interactive websites, applications, and HTML5 games. Out-of-the-box, cross-platform compatibility and graceful degradation mean you have less work to do and more fun doing it! If you want to create polished and refined experiences relatively quickly without delving into dense, low-level code, all while avoiding the headaches of browser inconsistencies, then sprinkle your next project with some PixiJS magic!

**Boost your development and feel free to use your imagination!**

### Current features

-   WebGL renderer (with automatic smart batching, allowing for REALLY fast performance)
-   WebGPU renderer (new to the latest browsers!)
-   Canvas renderer (Fastest in town!)
-   Full scene graph
-   Super easy to use API (similar to the flash display list API)
-   Support for texture atlases
-   Asset loader / sprite sheet loader
-   Auto-detect which renderer should be used
-   Full Mouse and Multi-touch Interaction
-   Text
-   BitmapFont text
-   Multiline Text
-   Render Texture
-   Primitive Drawing
-   Masking
-   Filters
-   Community-Supported Plugins
    -   React
    -   Spine
    -   Filters
    -   Animate
    -   Lights
    -   UI
    -   Layout
    -   GIF
    -   And more!

### Setup

It's easy to get started with PixiJS! Simply download a prebuilt build!

Alternatively, PixiJS can be installed with npm or simply using a content delivery network (CDN) URL to embed PixiJS directly on your HTML page.

#### NPM Install

npm install pixi.js

There is no default export. The correct way to import PixiJS is:

import \* as PIXI from 'pixi.js';

#### CDN Install

Via jsDelivr:

<script src\="https://cdn.jsdelivr.net/npm/pixi.js@8.x/dist/pixi.min.js"\></script\>

Or via unpkg:

<script src\="https://unpkg.com/pixi.js@8.x/dist/pixi.min.js"\></script\>

### Basic Usage Example

import { Application, Assets, Sprite } from 'pixi.js';

(async () \=>
{
    // Create a new application
    const app \= new Application();

    // Initialize the application
    await app.init({ background: '#1099bb', resizeTo: window });

    // Append the application canvas to the document body
    document.body.appendChild(app.canvas);

    // Load the bunny texture
    const texture \= await Assets.load('https://pixijs.com/assets/bunny.png');

    // Create a bunny Sprite
    const bunny \= new Sprite(texture);

    // Center the sprite's anchor point
    bunny.anchor.set(0.5);

    // Move the sprite to the center of the screen
    bunny.x \= app.screen.width / 2;
    bunny.y \= app.screen.height / 2;

    app.stage.addChild(bunny);

    // Listen for animate update
    app.ticker.add((time) \=>
    {
        // Just for fun, let's rotate mr rabbit a little.
        // \* Delta is 1 if running at 100% performance \*
        // \* Creates frame-independent transformation \*
        bunny.rotation += 0.1 \* time.deltaTime;
    });
})();

### Learn

-   Website: Find out more about PixiJS on the official website.
-   Getting Started:
    -   Check out the getting started guide.
    -   Also, check out @miltoncandelero's PixiJS tutorials aimed toward videogames with recipes and best practices here
-   Examples: Get stuck right in and play around with PixiJS code and features right here!
-   API Documentation: Get to know the PixiJS API by checking out the docs.
-   Guide: Supplementary usage guides to the API Documentation here.

### Demos

-   Filters Demo
-   Bunny Demo
-   Masking Demo
-   Interaction Demo
-   More examples

### Community

-   Forums: Check out the discussions and Stackoverflow -- both friendly places to ask your PixiJS questions.
-   Chat: You can join us on Discord to chat about PixiJS.

### How to build

Note that for most users you don't need to build this project. If all you want is to use PixiJS, then just download one of our prebuilt releases. The only time you should need to build PixiJS is if you are developing it.

If you don't already have Node.js and NPM, go install them. Then, in the folder where you have cloned the repository, install the build dependencies using npm:

npm install

Then, to build the source, run:

npm run build

### How to generate the documentation

The docs can be generated using npm:

npm run docs

### Contribute

Want to be part of the PixiJS project? Great! All are welcome! We will get there quicker together :) Whether you find a bug, have a great feature request, or you fancy owning a task from the road map above, feel free to get in touch.

Make sure to read the Contributing Guide before submitting changes.

### License

This content is released under the MIT License.
