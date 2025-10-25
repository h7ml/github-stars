---
project: ast-grep
stars: 10938
description: ⚡A CLI tool for code structural search, lint and rewriting. Written in Rust
url: https://github.com/ast-grep/ast-grep
---

ast-grep(sg)
------------

ast-grep(sg) is a CLI tool for code structural search, lint, and rewriting.

Introduction
------------

ast-grep is an abstract syntax tree based tool to search code by pattern code. Think of it as your old-friend `grep`, but matching AST nodes instead of text. You can write patterns as if you are writing ordinary code. It will match all code that has the same syntactical structure. You can use `$` sign + upper case letters as a wildcard, e.g. `$MATCH`, to match any single AST node. Think of it as regular expression dot `.`, except it is not textual.

Try the online playground for a taste!

Screenshot
----------

See more screenshots on the website.

Installation
------------

You can install it from npm, pip, cargo, cargo-binstall, homebrew, scoop or MacPorts!

npm install --global @ast-grep/cli
pip install ast-grep-cli
brew install ast-grep

Click for more installation methods

cargo install ast-grep --locked
cargo binstall ast-grep

# install via scoop, thank @brian6932
scoop install main/ast-grep

# install via MacPorts
sudo port install ast-grep

# try ast-grep in nix-shell
nix-shell -p ast-grep

Or you can build ast-grep from source. You need to install rustup, clone the repository and then

cargo install --path ./crates/cli --locked

Packages are available on other platforms too.

Command line usage example
--------------------------

ast-grep has following form.

```
ast-grep --pattern 'var code = $PATTERN' --rewrite 'let code = new $PATTERN' --lang ts
```

### Example

-   Rewrite code in null coalescing operator

ast-grep -p '$A && $A()' -l ts -r '$A?.()'

-   Rewrite Zodios

ast-grep -p 'new Zodios($URL,  $CONF as const,)' -l ts -r 'new Zodios($URL, $CONF)' -i

-   Implement eslint rule using YAML.

Sponsor
-------

If you find ast-grep interesting and useful for your work, please buy me a coffee so I can spend more time on the project!

Feature Highlight
-----------------

ast-grep's core is an algorithm to search and replace code based on abstract syntax tree produced by tree-sitter. It can help you to do lightweight static analysis and massive scale code manipulation in an intuitive way.

Key highlights:

-   An intuitive pattern to find and replace AST. ast-grep's pattern looks like ordinary code you would write every day (you could say the pattern is isomorphic to code).
    
-   jQuery like API for AST traversal and manipulation.
    
-   YAML configuration to write new linting rules or code modification.
    
-   Written in compiled language, with tree-sitter based parsing and utilizing multiple cores.
    
-   Beautiful command line interface :)
    

ast-grep's vision is to democratize abstract syntax tree magic and to liberate one from cumbersome AST programming!

-   If you are an open-source library author, ast-grep can help your library users adopt breaking changes more easily.
-   if you are a tech lead in your team, ast-grep can help you enforce code best practice tailored to your business need.
-   If you are a security researcher, ast-grep can help you write rules much faster.
