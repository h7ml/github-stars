---
project: Scoop
stars: 22860
description: A command-line installer for Windows.
url: https://github.com/ScoopInstaller/Scoop
---

Scoop
=====

Features | Installation | Documentation

* * *

Scoop is a command-line installer for Windows.

What does Scoop do?
-------------------

Scoop installs apps from the command line with a minimal amount of friction. It:

-   Eliminates User Account Control (UAC) prompt notifications.
-   Hides the graphical user interface (GUI) of wizard-style installers.
-   Prevents polluting the `PATH` environment variable. Normally, this variable gets cluttered as different apps are installed on the device.
-   Avoids unexpected side effects from installing and uninstalling apps.
-   Resolves and installs dependencies automatically.
-   Performs all the necessary steps to get an app to a working state.

Scoop is quite script-friendly. Your environment can become the way you like by using repeatable setups. For example:

scoop install sudo
sudo scoop install 7zip git openssh --global
scoop install aria2 curl grep sed less touch
scoop install python ruby go perl

If you have built software that you would like others to use, Scoop is an alternative to building an installer (like MSI or InnoSetup). You just need to compress your app to a `.zip` file and provide a JSON manifest that describes how to install it.

Installation
------------

Run the following commands from a regular (non-admin) PowerShell terminal to install Scoop:

Set-ExecutionPolicy \-ExecutionPolicy RemoteSigned \-Scope CurrentUser
Invoke-RestMethod \-Uri https://get.scoop.sh | Invoke-Expression

**Note**: The first command makes your device allow running the installation and management scripts. This is necessary because Windows 10 client devices restrict execution of any PowerShell scripts by default.

It will install Scoop to its default location:

`C:\Users\<YOUR USERNAME>\scoop`

You can find the complete documentation about the installer, including advanced installation configurations, in ScoopInstaller/Install. Please create new issues there if you have questions about the installation.

Multi-connection downloads with `aria2`
---------------------------------------

Scoop can utilize `aria2` to use multi-connection downloads. Simply install `aria2` through Scoop and it will be used for all downloads afterward.

scoop install aria2

By default, `scoop` displays a warning when running `scoop install` or `scoop update` while `aria2` is enabled. This warning can be suppressed by running `scoop config aria2-warning-enabled false`.

You can tweak the following `aria2` settings with the `scoop config` command:

-   aria2-enabled (default: true)
-   aria2-warning-enabled (default: true)
-   aria2-retry-wait (default: 2)
-   aria2-split (default: 5)
-   aria2-max-connection-per-server (default: 5)
-   aria2-min-split-size (default: 5M)
-   aria2-options (default: )

Inspiration
-----------

-   Homebrew
-   Sub

What sort of apps can Scoop install?
------------------------------------

The apps that are most likely to get installed fine with Scoop are those referred to as "portable" apps. These apps are compressed files which can run standalone after being extracted. This type of apps does not produce side effects like changing the Windows Registry or placing files outside the app directory.

Scoop also supports installer files and their uninstallation methods. Likewise, it can handle single-file apps and PowerShell scripts. These do not even need to be compressed. See the runat package for an example: it is simply a GitHub gist.

### Contribute to this project

If you would like to improve Scoop by adding features or fixing bugs, please read our Contributing Guide.

### Support this project

If you find Scoop useful and would like to support the ongoing development and maintenance of this project, you can donate here:

-   PayPal (one-time donations)

Known application buckets
-------------------------

The following buckets are known to Scoop:

-   main - Default bucket which contains popular non-GUI apps.
-   extras - Apps that do not fit the main bucket's criteria.
-   games - Open-source and freeware video games and game-related tools.
-   nerd-fonts - Nerd Fonts.
-   nirsoft - A collection of over 250+ apps from Nirsoft.
-   sysinternals - The Sysinternals suite from Microsoft.
-   java - A collection of Java development kits (JDKs) and Java runtime engines (JREs), Java's virtual machine debugging tools and Java based runtime engines.
-   nonportable - Non-portable apps (may trigger UAC prompts).
-   php - Installers for most versions of PHP.
-   versions - Alternative versions of apps found in other buckets.

The `main` bucket is installed by default. You can make use of more buckets by typing:

scoop bucket add <name>

For example, to add the `extras` bucket, type:

scoop bucket add extras

You would be able to install apps from the `extras` bucket now.

Other application buckets
-------------------------

Many other application buckets hosted on GitHub can be found on ScoopSearch or via other search engines.
