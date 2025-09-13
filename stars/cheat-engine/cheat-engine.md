---
project: cheat-engine
stars: 16929
description: Cheat Engine. A development environment focused on modding
url: https://github.com/cheat-engine/cheat-engine
---

Cheat Engine
============

Cheat Engine is a development environment focused on modding games and applications for personal use.

Download
========

-   **Latest Version**

Older versions

Links
=====

-   Website
-   Forum
-   Forum (alternate)
-   Forum (alternate)
-   Wiki

Social Media
------------

-   Reddit
-   Twitter

Donate
------

-   Patreon
-   PayPal

Basic Build Instructions
------------------------

1.  Download Lazarus 2.2.2 from https://sourceforge.net/projects/lazarus/files/Lazarus%20Windows%2064%20bits/Lazarus%202.2.2/ First install lazarus-2.2.2-fpc-3.2.2-win64.exe and then lazarus-2.2.2-fpc-3.2.2-cross-i386-win32-win64.exe
    
2.  Run Lazarus and click on `Project->Open Project`. Select `cheatengine.lpi` from the `Cheat Engine` folder as the project.
    
3.  Click on `Run->Build` or press SHIFT+F9.
    
    -   you can also click on `Run->Compile many Modes` (tip: select first three compile modes)
    -   If you want to run or debug from the IDE on Windows you will need to run Lazarus as administrator.

Do not forget to compile secondary projects you'd like to use:

```
 speedhack.lpr: Compile both 32- and 64-bit DLL's for speedhack capability
 luaclient.lpr: Compile both 32- and 64-bit DLL's for {$luacode} capability
 DirectXMess.sln: Compile for 32-bit and 64-bit for D3D overlay and snapshot capabilities
 DotNetcompiler.sln: for the cscompile lua command
 monodatacollector.sln: Compile both 32-bit and 64-bit dll's to get Mono features to inspect the .NET environment of the process    
 dotnetdatacollector.sln: Compile both 32- and 64-bit EXE's to get .NET symbols
 dotnetinvasivedatacollector.sln: Compile this managed .DLL to add support for runtime JIT support
 cejvmti.sln: Compile both 32- and 64-bit DLL's for Java inspection support
 tcclib.sln: Compile 32-32, 64-32 and 64-64 to add {$C} and {$CCODE} support in scripts
 vehdebug.lpr: Compile 32- and 64-bit DLL's to add support for the VEH debugger interface
 dbkkernel.sln: for kernelmode functions (settings->extra) You will need to build the no-sig version and either boot with unsigned driver support, or sign the driver yourself    
```

\*.SLN files require visual studio (Usually 2017)
