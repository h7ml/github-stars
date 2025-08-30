---
project: winmerge
stars: 7862
description: WinMerge is an Open Source differencing and merging tool for Windows. WinMerge can compare both folders and files, presenting differences in a visual text format that is easy to understand and handle.
url: https://github.com/WinMerge/winmerge
---

WinMerge
========

WinMerge is an open source differencing and merging tool for Windows. It can compare files and folders, presenting differences in a visual format that is easy to understand and manipulate. It has been in active development since 2000.

* * *

What Can WinMerge Do?
---------------------

WinMerge's features include:

-   **File Comparison**: visually compare the content of two or three text files side by side, highlighting the differences between them line by line. It can also highlight differences within a line.
-   **Folder Comparison**: compare the contents of two folders, showing which files are different, missing, or only present in one of the folders.
-   **Merging**: merge changes between files or folders. You can choose which differences to incorporate from one to the other.
-   **Syntax Highlighting**: syntax highlighting for various programming languages and file formats, making it easier to identify changes in code or structured text.
-   **Patch File Creation**: generate patch files (in normal, context, and unified formats) that describe the differences between files.
-   **Ignore Options**: configure it to ignore whitespace differences, case changes, or specific lines based on regular expressions.
-   **Shell Integration**: integrates with Windows Explorer, allowing you to right-click on files or folders and compare them directly with WinMerge.
-   **Archive Support**: using 7-Zip, compare files within archive formats.

In essence, this is a tool for anyone who needs to track changes in files, compare different versions of documents or code, or merge modifications made by different people.

* * *

How to Contribute
-----------------

If you think you've found a bug or would like to request a feature, submit an issue.

To contribute code, fork the main WinMerge repository and create a branch on that fork.

Format your code using Eric Allman indentation.

When your code is ready for review/merge, create a Pull Request, explaining the changes made.

* * *

Folder Structure
----------------

Source code for WinMerge, its plugins, filters, setup program, and various utilities are all kept in the subfolders:

-   `ArchiveSupport/Merge7z` - Contains Merge7z dlls, which connect WinMerge with 7-Zip, required to compile `WinMergeU.exe`.  There is also a standalone installer for Merge7z dlls.
-   `Build` - Created by the compiler when WinMerge is compiled. It contains compiled executables, libraries, the user manual, etc.
-   `BuildTmp` - Created by the compiler when WinMerge is compiled. It contains temporary files created during the compilation and can be safely deleted.
-   `ColorSchemes` - Color schemes / themes.
-   `Docs` - Both user and developer documentation, in different subfolders. Can be browsed by opening `index.html` in the `Docs` folder.
-   `Externals` - Contains several libraries from outside the WinMerge project. Required for building and possibly customized for WinMerge. Libraries include an XML parser and a regular expression parser.
-   `Filters` - WinMerge file filters.
-   `Installer` - Installer for WinMerge.
-   `Plugins` - Source code and binaries for WinMerge runtime plugin dlls & scripts.
-   `ShellExtension` - Windows Shell (Explorer) integration.  Adds menu items to Explorer context menu.
-   `Src` - Source code for the WinMerge program.
-   `Testing` - A suite of test diff files and a script to run them and report the results. This folder also has a `Google Test` subfolder containing unit tests made with Google Test Framework.
-   `Tools/Scripts` - Various utilities used by WinMerge developers - see readme files in each.
-   `Translation` - Language files for translation.

The changelog is in Docs/Users/ChangeLog.md.

* * *

How to RUN and DEBUG
--------------------

The WinMerge folder has different Visual Studio solution files (.sln) that you can use to build, debug and run while you test your changes.

If you have run any of the BuildAll scripts you can run WinMerge from path `\Build\X64\Release\WinMergeU.exe`

If your architecture is not `X64` look for any of the other folders generated after the build has finished.

Another way to Debug, run the exe from previous step, then from VS attach to the running process.

* * *

Build WinMerge
--------------

### Visual Studio 2017

-   _Community_, _Professional_ or _Enterprise_ Edition
-   VC++ 2017 latest v141 tools
-   Visual C++ compilers and libraries for (ARM, ARM64)
-   Windows XP support for C++
-   Visual C++ MFC for (x86 and x64, ARM, ARM64)
-   Visual C++ ATL for (x86 and x64, ARM, ARM64)
-   Windows 10 SDK

### Visual Studio 2019

-   _Community_, _Professional_ or _Enterprise_ Edition
-   MSVC v142 - VS 2019 C++ (x64/x86, ARM, ARM64) build tools (Latest)
-   C++ MFC for latest v142 build tools (x86 & x64, ARM, ARM64)
-   C++ ATL for latest v142 build tools (x86 & x64, ARM, ARM64)
-   Windows 10 SDK

### Visual Studio 2022

-   _Community_, _Professional_ or _Enterprise_ Edition
-   MSVC v143 Buildtools (x64/x86, ARM, ARM64)
-   C++ MFC for latest v143 build tools (x64/x86, ARM, ARM64)
-   C++ ATL for latest v143 build tools (x64/x86, ARM, ARM64)
-   Windows 10 SDK

### Other utilities/programs

-   git
-   Inno Setup 5.x and 6.x
-   7-Zip
-   Python
-   Pandoc
-   MSYS2 and MSYS2 packages (po4a and diffutils)

How to Build
------------

```
git clone --recurse-submodules https://github.com/WinMerge/winmerge
cd winmerge
DownloadDeps.cmd
BuildAll.vs2022.cmd [x86|x64|ARM|ARM64] or BuildAll.vs2019.cmd [x86|x64|ARM|ARM64] or BuildAll.vs2017.cmd [x86|x64|ARM|ARM64]
```
