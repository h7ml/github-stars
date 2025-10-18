---
project: theme-ui
stars: 5373
description: Build consistent, themeable React apps based on constraint-based design principles
url: https://github.com/system-ui/theme-ui
---

Theme UI
========

**The Design Graph Framework**

  
  
  

  
Theme UI is a library for creating themeable user interfaces based on constraint-based design principles. Build custom component libraries, design systems, web applications, Gatsby themes, and more with a flexible API for best-in-class developer ergonomics.

**stable docs**: https://theme-ui.com  
**develop (prerelease) docs**: https://dev.theme-ui.com

* * *

Built for design systems, white-labels, themes, and other applications where customizing colors, typography, and layout are treated as first-class citizens and based on a standard Theme Specification, Theme UI is intended to work in a variety of applications, libraries, and other UI components. Colors, typography, and layout styles derived from customizable theme-based design scales help you build UI rooted in constraint-based design principles.

-   The next evolution of Styled System
-   From the creators of utility-based, atomic CSS methodologies
-   Theme-based styling with the `sx` prop
-   Compatible with virtually any UI component library
-   Works with existing Styled System components
-   Quick mobile-first responsive styles
-   Built-in support for dark modes
-   Primitive page layout components
-   Completely customizable with robust theming
-   Built with a standard Theme Specification for interoperability
-   Built with Emotion for scoped styles
-   Plugin for use in Gatsby sites and themes
-   Style MDX content with a simple, expressive API
-   Works with Typography.js themes

Getting Started
---------------

npm install theme-ui @emotion/react

_If you don't need color modes or components you can install **@theme-ui/core**_.

Any styles in your app can reference values from the global `theme` object. To provide the theme in context, wrap your application with the `ThemeUIProvider` component and pass in a custom `theme` object.

// basic usage
import { ThemeUIProvider } from 'theme-ui'
import theme from './theme'

export default (props) \=> (
  <ThemeUIProvider theme\={theme}\>{props.children}</ThemeUIProvider\>
)

The `theme` object follows the System UI Theme Specification, which lets you define custom color palettes, typographic scales, fonts, and more. Read more about theming.

// example theme.js
export default {
  fonts: {
    body: 'system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", sans-serif',
    heading: '"Avenir Next", sans-serif',
    monospace: 'Menlo, monospace',
  },
  colors: {
    text: '#000',
    background: '#fff',
    primary: '#33e',
  },
}

`sx` prop
---------

The `sx` prop works similarly to Emotion's `css` prop, accepting style objects to add CSS directly to an element in JSX, but includes extra theme-aware functionality. Using the `sx` prop for styles means that certain properties can reference values defined in your `theme` object. This is intended to make keeping styles consistent throughout your app the easy thing to do.

The `sx` prop only works in modules that have defined a custom pragma at the top of the file, which replaces the default React JSX functions. This means you can control which modules in your application opt into this feature without the need for a Babel plugin or additional configuration.

/\*\* @jsxImportSource theme-ui \*/

export default (props) \=> (
  <div
    sx\={{
      fontWeight: 'bold',
      fontSize: 4, // picks up value from \`theme.fontSizes\[4\]\`
      color: 'primary', // picks up value from \`theme.colors.primary\`
    }}
  \>
    Hello
  </div\>
)

Read more about how the custom pragma works.

Responsive styles
-----------------

The `sx` prop also supports using arrays as values to change properties responsively with a mobile-first approach. This API originated in Styled System and is intended as a terser syntax for applying responsive styles across a singular dimension.

/\*\* @jsxImportSource theme-ui \*/

export default (props) \=> (
  <div
    sx\={{
      // applies width 100% to all viewport widths,
      // width 50% above the first breakpoint,
      // and 25% above the next breakpoint
      width: \['100%', '50%', '25%'\],
    }}
  />
)

* * *

Documentation
-------------

-   Theming
-   The `sx` Prop
-   Layout
-   Color Modes
-   Theme Spec
-   Themed
-   MDX Components
-   Gatsby Plugin
-   API

MIT License

Contributors ✨
--------------

Thanks goes to these wonderful people (emoji key):

  
**Brent Jackson**  
🤔 💻 🎨 📖 💡 ⚠️ 👀

  
**Piotr Monwid-Olechnowicz**  
💻 📖 ⚠️ 👀 💡

  
**Dany Castillo**  
💻 📖 💡 ⚠️

  
**Jordan Overbye**  
💻 💡 ⚠️

  
**Lachlan Campbell**  
💻 💡 ⚠️ 👀 📖 💬

  
**John Otander**  
💻 👀 📖 ⚠️ 🤔

  
**David Burles**  
💻 👀 ⚠️ 📖

  
**Max Stoiber**  
💻 👀 ⚠️ 💡

  
**Atanas Stoyanov**  
💻 💬 ⚠️ 🐛 📖

  
**Lennart**  
💻 🐛 📖 💡

  
**Aleksandra Sikora**  
💻

  
**LB**  
💻 ⚠️

  
**Francis Champagne**  
💻 🐛 ⚠️ 📖

  
**Alex Page**  
💻 📖

  
**Adam Schay**  
💻

  
**Alex**  
💻 📖

  
**James Edmonds**  
💻 📖

  
**Florent SCHILDKNECHT**  
💻 📖

  
**Cole Bemis**  
💻 ⚠️ 📖

  
**John Letey**  
📖

  
**Yuraima Estevez**  
💻

  
**Allan Pope**  
💻 📖

  
**Emmanuel Pilande**  
💻

  
**Justin Hall**  
💻

  
**Marek**  
💻 🐛

  
**Björn Clees**  
📖 💻

  
**Iurii Kucherov**  
📖

  
**Joe Strouth**  
💻 🐛

  
**Stewart Everett**  
💻

  
**Travis Arnold**  
💻 📖

  
**Ivo Reis**  
💻

  
**Benedikt Rötsch**  
🐛 📖

  
**Jacob Cofman**  
📖

  
**John Letey**  
📖

  
**Lawrence Gosset**  
📖

  
**Markos Konstantopoulos**  
📖

  
**Robin Millette**  
💻

  
**Rodney Folz**  
💻

  
**Rodrigo Pombo**  
💻 ⚠️ 📖

  
**Scott Silvi**  
📖

  
**Shawn Allen**  
📖

  
**Tomas Carnecky**  
💻 🐛

  
**John Polacek**  
💻 🐛

  
**mackie**  
💻

  
**Aaron Adams**  
💻 🐛 📖

  
**Amberley**  
💻

  
**Andreea Năstase**  
📖

  
**Anson Low Z.F**  
🐛 📖

  
**Bernhard Gschwantner**  
💻

  
**Bhanu Prakash Korthiwada**  
📖

  
**Bruno Lemos**  
📖

  
**Bryce Fischer**  
💻

  
**Dan Wood**  
📖

  
**Debs**  
📖

  
**Edward O'Reilly**  
💻 🐛

  
**Eric Schaefer**  
💻

  
**Felix Green**  
📖

  
**Gerhard Bliedung**  
💻 🐛

  
**Guayo Mena**  
💡

  
**Guilherme Lima**  
📖

  
**Herb Caudill**  
📖

  
**Jacob Bolda**  
💻 🐛

  
**Jason Lengstorf**  
🐛 📖

  
**Jason Rundell (he/him)**  
💡

  
**Joe Race**  
📖

  
**Kanstantsin Klimashevich**  
📖

  
**Eka**  
📖 🐛

  
**Keir Williams**  
📖

  
**Kristóf Poduszló**  
💻 🐛 🤔

  
**Kyle Gill**  
📖

  
**Kyle Holmberg**  
📖

  
**Jay Laiche**  
💻

  
**Marc Wiest**  
💻

  
**Matheus Teixeira**  
💻

  
**matt-cratebind**  
📖

  
**Matt Zabriskie**  
💻

  
**Maxime Khoy**  
💻

  
**Michael Friedman**  
📖

  
**Michael Zetterberg fd. Lopez**  
💻

  
**Nathan Knowler**  
💻

  
**Neeraj Lagwankar**  
📖

  
**Owen Young**  
💻

  
**Patrick Arminio**  
💻 🐛

  
**Pedro Duarte**  
💻

  
**Ray Clanan**  
💻

  
**Rich Werden**  
📖

  
**Rob Phoenix**  
📖 🐛

  
**Robert Moggach**  
💻 🐛

  
**Anand Narayan**  
💻 🐛

  
**Sam Poder**  
📖

  
**Sam Rose**  
📖

  
**Sohrab**  
💻

  
**Spencer Rinehart**  
💻

  
**Steve**  
📖

  
**Steve Barton**  
📖

  
**Tim Reynolds**  
💻 🐛

  
**Vinícius Lemes**  
📖

  
**Yihwan Kim**  
💻 🐛

  
**Yuriy Burychka**  
📖

  
**Zolwiastyl**  
💻

  
**Amrish Kushwaha**  
💻

  
**Joe Bell**  
💻 🐛

  
**kenny-loveholidays**  
💻

  
**⦇⦀∙ˇ∎ˇ∙⦀⦈**  
💻 🐛

  
**navsgh**  
📖

  
**Shane O'Neill**  
📖

  
**汪磊**  
💻 🐛

  
**Carolin Maisenbacher**  
💻 📖 ⚠️

  
**Alex Chan**  
📖 💡 ⚠️ 💻

  
**Kenny**  
💻

  
**Jordie Bodlay**  
📖

  
**Matt Gleich**  
📖

  
**William Pei**  
📖 💡 💻 ⚠️

  
**Greg Poole**  
📖

  
**Akash**  
📖 💻

  
**Cannon Lock**  
📖

  
**kamatte**  
📖 💻

  
**Simen A. W. Olsen**  
📖 💡 ⚠️ 💻

  
**Wahid Rahim**  
📖 💡 💻

  
**Justin Cooper**  
📖

  
**CJ**  
📖 💻

This project follows the all-contributors specification. Contributions of any kind welcome!
