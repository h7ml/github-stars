---
project: pnpm-patch-i
stars: 286
description: A better and interactive pnpm patch
url: https://github.com/antfu/pnpm-patch-i
---

pnpm-patch-i
============

A better and interactive `pnpm patch`.

Usage
-----

npx pnpm-patch-i package-name

This CLI wraps with `pnpm patch` and provides a better interactive experience:

-   Have the patch dir under your local `node_modules/` folder instead of a global temp folder
-   More human-friendly folder name instead of random string
-   Open the editing folder in your editor via `launch-editor`
-   Wait for your changes and automatically run `pnpm commit-patch <dir>` for you
-   Always runs at where `pnpm-lock.yaml` is located

### Apply Patch from a directory

It's also possible to apply a patch directly from a directory (normally a local build of the package), for example:

npx pnpm-patch-i vite ../vite/packages/vite --build

`--build` (`-b`) flag will invoke `npm run build` in the source directory before applying the patch.

Sponsors
--------

License
-------

MIT License © 2023 Anthony Fu
