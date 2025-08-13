---
project: hastscript
stars: 185
description: utility to create hast trees
url: https://github.com/syntax-tree/hastscript
---

hastscript
==========

hast utility to create trees with ease.

Contents
--------

-   What is this?
-   When should I use this?
-   Install
-   Use
-   API
    -   `h(selector?[, properties][, …children])`
    -   `s(selector?[, properties][, …children])`
    -   `Child`
    -   `Properties`
    -   `Result`
-   Syntax tree
-   JSX
-   Compatibility
-   Security
-   Related
-   Contribute
-   License

What is this?
-------------

This package is a hyperscript interface (like `createElement` from React and `h` from Vue and such) to help with creating hast trees.

When should I use this?
-----------------------

You can use this utility in your project when you generate hast syntax trees with code. It helps because it replaces most of the repetition otherwise needed in a syntax tree with function calls. It also helps as it improves the attributes you pass by turning them into the form that is required by hast.

You can instead use `unist-builder` when creating any unist nodes and `xastscript` when creating xast (XML) nodes.

Install
-------

This package is ESM only. In Node.js (version 16+), install with npm:

npm install hastscript

In Deno with `esm.sh`:

import {h} from 'https://esm.sh/hastscript@9'

In browsers with `esm.sh`:

<script type\="module"\>
  import {h} from 'https://esm.sh/hastscript@9?bundle'
</script\>

Use
---

import {h, s} from 'hastscript'

console.log(
  h('.foo#some-id', \[
    h('span', 'some text'),
    h('input', {type: 'text', value: 'foo'}),
    h('a.alpha', {class: 'bravo charlie', download: 'download'}, \[
      'delta',
      'echo'
    \])
  \])
)

console.log(
  s('svg', {viewbox: '0 0 500 500', xmlns: 'http://www.w3.org/2000/svg'}, \[
    s('title', 'SVG \`<circle>\` element'),
    s('circle', {cx: 120, cy: 120, r: 100})
  \])
)

Yields:

{
  type: 'element',
  tagName: 'div',
  properties: {className: \['foo'\], id: 'some-id'},
  children: \[
    {
      type: 'element',
      tagName: 'span',
      properties: {},
      children: \[{type: 'text', value: 'some text'}\]
    },
    {
      type: 'element',
      tagName: 'input',
      properties: {type: 'text', value: 'foo'},
      children: \[\]
    },
    {
      type: 'element',
      tagName: 'a',
      properties: {className: \['alpha', 'bravo', 'charlie'\], download: true},
      children: \[{type: 'text', value: 'delta'}, {type: 'text', value: 'echo'}\]
    }
  \]
}
{
  type: 'element',
  tagName: 'svg',
  properties: {viewBox: '0 0 500 500', xmlns: 'http://www.w3.org/2000/svg'},
  children: \[
    {
      type: 'element',
      tagName: 'title',
      properties: {},
      children: \[{type: 'text', value: 'SVG \`<circle>\` element'}\]
    },
    {
      type: 'element',
      tagName: 'circle',
      properties: {cx: 120, cy: 120, r: 100},
      children: \[\]
    }
  \]
}

API
---

This package exports the identifiers `h` and `s`. There is no default export. It exports the additional TypeScript types `Child`, `Properties`, and `Result`.

The export map supports the automatic JSX runtime. You can pass `hastscript` or `hastscript/svg` to your build tool (TypeScript, Babel, SWC) with an `importSource` option or similar.

### `h(selector?[, properties][, …children])`

Create virtual **hast** trees for HTML.

##### Signatures

-   `h(): root`
-   `h(null[, …children]): root`
-   `h(selector[, properties][, …children]): element`

##### Parameters

###### `selector`

Simple CSS selector (`string`, optional). When string, builds an `Element`. When nullish, builds a `Root` instead. The selector can contain a tag name (`foo`), IDs (`#bar`), and classes (`.baz`). If the selector is a string but there is no tag name in it then `h` defaults to build a `div` element and `s` to a `g` element. `selector` is parsed by `hast-util-parse-selector`.

###### `properties`

Properties of the element (`Properties`, optional).

###### `children`

Children of the node (`Child` or `Array<Child>`, optional).

##### Returns

Created tree (`Result`).

`Element` when a `selector` is passed, otherwise `Root`.

### `s(selector?[, properties][, …children])`

Create virtual **hast** trees for SVG.

Signatures, parameters, and return value are the same as `h` above. Importantly, the `selector` and `properties` parameters are interpreted as SVG.

### `Child`

(Lists of) children (TypeScript type).

When strings or numbers are encountered, they are turned into `Text` nodes. `Root` nodes are treated as “fragments”, meaning that their children are used instead.

###### Type

type Child \=
  | Array<Node | number | string | null | undefined\>
  | Node
  | number
  | string
  | null
  | undefined

### `Properties`

Map of properties (TypeScript type). Keys should match either the HTML attribute name or the DOM property name, but are case-insensitive.

###### Type

type Properties \= Record<
  string,
  | boolean
  | number
  | string
  | null
  | undefined
  // For comma- and space-separated values such as \`className\`:
  | Array<number | string\>
  // Accepts value for \`style\` prop as object.
  | Record<string, number | string\>
\>

### `Result`

Result from a `h` (or `s`) call (TypeScript type).

###### Type

type Result \= Element | Root

Syntax tree
-----------

The syntax tree is hast.

JSX
---

This package can be used with JSX. You should use the automatic JSX runtime set to `hastscript` or `hastscript/svg`.

> 👉 **Note** while `h` supports dots (`.`) for classes or number signs (`#`) for IDs in `selector`, those are not supported in JSX.

> 🪦 **Legacy**: you can also use the classic JSX runtime, but this is not recommended. To do so, import `h` (or `s`) yourself and define it as the pragma (plus set the fragment to `null`).

The Use example above can then be written like so, using inline pragmas, so that SVG can be used too:

`example-html.jsx`:

/\*\* @jsxImportSource hastscript \*/
console.log(
  <div class\="foo" id\="some-id"\>
    <span\>some text</span\>
    <input type\="text" value\="foo" />
    <a class\="alpha bravo charlie" download\>
      deltaecho
    </a\>
  </div\>
)

`example-svg.jsx`:

/\*\* @jsxImportSource hastscript/svg \*/
console.log(
  <svg xmlns\="http://www.w3.org/2000/svg" viewbox\="0 0 500 500"\>
    <title\>SVG \`&lt;circle&gt;\` element</title\>
    <circle cx\={120} cy\={120} r\={100} />
  </svg\>
)

Compatibility
-------------

Projects maintained by the unified collective are compatible with maintained versions of Node.js.

When we cut a new major release, we drop support for unmaintained versions of Node. This means we try to keep the current release line, `hastscript@9`, compatible with Node.js 16.

Security
--------

Use of `hastscript` can open you up to a cross-site scripting (XSS) when you pass user-provided input to it because values are injected into the syntax tree.

The following example shows how an image is injected that fails loading and therefore runs code in a browser.

const tree \= h()

// Somehow someone injected these properties instead of an expected \`src\` and
// \`alt\`:
const otherProps \= {onError: 'alert(1)', src: 'x'}

tree.children.push(h('img', {src: 'default.png', ...otherProps}))

Yields:

<img onerror\="alert(1)" src\="x"\>

The following example shows how code can run in a browser because someone stored an object in a database instead of the expected string.

const tree \= h()

// Somehow this isn’t the expected \`'wooorm'\`.
const username \= {
  type: 'element',
  tagName: 'script',
  children: \[{type: 'text', value: 'alert(2)'}\]
}

tree.children.push(h('span.handle', username))

Yields:

<span class\="handle"\><script\>alert(2)</script\></span\>

Either do not use user-provided input in `hastscript` or use `hast-util-santize`.

Related
-------

-   `unist-builder` — create unist trees
-   `xastscript` — create xast trees
-   `hast-to-hyperscript` — turn hast into React, Preact, Vue, etc
-   `hast-util-to-html` — turn hast into HTML
-   `hast-util-to-dom` — turn hast into DOM trees
-   `estree-util-build-jsx` — compile JSX away

Contribute
----------

See `contributing.md` in `syntax-tree/.github` for ways to get started. See `support.md` for ways to get help.

This project has a code of conduct. By interacting with this repository, organization, or community you agree to abide by its terms.

License
-------

MIT © Titus Wormer
