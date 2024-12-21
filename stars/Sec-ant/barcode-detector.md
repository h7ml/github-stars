---
project: barcode-detector
stars: 109
description: A Barcode Detection API polyfill that uses ZXing-C++ WebAssembly under the hood.
url: https://github.com/Sec-ant/barcode-detector
---

barcode-detector
================

A Barcode Detection API polyfill that uses ZXing-C++ WebAssembly under the hood.

Supported barcode formats: `aztec`, `code_128`, `code_39`, `code_93`, `codabar`, `databar`, `databar_expanded`, `databar_limited`, `data_matrix`, `dx_film_edge`, `ean_13`, `ean_8`, `itf`, `maxi_code` (only generated ones, and no position info), `micro_qr_code`, `pdf417`, `qr_code`, `rm_qr_code`, `upc_a`, `upc_e`, `linear_codes` and `matrix_codes` (for convenience).

Install
-------

To install, run the following command:

npm i barcode-detector

Recommended Usage with Node + ESM
---------------------------------

This package can be imported in three different ways:

### Pure Module

import { BarcodeDetector } from "barcode-detector/pure";

To avoid potential namespace collisions, you can also rename the export:

import { BarcodeDetector as BarcodeDetectorPolyfill } from "barcode-detector/pure";

This approach is beneficial when you want to use a package to detect barcodes without polluting `globalThis`, or when your runtime already provides an implementation of the Barcode Detection API, but you still want this package to function.

### Side Effects

import "barcode-detector/side-effects";

This approach is beneficial when you need a drop-in polyfill. If there's already an implementation of Barcode Detection API on `globalThis`, this won't take effect (type declarations will, as we cannot optionally declare types). In such cases, please use the pure module instead.

### Both

import { BarcodeDetector } from "barcode-detector";

This approach combines the pure module and side effects.

Recommended Usage in Modern Browsers
------------------------------------

For modern browsers that support ES modules, this package can be imported via the `<script type="module">` tags:

1.  Include side effects:
    
    <!-- register -->
    <script
      type\="module"
      src\="https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/es/side-effects.min.js"
    \></script\>
    
    <!-- use -->
    <script type\="module"\>
      const barcodeDetector \= new BarcodeDetector();
    </script\>
    
2.  Script scoped access:
    
    <script type\="module"\>
      import { BarcodeDetector } from "https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/es/pure.min.js";
      const barcodeDetector \= new BarcodeDetector();
    </script\>
    
3.  With import maps:
    
    <!-- import map -->
    <script type\="importmap"\>
      {
        "imports": {
          "barcode-detector/pure": "https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/es/pure.min.js"
        }
      }
    </script\>
    
    <!-- script scoped access -->
    <script type\="module"\>
      import { BarcodeDetector } from "barcode-detector/pure";
      const barcodeDetector \= new BarcodeDetector();
    </script\>
    

Usage with Legacy Compatibility
-------------------------------

Starting from v1.2, this package supports IIFE and CJS build outputs for use cases that require legacy compatibility.

### IIFE

For legacy browsers that lack support for module type `<script>` tags, or for userscripts, IIFE is the preferred choice. Upon executing the IIFE script, a variable named `BarcodeDetectionAPI` will be registered in the global.

<!-- 
  IIFE pure.js registers:
  window.BarcodeDetectionAPI.BarcodeDetector
  window.BarcodeDetectionAPI.setZXingModuleOverrides
  -->
<script src\="https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/iife/pure.min.js"\></script\>

<!-- 
  IIFE side-effects.js registers:
  window.BarcodeDetector
  window.BarcodeDetectionAPI.setZXingModuleOverrides
  -->
<script src\="https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/iife/side-effects.min.js"\></script\>

<!-- 
  IIFE index.js registers:
  window.BarcodeDetector
  window.BarcodeDetectionAPI.BarcodeDetector
  window.BarcodeDetectionAPI.setZXingModuleOverrides
  -->
<script src\="https://fastly.jsdelivr.net/npm/barcode-detector@2/dist/iife/index.min.js"\></script\>

### CJS

This package can also be consumed as a commonjs package:

1.  Vanilla Javascript:
    
    // src/index.js
    const { BarcodeDetector } \= require("barcode-detector/pure");
    
2.  With Typescript:
    
    // src/index.ts
    import { BarcodeDetector } from "barcode-detector/pure";
    
    `tsconfig.json`:
    
    {
      "compilerOptions": {
        "module": "CommonJS",
        "moduleResolution": "Node",
        "skipLibCheck": true
      },
      "include": \["src"\]
    }
    

`setZXingModuleOverrides`
-------------------------

In addition to `BarcodeDetector`, this package exports another function called `setZXingModuleOverrides`.

This package employs zxing-wasm to enable the core barcode reading functionality. As a result, a `.wasm` binary file is fetched at runtime. The default fetch path for this binary file is:

```
https://fastly.jsdelivr.net/npm/zxing-wasm@<version>/dist/reader/zxing_reader.wasm
```

The `setZXingModuleOverrides` function allows you to govern where the `.wasm` binary is served from, thereby enabling offline use of the package, use within a local network, or within a site having strict CSP rules.

For instance, should you want to inline this `.wasm` file in your build output for offline usage, with the assistance of build tools, you could try:

// src/index.ts
import wasmFile from "../node\_modules/zxing-wasm/dist/reader/zxing\_reader.wasm?url";

import {
  setZXingModuleOverrides,
  BarcodeDetector,
} from "barcode-detector/pure";

setZXingModuleOverrides({
  locateFile: (path, prefix) \=> {
    if (path.endsWith(".wasm")) {
      return wasmFile;
    }
    return prefix + path;
  },
});

const barcodeDetector \= new BarcodeDetector();

// detect barcodes
// ...

Alternatively, the `.wasm` file could be copied to your dist folder to be served from your local server, without incorporating it into the output as an extensive base64 data URL.

It's noteworthy that you'll always want to choose the correct version of the `.wasm` file, so the APIs exported by it are exactly what the js code expects.

For more information on how to use this function, you can check the notes here and discussions here and here.

This function is exported from all the subpaths, including the side effects.

API
---

Please check the spec, MDN doc and Chromium implementation for more information.

Lifecycle Events
----------------

The `BarcodeDetector` provided by this package also extends class `EventTarget` and provides 2 lifecycle events: `load` and `error`. You can use `addEventListener` and `removeEventListener` to register and remove callback hooks on these events.

### `load` Event

The `load` event, which is a `CustomEvent`, will be dispatched on the successful instantiation of ZXing wasm module. For advanced usage, the instantiated module is passed as the `detail` parameter.

import { BarcodeDetector } from "barcode-detector/pure";

const barcodeDetector \= new BarcodeDetector();

barcodeDetector.addEventListener("load", ({ detail }) \=> {
  console.log(detail); // zxing wasm module
});

### `error` Event

The `error` event, which is a `CustomEvent`, will be dispatched if the instantiation of ZXing wasm module is failed. An error is passed as the `detail` parameter.

import { BarcodeDetector } from "barcode-detector/pure";

const barcodeDetector \= new BarcodeDetector();

barcodeDetector.addEventListener("error", ({ detail }) \=> {
  console.log(detail); // an error
});

Example
-------

import { BarcodeDetector } from "barcode-detector/pure";

const barcodeDetector: BarcodeDetector \= new BarcodeDetector({
  formats: \["qr\_code"\],
});

const imageFile \= await fetch(
  "https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=Hello%20world!",
).then((resp) \=> resp.blob());

barcodeDetector.detect(imageFile).then(console.log);

License
-------

The source code in this repository, as well as the build output, except for the parts listed below, is licensed under the MIT license.

Test samples and resources are collected from web-platform-tests/wpt, which is licensed under the 3-Clause BSD license.
