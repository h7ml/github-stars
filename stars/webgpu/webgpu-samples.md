---
project: webgpu-samples
stars: 1994
description: WebGPU Samples
url: https://github.com/webgpu/webgpu-samples
---

WebGPU Samples
==============

**Please visit the WebGPU Samples website to run the samples!**

The WebGPU Samples are a set of samples and demos demonstrating the use of the WebGPU API. Please see the current implementation status and how to run WebGPU in your browser at webgpu.io.

Building
--------

`webgpu-samples` is built with Typescript and bundled using Rollup. Building the project requires an installation of Node.js.

-   Install dependencies: `npm ci`.
-   For development, start the dev server which will watch and recompile sources: `npm start`. You can navigate to http://localhost:8080 to view the project.
-   For production, compile the project: `npm run build`.
-   To run a production server to serve the built assets, do `npm run serve`.
