---
project: intro.js
stars: 23314
description: Lightweight, user-friendly onboarding tour library
url: https://github.com/usablica/intro.js
---

Intro.js
========

> User Onboarding and Product Walkthrough Library

Where to get
------------

You can obtain your local copy of Intro.js from:

**1)** This GitHub repository, using `git clone https://github.com/usablica/intro.js.git`

**2)** Using yarn `yarn add intro.js`

**3)** Using npm `npm install intro.js --save`

**4)** Download it from CDN (1, 2)

How to use
----------

Intro.js can be added to your site in three simple steps:

**1)** Include `intro.js` and `introjs.css` (or the minified version for production) in your page. Use `introjs-rtl.min.css` for Right-to-Left language support.

> CDN hosted files are available at jsDelivr (click Show More) & cdnjs.

**2)** Add `data-intro` and `data-step` to your HTML elements. To add hints you should use `data-hint` attribute.

For example:

<a href\='http://google.com/' data-intro\='Hello step one!'\></a\>

See all attributes here.

**3)** Call this JavaScript function:

introJs().start();

Optionally, pass one parameter to `introJs` function to limit the presentation section.

**For example** `introJs(".introduction-farm").start();` runs the introduction only for elements with `class='introduction-farm'`.

Documentation
-------------

Please visit Documentation.

Using with:
-----------

Intro.js has many wrappers for different purposes. Please visit Documentation for more info.

Build
-----

First you should install `nodejs` and `npm`, then first run this command: `npm install` to install all dependencies.

Now you can run this command to minify all static resources:

```
npm run build
```

Contributors ✨
--------------

  
**Afshin Mehrabani**  
💻 📖

  
**bozdoz**  
💻 📖

Support/Discussion
------------------

-   Stackoverflow

Usage Trends
------------

-   Usage Trends of Product Walkthrough Libraries

License
-------

### Commercial license

If you want to use Intro.js for a commercial application, theme or plugin the commercial license is the appropriate license. With this option, your source code is kept proprietary. Purchase a commercial license at introjs.com

### Open-source license

GNU AGPLv3
