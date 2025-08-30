---
project: anime
stars: 63539
description: JavaScript animation engine
url: https://github.com/juliangarnier/anime
---

Anime.js
========

**_Anime.js_ is a fast, multipurpose and lightweight JavaScript animation library with a simple, yet powerful API.  
It works with CSS properties, SVG, DOM attributes and JavaScript Objects.**

Sponsors
--------

Anime.js is 100% free and is only made possible with the help of our sponsors. Help the project become sustainable by sponsoring us on GitHub Sponsors.

### Platinum sponsors

### Silver sponsors

Usage
-----

Anime.js V4 works by importing ES modules like so:

import {
  animate,
  stagger,
} from 'animejs';

animate('.square', {
  x: 320,
  rotate: { from: \-180 },
  duration: 1250,
  delay: stagger(65, { from: 'center' }),
  ease: 'inOutQuint',
  loop: true,
  alternate: true
});

V4 Documentation
----------------

The full documentation is available here.

V3 Migration guide
------------------

You can find the v3 to v4 migration guide here.

NPM development scripts
-----------------------

First, run `npm i` to install all the necessary packages. Then, execute the following scripts with `npm run <script>`.

script

action

`dev`

Watch any changes in `src/` and compiles the esm version to `lib/anime.esm.js`

`dev-types`

Same as `dev`, but also run TypeScript and generate the `types/index.d.ts` file

`build`

Generate types definition and compiles ESM / UMD / IIFE versions to `lib/`

`test-browser`

Start a local server and start all browser related tests

`test-node`

Start all Node related tests

`open-examples`

Start a local server to browse the examples locally

© Julian Garnier | MIT License
