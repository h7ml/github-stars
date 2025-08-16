---
project: panda
stars: 5719
description: 🐼 Universal, Type-Safe, CSS-in-JS Framework for Design Systems ⚡️
url: https://github.com/chakra-ui/panda
---

  
Panda is a universal styling solution for the modern web —  
build time, type safe, and scalable CSS-in-JS  
  

  
  

Features
--------

-   ⚡️ Write style objects or style props, extract them at build time
-   ✨ Modern CSS output — cascade layers `@layer`, css variables and more
-   🦄 Works with most JavaScript frameworks
-   🚀 Recipes and Variants - Just like Stitches™️ ✨
-   🎨 High-level design tokens support for simultaneous themes
-   💪 Type-safe styles and autocomplete (via codegen)

  

* * *

**🐼 Get a taste of Panda. Try it out for yourself in  StackBlitz**

* * *

  

Documentation
-------------

Visit our official documentation.

Install
-------

The **recommended** way to install the latest version of Panda is by running the command below:

npm i -D @pandacss/dev

To scaffold the panda config and postcss

npx panda init -p

Setup and import the entry CSS file

@layer reset, base, tokens, recipes, utilities;

import 'path/to/entry.css'

Start the dev server of your project

npm run dev

Start using panda

import { css } from '../styled-system/css'
import { stack, vstack, hstack } from '../styled-system/patterns'

function Example() {
  return (
    <div\>
      <div className\={hstack({ gap: '30px', color: 'pink.300' })}\>Box 1</div\>
      <div className\={css({ fontSize: 'lg', color: 'red.400' })}\>Box 2</div\>
    </div\>
  )
}

Directory Structure
-------------------

Package

Description

cli

CLI package installed by the end user

core

Contains core features of Panda (utility, recipes, etc)

config

Contains functions for reading and merging the panda config

extractor

Contains code for fast AST parsing and scanning

generator

Contains codegen artifacts (js, css, jsx)

parser

Contains code for parsing a source code

is-valid-prop

Contains code for checking if a prop is a valid css prop

node

Contains the Node.js API of Panda's features

token-dictionary

Contains code used to process tokens and semantic tokens

shared

Contains shared TS functions

Contributing
------------

Feel like contributing? That's awesome! We have a contributing guide to help guide you.

### Want to help improve the docs?

Our docsite lives in the monorepo.

If you're interested in contributing to the documentation, check out the contributing guide.

Support
-------

Having trouble? Get help in the official Panda Discord.

Acknowledgement
---------------

The development of Panda was only possible due to the inspiration and ideas from these amazing projects.

-   Chakra UI - where it all started
-   Vanilla Extract - for inspiring the utilities API
-   Stitches - for inspiring the recipes and variants API
-   Tailwind CSS - for inspiring the JIT compiler and strategy
-   Class Variance Authority - for inspiring the `cva` name
-   Styled System - for the initial idea of Styled Props
-   Linaria - for inspiring the initial atomic css strategy
-   Uno CSS - for inspiring the studio and astro integration
-   Goober - for tiny and performant js functions in template literal styles

License
-------

MIT License © 2023-Present Segun Adebayo
