---
project: model-viewer
stars: 545
description: 3D Model Viewer supporting glTF and 3D Gaussian Splats
url: https://github.com/playcanvas/model-viewer
---

PlayCanvas Model Viewer
=======================

| User Manual | API Reference | Blog | Forum |

The PlayCanvas glTF scene viewer is blazingly fast and 100% compliant with the glTF 2.0 spec.

You can find a live version at:

https://playcanvas.com/model-viewer

Viewing Scenes
--------------

The viewer can load any glTF 2.0 scene. Embedded glTF and binary glTF (GLB) can be dragged directly into the 3D view. To load an unpacked glTF scene, drag its parent folder into the 3D view.

You can also drag and drop images into the 3D view to set a background. Options are:

-   Single file images are treated as equirectangular projections. Supported formats are PNG, JPG and HDR. Find high quality HDR images at HDRHaven.
-   Six images are treated as cube map faces. Naming should be one of the following 5 forms, where each face name below should be incorporated in the overall filename like `name_posx.png` for example:

Face 0

Face 1

Face 2

Face 3

Face 4

Face 5

posx

negx

posy

negy

posz

negz

px

nx

py

ny

pz

nz

right

left

up

down

front

back

right

left

top

bottom

forward

backward

0

1

2

3

4

5

### Supported URL Parameters

Some URL query parameters are available to override certain aspects of the viewer:

Parameter

Description

Example

`load`/`assetUrl`

Specify URL to a glTF scene to load

?load=URL

`cameraPosition`

Override the initial camera position

?cameraPosition=0,0,20

How to build
------------

Ensure you have Node.js installed (v18.0+). Then, from a command prompt, run:

```
npm install
npm run build
```

This will invoke Rollup and output the built viewer to the `dist` folder. To invoke Rollup with the `--watch` flag (which rebuilds the viewer on saving any source file), do:

```
npm run watch
```

How to run
----------

Run:

```
npm run serve
```

Open a browser and navigate to http://localhost:3000.

Development
-----------

Run:

```
npm run develop
```

Open a browser and navigate to http://localhost:3000.

N.B. To load local models run `npx server --cors` in the directory containing the model (disables CORS).

Library integration testing
---------------------------

The Model Viewer is built on the following open source libraries:

Library

Details

PlayCanvas Engine

Powers the Editor's 3D View and Launch Page

Observer

Data binding and history

PCUI

Front-end component library

To test the integration of these libraries use npm link. Follow these steps:

1.  Create a global link from source
    
    cd <library\>
    npm link
    
2.  Create a link to the global link
    
    cd model-viewer
    npm link <library\>
