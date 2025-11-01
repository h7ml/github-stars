---
project: vanilla-extract
stars: 10200
description: Zero-runtime Stylesheets-in-TypeScript
url: https://github.com/vanilla-extract-css/vanilla-extract
---

🧁 vanilla-extract
==================

**Zero-runtime Stylesheets-in-TypeScript.**

Write your styles in TypeScript (or JavaScript) with locally scoped class names and CSS Variables, then generate static CSS files at build time.

Basically, it’s “CSS Modules\-in-TypeScript” but with scoped CSS Variables + heaps more.

🔥   All styles generated at build time — just like Sass, Less, etc.

✨   Minimal abstraction over standard CSS.

🦄   Works with any front-end framework — or even without one.

🌳   Locally scoped class names — just like CSS Modules.

🚀   Locally scoped CSS Variables, `@keyframes` and `@font-face` rules.

🎨   High-level theme system with support for simultaneous themes. No globals!

🛠   Utils for generating variable-based `calc` expressions.

💪   Type-safe styles via CSSType.

🏃‍♂️   Optional runtime version for development and testing.

🙈   Optional API for dynamic runtime theming.

* * *

🌐 Check out the documentation site for setup guides, examples and API docs.

* * *

🖥   Try it out for yourself in CodeSandbox.

* * *

**Write your styles in `.css.ts` files.**

// styles.css.ts

import { createTheme, style } from '@vanilla-extract/css';

export const \[themeClass, vars\] \= createTheme({
  color: {
    brand: 'blue'
  },
  font: {
    body: 'arial'
  }
});

export const exampleStyle \= style({
  backgroundColor: vars.color.brand,
  fontFamily: vars.font.body,
  color: 'white',
  padding: 10
});

> 💡 Once you've configured your build tooling, these `.css.ts` files will be evaluated at build time. None of the code in these files will be included in your final bundle. Think of it as using TypeScript as your preprocessor instead of Sass, Less, etc.

**Then consume them in your markup.**

// app.ts

import { themeClass, exampleStyle } from './styles.css.ts';

document.write(\`
  <section class="${themeClass}">
    <h1 class="${exampleStyle}">Hello world!</h1>
  </section>
\`);

* * *

Want to work at a higher level while maximising style re-use? Check out 🍨 Sprinkles, our official zero-runtime atomic CSS framework, built on top of vanilla-extract.

* * *

Thanks
------

-   Nathan Nam Tran for creating css-in-js-loader, which served as the initial starting point for treat, the precursor to this library.
-   Stitches for getting us excited about CSS-Variables-in-JS.
-   SEEK for giving us the space to do interesting work.

License
-------

MIT.
