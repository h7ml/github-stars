---
project: feather
stars: 25389
description: Simply beautiful open-source icons
url: https://github.com/feathericons/feather
---

Feather
=======

What is Feather?
----------------

Feather is a collection of simply beautiful open-source icons. Each icon is designed on a 24x24 grid with an emphasis on simplicity, consistency, and flexibility.

https://feathericons.com

npm install feather-icons

Table of contents
-----------------

-   Quick start
-   Usage
    -   Client-side JavaScript
    -   Node
    -   SVG sprite
    -   Figma
-   API reference
    -   `feather.icons`
    -   `feather.icons[name].toSvg()`
    -   `feather.replace()`
    -   `feather.toSvg()` (DEPRECATED)
-   Contributing
-   Related projects
-   License

Quick start
-----------

Start with this CodePen Template to begin prototyping with Feather in the browser.

Or copy and paste the following code snippet into a blank `html` file.

<!DOCTYPE html\>
<html lang\="en"\>
  <title\></title\>
  <script src\="https://unpkg.com/feather-icons"\></script\>
  <body\>
    <!-- example icon -->
    <i data-feather\="circle"\></i\>

    <script\>
      feather.replace();
    </script\>
  </body\>
</html\>

Usage
-----

At its core, Feather is a collection of SVG files. This means that you can use Feather icons in all the same ways you can use SVGs (e.g. `img`, `background-image`, `inline`, `object`, `embed`, `iframe`). Here's a helpful article detailing the many ways SVGs can be used on the web: SVG on the Web – Implementation Options

The following are additional ways you can use Feather.

### Client-side JavaScript

#### 1\. Install

Note

If you intend to use Feather with a CDN, you can skip this installation step.

Install with npm.

npm install feather-icons --save

Or just copy `feather.js` or `feather.min.js` into your project directory. You don't need both `feather.js` and `feather.min.js`.

#### 2\. Include

Include `feather.js` or `feather.min.js` with a `<script>` tag:

<script src\="path/to/dist/feather.js"\></script\>

Note

`feather.js` and `feather.min.js` are located in the `dist` directory of the npm package.

Or load the script from a CDN provider:

<!-- choose one -->
<script src\="https://unpkg.com/feather-icons"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/feather-icons/dist/feather.min.js"\></script\>

After including the script, `feather` will be available as a global variable.

#### 3\. Use

To use an icon on your page, add a `data-feather` attribute with the icon name to an element:

<i data-feather\="circle"\></i\>

See the complete list of icons at feathericons.com.

#### 4\. Replace

Call the `feather.replace()` method:

<script\>
  feather.replace();
</script\>

All elements that have a `data-feather` attribute will be replaced with SVG markup corresponding to their `data-feather` attribute value. See the API Reference for more information about `feather.replace()`.

### Node

#### 1\. Install

Install with npm:

npm install feather-icons --save

#### 2\. Require

const feather \= require('feather-icons');

#### 3\. Use

feather.icons.x;
// {
//    name: 'x',
//    contents: '<line ... /><line ... />\`,
//    tags: \['cancel', 'close', 'delete', 'remove'\],
//    attrs: {
//      class: 'feather feather-x',
//      xmlns: 'http://www.w3.org/2000/svg',
//      width: 24,
//      height: 24,
//      viewBox: '0 0 24 24',
//      fill: 'none',
//      stroke: 'currentColor',
//      'stroke-width': 2,
//      'stroke-linecap': 'round',
//      'stroke-linejoin': 'round',
//    },
//    toSvg: \[Function\],
// }

feather.icons.x.toSvg();
// <svg class="feather feather-x" ...><line ... /><line ... /></svg>

feather.icons.x.toSvg({ class: 'foo bar', 'stroke-width': 1, color: 'red' });
// <svg class="feather feather-x foo bar" stroke-width="1" color="red" ...><line ... /><line ... /></svg>

See the API Reference for more information about the available properties and methods of the `feather` object.

### SVG sprite

#### 1\. Install

Note

If you intend to use Feather with a CDN, you can skip this installation step.

Install with npm.

npm install feather-icons --save

Or just copy `feather-sprite.svg` into your project directory.

#### 2\. Use

Include an icon on your page with the following markup:

<svg
  width\="24"
  height\="24"
  fill\="none"
  stroke\="currentColor"
  stroke-width\="2"
  stroke-linecap\="round"
  stroke-linejoin\="round"
\>
  <use href\="path/to/feather-sprite.svg#circle" />
</svg\>

Note

`circle` in the above example can be replaced with any valid icon name. See the complete list of icon names at feathericons.com.

However, this markup can be simplified using a simple CSS class to avoid repetition of SVG attributes between icons:

.feather {
  width: 24px;
  height: 24px;
  stroke: currentColor;
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  fill: none;
}

<svg class\="feather"\>
  <use href\="path/to/dist/feather-sprite.svg#circle" />
</svg\>

### Figma

Feather is available as a Figma component library. To use the components, log in to your Figma account and **duplicate** the file to your drafts.

API reference
-------------

### `feather.icons`

An object with data about every icon.

#### Usage

feather.icons.x;
// {
//    name: 'x',
//    contents: '<line ... /><line ... />',
//    tags: \['cancel', 'close', 'delete', 'remove'\],
//    attrs: {
//      class: 'feather feather-x',
//      xmlns: 'http://www.w3.org/2000/svg',
//      width: 24,
//      height: 24,
//      viewBox: '0 0 24 24',
//      fill: 'none',
//      stroke: 'currentColor',
//      'stroke-width': 2,
//      'stroke-linecap': 'round',
//      'stroke-linejoin': 'round',
//    },
//    toSvg: \[Function\],
// }

feather.icons.x.toString();
// '<line ... /><line ... />'

Note

`x` in the above example can be replaced with any valid icon name. See the complete list of icon names at feathericons.com. Icons with multi-word names (e.g. `arrow-right`) **cannot** be accessed using dot notation (e.g. `feather.icons.x`). Instead, use bracket notation (e.g. `feather.icons['arrow-right']`).

View Source

* * *

### `feather.icons[name].toSvg([attrs])`

Returns an SVG string.

#### Parameters

Name

Type

Description

`attrs` (optional)

Object

Key-value pairs in the `attrs` object will be mapped to HTML attributes on the `<svg>` tag (e.g. `{ foo: 'bar' }` maps to `foo="bar"`). All default attributes on the `<svg>` tag can be overridden with the `attrs` object.

Note

You might find these SVG attributes helpful for manipulating icons:

-   `color`
-   `width`
-   `height`
-   `stroke-width`
-   `stroke-linecap`
-   `stroke-linejoin`

#### Usage

feather.icons.circle.toSvg();
// '<svg class="feather feather-circle" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

feather.icons.circle.toSvg({ 'stroke-width': 1 });
// '<svg class="feather feather-circle" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

feather.icons.circle.toSvg({ class: 'foo bar' });
// '<svg class="feather feather-circle foo bar" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

View Source

* * *

### `feather.replace([attrs])`

Replaces all elements that have a `data-feather` attribute with SVG markup corresponding to the element's `data-feather` attribute value.

#### Parameters

Name

Type

Description

`attrs` (optional)

Object

Key-value pairs in the `attrs` object will be mapped to HTML attributes on the `<svg>` tag (e.g. `{ foo: 'bar' }` maps to `foo="bar"`). All default attributes on the `<svg>` tag can be overridden with the `attrs` object.

#### Usage

Important

`feather.replace()` only works in a browser environment.

Simple usage:

<i data-feather\="circle"\></i\>
<!--
<i> will be replaced with:
<svg class="feather feather-circle" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>
\-->

<script\>
  feather.replace();
</script\>

You can pass `feather.replace()` an `attrs` object:

<i data-feather\="circle"\></i\>
<!--
<i> will be replaced with:
<svg class="feather feather-circle foo bar" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>
\-->

<script\>
  feather.replace({ class: 'foo bar', 'stroke-width': 1 });
</script\>

All attributes on the placeholder element (i.e. `<i>`) will be copied to the `<svg>` tag:

<i data-feather\="circle" id\="my-circle" class\="foo bar" stroke-width\="1"\></i\>
<!--
<i> will be replaced with:
<svg id="my-circle" class="feather feather-circle foo bar" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>
\-->

<script\>
  feather.replace();
</script\>

View Source

* * *

### `feather.toSvg(name, [attrs])` (DEPRECATED)

Warning

`feather.toSvg()` is deprecated. Please use `feather.icons[name].toSvg()` instead.

Returns an SVG string.

#### Parameters

Name

Type

Description

`name`

string

Icon name

`attrs` (optional)

Object

Key-value pairs in the `attrs` object will be mapped to HTML attributes on the `<svg>` tag (e.g. `{ foo: 'bar' }` maps to `foo="bar"`). All default attributes on the `<svg>` tag can be overridden with the `attrs` object.

#### Usage

feather.toSvg('circle');
// '<svg class="feather feather-circle" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

feather.toSvg('circle', { 'stroke-width': 1 });
// '<svg class="feather feather-circle" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

feather.toSvg('circle', { class: 'foo bar' });
// '<svg class="feather feather-circle foo bar" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle></svg>'

View Source

Contributing
------------

For more info on how to contribute please see the contribution guidelines.

Caught a mistake or want to contribute to the documentation? Edit this page on Github

Related projects
----------------

-   feathericons.dev - Feather viewer featuring 30+ brand icons and 40+ payment services icons
-   angular-feather - Feather icons for Angular applications
-   elm-feather - Feather icons for Elm applications
-   react-feather - Feather icons as React components
-   sketch-feather - Feather icons as a Sketch library
-   vue-feather-icons - Feather icons as Vue components
-   php-feather - Feather icons as a PHP Library
-   hyva-feather - Feather icons as a Magento 2 Hyva template tag
-   wp-php-feather - Feather icons as a WordPress template tag
-   django-feather - Feather icons as Django Template Tag
-   svelte-feather-icons - Feather icons as Svelte components
-   gulp-feather - Feather icons rendering using gulp
-   astro-feather - Feather icons as Astro components
-   qwik-feather-icons - Feather icons for Qwik, the Resumable Framework
-   figma-feather – Feather icons as a Figma component
-   delphi-feather-icons - Feather icons as a Delphi Library
-   eleventy-plugin-feathericons - Feather icons as a plugin for 11ty

License
-------

Feather is licensed under the MIT License.
