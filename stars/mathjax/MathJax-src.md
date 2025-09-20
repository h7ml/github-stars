---
project: MathJax-src
stars: 2271
description: MathJax source code for version 3 and beyond
url: https://github.com/mathjax/MathJax-src
---

MathJax (Source Repository)
===========================

Beautiful math in all browsers
------------------------------

MathJax is an open-source JavaScript display engine for LaTeX, MathML, and AsciiMath notation that works in all modern browsers, with built-in support for assistive technology like screen readers, including automatic speech generation and an expression explorer that can be used to investigate typeset mathematics on a more granular level than the complete expression. It requires no setup on the part of the user (no plugins to download or software to install), so the page author can write web documents that include mathematics and be confident that users will be able to view it naturally and easily. Simply include MathJax and some mathematics in a web page, and MathJax does the rest.

Some of the main features of MathJax include:

-   High-quality display of LaTeX, MathML, and AsciiMath notation in HTML pages
    
-   Supported in most browsers with no plug-ins, extra fonts, or special setup for the reader
    
-   Easy for authors, flexible for publishers, extensible for developers
    
-   Supports math accessibility, cut-and-paste interoperability, and other advanced functionality
    
-   Powerful API for integration with other web applications
    

See http://www.mathjax.org/ for additional details about MathJax, and https://docs.mathjax.org for the MathJax documentation.

What's in this Repository
-------------------------

This repository contains the source files for MathJax, which are written in TypeScript. These are compiled into JavaScript files and then combined into component files for use on the web. The component files are available from several CDN services that host MathJax, and also from the MathJax Component Repository. Node applications can use either the component files, or call the MathJax JavaScript files directly.

Installation and Use
--------------------

### Using MathJax in web browsers

If you are loading MathJax from a CDN into a web page, there is no need to install anything. Simply use a `script` tag that loads MathJax from the CDN. E.g.,

<script src\="https://cdn.jsdelivr.net/npm/mathjax@4/tex-mml-chtml.js" defer\></script\>

See the MathJax documentation and the MathJax Web Demos, and the MathJax Node Demos for more information.

### Using MathJax Components in node applications

To use MathJax components in a node application, install the `mathjax` package:

npm install mathjax@4

Then import `mathjax` within your application and initialize it:

import MathJax from 'mathjax';
await MathJax.init({ ... });

where `{ ... }` is the MathJax configuration you want to use. E.g.,

import MathJax from 'mathjax';
await MathJax.init({
  loader: {load: \['input/tex', 'output/svg'\]}
});
const svg \= await MathJax.tex2svgPromise('\\\\frac{1}{x^2-1}', {display: true});
console.log(MathJax.startup.adaptor.outerHTML(svg));

Alternatively, in an ES5 node application, you can use

const MathJax \= require('mathjax');
MathJax.init({ ... }).then(() \=> { ... });

where the first `{ ... }` is a MathJax configuration, and the second `{ ... }` is the code to run after MathJax has been loaded. E.g.

const MathJax \= require('mathjax');
MathJax.init({
  loader: {load: \['input/tex', 'output/svg'\]}
}).then(() \=> {
  const svg \= MathJax.tex2svg('\\\\frac{1}{x^2-1}', {display: true});
  console.log(MathJax.startup.adaptor.outerHTML(svg));
}).catch((err) \=> console.log(err.message));

**Note:** the technique in the two examples above is for node-based application only, not for browser applications. This method sets up an alternative DOM implementation, which you don't need in the browser, and it depends on node and the local file system in other ways. This setup will not work properly in the browser, even if you webpack it or use some other bundler.

See the documentation and the MathJax Node Repository for more details.

### Using MathJax modules directly in node applications

You can use the MathJax JavaScript files (as opposed to MathJax components) directly in node applications. This gives you the greatest flexibility, but requires more coding. To use this approach, install the `@mathjax/src` package:

```
npm install @mathjax/src
```

This will provide the following directories:

```
node_modules/
  @mathjax/src/
    ts/                  the MathJax source TypeScript files
    js/                  the compiled JavaScript files
    components/          the component build tools and control files
    bundle/              the packages component files
```

You can use the components and JavaScript files directly in your node applications (see the MathJax node demos for examples).

If you want to work from the GitHub repository directly, then do the following:

git clone https://github.com/mathjax/MathJax-src.git mathjax-src
cd mathjax-src
npm run --silent build-all

in order to compile the JavaScript files from the TypeScript source, and build the component files from the JavaScript files.

Code Contributions
------------------

If you are interested in contributing code to MathJax, please see the documentation for contributors for details on how to do this, and for the policies for making pull requests. In particular, please be careful that you are working from the proper branch in the git repository, or you may be asked to rebase your changes when you make a pull request.

MathJax Community
-----------------

The main MathJax website is http://www.mathjax.org, and it includes announcements and other important information. A MathJax user forum for asking questions and getting assistance is hosted at Google, and the MathJax bug tracker is hosted at GitHub.

Before reporting a bug, please check that it has not already been reported. Also, please use the bug tracker (rather than the help forum) for reporting bugs, and use the user's forum (rather than the bug tracker) for questions about how to use MathJax.

MathJax Resources
-----------------

-   MathJax Documentation
-   MathJax Components
-   MathJax Source Code
-   MathJax Web Examples
-   MathJax Node Examples
-   MathJax Bug Tracker
-   MathJax Users' Group
