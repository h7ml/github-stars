---
project: PowerToys
stars: 118377
description: Windows system utilities to maximize productivity
url: https://github.com/microsoft/PowerToys
---

Microsoft PowerToys
===================

How to use PowerToys | Downloads & Release notes | Contributing to PowerToys | What's Happening | Roadmap

About
-----

Microsoft PowerToys is a set of utilities for power users to tune and streamline their Windows experience for greater productivity. For more info on PowerToys overviews and how to use the utilities, or any other tools and resources for Windows development environments, head over to learn.microsoft.com!

Current utilities:

Advanced Paste

Always on Top

PowerToys Awake

Color Picker

Command Not Found

Command Palette

Crop And Lock

Environment Variables

FancyZones

File Explorer Add-ons

File Locksmith

Hosts File Editor

Image Resizer

Keyboard Manager

Mouse utilities

Mouse Without Borders

New+

Paste as Plain Text

Peek

PowerRename

PowerToys Run

Quick Accent

Registry Preview

Screen Ruler

Shortcut Guide

Text Extractor

Workspaces

ZoomIt

Installing and running Microsoft PowerToys
------------------------------------------

### Requirements

-   Windows 11 or Windows 10 version 2004 (code name 20H1 / build number 19041) or newer.
-   x64 or ARM64 processor
-   Our installer will install the following items:
    -   Microsoft Edge WebView2 Runtime bootstrapper. This will install the latest version.

### Via GitHub with EXE \[Recommended\]

Go to the Microsoft PowerToys GitHub releases page and click on `Assets` at the bottom to show the files available in the release. Please use the appropriate PowerToys installer that matches your machine's architecture and install scope. For most, it is `x64` and per-user.

Description

Filename

sha256 hash

Per user - x64

PowerToysUserSetup-0.90.0-x64.exe

2A6036F5B2D454084E55816C306E1E57EF1D14C916691CBDA42B469797605CE0

Per user - ARM64

PowerToysUserSetup-0.90.0-arm64.exe

AB2E4DC87A9D764BE897C5170E2890E174C89CA912A1916FA3AE1E427536EA4A

Machine wide - x64

PowerToysSetup-0.90.0-x64.exe

12801C44F43D0CC61E90DF1EFDC40E4F3C88341E0199D5B20791042D9B173DCF

Machine wide - ARM64

PowerToysSetup-0.90.0-arm64.exe

2998007C8FCD7BD2770767C6502AAA2CC75B85EC30DE62986EC7005EB0014EDB

This is our preferred method.

### Via Microsoft Store

Install from the Microsoft Store's PowerToys page. You must be using the new Microsoft Store which is available for both Windows 11 and Windows 10.

### Via WinGet

Download PowerToys from WinGet. Updating PowerToys via winget will respect current PowerToys installation scope. To install PowerToys, run the following command from the command line / PowerShell:

#### User scope installer \[default\]

winget install Microsoft.PowerToys \-s winget

#### Machine-wide scope installer

winget install \--scope machine Microsoft.PowerToys \-s winget

### Other install methods

There are community driven install methods such as Chocolatey and Scoop. If these are your preferred install solutions, you can find the install instructions there.

Third-Party Run Plugins
-----------------------

There is a collection of third-party plugins created by the community that aren't distributed with PowerToys.

Contributing
------------

This project welcomes contributions of all types. Besides coding features / bug fixes, other ways to assist include spec writing, design, documentation, and finding bugs. We are excited to work with the power user community to build a set of tools for helping you get the most out of Windows.

We ask that **before you start work on a feature that you would like to contribute**, please read our Contributor's Guide. We would be happy to work with you to figure out the best approach, provide guidance and mentorship throughout feature development, and help avoid any wasted or duplicate effort.

Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you grant us the rights to use your contribution and that you have permission to do so.

For guidance on developing for PowerToys, please read the developer docs for a detailed breakdown. This includes how to setup your computer to compile.

What's Happening
----------------

### PowerToys Roadmap

Our prioritized roadmap of features and utilities that the core team is focusing on.

### 0.90 - March 2025 Update

In this release, we focused on new features, stability, and automation.

**✨Highlights**

-   New module: Command Palette ("CmdPal") - Created as the evolution of PowerToys Run with extensibility at the forefront, Command Palette is a quick launcher with a richer display and additional capabilities without sacrificing performance, allowing you to start anything with the shortcut **Win+Alt+Space**! Thanks @zadjii-msft, @niels9001, @michael-hawker, @joadoumie, @plante-msft, @ethanfangg and @krschau!
-   Enhanced the Color Picker by switching from WPF UI to .NET WPF, resulting in improved themes and visual consistency across different modes. Thanks @mantaionut! Thanks @Jay-o-Way and @niels9001 for helping with the review!
-   Added the ability to delete files directly from Peek, enhancing file management efficiency. Thanks @daverayment and thanks @htcfreek for the review!
-   Added support for variables in template filenames, enabling dynamic elements like date components and environment variables for enhanced customization in New+. Thanks @cgaarden!

### Color Picker

-   Replaced WPF UI with .NET WPF for the Color Picker, enhancing compatibility and improving theme support. Thanks @mantaionut! Thanks @Jay-o-Way and @niels9001 for helping with the review!

### Command Palette

-   Introduced the Windows Command Palette ("CmdPal"), the next iteration of PowerToys Run, designed with extensibility at its core. CmdPal includes features such as searching for installed apps, shell commands, files and WinGet package installation. This module aims to provide a more powerful and flexible launcher experience. Thanks @zadjii-msft, @niels9001, @michael-hawker, @joadoumie, @plante-msft, and the whole team!

### FancyZones

-   Fixed a bug where deleting a layout resulted in incorrect data being written to the JSON file.
-   Fixed a bug where layout hotkeys were displayed incorrectly, ensuring the hotkey list does not include invalid entries.
-   Fixed an issue where the "None" option was missing in the editor layout.

### Image Resizer

-   Fixed warnings in ImageResizer regarding the use of variables "shellItem" and "itemName" without being initialized.

### Mouse Without Borders

-   Enhanced the logger to properly track the file path for easier debugging.
-   Refactored the "Common" class into distinct individual classes to enhance maintainability, and updated all references and unit tests to reflect these changes. Thanks @mikeclayton for this!

### New+

-   Added support for variables in template filenames, including date/time components, parent folder name, and environment variables. Thanks @cgaarden!

### Peek

-   Added the ability to delete the file currently being previewed in Peek, including navigation updates and handling for deleted items. Thanks @daverayment and thanks @htcfreek for your help reviewing this!

### PowerToys Run

-   Fixed an issue where duplicated applications were shown by ensuring the shell link helper opens .ink files non-exclusively and correctly retrieves the "FullPath". Thanks @htcfreek and @davidegiacometti for review!
-   Fixed an issue where applying round corners on Windows 11 build 22000 caused crashes.
-   Async the OnRename method to unblock the thread. Thanks @davidegiacometti for review!
-   Added support for using `sq` instead of `^2` in the Unit Converter. Thanks @PesBandi!

### Settings

-   Disabled the spell check feature in the text boxes of plugin settings for PowerToys Run. Thanks @htcfreek!
-   Fixed an issue where InfoBars for release notes errors were not displayed properly, and added a retry button. Thanks @davidegiacometti!

### Workspaces

-   Fixed an issue where some minimized packaged apps (e.g., Microsoft ToDo, Settings) were not snapshotted.

### Documentation

-   Added the FirefoxBookmark plugin to the list of Third-Party plugins for PowerToys Run. Thanks @8LWXpg!
-   Added the SVGL third-party plugin to PowerToys Run, enabling users to search, browse, and copy SVG logos. Thanks @SameerJS6!
-   Added Monaco usage for the Registry Preview.

### Development

-   Updated WinGet configuration file location and extension. Thanks @mdanish-kh!
-   Removed the Markdown file bypass to ensure CI runs for commits that only update Markdown files.
-   Fixed an issue where the default generated file path exceeded the length limit of 260 characters for EnvironmentVariablesUILib.csproj, causing build failures.
-   Upgraded WindowsAppSDK to 1.6.250205002 and CsWinRT to 2.2.0. Thanks @htcfreek for review!
-   Upgraded XamlStyler to 3.2501.8 and dotnet-consolidate to 4.2.0. Thanks @davidegiacometti!
-   Updated .NET Packages from 9.0.2 to 9.0.3.
-   Optimized the UI Test Automation Framework and added UI test cases for the Hosts File Editor module.
-   Added fuzz testing for RegistryPreview.
-   Added new UI tests for the FancyZones editor, including tests for creating, duplicating, editing, and deleting layouts.
-   Added telemetry code to measure the module editor open time and evaluate the benefits of applying AOT.

### What is being planned for version 0.91

For v0.91, we'll work on the items below:

-   New module: File Actions Menu
-   New UI Automation tests
-   Working on installer upgrades
-   Upgrading Keyboard Manager's editor UI
-   Stability / bug fixes

PowerToys Community
-------------------

The PowerToys team is extremely grateful to have the support of an amazing active community. The work you do is incredibly important. PowerToys wouldn’t be nearly what it is today without your help filing bugs, updating documentation, guiding the design, or writing features. We want to say thank you and take time to recognize your work. Month by month, you directly help make PowerToys a better piece of software.

Code of Conduct
---------------

This project has adopted the Microsoft Open Source Code of Conduct.

Privacy Statement
-----------------

The application logs basic diagnostic data (telemetry). For more information on privacy and what we collect, see our PowerToys Data and Privacy documentation.
