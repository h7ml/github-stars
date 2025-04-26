---
project: flameshot
stars: 26055
description: Powerful yet simple to use screenshot software :desktop_computer: :camera_flash:
url: https://github.com/flameshot-org/flameshot
---

  
Flameshot
============

#### Powerful yet simple to use screenshot software.

  

Preview
-------

Index
-----

-   Features
-   Usage
    -   CLI configuration
    -   Config file
-   Keyboard Shortcuts
    -   Local
    -   Global
        -   On KDE Plasma desktop
        -   On Ubuntu
        -   On XFCE 4
-   Considerations
-   Installation
    -   Prebuilt Packages
    -   Packages from Repository
    -   MacOS
    -   Windows
-   Compilation
    -   Dependencies
        -   Compile-time
        -   Run-time
        -   Optional
        -   Debian
        -   Fedora
        -   Arch
    -   Build
    -   Install
-   License
-   Privacy Policy
-   Code Signing Policy
-   Contribute
-   Acknowledgment

Features
--------

-   Customizable appearance.
-   Easy to use.
-   In-app screenshot editing.
-   DBus interface.
-   Upload to Imgur.

Usage
-----

Executing the command `flameshot` without parameters will launch a running instance of the program in the background without taking actions. If your desktop environment provides tray area, a tray icon will also appear in the tray for users to perform configuration and management.

Example commands:

-   Capture with GUI:
    
    flameshot gui
    
-   Capture with GUI with custom save path:
    
    flameshot gui -p ~/myStuff/captures
    
-   Capture with GUI after 2 seconds delay (can be useful to take screenshots of mouse hover tooltips, etc.):
    
    flameshot gui -d 2000
    
-   Fullscreen capture with custom save path (no GUI) and delayed:
    
    flameshot full -p ~/myStuff/captures -d 5000
    
-   Fullscreen capture with custom save path copying to clipboard:
    
    flameshot full -c -p ~/myStuff/captures
    
-   Capture the screen containing the mouse and print the image (bytes) in PNG format:
    
    flameshot screen -r
    
-   Capture the screen number 1 and copy it to the clipboard:
    
    flameshot screen -n 1 -c
    

In case of doubt choose the first or the second command as shortcut in your favorite desktop environment.

A systray icon will be in your system's panel while Flameshot is running. Do a right click on the tray icon and you'll see some menu items to open the configuration window and the information window. Check out the About window to see all available shortcuts in the graphical capture mode.

### CLI configuration

You can use the graphical menu to configure Flameshot, but alternatively you can use your terminal or scripts to do so.

-   Open the configuration menu:
    
    flameshot config
    
-   Show the initial help message in the capture mode:
    
    flameshot config --showhelp true
    
-   For more information about the available options use the help flag:
    
    flameshot config -h
    

### Config file

You can also edit some of the settings (like overriding the default colors) in the configuration file.  
Linux path: `~/.config/flameshot/flameshot.ini`.  
Windows path: `C:\Users\{YOURNAME}\AppData\Roaming\flameshot\flameshot.ini`.

When copying over the config file from Linux to Windows or vice versa, make sure to correct the `savePath` variable,  
so that the screenshots save in the right directory on your desired file system.

Keyboard shortcuts
------------------

### Local

These shortcuts are available in GUI mode:

Keys

Description

P

Set the Pencil as paint tool

D

Set the Line as paint tool

A

Set the Arrow as paint tool

S

Set Selection as paint tool

R

Set the Rectangle as paint tool

C

Set the Circle as paint tool

M

Set the Marker as paint tool

T

Add text to your capture

B

Set Pixelate as the paint tool

←, ↓, ↑, →

Move selection 1px

Shift + ←, ↓, ↑, →

Resize selection 1px

Ctrl + Shift + ←, ↓, ↑, →

Symmetrically resize selection 2px

Esc

Quit capture

Ctrl + M

Move the selection area

Ctrl + C

Copy to clipboard

Ctrl + S

Save selection as a file

Ctrl + Z

Undo the last modification

Ctrl + Shift + Z

Redo the next modification

Ctrl + Q

Leave the capture screen

Ctrl + O

Choose an app to open the capture

Ctrl + Return

Commit text in text area

Return

Upload the selection to Imgur

Spacebar

Toggle visibility of sidebar with options of the selected tool, color picker for the drawing color and history menu

Right Click

Show the color wheel

Mouse Wheel

Change the tool's thickness

Print screen

Capture Screen

Shift + Print

Screenshot History

Ctrl + drawing _line_, _arrow_ or _marker_

Drawing only horizontally, vertically or diagonally

Ctrl + drawing _rectangle_ or _circle_

Keeping aspect ratio

Shift + drag a handler of the selection area: mirror redimension in the opposite handler.

### Global

Flameshot uses Print screen (Windows) and cmd\-shift\-x (macOS) as default global hotkeys.

On Linux, Flameshot doesn't yet support Prt Sc out of the box, but with a bit of configuration you can set this up:

#### On KDE Plasma desktop

To make configuration easier, there's a file in the repository that more or less automates this process. This file will assign the following hotkeys by default:

Keys

Description

Prt Sc

Start the Flameshot screenshot tool and take a screenshot

Ctrl + Prt Sc

Wait for 3 seconds, then start the Flameshot screenshot tool and take a screenshot

Shift + Prt Sc

Take a full-screen (all monitors) screenshot and save it

Ctrl + Shift + Prt Sc

Take a full-screen (all monitors) screenshot and copy it to the clipboard

If you don't like the defaults, they can be changed later.

Steps for using the configuration:

1.  The configuration file makes Flameshot automatically save screenshots to `~/Pictures/Screenshots` without opening the save dialog. Make sure that folder exists by running:
    
    mkdir -p ~/Pictures/Screenshots
    
    (If you don't like the default location, you can skip this step and configure your preferred directory later.)
    
2.  Download the configuration file:
    
    cd ~/Desktop
    wget https://raw.githubusercontent.com/flameshot-org/flameshot/master/docs/shortcuts-config/flameshot-shortcuts-kde.khotkeys
    
3.  Make sure you have the `khotkeys` installed using your package manager to enable custom shortcuts in KDE Plasma.
    
4.  Go to _System Settings_ → _Shortcuts_ → _Custom Shortcuts_.
    
5.  If an entry exists for Spectacle (the default KDE screenshot utility), you'll need to disable it because its shortcuts might conflict with Flameshot's. Do this by unchecking the _Spectacle_ entry.
    
6.  Click _Edit_ → _Import..._, navigate to the configuration file and open it.
    
7.  Now the Flameshot entry should appear in the list. Click _Apply_ to apply the changes.
    
8.  If you want to change the default hotkeys, you can expand the entry, select the appropriate action and modify it as you wish; the process is pretty self-explanatory.
    
9.  If you installed Flameshot as a Flatpak, you will need to create a symlink to the command:
    
    ln -s /var/lib/flatpak/exports/bin/org.flameshot.Flameshot ~/.local/bin/flameshot
    

#### On Ubuntu (Tested on 18.04, 20.04, 22.04)

To use Flameshot instead of the default screenshot application in Ubuntu we need to remove the binding on Prt Sc key, and then create a new binding for `/usr/bin/flameshot gui` (adapted from Pavel's answer on AskUbuntu).

1.  Remove the binding on Prt Sc:
    
    Ubuntu 18.04/20.04 using the following command:
    
    gsettings set org.gnome.settings-daemon.plugins.media-keys screenshot '\[\]'
    
    Ubuntu 22.04: Go to _Settings_ > _Keyboard_ > _View and Customise Shortcuts_ > _Screenshots_ > _Take a screenshot interactively_ and press `backspace`
    
2.  Add custom binding on Prt Sc:
    
    Ubuntu 18.04: Go to _Settings_ > _Device_ > _Keyboard_ and press the '+' button at the bottom.
    
    Ubuntu 20.04: Go to _Settings_ > _Keyboard Shortcuts_ and press the '+' button at the bottom.
    
    Ubuntu 22.04: Go to _Settings_ > _Keyboard_ > _View and Customise Shortcuts_ > _Custom shortcuts_ and press the '+' button at the bottom.
    
3.  Name the command as you like it, e.g. `flameshot`. And in the command insert `/usr/bin/flameshot gui`.
    
4.  Then click "_Set Shortcut.._" and press Prt Sc. This will show as "_print_".
    

Now every time you press Prt Sc, it will start the Flameshot GUI instead of the default application.

#### On XFCE 4

1.  Go to `Keyboard` settings
    
2.  Switch to the tab `Application Shortcuts`
    
3.  Find the entry
    
    ```
    Command                        Shortcut
    xfce4-screenshooter -fd 1      Print
    ```
    
4.  Replace `xfce4-screenshooter -fd 1` with `flameshot gui`
    

Now every time you press Prt Sc it will start Flameshot GUI instead of the default application.

Considerations
--------------

-   Experimental Gnome Wayland and Plasma Wayland support.
    
-   If you are using Gnome you need to install the AppIndicator and KStatusNotifierItem Support extension in order to see the system tray icon.
    
-   Press Enter or Ctrl + C when you are in a capture mode and you don't have an active selection and the whole desktop will be copied to your clipboard. Pressing Ctrl + S will save your capture to a file. Check the Shortcuts for more information.
    
-   Flameshot works best with a desktop environment that includes D-Bus. See this article for tips on using Flameshot in a minimal window manager (dwm, i3, xmonad, etc).
    
-   In order to speed up the first launch of Flameshot (D-Bus init of the app can be slow), consider starting the application automatically on boot.
    
    -   Quick tip: If you don't have Flameshot to autostart at boot and you want to set keyboard shortcut, use the following as the command for the keybinding:
    
    ( flameshot &; ) && ( sleep 0.5s && flameshot gui )
    

Installation
------------

Flameshot can be installed on Linux, Microsoft Windows, and macOS.

### Prebuilt packages

Some prebuilt packages are provided on the release page of the GitHub project repository.

### Packages from Repository

There are packages available in the repository of some Linux distributions:

-   Arch: `pacman -S flameshot`
    -   Snapshot also available via AUR: flameshot-git.
-   Debian 10+: `apt install flameshot`
    -   Package for Debian 9 ("Stretch") also available via stretch-backports.
-   Ubuntu 18.04+: `apt install flameshot`
-   openSUSE: `zypper install flameshot`
-   Void Linux: `xbps-install flameshot`
-   Solus: `eopkg it flameshot`
-   Fedora: `dnf install flameshot`
-   NixOS: `nix-env -iA nixos.flameshot`
-   ALT: `su - -c "apt-get install flameshot"`
-   Snap/Flatpak/AppImage
-   Docker
-   Windows

### macOS

-   MacPorts: `sudo port selfupdate && sudo port install flameshot`
-   Homebrew: `brew install --cask flameshot`

**Note** that because of macOS security features, you may not be able to open flameshot when installed using brew. If you see the message `“flameshot” cannot be opened because the developer cannot be verified.` you will need to follow the steps below:

1.  Go to the Applications folder (Finder > Go > Applications, or Shift+Command+A)
2.  Right-Click on "flameshot.app" and choose "Open" from the context menu
3.  In the dialog click "Open"

After following all those steps above, `flameshot` will open without problems in your Mac.

### Windows

-   Chocolatey

Expand this section to see what distros are using an up to date version of flameshot

### Tray icon

**Note** that for the Flameshot icon to appear in your tray area, you should have a systray software installed. This is especially true for users who use minimal window managers such as dwm. In some Desktop Environment installations (e.g Gnome), the systray might be missing and you can install an application or plugin (e.g Gnome shell extension) to add the systray to your setup. It has been reported) that icon of some software, including Flameshot, does not show in gnome-shell-extension-appindicator.

Alternatively, in case you don't want to have a systray, you can always call Flameshot from the terminal. See Usage section.

Compilation
-----------

To build the application in your system, you'll need to install the dependencies needed for it and package names might be different for each distribution, see Dependencies below for more information. You can also install most of the Qt dependencies via their installer. If you were developing Qt apps before, you probably already have them.

This project uses CMake build system, so you need to install it in order to build the project (on most Linux distributions it is available in the standard repositories as a package called `cmake`). If your distribution provides too old version of CMake (e.g. Ubuntu 18.04) you can download it on the official website.

Also you can open and build/debug the project in a C++ IDE. For example, in Qt Creator you should be able to simply open `CMakeLists.txt` via `Open File or Project` in the menu after installing CMake into your system. More information about CMake projects in Qt Creator.

### Dependencies

#### Compile-time

-   Qt >= 5.9
    -   Development tools
-   GCC >= 7.4
-   CMake >= 3.29

#### Run-time

-   Qt
    -   SVG

#### Optional

-   Git
-   OpenSSL
-   CA Certificates

#### Debian

# Compile-time
apt install g++ cmake build-essential qtbase5-dev qttools5-dev-tools libqt5svg5-dev qttools5-dev

# Run-time
apt install libqt5dbus5 libqt5network5 libqt5core5a libqt5widgets5 libqt5gui5 libqt5svg5

# Optional
apt install git openssl ca-certificates

#### Fedora

# Compile-time
dnf install gcc-c++ cmake qt5-qtbase-devel qt5-linguist

# Run-time
dnf install qt5-qtbase qt5-qtsvg-devel

# Optional
dnf install git openssl ca-certificates

#### Arch

# Compile-time
pacman -S cmake base-devel git qt5-base qt5-tools

# Run-time
pacman -S qt5-svg

# Optional
pacman -S openssl ca-certificates

#### NixOS

nix-shell

#### macOS

First of all you need to install brew and then install the dependencies

brew install qt5
brew install cmake

### Build

After installing all the dependencies, flameshot can be built.

#### Installation/build dir

For the translations to be loaded correctly, the build process needs to be aware of where you want to install flameshot.

# Directory where build files will be placed, may be relative
export BUILD\_DIR=build

# Directory prefix where flameshot will be installed. If you are just building and don't want to
# install, comment this environment variable.
# This excludes the bin/flameshot part of the install,
# e.g. in /opt/flameshot/bin/flameshot, the CMAKE\_INSTALL\_PREFIX is /opt/flameshot
# This must be an absolute path. Requires CMAKE 3.29.
export CMAKE\_INSTALL\_PREFIX=/opt/flameshot

# Linux
cmake -S . -B "$BUILD\_DIR" \\
    && cmake --build "$BUILD\_DIR"

#MacOS
cmake -S . -B "$BUILD\_DIR" \\
    -DQt5\_DIR="$(brew --prefix qt5)/lib/cmake/Qt5" \\
    && cmake --build "$BUILD\_DIR"

When the `cmake --build` command has completed you can launch flameshot from the `project_folder/build/src` folder.

### Install

Note that if you install from source, there _is no_ uninstaller, so consider installing to a custom directory.

#### To install into a custom directory

Make sure you are using cmake `>= 3.29` and build flameshot with `$CMAKE_INSTALL_PREFIX` set to the installation directory. If this is not done, the translations won't be found when using a custom directory. Then, run the following:

# !Build with CMAKE\_INSTALL\_PREFIX and use cmake >= 3.29! Using an older cmake will cause
# installation into the default /usr/local dir.

# You may need to run this with privileges
cmake --install "$BUILD\_DIR"

#### To install to the default install directory

# You may need to run this with privileges
cmake --install "$BUILD\_DIR"

### FAQ

https://flameshot.org/docs/guide/faq/

License
-------

-   The main code is licensed under GPLv3
-   The logo of Flameshot is licensed under Free Art License v1.3
-   The button icons are licensed under Apache License 2.0. See: https://github.com/google/material-design-icons
-   The code at capture/capturewidget.cpp is based on https://github.com/ckaiser/Lightscreen/blob/master/dialogs/areadialog.cpp (GPLv2)
-   The code at capture/capturewidget.h is based on https://github.com/ckaiser/Lightscreen/blob/master/dialogs/areadialog.h (GPLv2)
-   I copied a few lines of code from KSnapshot regiongrabber.cpp revision `796531` (LGPL)
-   Qt-Color-Widgets taken and modified from https://github.com/mbasaglia/Qt-Color-Widgets (see their license and exceptions in the project) (LGPL/GPL)

Info: If I take code from your project and that implies a relicense to GPLv3, you can reuse my changes with the original previous license of your project applied.

Privacy Policy
--------------

This program will not transfer any information to other networked systems unless specifically requested by the user or the person installing or operating it.

Code Signing Policy
-------------------

For Windows binaries, this program uses free code signing provided by SignPath.io, and a certificate by the SignPath Foundation.

Code signing is currently a manual process so not every patch release will be signed.

Contribute
----------

If you want to contribute check the CONTRIBUTING.md

Acknowledgment
--------------

Thanks to those who have shown interest in the early development process:

-   lupoDharkael
-   Cosmo
-   XerTheSquirrel
-   The members of Sugus GNU/Linux
-   ismatori

Thanks to sponsors:

-   Namecheap
-   JetBrains
-   SignPath
-   addy.io
