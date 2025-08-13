---
project: blueprintui
stars: 323
description: :blue_book: Accelerate your development with flexible UI components and tools that work everywhere.
url: https://github.com/blueprintui/blueprintui
---

#### A collection of tools and UI components for building Web UIs that work everywhere.

-   Easy to use Web Components
-   Works in any Framework (Angular, React, Vue...)
-   Responsive and Customizable Themes
-   Layout, Typography, and Icons Utilites

Package

Downloads

CI Status

CDN

Documentation
-------------

-   Documentation
-   JavaScript CDN
-   Angular
-   Vue
-   React

Installation
------------

Blueprint UI components are built as Web Components. This enables them to work in a variety of frameworks and libraries. Blueprint UI is split into several packages that can be used independently. To use components its install the following,

npm install @blueprintui/components

Optional packages for layout and typography utilities are also available.

npm install @blueprintui/layout @blueprintui/typography

CSS
---

To use components the base theme CSS file must be loaded into the page. This can be done via a CSS import or HTML link.

@import '@blueprintui/themes/index.min.css';
@import '@blueprintui/themes/dark/index.min.css';

or

<link rel\="stylesheet" href\="@blueprintui/themes/index.min.css"\> 
<link rel\="stylesheet" href\="@blueprintui/themes/dark/index.min.css"\> 

CDN
---

Blueprint UI Components can be used via CDNs for fast and easy prototyping.

<link rel\="stylesheet" href\="https://unpkg.com/@blueprintui/themes/index.min.css"\>
<link rel\="stylesheet" href\="https://unpkg.com/@@blueprintui/themes/dark/index.min.css"\>

<script type\="module"\>
  import 'https://cdn.jsdelivr.net/npm/@blueprintui/components/include/alert.js/+esm';
</script\>

Using a Component
-----------------

Once the theme CSS is loaded, components can be imported via JavaScript imports.

import '@blueprintui/components/include/alert.js';

<body bp-theme\=" { theme: 'dark' });"\>

  <bp-alert status\="success"\>hello there!</bp-alert\>

</body\>
