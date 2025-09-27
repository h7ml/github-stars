---
project: watermark-js-plus
stars: 496
description: watermark for the browser
url: https://github.com/zhensherlock/watermark-js-plus
---

  

Watermark
=========

> This is a _canvas-based_ watermark for browser.

-   🛠️ Rich Features
-   🔑 Fully Typed APIs
-   📦️ Extremely light

Watermark works with both Vue 2 , Vue 3 And React.

Translations
============

-   中文文档

Installing
----------

# or pnpm or yarn
npm install watermark-js-plus

Usage
-----

Demo Collection

### Watermark

import { Watermark } from 'watermark-js-plus'

const watermark \= new Watermark({
  content: 'hello my watermark',
  width: 200,
  height: 200,
  onSuccess: () \=> {
    // success callback
  }
})

watermark.create()

### Blind Watermark

import { BlindWatermark } from 'watermark-js-plus'

const watermark \= new BlindWatermark({
  content: 'hello my watermark',
  width: 200,
  height: 200,
  onSuccess: () \=> {
    // success callback
  }
})

watermark.create()

### Decode Blind Watermark

import { BlindWatermark } from 'watermark-js-plus'

BlindWatermark.decode({
  url: uploadFile.url, // image url
  onSuccess: (imageBase64) \=> {
    // success callback
  }
})

Documentation
-------------

To learn more, check its documentation.

Maintainers
-----------

@zhensherlock.

Contributing
------------

Feel free to dive in! Open an issue or submit PRs.

Standard Readme follows the Contributor Covenant Code of Conduct.

### Contributors

This project exists thanks to all the people who contribute.

License
-------

MIT © MichaelSun
