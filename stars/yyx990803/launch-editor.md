---
project: launch-editor
stars: 664
description: Open file in editor from Node.js.
url: https://github.com/yyx990803/launch-editor
---

launch-editor
=============

Open file with line numbers in editor from Node.js.

The main functionality is extracted from react-dev-utils with slight modifications so that it can be used as a standalone package. The original source code is licensed under MIT.

Also added column number support.

Why
---

There are also a few other existing packages with the same purpose:

-   lahmatiy/open-in-editor
-   sindresorhus/open-editor

However, both expects env variables like `EDITOR` to be set in order to open files. This package infers the editor to open by checking current running processes before falling back to env variables.

On the other hand,`react-dev-utils` includes many other utilities and dependencies and is thus not suitable for standalone usage.

Usage
-----

const launch \= require('launch-editor')

launch(
  // filename:line:column
  // both line and column are optional
  // \`file://\` URIs are also supported
  'foo.js:12:34',
  // try specific editor bin first (optional)
  'code',
  // callback if failed to launch (optional)
  (fileName, errorMsg) \=> {
    // log error if any
  }
)

### Middleware

An express/connect/webpack-dev-server compatible middleware is also available:

const launchMiddleware \= require('launch-editor-middleware')

app.use('/\_\_open-in-editor', launchMiddleware())

The middleware factory function accepts the following arguments (all optional, the callback can be in any position as long as it's the last argument):

1.  A specific editor bin to try first. Defaults to inferring from running processes, then fallback to env variables like `EDITOR` and `VISUAL`.
2.  The root directory of source files, in case the file path is relative. Defaults to `process.cwd()`.
3.  a callback when it fails to launch the editor.

To launch files, send requests to the server like the following:

```
/__open-in-editor?file=src/main.js:13:24
```

### Supported editors

Value

Editor

Linux

Windows

macOS

`appcode`

AppCode

✓

`atom`

Atom

✓

✓

✓

`atom-beta`

Atom Beta

✓

`brackets`

Brackets

✓

✓

✓

`clion`

Clion

✓

✓

`code`

Visual Studio Code

✓

✓

✓

`code-insiders`

Visual Studio Code Insiders

✓

✓

✓

`codium`

VSCodium

✓

✓

✓

`cursor`

Cursor

✓

✓

`emacs`

Emacs

✓

`idea`

IDEA

✓

✓

✓

`notepad++`

Notepad++

✓

`pycharm`

PyCharm

✓

✓

✓

`phpstorm`

PhpStorm

✓

✓

✓

`rider`

Rider

✓

✓

✓

`rubymine`

RubyMine

✓

✓

✓

`sublime`

Sublime Text

✓

✓

✓

`vim`

Vim

✓

`visualstudio`

Visual Studio

✓

`webstorm`

WebStorm

✓

✓

✓

`zed`

Zed

✓

✓

### Custom editor support

You can use the `LAUNCH_EDITOR` environment variable

#### to force a specific supported editor

LAUNCH\_EDITOR=codium

#### to run a custom launch script

LAUNCH\_EDITOR=my-editor-launcher.sh

# gets called with 3 args: filename, line, column
filename=$1
line=$2
column=$3

# call your editor with whatever args it expects
my-editor -l $line -c $column -f $filename
