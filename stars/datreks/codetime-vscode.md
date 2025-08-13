---
project: codetime-vscode
stars: 91
description: The Codetime extension for Visual Studio Code.
url: https://github.com/datreks/codetime-vscode
---

CodeTime
========

CodeTime vscode plugin. Statistical analysis of programming time.

Web Site: Code Time

Previews
--------

Usage
-----

1.  Login from web site: CodeTime.
2.  Get token from web site: CodeTime / settings.
3.  In VSCode, Press F1, enter `token` to find the command: `CodeTime: Enter Token`, Press Enter and then input your token.
4.  Write some code, visit the dashboard and check if data is available.

> If using an online IDE like GitHub Codespaces, add your token to global ENV variable `CODETIME_TOKEN`.

Settings
--------

### Status Bar Info

You are able to select what time to show in your status bar by:

-   Press Ctrl (or command in Mac OS) + ,, then search `codetime` to find the options.
-   Press F1, enter `codetime` to find the options.

Supported options are:

-   total: Show total code time
-   average: Show average code time.
-   today: Show today code time.

### Language / displayLanguage

#### Purpose

The `displayLanguage` option is used to switch the display language of the plugin interface. You can choose a specific language as needed, or use "auto" mode to automatically follow VSCode's interface language.

#### Supported Languages

-   `auto`: Auto mode, follows VSCode's current interface language
-   `en`: English
-   `zh-cn`: Simplified Chinese
-   `zh-tw`: Traditional Chinese
-   `de`: Deutsch (German)
-   `es`: Español (Spanish)
-   `fr`: Français (French)
-   `hi`: हिन्दी (Hindi)
-   `it`: Italiano (Italian)
-   `ja`: 日本語 (Japanese)
-   `ko`: 한국어 (Korean)
-   `pt-br`: Português (Brasil) (Portuguese-Brazil)
-   `ru`: Русский (Russian)

#### How to Switch

1.  Press Ctrl (or command on Mac) + , to open settings, search for `codetime displayLanguage`.
2.  Or press F1, enter `codetime`, and find the `displayLanguage` option in settings to switch.
