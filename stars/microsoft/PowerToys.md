---
project: PowerToys
stars: 116496
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

Command Not Found

Color Picker

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

Peek

Paste as Plain Text

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

PowerToysUserSetup-0.89.0-x64.exe

B4F130CC96F321024A257499247F6FF6DA56612215ED3882E868AAE26C689E33

Per user - ARM64

PowerToysUserSetup-0.89.0-arm64.exe

F69B00F4E520EB09FA0D1D1669E21910C5225FE7A2EEDC0FA7C283B201A5F9C6

Machine wide - x64

PowerToysSetup-0.89.0-x64.exe

E18AC8F9023E341CF7DAD35367FB9DDDB6565D83D8155DBCDDB40AE8A24AE731

Machine wide - ARM64

PowerToysSetup-0.89.0-arm64.exe

17DEADEC601D6061D7AF4F487595CC36D9191813003CC2ECE381017F0EC71FBB

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

### 0.89 - February 2025 Update

In this release, we focused on new features, stability, accessibility and automation.

**✨Highlights**

-   Enhanced Advanced Paste by adding media transcoding support to convert different video and audio file formats! Thanks @snickler for your help!
-   Fixed crashes when loading thumbnails after the .NET 9 update and resolved PowerLauncher.exe blocking other MSI installers from creating shortcuts!
-   Fixed accessibility issues across FancyZones, Image Resizer, and Settings to improve screen reader support and clarity!
-   Enhanced UI automation framework across modules and added new tests to cover manual checks, with more improvements coming!

### General

-   Fixed an issue where updating PowerToys on Windows 11 did not properly update context menu entries, impacting New+, PowerRename, Image Resizer, and File Locksmith.
-   Updated .NET Packages from 9.0.1 to 9.0.2. Thanks @snickler for this.
-   Enabled compatibility with VS17.3 and later, for C++23. Thanks @LNKLEO for this.

### Advanced Paste

-   Added media transcoding support to convert different video and audio file formats, improved UI layouts, refined clipboard handling, and integrated Semantic Kernel for smarter pasting. Thanks @snickler for your help!

### FancyZones

-   Fixed accessibility by improving the text for monitors, ensuring clearer naming and help text for screen readers.

### Image Resizer

-   Fixed issues with Width and Height fields in Image Resizer's Custom preset, ensuring empty values no longer cause errors, settings save correctly, and auto-scaling behaves as expected. Thanks @daverayment!
-   Fixed accessibility by ensuring screen readers announce selected image dimensions in the combo-box for better navigation.

### Monaco Preview

-   Fixed open link in default browser rather than Microsoft Edge. Thanks @OldUser101!

### Mouse Highlighter

-   Fixed a highlight released on an Administrator window will start fading, instead of staying on the screen indefinitely until the mouse button is pressed again on an unelevated window.

### Mouse Without Borders

-   Fixed an issue in service mode where copy-paste and drag-drop file transfers didn’t work, ensuring seamless file operations.
-   Enabled GPO for enable/disable for Mouse Without Borders in Service Mode. Thanks @htcfreek for review and comments!
-   Fixed code maintainability by refactoring the oversized 'Common' class in Mouse Without Borders into smaller, focused classes for better structure and clarity. Thanks @mikeclayton and thanks @htcfreek for review!

### PowerRename

-   Supported negative value as Start value in regular expression, e.g. ${start=-1314}
-   Enhanced RegEx help by adding $, ^, quantifiers, and common patterns for better usability. Thanks @PesBandi and thanks @htcfreek for review.

### PowerToys Run

-   Fixed crashes when loading thumbnails after the .NET 9 update by disabling CETCompat.
-   Fixed PowerLauncher.exe blocking other MSI installers creating shortcuts. Thanks @OneBlue!
-   Fixed Run’s dark mode detection to work reliably, preventing issues with incorrect theme detection and ensuring a smoother user experience. Thanks @daverayment!
-   Fixed list separator handling in Calculator, allowing functions with multiple arguments to work correctly across different locales. For example pow(2;3) would be replaced with pow(2,3). Thanks @PesBandi and thanks @htcfreek for review!
-   Fixed angle unit conversions in the PowerToys Run calculator, allowing quick conversions between radians, degrees, and gradians. Thanks @OldUser101!

### Quick Accent

-   Added ǎ, ǒ and ǔ to the IPA character set. Thanks @PesBandi!
-   Added \` (backtick) and ~ (tilde) to the VK\_OEM\_5 character set. Thanks @xanatos!
-   Added ς (final sigma) to the Greek character set. Thanks @IamSmeagol!

### Settings

-   Enabled GPO for the "run at startup" setting. Thanks @htcfreek for review and comments!
-   Fixed accessibility issue by allowing screen readers to announce the group name for secondary links in Settings pages, instead of reading link descriptions without context.
-   Fixed an issue where the Color Picker shortcut was not displaying correctly in the Dashboard.

### Workspaces

-   Fixed if a window was last placed on a disconnected monitor, it launches minimized and repositions within the main monitor's visible area when restored, instead of remaining off-screen and invisible.
-   Fixed on ARM64 to correctly display icons for packaged apps by resolving path mismatches.

### ZoomIt

-   Fixed warning C4706 and related error C2220 during build. Thanks @xanatos!

### Documentation

-   Fixed runner-ipc.md doc on the broken link. Thanks @daverayment!
-   Fixed the new plugin checklist by updating the target framework, removing duplicates, and improving statement organization. Thanks @hlaueriksson!
-   Updated runner documentation to align with the latest code structure.

### Development

-   Stabilized pipeline on ARM64 and forked build.
-   Added fuzz testing for HostUILib, added as part of pipeline for OneFuzz.
-   Fixed and improved UI-Test automation framework, and added new test cases for the FancyZones and Hosts module.
-   Optimized Logger function as AOT compatible, improving performance by 18%.
-   Made Common.UI and Setting.UI to be AOT compatible.

### What is being planned for version 0.90

For v0.90, we'll work on the items below:

-   New module: PowerToys Run v2
-   New module: File Actions Menu
-   Working on installer upgrades
-   Upgrading keyboard manager's editor UI
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
