---
project: PowerToys
stars: 124061
description: Microsoft PowerToys is a collection of utilities that help you customize Windows and streamline everyday tasks
url: https://github.com/microsoft/PowerToys
---

Microsoft PowerToys
===================

### Installation · Documentation · Blog · Release notes

  
  
Microsoft PowerToys is a collection of utilities that help you customize Windows and streamline everyday tasks.  
  

Advanced Paste

Always on Top

Awake

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

📋 Installation
---------------

For detailed installation instructions, visit the installation docs.

Before you begin, make sure your device meets the system requirements:

Note

-   Windows 11 or Windows 10 version 2004 (20H1 / build 19041) or newer
-   64-bit processor: x64 or ARM64
-   Latest stable version of Microsoft Edge WebView2 Runtime is installed via the bootstrapper during setup

Choose one of the installation methods below:

Download .exe from GitHub

Go to the PowerToys GitHub releases, click Assets to reveal the downloads, and choose the installer that matches your architecture and install scope. For most devices, that's the x64 per-user installer.

Description

Filename

Per user - x64

PowerToysUserSetup-0.94.0-x64.exe

Per user - ARM64

PowerToysUserSetup-0.94.0-arm64.exe

Machine wide - x64

PowerToysSetup-0.94.0-x64.exe

Machine wide - ARM64

PowerToysSetup-0.94.0-arm64.exe

Microsoft Store You can easily install PowerToys from the Microsoft Store:

WinGet

Download PowerToys from WinGet. Updating PowerToys via winget will respect the current PowerToys installation scope. To install PowerToys, run the following command from the command line / PowerShell:

_User scope installer \[default\]_

winget install Microsoft.PowerToys \-s winget

_Machine-wide scope installer_

winget install \--scope machine Microsoft.PowerToys \-s winget

Other methods

There are community driven install methods such as Chocolatey and Scoop. If these are your preferred install solutions, you can find the install instructions there.

✨ What's new
------------

**Version 0.94 (September 2025)**

For an in-depth look at the latest changes, visit the Windows Command Line blog.

**✨ Highlights**

-   PowerToys Settings added a Settings search with fuzzy matching, suggestions, a results page, and UX polish to make finding options faster.
-   A comprehensive hotkey conflict detection system was introduced in Settings to surface and help resolve conflicting shortcuts. Note that the default hotkey settings (Win+Ctrl+Shift+T, Win+Ctrl+V, Win+Ctrl+T, Win+Shift+T) may overlap with existing Windows system shortcuts. This is expected. You can resolve the conflict by assigning different hotkeys.
-   Mouse Utilities added a “Gliding cursor” accessibility feature to Mouse Pointer Crosshairs for single‑button cursor movement and clicking. Thanks @mikehall-ms!
-   The installer was upgraded to WiX 5 after WiX 3 reached end-of-life; this move improved installer security, reliability, and community support.
-   Tons of bug fixes and improvements for Command Palette, including visual updates and new support for filters on ListPages (handy for extension developers).
-   Hosts Editor now has a “No leading spaces” option so active host entries can start at column 0 even if others are disabled. Thanks @mohammed-saalim!
-   Context menu registration was moved from the installer to runtime to avoid loading disabled modules (runtime registrations).
-   Quick Accent now supports Maltese, and frequently used accents appear first (and are remembered across sessions). Thanks @rovercoder! @davidegiacometti!

### Always On Top

-   Fixed the border hover cursor so it shows the arrow instead of the wait cursor. Thanks @davidegiacometti!

### Command Palette

-   Applied single-click activation only to pointer input; keyboard always activates immediately. Thanks @jiripolasek!
-   Let context menus open at the cursor by removing window-bound constraints. Thanks @jiripolasek!
-   Made error messages clearer with timestamps, HRESULTs, and full details for easier diagnosis. Thanks @jiripolasek!
-   Prevented crashes and improved robustness when updating providers without commands. Thanks @jiripolasek!
-   Ensured the Settings window reliably comes to the front when opened. Thanks @jiripolasek!
-   Replaced the Clipboard History icon with a colorful Fluent icon. Thanks @jiripolasek!
-   Hardened ContentIcon to avoid duplicate parenting and improve diagnostics. Thanks @jiripolasek!
-   Standardized null checks using C# pattern matching for safer behavior.
-   Improved accessibility by focusing the activation shortcut dialog and making text reachable. Thanks @chatasweetie!
-   Moved the extension SDK to a stable Windows SDK and cleaned up message namespaces.
-   Added path shortcuts: ~ to home, and / or \\ to system root, plus UNC support. Thanks @davidegiacometti!
-   Fixed a race in cancellation handling to avoid InvalidOperationException. Thanks @jiripolasek!
-   Aligned separator styling with WinUI 3 for consistent visuals. Thanks @jiripolasek!
-   Added ARM64 PDBs to the Extensions SDK NuGet for better debugging.
-   Added single-select filters to DynamicListPage and updated Windows Services sample.
-   Updated main page placeholder text to better describe what can be searched. Thanks @jiripolasek!
-   Removed explicit WinAppSDK/WebView2 dependencies from toolkit and API. Thanks @rluengen!
-   Added a local keyboard hook to handle the GoBack key reliably. Thanks @jiripolasek!
-   Propagated alias changes safely and resolved conflicts across view models.
-   Allowed providers to override Dispose with a virtual method.
-   Fixed memory leaks by cleaning up removed or cancelled list items.
-   Sorted DateTime extension results by relevance for better usability.
-   Reduced search text "jiggling" by avoiding redundant change notifications.
-   Centralized automation notifications in a UIHelper for better accessibility. Thanks @chatasweetie!
-   Preserved Adaptive Card action types during trimming via DynamicDependency.
-   Added an acrylic backdrop and refined styling to the context menu. Thanks @jiripolasek!
-   Prevented disposed pages and Settings windows from handling stale messages. Thanks @jiripolasek!
-   Made the extension API easier to evolve without breaking clients.
-   Added "evil" sample pages to help reproduce tricky bugs.
-   Fixed WinGet trim-safety issues by replacing LINQ with manual iteration.
-   Cancelled stale list fetches to avoid older results overwriting newer ones in CmdPal.

### Command Palette extensions

-   Improved empty states and ranking logic for multiple extensions. Thanks @htcfreek!
-   Added app icons to the All Apps "Run" context command when available.
-   Restored missing builtin icons by standardizing extension dependencies.
-   Unblocked local deployment by adding WinAppSDK to two sample extensions.

### Hosts File Editor

-   Added a "No leading spaces" option so active hosts entries can start at column 0 even when others are disabled. Thanks @mohammed-saalim!

### Image Resizer

-   Fixed Image Resizer localization by installing satellite resources under the WinUI 3 apps culture path.

### Mouse Utilities

-   Introduced "Gliding cursor" to control the pointer and click with a single hotkey for better accessibility. Thanks @mikehall-ms!

### Mouse Without Borders

-   Blocked Easy Mouse from switching machines during fullscreen apps, with an allow-list for exceptions. Thanks @dot-tb!

### Peek

-   Added Visual Studio shared project file types to XML preview and fixed bgcode handler registration. Thanks @rezanid!
-   Fixes bgcode preview handler registration and events for reliable previews. Thanks @pedrolamas!

### PowerRename

-   Changed the Explorer accelerator key to PowErRename to avoid clashing with the New menu. Thanks @aaron-ni!

### Quick Accent

-   Remembered character usage across sessions so frequently used accents appear first. Thanks @davidegiacometti!
-   Added Maltese language support with specific characters and the Euro symbol. Thanks @rovercoder!
-   Reduced GPU usage issues by making the window Topmost only when the picker is visible. Thanks @daverayment!

### Settings

-   Added telemetry to track usage of the new shortcut conflict detection workflow.
-   Moved the shutdown action from the title bar to a footer menu item with confirmation. Thanks @davidegiacometti!
-   Implemented comprehensive hotkey conflict detection with a dedicated resolution dialog.
-   Added branded visuals for Office and Copilot keys in the KeyVisual control.
-   Introduced Settings search with fuzzy matching and navigation to specific controls.
-   Corrected Spanish localization so product names like Awake remain in English across Settings and OOBE.
-   Simplified the Advanced Paste description in Settings for quicker reading and consistent capitalization. Thanks @OldUser101!
-   Localized conflict messages in the conflict window and dialog.

### Installer

-   Upgraded the installer to WiX 5 with silent "Files in Use" handling for smoother winget installs.
-   Switched Win10 context menu modules to runtime registration and added cleanup on uninstall to avoid stale entries.

### Documentation

-   Adds docs for building the installer locally and testing winget installs.
-   Fixed a broken style guide link in developer documentation. Thanks @denizmaral!

### Development

-   Excluded test and coverage DLLs from BinSkim scans to cut false positives and speed up security analysis.
-   Simplified NOTICE maintenance by removing version numbers and filtering out Microsoft/System packages.
-   Improved NuGet dependency validation to prevent package downgrades and catch issues during restore.
-   Updated UTF.Unknown to a modern version to improve compatibility without breaking changes. Thanks @304NotModified!
-   Refreshed package catalog in CI before installing dependencies to prevent Linux workflow failures.
-   Refactored CmdPal tests with dependency injection and added coverage for queries and settings.
-   Added unit tests to verify Close on Enter swaps Copy/Save as expected. Thanks @mohammed-saalim!
-   Added accessibility IDs to CmdPal UI for stable UI tests.
-   Rewrote system command tests with a new test base and cleaner patterns.
-   Added unit tests for WebSearch and Shell extensions with mockable settings.
-   Added unit tests and abstractions for Apps and Bookmarks extensions.
-   Cleans up AI-generated tests; adds meaningful query tests across extensions.
-   Removed the obsolete debug dialog from Settings for a smoother developer loop.

🛣️ Roadmap
-----------

For v0.95, we'll work on the items below:

-   Continued Command Palette polish
-   Working on Shortcut Guide v2 (Thanks @noraa-junker!)
-   Upgrading Keyboard Manager's editor UI
-   UI tweaking utility with day/night theme switcher
-   DSC v3 support for top utilities
-   New UI automation tests
-   Stability, bug fixes

❤️ PowerToys Community
----------------------

The PowerToys team is extremely grateful to have the support of an amazing active community. The work you do is incredibly important. PowerToys wouldn't be nearly what it is today without your help filing bugs, updating documentation, guiding the design, or writing features. We want to say thank you and take time to recognize your work. Your contributions and feedback improve PowerToys month after month!

Contributing
------------

This project welcomes contributions of all types. Besides coding features / bug fixes, other ways to assist include spec writing, design, documentation, and finding bugs. We are excited to work with the power user community to build a set of tools for helping you get the most out of Windows.

We ask that **before you start work on a feature that you would like to contribute**, please read our Contributor's Guide. We would be happy to work with you to figure out the best approach, provide guidance and mentorship throughout feature development, and help avoid any wasted or duplicate effort.

Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you grant us the rights to use your contribution and that you have permission to do so.

For guidance on developing for PowerToys, please read the developer docs for a detailed breakdown. This includes how to setup your computer to compile.

Code of Conduct
---------------

This project has adopted the Microsoft Open Source Code of Conduct.

Privacy Statement
-----------------

The application logs basic diagnostic data (telemetry). For more privacy information and what we collect, see our PowerToys Data and Privacy documentation.
