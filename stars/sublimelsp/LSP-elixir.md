---
project: LSP-elixir
stars: 49
description: Elixir support for Sublime LSP plugin
url: https://github.com/sublimelsp/LSP-elixir
---

LSP-elixir
==========

Elixir support for Sublime Text's LSP plugin provided through ElixirLS.

Requires **Elixir 1.14.0+** and **OTP 25+**. A good way of installing these is using the ASDF package manager with the asdf-elixir plugin. On Windows, Scoop is a solid option. `scoop install elixir` or `scoop install elixir@1.18.2-otp-27`.

Installation
------------

Install the following packages in Sublime Text:

-   Elixir or Elixir Sublime Syntax - Elixir syntax support
-   LSP - Base LSP package
-   LSP-elixir - This plugin

Configuration
-------------

Defaults can be edited by selecting `Preferences: LSP-elixir Settings` from the command palette.

### Format on save

To format your code on save add the following setting to your syntax-specific settings (Elixir in this case) and/or project files:

{
  "lsp\_format\_on\_save": true
}

Upgrade to latest version
-------------------------

For developers! To upgrade this library to use the latest version of elixir-ls, run:

```
./scripts/update.py
```

This will update the server info in `plugin.py` to match the latest release of elixir-ls.
