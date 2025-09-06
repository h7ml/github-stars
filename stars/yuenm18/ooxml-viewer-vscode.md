---
project: ooxml-viewer-vscode
stars: 75
description: An OOXML Viewer for Visual Studio Code
url: https://github.com/yuenm18/ooxml-viewer-vscode
---

OOXML Viewer VSCode Extension
=============================

\* Please note, files must be stored locally, i.e. not in OneNote, Dropbox, etc.

Features
--------

-   Display the contents of OOXML documents in VS Code
-   Edit the contents of an OOXML documents in VS Code
-   Get diff when OOXML documents are edited from outside, e.g. in Microsoft Word, Libre Office Writer, Microsoft Excel, Libre Office Calc, etc.
-   Search all parts
-   Search parts of any file that uses the Open Packaging Conventions

### Display the contents of OOXML documents in VS Code

To view the contents of an OOXML document, right click on the file in the context menu, then click on the part you want to view.

### Edit the contents of OOXML documents in VS Code

To edit an OOXML part, select the part in the OOXML Viewer menu then edit and save. The changes will be reflected in the OOXML document.

### Get diff when OOXML documents are edited from outside, e.g. in Microsoft Word, Libre Office Writer, Microsoft Excel, Libre Office Calc, etc.

When a document opened by the OOXML Viewer is edited from an external program, changed parts are marked with a yellow asterisk, deleted parts are marked with a red asterisk, and new parts are marked with a green asterisk.

To view a diff with the previous version of an OOXML part, right click on the part in the OOXML Viewer menu and click "Compare with Previous".

#### Diff adding text to a odt file

#### Diff adding a slide to a pptx file

#### Diff removing a slide from a pptx file

### Search all parts

To search all parts, right click on the OOXML package in the tree view, select "Search Parts", enter your search term, and press enter/return. The initial search is not case sensitive or whole words only, but once the OOXML Viewer opens the search pane, all VS Code search options are available.

### Search parts of any file that uses the Open Packaging Conventions

By default, the OOXML Viewer can view and edit the contents of files with these extensions: ".docx", ".xlsx", ".pptx", ".odt", ".ods", ".odp", ".docm", ".dotm", ".xlsm", ".pptm", ".dotx", ".xltx", ".xltm", ".potx", ".sldx", ".ppsx". But the OOXML Viewer extension can be used with any file type that uses the Open Packaging Conventions or any zip based file type.

To add additional file types, open the `settings.json` and add or update the `files.associations` and add an associate with "ooxml". For example, to add "\*.vsix" files, settings.json should include

"files.associations": {
  "\*.vsix": "ooxml"
}

After adding the file extension, restart VS Code and right click on the file to open and select "Open OOXML File" to view and edit it's contents.

Extension Settings
------------------

This extension contributes the following variables to the settings:

-   `ooxmlViewer.preserveComments`: Boolean, determines if comments will be preserved in XML or removed on save. Defaults to true.
-   `ooxmlViewer.maximumOoxmlFileSizeBytes`: Number, the maximum size of an ooxml package that the ooxml viewer will be allowed to open. Defaults to 50,000,000.
-   `ooxmlViewer.maximumNumberOfOoxmlParts`: Number, the maximum number of parts the ooxml viewer will be allowed to open. Defaults to 1,000.
-   `ooxmlViewer.maximumXmlPartsFileSizeBytes`: Number, the maximum size of an xml file in bytes that the ooxml viewer will try to format. Defaults to 1,000,000.

Release Notes
-------------

Please see the Changelog
