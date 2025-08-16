---
project: engine-toolkit
stars: 92
description: Some out-of-the-box utility features based on the Galacean engine.
url: https://github.com/galacean/engine-toolkit
---

Galacean Engine Toolkit
=======================

Some out-of-the-box utility features based on the Galacean engine `Script` and `Material`, welcome to enjoy!

Features
--------

-   📊  **Stats** - Statistics rendering data
    
-   🛸  **Controls** - Some camera controllers
    
-   🎥  **Tween** - Library for tween animation
    
-   🫧  **FrameBufferPicker** - Pixel-based object picking
    
-   ➡️  **Gizmo** - Operation tools for transforming (displacement, rotation, scaling)
    
-   🧭  **Navigation Gizmo** - Three-view & visualized operation for camera control
    
-   🛣  **Waypoint** - control entity move along waypoint
    
-   🪁  **Dynamic Bone** - use dynamic spring movement to enhance skeleton animation
    
-   📐  **Lines** - 2D Solid Line & Dash Line
    
-   🖇  **Auxiliary Lines** - Draw wireframe for entity and component
    
-   🧍🏼  **Skeleton Helper** - Skeleton visualization
    
-   ⭕️  **Outline** - Show outline of mesh renderers
    
-   🖼  **Geometry Sketch** - Convert geometry into texture && sketch normal and mesh wireframe
    
-   🖱  **Input Logger** - Outputs `keyboard` and `pointer` information in real time for developers
    
-   📦  **Draco** - Support draco compressed mesh
    

### Custom Materials

-   ⚔️  **Grid Material** - Infinity grid material
-   🗳  **Planar Shadow Material** - Two-pass shadow on the planar
-   🍞  **Bake PBR Material** - Bake texture with ibl lighting
-   🍞  **Shader Lab** - a declarative language for creating shader

npm
---

The toolkit is published on npm with full typing support. To install, use:

npm install @galacean/engine-toolkit

This will allow you to import toolkit entirely using:

import \* as TOOLKIT from "@galacean/engine-toolkit";

or individual classes using:

import { OrbitControl, FramebufferPicker } from "@galacean/engine-toolkit";

Contributing
------------

Everyone is welcome to join us! Whether you find a bug, have a great feature request or you fancy owning a task from the road map feel free to get in touch.

Make sure to read the Contributing Guide / 贡献指南 before submitting changes.

Build
-----

prerequisites:

-   Node.js v15.0.0+ and NPM (Install Node.js By official website)
-   PNPM (Install Pnpm globally by `npm install -g pnpm`)

First, you need to install the dependencies:

pnpm install

Then, to build the source, using npm:

npm run b:all

Links
-----

-   Official Site
-   Examples
-   Documentation
-   API References

License
-------

The engine is released under the MIT license. See LICENSE file.
