---
project: vscode-react-javascript-snippets
stars: 1810
description: Extension for React/Javascript snippets with search supporting ES7+ and babel features
url: https://github.com/r5n-labs/vscode-react-javascript-snippets
---

VS Code ES7+ React/Redux/React-Native/JS snippets
=================================================

JavaScript and React/Redux snippets in ES7+ with Babel plugin features for VS Code

Installation
------------

### Visual Studio Marketplace

Launch _Quick Open_:

-   _Linux_: `Ctrl+P`
-   _macOS_: `⌘P`
-   _Windows_: `Ctrl+P`

Paste the following command and press `Enter`:

ext install dsznajder.es7-react-js-snippets

Options
-------

From version 4 extension provides options to customize the behavior of the snippets:

Option

Description

languageScopes

list of supported languages / files recognition

prettierEnabled

determines if snippets should be parsed with project prettier config

importReactOnTop

If disabled, snippets won't contain `import React` on top. React 17+ support

typescript

adds additional typescript snippets

Sponsors
========

  
Manage pull requests and conduct code reviews in your IDE with full source-tree context. Comment on any line, not just the diffs. Use jump-to-definition, your favorite keybindings, and code intelligence with more of your workflow.  
Learn More

  

### Conquer of Completion

It is possible to use this package in your vim/neovim text editor, to make this possible, make sure you have the `coc.nvim` previously configured, then add this command to your `init.vim`

Plug 'dsznajder/vscode-es7-javascript-react-snippets', { 'do': 'yarn install --frozen-lockfile && yarn compile' }

Update your vim / neovim settings with `:source %` and then install the new package with `:PlugInstall`

Note: This example uses `vim-plug` as a package manager, feel free to use some other

  

### Packer

For use with packer the syntax is a little different. Just add in your `init.vim` or `init.lua`:

use {'dsznajder/vscode-es7-javascript-react-snippets',
run = 'yarn install --frozen-lockfile && yarn compile'
}

When saving the file, the update will be done ( `:w` )

  

Search command
--------------

You can search through snippets with `ES7 snippet search` command which can be run with `CMD + Shift + P` or just use `CMD + Shift + R` (`CTRL + ALT + R` for Windows & Linux) keybinding.

Here is direct link to marketplace ES7 React/Redux/React-Native/JS Snippets

  

Snippets
--------
