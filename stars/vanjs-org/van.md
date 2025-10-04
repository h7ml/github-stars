---
project: van
stars: 4211
description: 🍦 VanJS: World's smallest reactive UI framework. Incredibly Powerful, Insanely Small - Everyone can build a useful UI app in an hour.
url: https://github.com/vanjs-org/van
---

🍦 **VanJS**: The Smallest Reactive UI Framework in the World
=============================================================

📣 Introducing VanX →  

🖊️ Get Started

📖 Tutorial

📚 Examples

📝 HTML/MD to VanJS Converter

⚔️ VanX

💬 Discuss

> Enable everyone to build useful UI apps with a few lines of code, anywhere, any time, on any device.

**VanJS** is an _**ultra-lightweight**_, _**zero-dependency**_ and _**unopinionated**_ Reactive UI framework based on pure vanilla JavaScript and DOM. Programming with **VanJS** feels like building React apps in a scripting language, without JSX. Check-out the `Hello World` code below:

// Reusable components can be just pure vanilla JavaScript functions.
// Here we capitalize the first letter to follow React conventions.
const Hello \= () \=> div(
  p("👋Hello"),
  ul(
    li("🗺️World"),
    li(a({href: "https://vanjs.org/"}, "🍦VanJS")),
  ),
)

van.add(document.body, Hello())
// Alternatively, you can write:
// document.body.appendChild(Hello())

Try on jsfiddle

You can convert any HTML or MD snippet into **VanJS** code with our online converter.

**VanJS** helps you manage states and UI bindings as well, with a more natural API:

const Counter \= () \=> {
  const counter \= van.state(0)
  return div(
    "❤️ ", counter, " ",
    button({onclick: () \=> ++counter.val}, "👍"),
    button({onclick: () \=> \--counter.val}, "👎"),
  )
}

van.add(document.body, Counter())

Try on jsfiddle

Why VanJS?
----------

### Reactive Programming without React/JSX

Declarative DOM tree composition, reusable components, reactive state binding - **VanJS** offers every good aspect that React does, but without the need of React, JSX, transpiling, virtual DOM, or any hidden logic. Everything is built with simple JavaScript functions and DOM.

### Grab 'n Go

_**No installation**_, _**no configuration**_, _**no dependencies**_, _**no transpiling**_, _**no IDE setups**_. Adding a line to your script or HTML file is all you need to start coding. And any code with **VanJS** can be pasted and executed directly in your browser's developer console. **VanJS** allows you to focus on the business logic of your application, rather than getting bogged down in frameworks and tools.

### Ultra-Lightweight

**VanJS** is the smallest reactive UI framework in the world, with just 1.0kB in the gzipped minified bundle. It's **50~100 times** smaller than most popular alternatives. Guess what you can get from this 1.0kB framework? All essential features of modern web frameworks - DOM templating, state, state binding, state derivation, effect, SPA, client-side routing and even hydration!

> _Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away._
> 
> _\-- Antoine de Saint-Exupéry, Airman's Odyssey_

### Easy to Learn

Simplicity at its core. Only 5 functions (`van.tags`, `van.add`, `van.state`, `van.derive`, `van.hydrate`). The entire tutorial plus the API reference is just one single web page, and can be learned within 1 hour for most developers.

### Performance

**VanJS** is among the fastest web frameworks, according to the results by krausest/js-framework-benchmark. For SSR, **Mini-Van** is **1.75X** to **2.25X** more efficient compared to React.

### TypeScript Support

**VanJS** provides first-class support for TypeScript. With the `.d.ts` file in place, you'll be able to take advantage of type-checking, IntelliSense, large-scale refactoring provided by your preferred development environment. Refer to the Download Table to find the right `.d.ts` file to work with.

Want to Learn More?
-------------------

-   Get Started (CDN, NPM or local download)
-   Learn from the Tutorial
-   Learn by Examples (and also Community Examples)
-   Get bored? 🎮 Play a fun game built with **VanJS** under 60 lines
-   Convert HTML or MD snippet to **VanJS** code with our online HTML/MD to **VanJS** Converter
-   Check out **VanUI** - A collection of grab 'n go reusable utility and UI components for **VanJS**
-   Want reactive list, global app state, server-driven UI, serialization and more? Check out **VanX** - The 1.2kB official **VanJS** extension
-   Want server-side rendering? Check out **Mini-Van** and Hydration (the entire vanjs.org site is built on top of **Mini-Van**)
-   Debugging complex dependencies in your app? checkout **VanGraph**
-   For questions, feedback or general discussions, visit our Discussions page
-   How did **VanJS** get its name?
-   ✨ Ask **VanJS** Guru - a **VanJS**\-focused AI to answer your questions

IDE Plug-ins
------------

-   VS Code Extension

See Also
--------

A Guide to Reading **VanJS** Codebase

Support & Feedback
------------------

🙏 **VanJS** aims to build a better world by reducing the entry barrier of UI programming, with no intention or plan on commercialization whatsoever. If you find **VanJS** interesting, or could be useful for you some day, please consider starring the project. It takes just a few seconds but your support means the world to us and helps spread **VanJS** to a wider audience.

> In the name of **Van**illa of the House **J**ava**S**cript, the First of its name, Smallest Reactive UI Framework, 1.0kB JSX-free Grab 'n Go Library, Scripting Language for GUI, GPT-Empowered Toolkit, by the word of Tao of the House Xin, Founder and Maintainer of **VanJS**, I do hereby grant you the permission of **VanJS** under MIT License.

Contact us: @taoxin / tao@vanjs.org / Tao Xin

Community Add-ons
-----------------

**VanJS** can be extended via add-ons. Add-ons add more features to **VanJS** and/or provide an alternative styled API. Below is a curated list of add-ons built by **VanJS** community:

Add-on

Description

Author

Van Cone

An SPA framework add-on for **VanJS**

b-rad-c

van\_element

Web Components with **VanJS**

Atmos4

VanJS Prerender

SSR support for **VanJS** (alternative to **Mini-Van**)

Binh Tran

VanJS Feather

Feather Icons for **VanJS**

thednp

van\_dml.js

A new flavour of composition for **VanJS**

Eckehard

van-jsx

A JSX wrapper for **VanJS**, for people who like the JSX syntax more

cqh963852

vanjs-router

A router solution for **VanJS** (`README.md` in simplified Chinese)

欧阳鹏

VanJS Routing

Yet another routing solution for **VanJS**

Kwame Opare Asiedu

VanJS Form

Fully typed form state management library (with validation) for **VanJS**

Kwame Opare Asiedu

vanjs-bootstrap

**VanJS** Bootstrap Components

Willi Commer

vanrx

An ultra-lightweight Redux addon for **VanJS**

Meddah Abdallah

VanFS

1:1 bindings from F# to **VanJS**

Ken Okabe

Van-wrapper

A tool that facilitates the rendering of **VanJS** elements within other popular frameworks

Zakaria Elalaoui

Create VanJS

The fastest way to kickstart your first **VanJS** Project: `npm create vanjs@latest`

thednp

Vite Plugin for VanJS

A mini meta-framework for **VanJS** featuring routing, metadata, isomorphic rendering and JSX transformation

thednp

Vite VanJS SVG

A Vite plugin to transform SVG files to **VanJS** components on the fly

thednp

VanJS Lucide

Lucide Icons for **VanJS**

thednp

P5.wrapper

A p5.js wrapper for **VanJS** built on top of ZikoJS

Zakaria Elalaoui

Van-Mdx

A Markdown preprocessor for **VanJS**

Zakaria Elalaoui

Van-Server

Server-side rendering for **VanJS** with file-based routing and client-side hydration

Zakaria Elalaoui

Contributors (68)
-----------------

_If I miss anyone's contribution here, apologies for my oversight 🙏, please comment on #87 to let me know._

Emoji key

  
**Tao Xin**  
🎨 💻 📖 💡

  
**Wei Sun**  
🐛

  
**Ryan Olson**  
🖋

  
**Tamotsu Takahashi**  
💻

  
**icecream17**  
💻

  
**enpitsulin**  
💡 💻

  
**Elliot Ford**  
💻

  
**andrewgryan**  
🎨 💻 🐛

  
**FredericH**  
💡 💻

  
**ebraminio**  
💻 ⚠️

  
**Eckehard**  
💻 🔌

  
**Austin Merrick**  
💻 🤔 🎨

  
**Lee Byonghun**  
💻

  
**caputdraconis**  
💻

  
**Achille Lacoin**  
💻

  
**cqh**  
💻 🔌

  
**awesome**  
📹

  
**artydev**  
💡 💬

  
**Neven DREAN**  
💡 🐛

  
**Stephen Handley**  
💡

  
**Ionut Stoica**  
🤔

  
**Rasmus Schultz**  
🤔

  
**cloudspeech**  
🤔

  
**Daniel Upshaw**  
🔌

  
**barrymun**  
💡

  
**Giulio Malventi**  
🖋 🐛 💻 🔌

  
**Yahia Berashish**  
🐛 💻 🔌 🤔 💡

  
**Phil Schumann**  
🐛

  
**Raphaël Gauthier**  
💻 🔌

  
**Nail**  
💻 🔌

  
**Brian Takita**  
🐛 🤔

  
**Jonny Fillmore**  
🐛

  
**Lima Neto**  
🖋

  
**b rad c**  
💻 🔌

  
**欧阳鹏**  
🔌 📹

  
**Daniel Mazurkiewicz**  
💻

  
**Atmos4**  
💻 🔌

  
**Kwame Opare Asiedu**  
🔌 💡

  
**ali-alnasser570**  
🤔

  
**Auryn Engel**  
📹

  
**Samuel Wyndham**  
📹

  
**sekoyo**  
🐛

  
**Owen Furnell**  
🐛

  
**MrVoltz**  
🐛

  
**Kane**  
💡

  
**Vlad Sirenko**  
💡 💻 🐛 🤔

  
**董凯**  
💡

  
**Meddah Abdallah**  
🔌

  
**Miroslaw**  
🐛

  
**Jon Nyman**  
🤔

  
**ericraider33**  
🐛

  
**Ken Okabe**  
🔌

  
**Nick**  
💡

  
**thednp**  
🔌 💻 🐛

  
**Bairui Su**  
💻

  
**jroush-ipg**  
🐛

  
**kangaroolab**  
💡

  
**Graham Stratford**  
🐛

  
**Kursat Aktas**  
💻 🔌

  
**bleistivt**  
🐛

  
**David Bismut**  
💻 🔌 🐛

  
**ZAKARIA ELALAOUI**  
🔌

  
**Michael Burdi**  
💻

  
**carlosmintfan**  
🐛

  
**reserved-word**  
🐛

  
**Binh Tran**  
🤔 💻 🔌

  
**Torbjorn Tyridal**  
🤔

  
**cubxx**  
🤔
