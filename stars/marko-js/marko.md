---
project: marko
stars: 13668
description: A declarative, HTML-based language that makes building web apps fun
url: https://github.com/marko-js/marko
---

**A declarative, HTML-based language that makes building web apps fun 🔥**

Docs ∙ Try Online ∙ Contribute ∙ Get Support

Intro
-----

Marko is HTML _reimagined_ as a language for building dynamic and reactive user interfaces. Almost any valid HTML is valid Marko, and Marko extends HTML for building modern applications more declaratively. Among these extensions are conditionals and lists, state, and components.

Marko supports both single-file components and components across separate files.

### Single-file component

The following renders a button and a counter of how many times the button has been pressed:

**click-count.marko**

class {
  onCreate() {
    this.state \= { count: 0 };
  }
  increment() {
    this.state.count++;
  }
}

style {
  .count {
    color: #09c;
    font-size: 3em;
  }
  .press-me {
    padding: 0.5em;
  }
}

<output.count\>
  ${state.count}
</output\>
<button.press-me on-click('increment')\>
  Press me!
</button\>

### Multi-file component

The same component as above, but split into:

-   `index.marko` template file
-   `component.js` component JS logic file
-   `style.css` component styles file

**index.marko**

<output.count\>
  ${state.count}
</output\>
<button.press-me on-click('increment')\>
  Press me!
</button\>

**component.js**

export default {
  onCreate() {
    this.state \= { count: 0 };
  },
  increment() {
    this.state.count++;
  },
};

**style.css**

.count {
  color: #09c;
  font-size: 3em;
}
.press-me {
  padding: 0.5em;
}

Concise Syntax
--------------

Marko also supports a beautifully concise syntax as an alternative to its HTML syntax:

Concise syntax

HTML syntax

ul.example-list
  for|color| of\=\[a, b, c\]
    li -- ${color}

<ul class\="example-list"\>
  <for|color| of\=\[a, b, c\]\>
    <li\>${color}</li\>
  </for\>
</ul\>

Getting Started
---------------

1.  `npm install marko`
2.  Read the docs

Community & Support
-------------------

Ask and answer StackOverflow questions with the `#marko` tag

Come hang out in our Discord chat, ask questions, and discuss project direction

Tweet to `@MarkoDevTeam`, or with the `#markojs` hashtag

### Contributors

Marko would not be what it is without all those who have contributed ✨

### Get Involved!

-   Pull requests are welcome!
-   Submit GitHub issues for any feature enhancements, bugs, or documentation problems
-   Read the Contribution Tips and Guidelines
-   Participants in this project agree to abide by its Code of Conduct
