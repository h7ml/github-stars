---
project: pnpm-patch-i
stars: 288
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

It's also possible to apply a patch directly from a directory, for example:

npx pnpm-patch-i vite ../vite/packages/vite

You can also use `--build` (`-b`) flag to invoke `npm run build` in the source directory before applying the patch.

Note

If the source package is in a monorepo with custom linking, or using catalogs, directly applying the patch from a directory might resulting copying the linking where the current project might not be able to resolve. In that case, it's recommended to pack the source package into a tgz file and apply the patch from the tgz file with `--pack` (`-p`) flag.

Sponsors
--------

License
-------

MIT License © 2023 Anthony Fu
