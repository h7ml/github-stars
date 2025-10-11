---
project: vscode-office
stars: 1221
description: Let VSCode support previewing PDF, Excel, Word and other formats, and add markdown WYSIWYG editor.
url: https://github.com/cweijan/vscode-office
---

Officew Viewer
==============

Introduction
------------

English | 简体中文 | 繁體中文

This extension supports previewing these common office file formats in VS Code.

-   Excel: .xls, .xlsx, .csv
-   Word: .docx
-   Svg: .svg
-   Pdf: .pdf
-   Font: .ttf, .otf, .woff, .woff2
-   Markdown: .md
-   HttpRequest: .http
-   Windows Reg: .reg
-   Compressed file: .zip, .jar, .vsix, .rar

Markdown
--------

This extension changes the default markdown editor to the vditor. **Please note that this editor is no longer actively maintained.**

If you want to use the original vscode editor, insert this in your `settings.json`.

{
    "workbench.editorAssociations": {
        "\*.md": "default",
        "\*.markdown": "default"
    }
}

Shortcuts: Base on Vditor shortcuts and more:

-   Move list up: `Ctrl Alt I` / `⌘ ^ I`
-   Move list down: `Ctrl Alt J` / `⌘ ^ J`
-   Edit in VS Code: `Ctrl Alt E` / `⌘ ^ E`

Tips:

-   Resize editor via ctrl/cmd+mouse scroll.
-   Hyperlinks can be opened by ctrl/meta+click or double-click.

HTML
----

The html editor supports live viewing. Press ctrl+shift+v to open the live view.

Sponsor
-------

Database Client for Visual Studio Code, supporting the management **MySQL/MariaDB, PostgreSQL, SQLite, Redis** and **ElasticSearch**, and works as an **SSH** client, boost your maximum productivity! Get it now.

Credits
-------

-   PDF rendering: mozilla/pdf.js/
-   Docx rendering: VolodymyrBaydalka/docxjs
-   XLSX rendering:
    -   SheetJS/sheetjs: XLSX parsing
    -   myliang/x-spreadsheet: XLSX rendering
-   HTTP: Rest Client
-   Markdown: Vanessa219/vditor
-   Material Icon theme: PKief/vscode-material-icon-theme
