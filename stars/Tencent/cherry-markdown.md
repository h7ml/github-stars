---
project: cherry-markdown
stars: 4386
description: ✨ A Markdown Editor
url: https://github.com/Tencent/cherry-markdown
---

Cherry Markdown Writer
======================

English | 简体中文

Introduction
------------

Cherry Markdown Writer is a Javascript Markdown editor. It has the advantages such as out-of-the-box, lightweight and easy to extend. It can run in browser or server(with NodeJs).

### Document

-   Getting Started with Cherry Markdown Editor
-   hello world
-   Configuring Image & File Upload Interfaces
-   Adjusting the Toolbar
-   Comprehensive Configuration Options
-   Custom Syntax
-   Configuring Themes
-   Extending Code Block Syntax
-   Events & Callbacks
-   API

### Demos

-   Full Model
-   Basic
-   Mobile
-   Multiple Instances
-   Editor Without Toolbar
-   Pure Preview
-   XSS (Disabled by default; requires configuration to enable XSS)
-   IMG WYSIWYG
-   Table WYSIWYG
-   Headers with Auto Num
-   Stream Input Mode (AI chat scenario)
-   VIM Editing Mode
-   Utilize Your Own Mermaid.js

* * *

### **Out-of-the-box**

Developer can call and instantiate Cherry Markdown Editor in a very simple way. The instantiated Cherry Markdown Editor supports most commonly used markdown syntax (such as title, TOC, flowchart, formula, etc.) by default.

### **Easy to extend**

When the syntax that Cherry Markdown writer support can not meet your needs, secondary development or function extention can be carried out quickly. At the same time, Cherry Markdown writer should be implemented by pure JavaScript, and should not rely on framework technology such as angular, vue and react. Framework only provide a container environment.

Feature
-------

### Syntax Feature

1.  Image zoom, alignment and reference
2.  Generate a chart based on table content
3.  Adjust font color and size
4.  Font background color, superscript and subscript
5.  Insert checklist
6.  Insert audio and video
7.  Mermaid diagrams and math formulas
8.  Info panels

### Functional Feature

1.  Paste from rich text as markdown
2.  Classic & regular line break modes
3.  Multi-cursor editing
4.  Image size editing
5.  Table editing
6.  Table -> Chart (generate chart from table content)
7.  Export as image or PDF
8.  Floating toolbar: appears at the beginning of a new line
9.  Bubble toolbar: appears when text is selected
10.  Set shortcut keys
11.  Floating table of contents
12.  Theme switching
13.  Input suggestion (autocomplete)
14.  AI Chat scenario: stream-mode output supported

### Performance Feature

1.  partial rendering
2.  partial update

### Security

Cherry Markdown has a built-in security Hook, by filtering the whitelist and DomPurify to do scan filter.

### Style theme

Cherry Markdown has a variety of style themes to choose from.

### Features Showcase

Click to view the features demonstration Features demo

Install
-------

Via yarn

yarn add cherry-markdown

Via npm

npm install cherry-markdown --save

If you need to enable the functions of `mermaid` drawing and table-to-chart, you need to add `mermaid` and `echarts` packages at the same time.

Cherry Markdown has built-in mermaid, if you want to use a specified version of mermaid, you can refer to wiki

Quick start
-----------

### Browser

#### UMD

<link href\="cherry-editor.min.css" />
<div id\="markdown-container"\></div\>
<script src\="cherry-editor.min.js"\></script\>
<script\>
  new Cherry({
    id: 'markdown-container',
    value: '# welcome to cherry editor!',
  });
</script\>

#### ESM

import 'cherry-markdown/dist/cherry-markdown.css';
import Cherry from 'cherry-markdown';
const cherryInstance \= new Cherry({
  id: 'markdown-container',
  value: '# welcome to cherry editor!',
});

### Node

const { default: CherryEngine } \= require('cherry-markdown/dist/cherry-markdown.engine.core.common');
const cherryEngineInstance \= new CherryEngine();
const htmlContent \= cherryEngineInstance.makeHtml('# welcome to cherry editor!');

Lite Version
------------

Because the size of the mermaid library is very large, the cherry build product contains a core build package without built-in Mermaid. The core build can be imported in the following ways.

### Full mode (With UI Interface)

import 'cherry-markdown/dist/cherry-markdown.css';
import Cherry from 'cherry-markdown/dist/cherry-markdown.core';
const cherryInstance \= new Cherry({
  id: 'markdown-container',
  value: '# welcome to cherry editor!',
});

### Engine Mode (Just Syntax Compile)

// Import Cherry engine core construction
// Engine configuration items are the same as Cherry configuration items, the following document content only introduces the Cherry core package
import CherryEngine from 'cherry-markdown/dist/cherry-markdown.engine.core';
const cherryEngineInstance \= new CherryEngine();
const htmlContent \= cherryEngineInstance.makeHtml('# welcome to cherry editor!');

// --> <h1>welcome to cherry editor!</h1>

### ⚠️ About mermaid

The core build package does not contain mermaid dependency, should import related plug-ins manually.

import 'cherry-markdown/dist/cherry-markdown.css';
import Cherry from 'cherry-markdown/dist/cherry-markdown.core';
import CherryMermaidPlugin from 'cherry-markdown/dist/addons/cherry-code-block-mermaid-plugin';
import mermaid from 'mermaid';

// Plug-in registration must be done before Cherry is instantiated
Cherry.usePlugin(CherryMermaidPlugin, {
  mermaid, // pass in mermaid object
  // mermaidAPI: mermaid.mermaidAPI, // Can also be passed in mermaid API
  // At the same time, you can configure mermaid's behavior here, please refer to the official mermaid document
  // theme: 'neutral',
  // sequence: { useMaxWidth: false, showSequenceNumbers: true }
});

const cherryInstance \= new Cherry({
  id: 'markdown-container',
  value: '# welcome to cherry editor!',
});

From mermaid v10.0.0, the rendering logic changed from synchronous to asynchronous. After `afterChange` or `afterInit` events, mermaid code blocks are rendered as placeholders first, then rendered asynchronously and replaced.

If you need to get the content after asynchronous rendering is finished, you can use the following example:

const cherryInstance \= new Cherry({
  id: 'markdown-container',
  // Use a template string to include the mermaid code block directly
  value: \`
    \`\`\`mermaid
    graph LR
        A\[Company\] \--\>| Off work | B(Market)
        B \--\> C{See<br\>melon seller}
        C \--\>|Yes| D\[Buy a bun\]
        C \--\>|No| E\[Buy one pound of buns\]
    \`\`\`
  \`,
  callback: {
    afterAsyncRender: (md, html) \=> {
      // md is the markdown source, html is the rendered result
    }
  }
});

### Dynamic import

**recommend** Using Dynamic import, the following is an example of webpack Dynamic import.

import 'cherry-markdown/dist/cherry-markdown.css';
import Cherry from 'cherry-markdown/dist/cherry-markdown.core';

const registerPlugin \= async () \=> {
  const \[{ default: CherryMermaidPlugin }, mermaid\] \= await Promise.all(\[
    import('cherry-markdown/src/addons/cherry-code-block-mermaid-plugin'),
    import('mermaid'),
  \]);
  Cherry.usePlugin(CherryMermaidPlugin, {
    mermaid, // pass in mermaid object
  });
};

registerPlugin().then(() \=> {
  //  Plug-in registration must be done before Cherry is instantiated
  const cherryInstance \= new Cherry({
    id: 'markdown-container',
    value: '# welcome to cherry editor!',
  });
});

Configuration
-------------

see `/src/Cherry.config.js` or click here

Example
-------

Click here for more examples.

### Client

Under development, please stay tuned or see `/packages/client/`

Extension
---------

### Customize Syntax

See the custom syntax documentation: Custom syntax docs

### Customize Toolbar

Cherry supports five toolbar positions, each position can be extended with custom toolbar buttons. See the toolbar configuration documentation for details: Customize toolbar buttons.

Unit Test
---------

`Vitest` has been added as a basic configuration, but the related test cases have not been fully tested. Welcome to submit rich test cases.

Contribution Guidelines
-----------------------

Welcome to join us in building a powerful Markdown editor. You can also submit feature requests as issues. Before writing new features, you can learn about the Introduction to cherry-markdown editor. Please read the Contribution Guidelines before making contributions.

Stargazers over time
--------------------

License
-------

Apache-2.0
