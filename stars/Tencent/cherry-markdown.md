---
project: cherry-markdown
stars: 4312
description: ✨ A Markdown Editor
url: https://github.com/Tencent/cherry-markdown
---

Cherry Markdown Writer
======================

English | 简体中文 | 日本語

Introduction
------------

Cherry Markdown Writer is a Javascript Markdown editor. It has the advantages such as out-of-the-box, lightweight and easy to extend. It can run in browser or server(with NodeJs).

### Document

-   初识cherry markdown 编辑器
-   hello world
-   配置图片&文件上传接口
-   调整工具栏
-   自定义语法
-   配置项全解
-   配置主题
-   扩展代码块语法
-   事件&回调
-   API

### Demos

-   full model
-   basic
-   mobile
-   multiple instances
-   editor without toolbar
-   pure preview
-   XSS（Not allowed by default）
-   img wysiwyg
-   table wysiwyg
-   headers with auto num
-   流式输入模式（AI chart场景）
-   VIM 编辑模式

* * *

### **Out-of-the-box**

Developer can call and instantiate Cherry Markdown Editor in a very simple way. The instantiated Cherry Markdown Editor supports most commonly used markdown syntax (such as title, TOC, flowchart, formula, etc.) by default.

### **Easy to extend**

When the syntax that Cherry Markdown writer support can not meet your needs, secondary development or function extention can be carried out quickly. At the same time, Cherry Markdown writer should be implemented by pure JavaScript, and should not rely on framework technology such as angular, vue and react. Framework only provide a container environment.

Feature
-------

### Syntax Feature

1.  Image zoom, alignment and reference
2.  Generate a chart based on the content of the table
3.  Adjust font color and size
4.  Font background color, superscript and subscript
5.  Insert checklist
6.  Insert audio or video

### Multiple modes

1.  Live preview with Scroll Sync
2.  Preview-only mode
3.  No toolbar mode (minimalist editing mode)
4.  Mobile preview mode

### Functional Feature

1.  Copy from rich text and paste as markdown text
2.  Classic line feed & regular line feed
3.  Multi-cursor editing
4.  Image size editing
5.  Export as image or pdf
6.  Float toolbar: appears at the beginning of a new line
7.  Bubble toolbar: appears when text is selected

### Performance Feature

1.  partial rendering
2.  partial update

### Security

Cherry Markdown has a built-in security Hook, by filtering the whitelist and DomPurify to do scan filter.

### Style theme

Cherry Markdown has a variety of style themes to choose from.

### Features Showcase

Click to view feature demonstration here

Install
-------

Via yarn

yarn add cherry-markdown

Via npm

npm install cherry-markdown --save

If you need to enable the functions of `mermaid` drawing and table-to-chart, you need to add `mermaid` and `echarts` packages at the same time.

Currently, the plug-in version **Cherry** recommend is `echarts@4.6.0` `mermaid@9.4.3`.

# Install mermaid, enable mermaid and drawing function
yarn add mermaid@9.4.3
# Install echarts, turn on the table-to-chart function
yarn add echarts@4.6.0

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

Under development, please stay tuned or see `/client/`

Extension
---------

### Customize Syntax

click here

### Customize Toolbar

click here

Unit Test
---------

Jest is selected as a unit testing tool for its assertion, asynchronous support and snapshot. Unit test includes CommonMark test and snapshot test.

### CommonMark Test

Call `yarn run test:commonmark` to test the official CommonMark suites. This command runs fast.

Suites are located in `test/suites/commonmark.spec.json`, for example:

{
  "markdown": " \\tfoo\\tbaz\\t\\tbim\\n",
  "html": "<pre><code>foo\\tbaz\\t\\tbim\\n</code></pre>\\n",
  "example": 2,
  "start\_line": 363,
  "end\_line": 368,
  "section": "Tabs"
},

In this case, Jest will compare the html generated by `Cherry.makeHtml(" \tfoo\tbaz\t\tbim\n")` with the expected result `"<pre><code>foo\tbaz\t \tbim\n</code></pre>\n"`. Cherry Markdown's matcher has ignored private attributes like `data-line`.

CommonMark specifications and suites are from: commonmark.org.

### Snapshot Test

Call `yarn run test:snapshot` to run snapshot test. You can write snapshot suite like `test/core/hooks/List.spec.ts`. At the first time, a snapshot will be automatically generated. After that, Jest can compare the snapshot with the generated HTML. If you need to regenerate a snapshot, delete the old snapshot under `test/core/hooks/__snapshots__` and run this command again.

Snapshot test runs slower. It should only be used to test Hooks that are error-prone and contain Cherry Markdown special syntax.

Contribution Guidelines
-----------------------

Welcome to join us in building a powerful Markdown editor. You can also submit feature requests as issues. Before writing new features, you can learn about the Introduction to cherry-markdown editor. Please read the Contribution Guidelines before making contributions.

Stargazers over time
--------------------

License
-------

Apache-2.0
