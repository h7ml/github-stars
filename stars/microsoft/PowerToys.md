---
project: PowerToys
stars: 122739
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

Mouse Utilities

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

PowerToysUserSetup-0.93.0-x64.exe

Per user - ARM64

PowerToysUserSetup-0.93.0-arm64.exe

Machine wide - x64

PowerToysSetup-0.93.0-x64.exe

Machine wide - ARM64

PowerToysSetup-0.93.0-arm64.exe

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

### 0.93 - Aug 2025 Update

In this release, we focused on new features, stability, optimization improvements, and automation.

**✨Highlights**

-   PowerToys settings debuts a modern, card-based dashboard with clearer descriptions and faster navigation for a streamlined user experience.
-   Command Palette had over 99 issues resolved, including bringing back Clipboard History, adding context menu shortcuts, pinning favorite apps, and supporting history in Run.
-   Command Palette reduced its startup memory usage by ~15%, load time by ~40%, built-in extensions loading time by ~70%, and installation size by ~55%—all due to using the full Ahead-of-Time (AOT) compilation mode in Windows App SDK.
-   Peek now supports instant previews and embedded thumbnails for Binary G-code (.bgcode) 3D printing files, making it easy to inspect models at a glance. Thanks @pedrolamas!
-   Mouse Utilities introduces a new spotlight highlighting mode that dims the screen and draws attention to your cursor, perfect for presentations.
-   Test coverage improvements for multiple PowerToys modules including Command Palette, Advanced Paste, Peek, Text Extractor, and PowerRename — ensuring better reliability and quality, with over 600 new unit tests (mostly for Command Palette) and doubled UI automation coverage.

### Command Palette

-   Ensured screen readers are notified when the selected item in the list changes for better accessibility.
-   Fixed command title changes not being properly notified to screen readers. Thanks @jiripolasek!
-   Made icon controls excluded from keyboard navigation by default for better accessibility. Thanks @jiripolasek!
-   Improved UI design with better text sizing and alignment.
-   Fixed keyboard shortcuts to work better in text boxes and context menus.
-   Added right-click context menus with critical command styling and separators.
-   Improved various context menu issues, improving item selection, handling of long titles, search bar text scaling, initial item behavior, and primary button functionality.
-   Fixed context menu crashes with better type handling.
-   Fixed "Reload" command to work with both uppercase and lowercase letters.
-   Added mouse back button support for easier navigation. Thanks @jiripolasek!
-   Fixed Alt+Left Arrow navigation not working when search box contains text. Thanks @jiripolasek!
-   Updated back button tooltip to show keyboard shortcut information. Thanks @jiripolasek!
-   Fixed Command Palette window not appearing properly when activated. Thanks @jiripolasek!
-   Fixed Command Palette window staying hidden from taskbar after File Explorer restarts. Thanks @jiripolasek!
-   Fixed window focus not returning to previous app properly.
-   Fixed Command Palette window to always appear on top when shown and move to bottom when hidden. Thanks @jiripolasek!
-   Fixed window hiding to properly work on UI thread. Thanks @jiripolasek!
-   Fixed crashes and improved stability with better synchronization of Command list updates. Thanks @jiripolasek!
-   Improved extension disposal with better error handling to prevent crashes. Thanks @jiripolasek!
-   Improved stability by fixing a UI threading issue when loading more results, preventing possible crashes and ensuring the loading state resets if loading fails. Thanks @jiripolasek!
-   Enhanced icon loading stability with better exception handling. Thanks @jiripolasek!
-   Added thread safety to recent commands to prevent crashes. Thanks @MaoShengelia!
-   Fixed acrylic (frosted glass) system backdrop display issues by ensuring proper UI thread handling. Thanks @jiripolasek!

### Command Palette extensions

-   Added settings to each provider to control which fallback commands are enabled. Thanks @jiripolasek! for fixing a regression in this feature.
-   Added sample code showing how Command Palette extensions can track when their pages are loaded or unloaded. Check it out here.
-   Fixed _Calculator_ to accept regular spaces in numbers that use space separators. Thanks @PesBandi!
-   Added a new setting to _Calculator_ to make "Copy" the primary button (replacing “Save”) and enable "Close on Enter", streamlining the workflow. Thanks @PesBandi!
-   Improved _Apps_ indexing error handling and removed obsolete code. Thanks @davidegiacometti!
-   Prevented apps from showing in search when the _Apps_ extension is disabled. Thanks @jiripolasek!
-   Added ability to pin/unpin _Apps_ using Ctrl+P shortcut.
-   Added keyboard shortcuts to the _Apps_ context menu items for faster access.
-   Added all file context menu options to the _Apps_ items context menu, making all file actions available there for better functionality.
-   Streamlined All _Apps_ extension settings by removing redundant descriptions, making the UI clearer.
-   Added command history to the _Run_ page for easier access to previous commands.
-   Fixed directory path handling in _Run_ fallback for better file navigation.
-   Fixed URL fallback item hiding properly in _Web Search_ extension when search query becomes invalid. Thanks @jiripolasek!
-   Added proper empty state message for _Web Search_ extension when no results found. Thanks @jiripolasek!
-   Added fallback command to _Windows Settings_ extension for better search results.
-   Re-enabled _Clipboard History_ feature with proper window handling.
-   Improved _Add Bookmark_ extension to automatically detect file, folder, or URL types without manual input.
-   Updated terminology from "Kill process" to "End task" in _Window Walker_ for consistency with Windows.
-   Fixed minor grammar error in SamplePagesExtension code comments. Thanks @purofle!

### Mouse Utilities

-   Added a new spotlight highlighting mode that creates a large transparent circle around your cursor with a backdrop effect, providing an alternative to the traditional circle highlight. Perfect for presentations where you want to focus attention on a specific area while dimming the rest of the screen.

### Peek

-   Added preview and thumbnail support for Binary G-code (.bgcode) files used in 3D printing. You can now see embedded thumbnails and preview these compressed 3D printing files directly in Peek and File Explorer. Thanks @pedrolamas!

### Quick Accent

-   Added Vietnamese language support to Quick Accent, mappings for Vietnamese vowels (a, e, i, o, u, y) and the letter d. Thanks @octastylos-pseudodipteros!

### Settings

-   Completely redesigned the Settings dashboard with a modern card-based layout featuring organized sections for quick actions and shortcuts overview, replacing the old module list.
-   Rewrote setting descriptions to be more concise and follow Windows writing style guidelines, making them easier to understand.
-   Improved formatting and readability of release notes in the "What's New" section with better typography and spacing.
-   Added missing deep link support for various settings pages (Peek, Quick Accent, PowerToys Run, etc.) so you can jump directly to specific settings.
-   Resolved an issue where the settings page header would drift away from its position when resizing the settings window.
-   Resolved a settings crash related to incompatible property names in ZoomIt configuration.

### Documentation

-   Added detailed step-by-step instructions for first-time developers building the Command Palette module, including prerequisites and Visual Studio setup guidance. Thanks @chatasweetie!
-   **Fixed Broken SDK Link**: Corrected a broken markdown link in the Command Palette SDK README that was pointing to an incorrect directory path. Thanks @ChrisGuzak!
-   Added documentation for the "Open With Cursor" plugin that enables opening Visual Studio and VS Code recent files using Cursor AI. Thanks @VictorNoxx!
-   Added documentation for two new community plugins - Hotkeys plugin for creating custom keyboard shortcuts, and RandomGen plugin for generating random data like passwords, colors, and placeholder text. Thanks @ruslanlap!

### Development

-   Updated .NET libraries to 9.0.8 for performance and security. Thanks @snickler!
-   Updated the spell check system to version 0.0.25 with better GitHub integration and SARIF reporting, plus fixed numerous spelling errors throughout the codebase including property names and documentation. Thanks @jsoref!
-   Cleaned up spelling check configuration to eliminate false positives and excessive noise that was appearing in every pull request, making the development process smoother.
-   Replaced NuGet feed with Azure Artifacts for better package management.
-   Implemented configurable UI test pipeline that can use pre-built official releases instead of building everything from scratch, reducing test execution time from 2+ hours.
-   Replaced brittle pixel-by-pixel image comparison with perceptual hash (pHash) technology that's more robust to minor rendering differences - no more test failures due to anti-aliasing or compression artifacts.
-   Reduced CI/fuzzing/UI test timeouts from 4 hours to 90 minutes, dramatically improving developer feedback loops and preventing long waits when builds get stuck.
-   Standardized test project naming across the entire codebase and improved pipeline result identification by adding platform/install mode context to test run titles. Thanks @khmyznikov!
-   Added comprehensive UI test suites for multiple PowerToys modules including Command Palette, Advanced Paste, Peek, Text Extractor, and PowerRename - ensuring better reliability and quality.
-   Enhanced UI test automation with command-line argument support, better session management, and improved element location methods using pattern matching to avoid failures from minor differences in exact matches.

### What is being planned over the next few releases

For v0.94, we'll work on the items below:

-   Continued Command Palette polish
-   Working on Shortcut Guide v2 (Thanks @noraa-junker!)
-   Working on upgrading the installer to WiX 5
-   Working on shortcut conflict detection
-   Working on setting search
-   Upgrading Keyboard Manager's editor UI
-   New UI automation tests
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
