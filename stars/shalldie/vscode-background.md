---
project: vscode-background
stars: 1591
description: Bring background images to your vscode. vscode background 背景扩展插件。
url: https://github.com/shalldie/vscode-background
---

**English** | 中文 | 日本語

**vscode-background**
=====================

### Bring background images to your Visual Studio Code

`fullscreen`、`editor`、`sidebar`、`auxiliarybar`、`panel`、`carousel`、`custom images/styles`...

GitHub | Visual Studio Marketplace

Multiple sections, `editor`、`sidebar`、`auxiliarybar`、`panel`

`fullscreen`

Installation
------------

There are 2 ways to install this extension:

1.  Install from Visual Studio Marketplace.
2.  Search `shalldie.background` from vscode.

Custom
------

User defined requirements can be met by changing the configuration(`settings.json`).

what's `settings.json` | where?

Config
------

### Global Config

Name

Type

Default

Description

`background.enabled`

`Boolean`

`true`

Whether to enable background extension.

### Editor Section Config

Edit `background.editor` to config editor section.

Name

Type

Default

Description

`useFront`

`boolean`

`true`

Place the image above or below the code.

`style`

`object`

`{}`

Custom style for images. MDN Reference

`styles`

`object[]`

`[{},{},{}]`

Each style of editor section image.

`images`

`string[]`

`[]`

Your custom images, support `https` and `file` protocol.

`interval`

`number`

`0`

Seconds of interval for carousel, default `0` to disabled.

`random`

`boolean`

`false`

Whether to randomly display images.

example:

{
  "background.editor": {
    "useFront": true,
    "style": {
      "background-position": "100% 100%",
      "background-size": "auto",
      "opacity": 0.6
    },
    "styles": \[{}, {}, {}\],
    // Local images can be dragged into the browser to quickly get the file protocol address from the address bar
    "images": \["https://pathtoimage.png", "file:///path/to/local/file"\],
    "interval": 0,
    "random": false
  }
}

### Fullscreen、Sidebar、Auxiliarybar、Panel Section Config

Edit `background.fullscreen`、`background.sidebar`、`background.auxiliarybar`、`background.panel` to config these sections.

Name

Type

Default

Description

`images`

`string[]`

`[]`

Your custom images, support `https` and `file` protocol.

`opacity`

`number`

`0.1`

Opacity of the images, alias to opacity, `0.1 ~ 0.3` recommended.

`size`

`string`

`cover`

Alias to background-size, `cover` to self-adaption (recommended).

`position`

`string`

`center`

Alias to background-position, default `center`.

`interval`

`number`

`0`

Seconds of interval for carousel, default `0` to disabled.

`random`

`boolean`

`false`

Whether to randomly display images.

example：

{
  "background.fullscreen": {
    // Local images can be dragged into the browser to quickly get the file protocol address from the address bar
    "images": \["https://pathtoimage.png", "file:///path/to/local/file"\],
    "opacity": 0.1,
    "size": "cover",
    "position": "center",
    "interval": 0,
    "random": false
  },
  // \`sidebar\` and \`panel\` have the same config as \`fullscreen\`
  "background.sidebar": {},
  "background.panel": {}
}

Quick Command
-------------

Click the 「Background」 button on the right-bottom of statusbar, all commands of `background` will appear:

Common Issues
-------------

> **This extension works by editting the vscode's js file.**

Please refer to the Common Issues if you met some problems.

Uninstall
---------

Please refer to Common Issues#how-to-uninstall.

Contributors 🙏
---------------

Contributing Guide
------------------

Refer to Contributing Guide.

Change Log
----------

You can checkout all our changes in our CHANGELOG.

Share Your Images
-----------------

We share background images here.

Migration from v1
-----------------

The configuration of v1 is outdated and currently maintains a certain level of compatibility. Please refer to migration-from-v1.md for migration.

LICENSE
-------

MIT
