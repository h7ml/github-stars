---
project: snapdom
stars: 6341
description: snapDOM captures HTML elements to images with exceptional speed and accuracy.
url: https://github.com/zumerlab/snapdom
---

snapDOM
=======

**snapDOM** is a fast and accurate DOM-to-image capture tool built for **Zumly**, a zoom-based view transition framework.

It captures any HTML element as a scalable SVG image, preserving styles, fonts, background images, pseudo-elements, and even shadow DOM. It also supports export to raster image formats and canvas.

-   📸 Full DOM capture
-   🎨 Embedded styles, pseudo-elements, and fonts
-   🖼️ Export to SVG, PNG, JPG, WebP, `canvas`, or Blob
-   ⚡ Ultra fast, no dependencies
-   📦 100% based on standard Web APIs
-   Support same-origin `ìframe`
-   Support CSS counter() and CSS counters()
-   Support `...` line-clamp

Demo
----

https://snapdom.dev

Table of Contents
-----------------

-   Installation
    -   NPM / Yarn (stable)
    -   NPM / Yarn (dev builds)
    -   CDN (stable)
    -   CDN (dev builds)
-   Basic usage
    -   Reusable capture
    -   One-step shortcuts
-   API
    -   snapdom(el, options?)
    -   Shortcut methods
-   Options
    -   Fallback image on `<img>` load failure
    -   Dimensions (`scale`, `width`, `height`)
    -   Cross-Origin Images & Fonts (`useProxy`)
    -   Fonts
        -   embedFonts
        -   localFonts
        -   iconFonts
        -   excludeFonts
    -   Filtering nodes: `exclude` vs `filter`
    -   straighten
    -   noShadows
    -   Cache control
-   preCache
-   Limitations
-   ⚡ Performance Benchmarks (Chromium)
    -   Simple elements
    -   Complex elements
    -   Run the benchmarks
-   Roadmap
-   Development
-   Contributors 🙌
-   💖 Sponsors
-   Star History
-   License

Installation
------------

### NPM / Yarn (stable)

npm i @zumer/snapdom
yarn add @zumer/snapdom

### NPM / Yarn (dev builds)

For early access to new features and fixes:

npm i @zumer/snapdom@dev
yarn add @zumer/snapdom@dev

⚠️ The `@dev` tag usually includes improvements before they reach production, but may be less stable.

### CDN (stable)

<!-- Minified UMD build -->
<script src\="https://unpkg.com/@zumer/snapdom/dist/snapdom.min.js"\></script\>

<!-- ES Module build -->
<script type\="module"\>
  import { snapdom } from "https://unpkg.com/@zumer/snapdom/dist/snapdom.mjs";
</script\>

### CDN (dev builds)

<!-- Minified UMD build (dev) -->
<script src\="https://unpkg.com/@zumer/snapdom@dev/dist/snapdom.min.js"\></script\>

<!-- ES Module build (dev) -->
<script type\="module"\>
  import { snapdom } from "https://unpkg.com/@zumer/snapdom@dev/dist/snapdom.mjs";
</script\>

Basic usage
-----------

### Reusable capture

const el \= document.querySelector('#target');
const result \= await snapdom(el);

const img \= await result.toPng();
document.body.appendChild(img);

await result.download({ format: 'jpg', filename: 'my-capture' });

### One-step shortcuts

const el \= document.querySelector('#target');
const png \= await snapdom.toPng(el);
document.body.appendChild(png);

const blob \= await snapdom.toBlob(el);

API
---

### `snapdom(el, options?)`

Returns an object with reusable export methods:

{
  url: string;
  toRaw(): string;
  toImg(): Promise<HTMLImageElement\>; // deprecated 
  toSvg(): Promise<HTMLImageElement\>;
  toCanvas(): Promise<HTMLCanvasElement\>;
  toBlob(options?): Promise<Blob\>;
  toPng(options?): Promise<HTMLImageElement\>;
  toJpg(options?): Promise<HTMLImageElement\>;
  toWebp(options?): Promise<HTMLImageElement\>;
  download(options?): Promise<void\>;
}

### Shortcut methods

Method

Description

`snapdom.toImg(el, options?)`

Returns an SVG `HTMLImageElement` (deprecated)

`snapdom.toSvg(el, options?)`

Returns an SVG `HTMLImageElement`

`snapdom.toCanvas(el, options?)`

Returns a `Canvas`

`snapdom.toBlob(el, options?)`

Returns an SVG or raster `Blob`

`snapdom.toPng(el, options?)`

Returns a PNG image

`snapdom.toJpg(el, options?)`

Returns a JPG image

`snapdom.toWebp(el, options?)`

Returns a WebP image

`snapdom.download(el, options?)`

Triggers a download

Options
-------

> ✅ **Note:** Style compression is now always on internally. The `compress` option has been removed.

All capture methods accept an `options` object:

Option

Type

Default

Description

`fast`

boolean

`true`

Skips small idle delays for faster results

`embedFonts`

boolean

`false`

Inlines non-icon fonts (icon fonts always on)

`localFonts`

array

`[]`

Local fonts `{ family, src, weight?, style? }`

`iconFonts`

string|RegExp|Array

`[]`

Extra icon font matchers

`excludeFonts`

object

`{}`

Exclude families/domains/subsets during embedding

`scale`

number

`1`

Output scale multiplier

`dpr`

number

`devicePixelRatio`

Device pixel ratio

`width`

number

\-

Output width

`height`

number

\-

Output height

`backgroundColor`

string

`"#fff"`

Fallback color for JPG/WebP

`quality`

number

`1`

Quality for JPG/WebP (0 to 1)

`useProxy`

string

`''`

Proxy base for CORS fallbacks

`type`

string

`svg`

Default Blob type (`svg`|`png`|`jpg`|`webp`)

`exclude`

string\[\]

\-

CSS selectors to exclude

`excludeMode`

`"hide"`|`"remove"`

`"hide"`

How `exclude` is applied

`filter`

function

\-

Custom predicate `(el) => boolean`

`filterMode`

`"hide"`|`"remove"`

`"hide"`

How `filter` is applied

`cache`

string

`"soft"`

`disabled` | `soft` | `auto` | `full`

`placeholders`

boolean

`true`

Show placeholders for images/CORS iframes

`fallbackURL`

string | function

\-

Fallback image for `<img>` load failure

`straighten`

boolean

`false`

Straightens the root: removes `translate/rotate` but preserves `scale/skew`, producing a flat, reusable capture

`noShadows`

boolean

`false`

Do not expand the root’s bounding box for shadows/blur/outline, and strip those visual effects from the cloned root

### Fallback image on `<img>` load failure

Provide a default image for failed `<img>` loads. You can pass a fixed URL or a callback that receives measured dimensions and returns a URL (handy to generate dynamic placeholders).

// 1) Fixed URL fallback
await snapdom.toSvg(element, {
  fallbackURL: '/images/fallback.png'
});

// 2) Dynamic placeholder via callback
await snapdom.toSvg(element, {
  fallbackURL: ({ width: 300, height: 150 }) \=>
    \`https://placehold.co/${width}x${height}\`
});

// 3) With proxy (if your fallback host has no CORS)
await snapdom.toSvg(element, {
  fallbackURL: ({ width \= 300, height \= 150 }) \=>
    \`https://dummyimage.com/${width}x${height}/cccccc/666.png&text=img\`,
  useProxy: 'https://proxy.corsfix.com/?'
});

Notes:

-   If the fallback image also fails to load, snapDOM replaces the `<img>` with a placeholder block preserving width/height.
-   Width/height used by the callback are gathered from the original element (dataset, style/attrs, etc.) when available.

### Dimensions (`scale`, `width`, `height`)

-   If `scale` is provided, it **takes precedence** over `width`/`height`.
-   If only `width` is provided, height scales proportionally (and vice versa).
-   Providing both `width` and `height` forces an exact size (may distort).

### Cross-Origin Images & Fonts (`useProxy`)

By default snapDOM tries `crossOrigin="anonymous"` (or `use-credentials` for same-origin). If an asset is CORS-blocked, you can set `useProxy` to a prefix URL that forwards the actual `src`:

await snapdom.toPng(el, {
  useProxy: 'https://proxy.corsfix.com/?' // Note: Any cors proxy could be used 'https://proxy.corsfix.com/?'
});

-   The proxy is only used as a **fallback**; same-origin and CORS-enabled assets skip it.

### Fonts

#### `embedFonts`

When `true`, snapDOM embeds **non-icon** `@font-face` rules detected as used within the captured subtree. Icon fonts (Font Awesome, Material Icons, etc.) are embedded **always**.

#### `localFonts`

If you serve fonts yourself or have data URLs, you can declare them here to avoid extra CSS discovery:

await snapdom.toPng(el, {
  embedFonts: true,
  localFonts: \[
    { family: 'Inter', src: '/fonts/Inter-Variable.woff2', weight: 400, style: 'normal' },
    { family: 'Inter', src: '/fonts/Inter-Italic.woff2', style: 'italic' }
  \]
});

#### `iconFonts`

Add custom icon families (names or regex matchers). Useful for private icon sets:

await snapdom.toPng(el, {
  iconFonts: \['MyIcons', /^(Remix|Feather) Icons?$/i\]
});

#### `excludeFonts`

Skip specific non-icon fonts to speed up capture or avoid unnecessary downloads.

await snapdom.toPng(el, {
  embedFonts: true,
  excludeFonts: {
    families: \['Noto Serif', 'SomeHeavyFont'\],     // skip by family name
    domains: \['fonts.gstatic.com', 'cdn.example'\], // skip by source host
    subsets: \['cyrillic-ext'\]                      // skip by unicode-range subset tag
  }
});

_Notes_

-   `excludeFonts` only applies to **non-icon** fonts. Icon fonts are always embedded.
-   Matching is case-insensitive for `families`. Hosts are matched by substring against the resolved URL.

#### Filtering nodes: `exclude` vs `filter`

-   `exclude`: remove by **selector**.
-   `excludeMode`: `hide` applies `visibility:hidden` CSS rule on excluded nodes and the layout remains as the original. `remove` do not clone excluded nodes at all.
-   `filter`: advanced predicate per element (return `false` to drop).
-   `filterMode`: `hide` applies `visibility:hidden` CSS rule on filtered nodes and the layout remains as the original. `remove` do not clone filtered nodes at all.

**Example: filter out elements with `display:none`:**

/\*\*
 \* Example filter: skip elements with display:none
 \* @param {Element} el
 \* @returns {boolean} true = keep, false = exclude
 \*/
function filterHidden(el) {
  const cs \= window.getComputedStyle(el);
  if (cs.display \=== 'none') return false;
  return true;
}

await snapdom.toPng(document.body, { filter: filterHidden });

**Example with `exclude`:** remove banners or tooltips by selector

await snapdom.toPng(el, {
  exclude: \['.cookie-banner', '.tooltip', '\[data-test="debug"\]'\]
});

### Straighten

When capturing rotated or translated elements, you may want to **straighten** the root so the snapshot can be reused in another layout without inheriting those transforms.

-   **`straighten: true`**  
    Straightens the cloned root: **removes `translate` and `rotate`** but **keeps `scale/skew`** to preserve proportions.  
    The output is **flat, upright, and ready** to embed elsewhere.

### noShadows

-   **`noShadows: true`**  
    Prevents expanding the bounding box for shadows, blur, or outline on the root, and also strips `box-shadow`, `text-shadow`, `filter: blur()/drop-shadow()`, and `outline` from the cloned root.

> 💡 **Tip:** Using both (`straighten` + `noShadows`) produces a strict, minimal bounding box with no visual bleed.

**Example**

// Straighten and remove shadow bleed
await snapdom.toSvg(el, { straighten: true, noShadows: true });

Cache control
-------------

SnapDOM maintains internal caches for images, backgrounds, resources, styles, and fonts. You can control how they are cleared between captures using the `cache` option:

Mode

Description

`"disabled"`

No cache

`"soft"`

Clears session caches (`styleMap`, `nodeMap`, `styleCache`) _(default)_

`"auto"`

Minimal cleanup: only clears transient maps

`"full"`

Keeps all caches (nothing is cleared, maximum performance)

**Examples:**

// Use minimal but fast cache
await snapdom.toPng(el, { cache: 'auto' });

// Keep everything in memory between captures
await snapdom.toPng(el, { cache: 'full' });

// Force a full cleanup on every capture
await snapdom.toPng(el, { cache: 'disabled' });

`preCache()` – Optional helper
------------------------------

Preloads external resources to avoid first-capture stalls (helpful for big/complex trees).

import { preCache } from '@zumer/snapdom';

await preCache({
  root: document.body,
  embedFonts: true,
  localFonts: \[{ family: 'Inter', src: '/fonts/Inter.woff2', weight: 400 }\],
  useProxy: 'https://proxy.corsfix.com/?'
});

Limitations
-----------

-   External images should be CORS-accessible (use `useProxy` option for handling CORS denied)
-   When WebP format is used on Safari, it will fallback to PNG rendering.
-   `@font-face` CSS rule is well supported, but if need to use JS `FontFace()`, see this workaround `#43`

Performance Benchmarks
----------------------

**Setup.** Vitest benchmarks on Chromium, repo tests. Hardware may affect results. Values are **average capture time (ms)** → lower is better.

### Simple elements

Scenario

SnapDOM current

SnapDOM v1.9.9

html2canvas

html-to-image

Small (200×100)

**0.5 ms**

0.8 ms

67.7 ms

3.1 ms

Modal (400×300)

**0.5 ms**

0.8 ms

75.5 ms

3.6 ms

Page View (1200×800)

**0.5 ms**

0.8 ms

114.2 ms

3.3 ms

Large Scroll (2000×1500)

**0.5 ms**

0.8 ms

186.3 ms

3.2 ms

Very Large (4000×2000)

**0.5 ms**

0.9 ms

425.9 ms

3.3 ms

* * *

### Complex elements

Scenario

SnapDOM current

SnapDOM v1.9.9

html2canvas

html-to-image

Small (200×100)

**1.6 ms**

3.3 ms

68.0 ms

14.3 ms

Modal (400×300)

**2.9 ms**

6.8 ms

87.5 ms

34.8 ms

Page View (1200×800)

**17.5 ms**

50.2 ms

178.0 ms

429.0 ms

Large Scroll (2000×1500)

**54.0 ms**

201.8 ms

735.2 ms

984.2 ms

Very Large (4000×2000)

**171.4 ms**

453.7 ms

1,800.4 ms

2,611.9 ms

### Run the benchmarks

git clone https://github.com/zumerlab/snapdom.git
cd snapdom
npm install
npm run test:benchmark

Roadmap
-------

Planned improvements for future versions of SnapDOM:

-   **Implement plugin system** SnapDOM will support external plugins to extend or override internal behavior (e.g. custom node transformers, exporters, or filters).
    
-   **Refactor to modular architecture** Internal logic will be split into smaller, focused modules to improve maintainability and code reuse.
    
-   **Decouple internal logic from global options** Functions will be redesigned to avoid relying directly on `options`. A centralized capture context will improve clarity, autonomy, and testability. See `next` branch
    
-   **Expose cache control** Users will be able to manually clear image and font caches or configure their own caching strategies.
    
-   **Auto font preloading** Required fonts will be automatically detected and preloaded before capture, reducing the need for manual `preCache()` calls.
    
-   **Document plugin development** A full guide will be provided for creating and registering custom SnapDOM plugins.
    
-   **Make export utilities tree-shakeable** Export functions like `toPng`, `toJpg`, `toBlob`, etc. will be restructured into independent modules to support tree shaking and minimal builds.
    

Have ideas or feature requests? Feel free to share suggestions or feedback in GitHub Discussions.

Development
-----------

To contribute or build snapDOM locally:

# Clone the repository
git clone https://github.com/zumerlab/snapdom.git
cd snapdom

# Switch to dev branch
git checkout dev

# Install dependencies
npm install

# Compile the library (ESM, CJS, and minified versions)
npm run compile

# Install playwright browsers (necessary for running tests)
npx playwright install

# Run tests
npm test

# Run Benchmarks
npm run test:benchmark

The main entry point is in `src/`, and output bundles are generated in the `dist/` folder.

For detailed contribution guidelines, please see CONTRIBUTING.

Contributors
------------

Sponsors
--------

Special thanks to @megaphonecolin, @sdraper69, @reynaldichernando and @gamma-app, for supporting this project!

If you'd like to support this project too, you can become a sponsor.

Star History
------------

License
-------

MIT © Zumerlab
