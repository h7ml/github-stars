---
project: jetbrains-wakatime
stars: 1199
description: IntelliJ IDEA, PyCharm, RubyMine, PhpStorm, AppCode, AndroidStudio, Goland, Rider, & WebStorm plugin for quantifying your coding.
url: https://github.com/wakatime/jetbrains-wakatime
---

jetbrains-wakatime
==================

WakaTime is an open source Jetbrains plugin for metrics, insights, and time tracking automatically generated from your programming activity.

Supports Jetbrains IDES:

-   Android Studio
-   AppCode
-   CLion
-   DataGrip
-   GoLand
-   IntelliJ IDEA
-   PhpStorm
-   PyCharm
-   Rider
-   RubyMine
-   WebStorm

Installation
------------

1.  Inside your IDE, select `Preferences → Plugins`.
    
2.  Search for `WakaTime`.
    
3.  Click the green `Install` button.
    
4.  Re-launch your IDE.
    
5.  Enter your api key in `Tools → WakaTime API Key`, then click `Save`.
    
6.  Use your IDE and your coding activity will be displayed on your WakaTime dashboard.
    

Screen Shots
------------

Configuring
-----------

WakaTime for Jetbrains IDE's can be configured via Tools → WakaTime Settings.

For more settings, WakaTime plugins share a common config file `.wakatime.cfg` located in your user home directory with these options available.

Uninstalling
------------

Inside your IDE, select `Preferences → Plugins`, then find the `WakaTime` plugin. Click `Uninstall`. Then delete your `~/.wakatime.cfg` config file.

Troubleshooting
---------------

If you’re using a proxy, try excluding `*.wakatime.com` from using your IDE proxy:

Next, turn on debug mode from `Tools → WakaTime Settings`. Then restart your IDE.

Note: If the plugin wasn’t loaded, you won’t have a WakaTime Settings menu. In that case, check for error messages in your IDE’s `idea.log` file indicating why the plugin couldn’t load.

Check your IDE’s `idea.log` file for WakaTime related messages:

`Help → Show Log` ( Locating your idea.log file )

For more general troubleshooting information, see WakaTime CLI Troubleshooting.
