---
project: PowerToys
stars: 119571
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

PowerToysUserSetup-0.91.1-x64.exe

42EA4A3E8C79A5456476D19E72B3E2AB9393A89C4DC7442EB7EE5A1E3490D38A

Per user - ARM64

PowerToysUserSetup-0.91.1-arm64.exe

F3F433FE04049F9197411D792AADEBF34E3BE7FE16327BD8B73D2A046ED8BAF6

Machine wide - x64

PowerToysSetup-0.91.1-x64.exe

EC4BC3A8625775866B0ED4577CCF83E6EC7B1A0AD267379DDBAF4FE49C7B5BDD

Machine wide - ARM64

PowerToysSetup-0.91.1-arm64.exe

9CB8911008420D0E446AE3D5CE365E447FA4DF9DCF9337F3A80F933C00FC3689

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

### 0.91 - May 2025 Update

In this release, we focused on new features, stability, and automation.

**✨Highlights**

-   We focused on greatly improving Command Palette's performance and fixing a large amount of bugs. Some new features we've added are:
-   Added the ability for Command Palette to search any file using a fallback command.
-   Added the ability to make the Command Palette global hotkey a low-level keyboard hook.
-   Added open URL fallback command for the WebSearch extension, enabling users to directly open URLs in the browser from Command Palette.
-   You can now define custom formats in the Date and Time plugins of PT Run and Command Palette. Thanks @htcfreek!

### Advanced Paste

-   Fixed an issue where Advanced Paste failed to create the OCR engine for certain English language tags (e.g., en-CA) by initializing the OCR engine with the user profile language. Thanks @cryolithic!

### Color Picker

-   Fixed an issue where a resource leak caused hangs or crashes by properly disposing of the Graphics object. Thanks @dcog989!
-   Fixed an issue where Color Picker exited on Backspace keypress by ensuring it only closes when focused and aligning Escape/Backspace behavior. Thanks @PesBandi!
-   Added support for Oklab and Oklch color formats in Color Picker. Thanks @lemonyte!

### Command Not Found

-   Updated the WinGet Command Not Found script to only enable the experimental features if they actually exist.

### Command Palette

-   Updated bug template to include Command Palette module.
-   Fixed an issue where the toast window was not scaled for DPI, causing layout issues under display scaling.
-   Fixed an issue where Up/Down keyboard navigation didn't move selection when caret was at position 0, and add continuous navigation like PT Run v1. Thanks @davidegiacometti!
-   Updated the Time and Date extension code to simplify it and improve clarity.
-   Fixed an issue where capitalization in the command causes failure when trying to go to the mouse pointer, resolved by adjusting the command to lowercase.
-   Added open URL fallback command for the WebSearch extension, enabling users to directly open URLs in the browser from Command Palette. Thanks @htcfreek!
-   Added setting to enable/disable system tray icon in CmdPal and align terminology with Windows 11. Thanks @davidegiacometti!
-   Fixed an alias update issue by removing the old alias when a new one is set.
-   Resolved GitHub casing conflict by migrating Exts and exts into a new ext directory, ensuring consistent structure across platforms and preventing path fragmentation.
-   Fix an issue where the 'Create New Extension' command generated empty file names.
-   Added the ability to make the global hotkey a low-level keyboard hook.
-   Added support for JUMBO thumbnails, enabling access to high-resolution icons.
-   Fixed crashes when CmdPal auto-hid itself while an MSAL dialog was opened, by preventing CmdPal from hiding if it's disabled.
-   Added support for immediately selecting search text when a page is loaded.
-   Fixed a bug where extension settings pages failed to reload on reopen by updating the settings form when extension settings are saved.
-   Fixed an issue where the Command Palette failed to launch from the runner.
-   Refactored and ported the PowerToys Run v1 calculator logic into Command Palette, added settings support, and improved fallback behavior.
-   Re-added support for list item keyboard shortcuts.
-   Enhanced accessibility in Command Palette by adding proper labels, refining animations, improving localization, and fixed a11y related issues.
-   Ported custom format support to the Time and Date plugin, reordered and cleaned up settings, improved error messaging, and fixed edge-case crashes for more robust and user-friendly behavior. Thanks @htcfreek!
-   Added fallback item for system command.
-   Fixed a bug in Windows System Command where the key prompt incorrectly displayed "Empty" for the "Open Recycle Bin" action. Thanks @jironemo!
-   Fixed an issue where the 'more commands' list showed commands that shouldn't be visible. Thanks @davidegiacometti!
-   Fixed an issue where the details view in Command Palette displayed an oversized icon and misaligned text, aligning it with Windows Search behavior.
-   Fixed a bug where empty screen content and command bar commands were cut off when using long labels, ensuring proper layout and visibility.
-   Improved CmdPal’s WinGet integration by fixing version display for installed packages, enabling updates with icons, and migrating the preview winget API to a stable version.
-   Fixed a bug where commands for ContentPage didn't update until after exit, by ensuring context menus are fully initialized when they change.
-   Added fallback support to the TimeDate extension, enabling direct date/time queries without pre-selecting the command.
-   Added import of Common.Dotnet.AotCompatibility.props across multiple CmdPal project files to enhance AOT compilation support.
-   Fixed a crash in CmdPal settings caused by a null HotKey when settings.json is missing or lacks a defined hotkey. Thanks @davidegiacometti!
-   Added support for filterable, nested context menus in CmdPal, including a search box to maintain focus behavior.
-   Refactored CmdPal classes to improve JSON serialization and introduced new serialization contexts for better performance and maintainability.
-   Added support for ahead-of-time (AoT) compilation.
-   Added retry mechanism for CmdPal launch.
-   Removed some unused files from CmdPal.Common to simplify codebase and facilitate marking it as AoT-compatible.
-   Fixed a bug where a race condition in the update of SearchText caused the cursor in the input box to automatically jump to the end of the line, ensuring SearchText is only updated after it has actually been changed.
-   Added support for searching any file in fallback command.
-   Cleaned up AoT-related code to prevent duplicate operations during testing.
-   Reduced CmdPal load time by parallelizing extension startup and adding timeouts to prevent misbehaving extensions from blocking others.
-   Enhanced UI behavior by dismissing the details pane when the list gets emptied, avoiding inconsistent visual states.
-   Added support to unset the fallback command in CmdPal when no matching command is found, ensuring cleaner reload behavior.
-   Fixed a leak in the CmdPal extension template by addressing improper ComServer use.
-   Prevented CmdPal window from maximizing on title bar double-click to maintain intended window behavior. Thanks @davidegiacometti!
-   Fixed an issue where the Settings UI launched too small by making window dimensions DPI-aware and enforcing minimum width and height using WinUIEx.
-   Fixed white flash and one-time animation issues in CmdPal by cloaking the window instead of hiding it.
-   Fixed a bug where all extension settings were fetched on startup by lazy-loading extension settings, reducing initialization overhead.
-   Added support for protecting CmdPal from crashes on Adaptive Card parse failure.
-   Replaced shell:AppsFolder with URI activation in CmdPal to improve reliability.
-   Added ability to open CmdPal settings from PowerToys Settings.
-   Added ability for CmdPal to observe and dynamically update extension details by tracking property changes on the selected item.
-   Bumped the toolkit version used in the CmdPal extension template to 0.2.0.

### Image Resizer

-   Fixed an issue where deleting an Image Resizer preset removed the wrong preset.

### Keyboard Manager

-   Fixed an issue where a modifier key, when set without specifying left or right, would get stuck due to incorrect key handling, by tracking the pressed keys and sending the correct key accordingly. Thanks @mantaionut!

### PowerRename

-   Enhanced PowerRename's time formatting capabilities by adding 12-hour time format patterns with AM/PM support. Thanks @bitmap4!

### PowerToys Run

-   Added support for custom formats in the "Time and Date" plugin and improves error messages for invalid input formats. Thanks @htcfreek!
-   Fix two crashes: one for WFT on very early dates and another for calculating the week of the month on very late dates (e.g., 31.12.9999), and reorder UI settings. Thanks @htcfreek!
-   Fix an issue where capitalization in the command causes failure when trying to go to the mouse pointer, resolved by adjusting the command to lowercase.
-   Added version details to plugin error messages for 'Loading error' and 'Init error'. Thanks @htcfreek!
-   Enhanced result model by adding support for preventing usage-based ordering, giving plugin developers greater control over sorting behavior. Thanks @CoreyHayward and @htcfreek!

### Quick Accent

-   Updated the letter mapping in GetDefaultLetterKeyEPO, replacing "ǔ" with "ŭ" for the VK\_U key to accurately reflect Esperanto phonetics. Thanks @OlegKharchevkin!
-   Fixed an issue where Quick Accent did not work properly when using the on-screen keyboard. Thanks @davidegiacometti!

### Registry Preview

-   Enhanced Registry Preview to support pasting registry keys and values without manually writing the file header, and added a new button for resetting the app. Thanks @htcfreek!

### Settings

-   Fix an issue where the Settings app randomly showed a blank icon in the taskbar by deferring icon assignment until the window is activated.
-   Added the ability to maximize the "What's New" window for a more comfortable reading experience.

### Workspaces

-   Fixed bugs where Steam games were not captured or launched correctly by updating window filtering and integrating Steam URL protocol handling.

### Documentation

-   Added QuickNotes to the third-party plugins documentation for PowerToys Run. Thanks @ruslanlap!
-   Added Weather and Pomodoro plugins to the PowerToys Run third-party plugin documentation. Thanks @ruslanlap!
-   Added the Linear plugin to PowerToys Run's third-party plugin documentation. Thanks @vednig!
-   Fixed formatting issues in documentation files and updated contributor and team member information. Thanks @DanielEScherzer and @RokyZevon!

### Development

-   Updated GitHub Action to install .NET 9 for MSStore release support.
-   Updated version placeholder in bug\_report.yml to prevent incorrect v0.70.0 versioning in issue reports.
-   Updated GitHub Action to upgrade actions/setup-dotnet from version 3 to version 4 for MSStore release.
-   Added securityContext to WinGet configuration files, allowing invocation from user context and prompting a single UAC for elevated resources in a separate process. Thanks @mdanish-kh!
-   Changed log file extensions from .txt to .log to support proper file associations and tooling compatibility, and added logs for Workspace. Thanks @benwa!
-   Upgraded testing framework dependencies and aligned package versions across components.
-   Upgraded dependencies to fix vulnerabilities.
-   Enhanced repository security by pinning GitHub Actions and Docker tags to immutable full-length commits and integrating automated dependency vulnerability scanning via Dependency Review Workflow. Thanks @Nick2bad4u!
-   Upgraded Boost dependencies to a newer version.
-   Upgraded toolkit to the latest version, suppressed AoT-related warnings.
-   Fixed an issue where missing signing for newly added files caused build failures.
-   Update release pipeline to prevent publishing private symbols for 100 years.
-   Introduced fuzzing for PowerRename to improve reliability and added setup guidance for extending fuzzing to other C++ modules.
-   Added centralized pre-creation of generated folders for all .csproj projects to prevent build failures.
-   Updated WinAppSDK to the latest 1.7 version.
-   Upgraded Boost dependencies to the latest version for the PowerRename Fuzzing project.
-   Updated the ADO area path in tsa.json to resolve TSA pipeline errors caused by a deprecated path.
-   Initiated AoT support for CmdPal with foundational work in progress.

### Tool/General

-   Added support for automating bug report creation by generating a pre-filled GitHub issue URL with system and diagnostic information. Thanks @donlaci!
-   Added scripts to locally build the installer, ensuring the CmdPal can also be launched in a local environment.
-   Removed export PFX logic to eliminate hardcoded password usage and resolve PSScriptAnalyzer security warning.
-   Added PowerShell script and CI integration to enforce consistent use of Common.Dotnet.CsWinRT.props across all C# projects under the src folder.

### What is being planned for version 0.92

For v0.92, we'll work on the items below:

-   Continued Command Palette polish
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
