---
project: html-to-markdown-cli
stars: 104
description: Command line tool that converts HTML to markdown.
url: https://github.com/jaywcjlove/html-to-markdown-cli
---

`@wcj/html-to-markdown`
=======================

HTML conversion tool to markdown. Command line tool => `@wcj/html-to-markdown-cli`.

Installation
------------

This package is ESM only: Node 14+ is needed to use it and it must be import instead of require.

npm i @wcj/html-to-markdown

Command line tool

$ npx @wcj/html-to-markdown-cli ./html/index.html
# 🌐 Request: /Users/xxx/index.html
# 🎉 Compliled successfully!
# ╰┈ Output: /Users/xxx/dist/index.md

$ npx @wcj/html-to-markdown-cli https://jaywcjlove.github.io/idoc/
# 🌐 Request: https://jaywcjlove.github.io/idoc/
# 🎉 Compliled successfully!
# ╰┈ Output: /Users/xxx/dist/idoc.md

# Or

$ sudo npm i @wcj/html-to-markdown-cli -g
$ html-to-markdown ./html/index.html
# 🌐 Request: /Users/xxx/html/index.html
# 🎉 Compliled successfully!
# ╰┈ Output: /Users/xxx/html/dist/index.md

$ html-to-markdown https://jaywcjlove.github.io/idoc/
# 🌐 Request: https://jaywcjlove.github.io/idoc/
# 🎉 Compliled successfully!
# ╰┈ Output: /Users/xxx/dist/idoc.md

Command Help

Usage: html-to-markdown <URL|file path|\-\> \[options\] \[--help|h\] \[--version|v\]

Passing "\-" as the first arg will take input from STDIN

Options:

  -v, --version, Show version number
  -h, --help, Displays help information.
  -o, --output <dir-path\>, Output directory. defalut(dist)
  -s, --stdout, Output to stdout

Example:

  html-to-markdown ./html/index.html
  html-to-markdown https://jaywcjlove.github.io/idoc/
  html-to-markdown --output="dist"
  echo "<h1>hello world</h1>"| html-to-markdown - --stdout

Support Config

In the project's root directory, add a `.htm2mdrc.js` file with the following configuration to enable the rehype and remark plugins.

/\*\*
 \* @typedef {import("@wcj/html-to-markdown").Options} Options
 \* @type {Options}
 \*\*/
export default { 
  rehypeParseOption: {},
  rehypePlugins: \[\],
  remarkPlugins: \[\],
};

Usage
-----

import htmlToMarkdown from '@wcj/html-to-markdown';

htmlToMarkdown({ html: '<h1>Markdown String</h1>' });
// => # Markdown String

API
---

import { PluggableList } from 'unified';
import { Options as RehypeParseOptions } from 'rehype-parse';
declare type Options \= {
  html?: string;
  url?: string;
  rehypeParseOption?: RehypeParseOptions;
  /\*\*
   \* List of \[remark plugins\](https://github.com/remarkjs/remark/blob/main/doc/plugins.md#list-of-plugins) to use.
   \* See the next section for examples on how to pass options
   \*/
  remarkPlugins?: PluggableList;
  /\*\*
   \* List of \[rehype plugins\](https://github.com/rehypejs/rehype/blob/main/doc/plugins.md#list-of-plugins) to use.
   \* See the next section for examples on how to pass options
   \*/
  rehypePlugins?: PluggableList;
};
export default function htmlToMarkdown(options?: Options): Promise<string\>;

Development
-----------

$ npm i
$ npm install --workspaces
$ npm run build
$ npm run build:cli

Related
-------

-   markdown-to-html-cli Command line tool that converts markdown to HTML.

Contributors
------------

As always, thanks to our amazing contributors!

Made with contributors.

License
-------

Licensed under the MIT License.
