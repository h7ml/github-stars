---
project: papanasi
stars: 597
description: 🥯Papanasi is the Frontend UI library to use cross Frameworks. A set of components to use in Angular, Preact, Qwik, React, Solid, Svelte, Vue and Web Components
url: https://github.com/CKGrafico/papanasi
---

Sorry I've no time right now consider this a little bit outdated/archived.

The Universal UI Library


============================

### 🔍 Overview

🥯Papanasi _(pronunced pɑpənæʃ or papanash)_ is a **UI library to use cross Frameworks**. A set of components to use in Angular, Preact, Qwik, React, Solid, Svelte, Vue and Web Components. Is based on the Mitosis library and documented using Storybook.

### 🚀 Platforms

  
**Angular**  

  
**Preact**  

  
**Qwik**  

  
**React**  

  
**Solid**  

  
**Svelte**  

  
**Vue**  

  
**Web Comps.**  

### 🔮 Demos

  
**Nextjs**  

  
**Nuxt 3**  

  
**Svelte Kit**  

  
**Solid Start**  

  
**Qwik City**  

### 📣 Manifesto

This library born as a pet project to create universal components, easy to extend in any project and easy to use with any framework, is based on the next principles:

#### A Component...

-   ...should be **cross-libraries** but the code should be written once.
-   ...should have a **minimum style** but easy to extend it via CSS by any dev.
-   ...should provide some **optional themes** to make it easy to use.
-   ...should be **accessible** (FUTURE RELEASES).
-   ...should be **made for developers** not for non-coders, they will decide how to style most of the things.
-   ...should be tree-shakable.
-   ...should be compatible with **StoryBook**.
-   ...should be inspired by other UI Libraries and **don't reinvent the wheel**.
-   ...should be easy to create new **variants**.

### 🧩 Elements Showcase

#### Layout

  
**Container**  
  
  

  
**Row**  
  
  

  
**Column**  
  
  

  
**Grid**  
  
  

#### Components

  
**Avatar**  
  
  

  
**Button**  
  
  

  
**Code**  
  
  

  
**Pill**  
  
  

  
**Spinner**  
  
  

#### Enterprise

  
**Itchio**  
  
  

#### Extensions

  
**Tooltip**  
  
  

### 📚 Setup and scripts

With **npm**:

```
$ npm install @papanasi/[target] # ex: @papanasi/react
```

With **yarn**:

```
$ yarn add @papanasi/[target] # ex: @papanasi/vue
```

### 🪲 Debugger

To debug elements you can use `setDebugLevel` function from `@papanasi/[target]` package. This function is totally optional and the default value is `DebugLevel.None` the recommended is to use `DebugLevel.Log` to have a log of the different events happening.

window.addEventListener('load', () \=> {
  setDebugLevel(DebugLevel.Log);
});

### 📗 Documentation

To learn more about Papanasi, check the documentation.

### 📃 License

MIT

### 🚀 Contributing

Contributing Guidelines

To build the project run:

```
> yarn compile
```

You can choose which frameworks to build by passing the `--platforms`:

```
> yarn compile --platforms react vue
```

It is also possible to specify which components to build `--elements`:

```
> yarn compile --elements avatar pill
```

If you want to disable the linting use `--no-lint`:

```
> yarn compile --no-lint
```

To contribute and watch the changes in local environment just use:

```
> yarn dev
```

Finally, to launch storybook use:

```
> yarn start
```

### Our Sponsors

  
Sponsor the project

  
HelpDev

### Thanks to everyone who contributed:

And special thanks to @samijaber @mhevery and Builder project
