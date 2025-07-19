---
project: PowerToys
stars: 120990
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

Per user - x64

PowerToysUserSetup-0.92.1-x64.exe

Per user - ARM64

PowerToysUserSetup-0.92.1-arm64.exe

Machine wide - x64

PowerToysSetup-0.92.1-x64.exe

Machine wide - ARM64

PowerToysSetup-0.92.1-arm64.exe

This is our preferred method.

### Via Microsoft Store

Install from the Microsoft Store's PowerToys page. You must be using the new Microsoft Store, which is available for both Windows 11 and Windows 10.

### Via WinGet

Download PowerToys from WinGet. Updating PowerToys via winget will respect the current PowerToys installation scope. To install PowerToys, run the following command from the command line / PowerShell:

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

### 0.92 - June 2025 Update

In this release, we focused on new features, stability, optimization improvements, and automation.

**✨Highlights**

-   PowerToys settings now has a toggle for the system tray icon, giving users control over its visibility based on personal preference. Thanks @BLM16!
-   Command Palette now has Ahead-of-Time (AOT) compatibility for all first-party extensions, improved extensibility, and core UX fixes, resulting in better performance and stability across commands.
-   Color Picker now has customizable mouse button actions, enabling more personalized workflows by assigning functions to left, right, and middle clicks. Thanks @PesBandi!
-   Bug Report Tool now has a faster and clearer reporting process, with progress indicators, improved compression, auto-cleanup of old trace logs, and inclusion of MSIX installer logs for more efficient diagnostics.
-   File Explorer add-ons now have improved rendering stability, resolving issues with PDF previews, blank thumbnails, and text file crashes during file browsing.

### Color Picker

-   Added mouse button actions so you can choose what left, right, or middle click does. Thanks @PesBandi!

### Crop & Lock

-   Aligned window styling with current Windows theme for a cleaner look. Thanks @sadirano!

### Command Palette

-   Enhanced performance by resolving a regression in page loading.
-   Applied consistent hotkey handling across all Command Palette commands for a smoother user experience.
-   Improved graceful closing of Command Palette. Thanks @davidegiacometti!
-   Fixed consistency issue for extensions' alias with "Direct" setting and enabled localization for "Direct" and "Indirect" for better user understanding. Thanks @davidegiacometti!
-   Improved visual clarity by styling critical context items correctly.
-   Automatically focused the field when only one is present on the content page.
-   Improved stability and efficiency when loading file icons in SDK ThumbnailHelper.cs by removing unnecessary operations. Thanks @OldUser101!
-   Enhanced details view with commands implementation. (See Extension sample)

### Command Palette extensions

-   Added "Copy Path" command to _App_ search results for convenience. Thanks @PesBandi!
-   Improved _Calculator_ input experience by ignoring leading equal signs. Thanks @PesBandi!
-   Corrected input handling in the _Calculator_ extension to avoid showing errors for input with only leading whitespace.
-   Improved _New Extension_ wizard by validating names to prevent namespace errors.
-   Ensured consistent context items display for the _Run_ extension between fallback and top-level results.
-   Fixed missing _Time & Date_ commands in fallback results. Thanks @htcfreek!
-   Fixed outdated results in the _Time & Date_ extension. Thanks @htcfreek!
-   Fixed an issue where _Web Search_ always opened Microsoft Edge instead of the user's default browser on Windows 11 24H2 and later. Thanks @RuggMatt!
-   Improved ordering of _Windows Settings_ extension search results from alphabetical to relevance-based for quicker access.
-   Added "Restart Windows Explorer" command to the _Windows System Commands_ provider for gracefully terminate and relaunch explorer.exe. Thanks @jiripolasek!

### Command Palette Ahead-of-Time (AOT) readiness

-   We’ve made foundational changes to prepare the Command Palette for future Ahead-of-Time (AOT) publishing. This includes replacing the calculator library with ExprTk, improving COM object handling, refining Win32 interop, and correcting trimming behavior—all to ensure compatibility, performance, and reliability under AOT constraints. All first-party extensions are now AOT-compatible. These improvements lay the groundwork for publishing Command Palette as an AOT application in the next release.
-   Special thanks to @Sergio0694 for guidance on making COM APIs AOT-compatible, @jtschuster for fixing COM object handling, @ArashPartow from ExprTk for integration suggestions, and @tian-lt from the Windows Calculator team for valuable suggestion throughout the migration journey and review.
-   As part of the upcoming release, we’re also enabling AOT compatibility for key dependencies, including markdown rendering, Adaptive Cards, internal logging and telemetry library, and the core Command Palette UX.

### FancyZones

-   Fixed DPI-scaling issues to ensure FancyZones Editor displays crisply on high-resolution monitors. Thanks @HO-COOH! This inspired us a broader review across other PowerToys modules, leading to DPI display optimizations in Awake, Color Picker, PowerAccent, and more.

### File Explorer add-ons

-   Fixed potential failures in PDF previewer and thumbnail generation, improving reliability when browsing PDF files. Thanks @mohiuddin-khan-shiam!
-   Prevented Monaco Preview Handler crash when opening UTF-8-BOM text files.

### Hosts File Editor

-   Added an in-app _“Learn more”_ link to warning dialogs for quick guidance. Thanks @PesBandi!

### Mouse Without Borders

-   Fixed firewall rule so MWB now accepts connections from IPs outside your local subnet.
-   Cleaned legacy logs to reduce disk usage and noise.

### Peek

-   Updated QOI reader so 3-channel QOI images preview correctly in Peek and File Explorer. Thanks @mbartlett21!
-   Added codec detection with a clear warning when a video can’t be previewed, along with a link to the Microsoft Store to download the required codec.

### PowerRename

-   Added support for $YY-$MM-$DD in ModificationTime and AccessTime to enable flexible date-based renaming.

### PowerToys Run

-   Suppressed error UI for known WPF-related crashes to reduce user confusion, while retaining diagnostic logging for analysis. This targets COMException 0xD0000701 and 0x80263001 caused by temporary DWM unavailability.

### Registry Preview

-   Added "Extended data preview" via magnifier icon and context menu in the Data Grid, enabled easier inspection of complex registry types like REG\_BINARY, REG\_EXPAND\_SZ, and REG\_MULTI\_SZ, etc. Thanks @htcfreek!
-   Improved file-saving experience in Registry Preview by aligning with Notepad-like behavior, enhancing user prompts, error handling, and preventing crashes during unsaved or interrupted actions. Thanks @htcfreek!

### Settings

-   Added an option to hide or show the PowerToys system tray icon. Thanks @BLM16!
-   Improved settings to show progress while a bug report package is being generated.

### Workspaces

-   Stored Workspaces icons in user AppData to ensure profile portability and prevent loss during temporary folder cleanup.
-   Enabled capture and launch of PWAs on non-default Edge or Chrome profiles, ensuring consistent behavior during creation and execution.

### Documentation

-   Added SpeedTest and Dictionary Definition to the third-party plugins documentation for PowerToys Run. Thanks @ruslanlap!
-   Corrected sample links and typo in Command Palette documentation. Thanks @daverayment and @roycewilliams!

### Development

-   Updated .NET libraries to 9.0.6 for performance and security. Thanks @snickler!
-   Updated WinAppSDK to 1.7.2 for better stability and Windows support.
-   Introduced a one-step local build script that generates a signed installer, enhancing developer productivity.
-   Generated portable PDBs so cross-platform debuggers can read symbol files, improving debugging experience in VSCode and other tools.
-   Simplified WinGet configuration files by using the Microsoft.Windows.Settings module to enable Developer Mode. Thanks @mdanish-kh!
-   Adjusted build scripts for the latest Az.Accounts module to keep CI green.
-   Streamlined release pipeline by removing hard-coded telemetry version numbers, and unified Command Palette versioning with Windows Terminal's versioning method for consistent updates.
-   Enhanced the build validation step to show detailed differences between NOTICE.md and actual package dependencies and versions.
-   Improved spell-checking accuracy across the repo. Thanks @rovercoder!
-   Upgraded CI to TouchdownBuild v5 for faster pipelines.
-   Added context comments to _Resources.resw_ to help translators.
-   Expanded fuzz testing coverage to include FancyZones.
-   Integrated all unit tests into the CI pipeline, increasing from ~3,000 to ~5,000 tests.
-   Enabled daily UI test automation on the main branch, now covering over 370 UI tests for end-to-end validation.
-   Newly added unit tests for WorkspacesLib to improve reliability and maintainability.

### General

-   Updated bug report compression library (cziplib 0.3.3) for faster and more reliable package creation. Thanks @Chubercik!
-   Included App Installer (“AppX Deployment Server”) event logs in bug reports for more thorough diagnostics.

### What is being planned for version 0.93

For v0.93, we'll work on the items below:

-   Continued Command Palette polish
-   New UI automation tests
-   Working on installer upgrades
-   Working on shortcut conflict detection
-   Upgrading Keyboard Manager's editor UI
-   Stability, bug fixes

PowerToys Community
-------------------

The PowerToys team is extremely grateful to have the support of an amazing active community. The work you do is incredibly important. PowerToys wouldn’t be nearly what it is today without your help filing bugs, updating documentation, guiding the design, or writing features. We want to say thank you and take time to recognize your work. Month by month, you directly help make PowerToys a better piece of software.

Code of Conduct
---------------

This project has adopted the Microsoft Open Source Code of Conduct.

Privacy Statement
-----------------

The application logs basic diagnostic data (telemetry). For more privacy information and what we collect, see our PowerToys Data and Privacy documentation.
