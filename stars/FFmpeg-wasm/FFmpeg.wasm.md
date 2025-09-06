---
project: FFmpeg.wasm
stars: 66
description: A fork of ffmpeg.wasm. Powered by WebAssembly
url: https://github.com/FFmpeg-wasm/FFmpeg.wasm
---

FFmpeg.wasm
===========

About this fork
---------------

Thanks to Jerome Wu for creating the very cool package ffmpegwasm!  
However, because this package hasn't been updated in a long time, a lot of features are on hold and it's not compatible with node18 and above (because the emsdk version is too old). So I decided to maintain a fork, fix the problems and continue development iterations.  
Update: Jerome Wu updated ffmpegwasm, but dropped nodejs support because "If you are not in browser, there are a lot of better choices than using WebAssembly for a better performance ". However, I don't entirely agree with this. WebAssembly gives us the possibility of run programs at high performance in both native and browser environments with the same code. The convenience and portability it brings is unmatched by any other solution, and the current performance issues will hopefully be resolved in the foreseeable future. So I decide to keep maintaining this project. Feel free to create issues or pull requests ヾ(≧▽≦\*)o

### Release Plan

> See the Todos section for more plans

-   v0.12 is fully compatible with ffmpegwasm v0.11.x, but updates emsdk to the latest and fixes some bugs
-   Since v0.13, we'll try to add some new features and refactor it using a modern toolchain **this may bring some breaking changes in minor version**.

### Migration from ffmpegwasm

1.  Change package names and update imports:
    -   `@ffmpeg/ffmpeg` => `@ffmpeg.wasm/main`
    -   `@ffmpeg/core` & `@ffmpeg/core-mt` => `@ffmpeg.wasm/core-mt`
    -   `@ffmpeg/core-st` => `@ffmpeg.wasm/core-st`
2.  Update version to `^0.12.0`

### Todos

-   Update emsdk to latest
-   Release with Github Action
-   Migrate to pnpm
-   ESM Support
-   Test with `vitest`
-   Update deps
-   Rewrite with TypeScript
-   Support for parallel tasks in multi-threaded mode
-   Migrate to monorepo
-   Build with xmake(WIP)
-   Support build cache(WIP)
-   Upgrade to FFmpeg@6(WIP)
-   Use the faster `libsvtav1` instead of `libaom` (currently disabled because it is too slow)(WIP)
-   Document site
-   Benchmark
-   SIMD and WASI version

Original readme
---------------

ffmpeg.wasm is a pure Webassembly port of FFmpeg. It enables video & audio record, convert and stream right inside browsers.

Installation
------------

**Node**

```
$ npm install @ffmpeg.wasm/main @ffmpeg.wasm/core-mt
```

**Browser**

Or, using a script tag in the browser (only works in some browsers, see list below):

> Only browsers with `SharedArrayBuffer` support can use multi-thread core(`@ffmpeg.wasm/core-mt`), you can check HERE for the complete list.

> SharedArrayBuffer is only available to pages that are cross-origin isolated. You need to send headers `Cross-Origin-Embedder-Policy: require-corp` and `Cross-Origin-Opener-Policy: same-origin` for your site, and make sure your static resource server(or public CDN) contains the header `Cross-Origin-Resource-Policy: cross-origin`(e.g. JSdelivr, not Unpkg)

<script src\="https://cdn.jsdelivr.net/npm/@ffmpeg.wasm/main/dist/index.global.js"\></script\>
<script\>
  const ffmpeg \= FFmpeg.create({
    /\* ... \*/
  });
</script\>

Usage
-----

`ffmpeg.wasm` provides simple to use APIs, to transcode a video you only need few lines of code:

import { readFile, writeFile } from "fs/promises";
import { FFmpeg } from "@ffmpeg.wasm/main";

const ffmpeg \= await FFmpeg.create({ core: "@ffmpeg.wasm/core-mt" });

ffmpeg.fs.writeFile("test.avi", await readFile("./test.avi"));
await ffmpeg.run("-i", "test.avi", "test.mp4");
await writeFile("./test.mp4", ffmpeg.fs.readFile("test.mp4"));
process.exit(0);

### Use other version of ffmpeg.wasm core

For each version of ffmpeg.wasm, there is a default version of `@ffmpeg.wasm/core-mt` (you can find it in `devDependencies` section of package.json), but sometimes you may need to use newer version of `@ffmpeg.wasm/core-mt` to use the latest/experimental features. **Warning:** before reaching v1.0.0, there may be incompatibilities between each minor version of the core, see the migration guide for more details!

#### Node

Just install the specific version you need:

$ npm install @ffmpeg.wasm/core-mt@$version

Or use your own version with customized path

const ffmpeg \= await FFmpeg.create({
  core: "path/to/your/ffmpeg.wasm/core.js",
});

#### Browser

const ffmpeg \= await FFmpeg.create({
  core: "https://cdn.jsdelivr.net/npm/@ffmpeg.wasm@$version/core-mt/dist/core.min.js",
});

### Use single thread version

const ffmpeg \= await FFmpeg.create({
  core: "@ffmpeg.wasm/core-st",
});

Multi-threading
---------------

Multi-threading need to be configured per external libraries, only following libraries supports it now:

### x264

Run it multi-threading mode by default, no need to pass any arguments.

### libvpx / webm

Need to pass `-row-mt 1`, but can only use one thread to help, can speed up around 30%

Documentation
-------------

-   API
-   Supported External Libraries

FAQ
---

### What is the license of ffmpeg.wasm?

There are two components inside ffmpeg.wasm:

-   @ffmpeg.wasm/main (https://github.com/FFmpeg-wasm/ffmpeg.wasm)
-   @ffmpeg.wasm/core-mt (https://github.com/FFmpeg-wasm/ffmpeg.wasm-core)

@ffmpeg.wasm/core-mt contains WebAssembly code which is transpiled from original FFmpeg C code with minor modifications, but overall it still following the same licenses as FFmpeg and its external libraries (as each external libraries might have its own license).

@ffmpeg.wasm/main contains kind of a wrapper to handle the complexity of loading core and calling low-level APIs. It is a small code base and under MIT license.

### What is the maximum size of input file?

1 GB, which is a hard limit in WebAssembly. Might become 4 GB in the future.
