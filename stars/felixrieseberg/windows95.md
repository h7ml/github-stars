---
project: windows95
stars: 22281
description: 💩🚀 Windows 95 in Electron. Runs on macOS, Linux, and Windows.
url: https://github.com/felixrieseberg/windows95
---

windows95
=========

This is Windows 95, running in an Electron app. Yes, it's the full thing. I'm sorry.

Downloads
---------

  
Windows

32-bit 💿 Installer | 📦 Standalone Zip  
64-bit 💿 Installer | 📦 Standalone Zip  
ARM64 💿 Installer | 📦 Standalone Zip  
❓ Don't know what kind of chip you have? Hit start, enter "processor" for info.

  
macOS

Intel Processor 📦 Standalone Zip  
Apple M1 Processor 📦 Standalone Zip  
❓ Don't know what kind of chip you have? Learn more at apple.com.

  
Linux

64-bit 💿 rpm | 💿 deb  
ARM64 💿 rpm | 💿 deb  
ARMv7 (armhf) 💿 rpm | 💿 deb

* * *

Does it work?
-------------

Yes! Quite well, actually - on macOS, Windows, and Linux. Bear in mind that this is written entirely in JavaScript, so please adjust your expectations.

Should this have been a native app?
-----------------------------------

Absolutely.

Does it run Doom (or my other favorite game)?
---------------------------------------------

You'll likely be better off with an actual virtualization app, but the short answer is yes. Thanks to @DisplacedGamers I can recommend that you switch to a resolution of 640x480 @ 256 colors before starting DOS games - just like in the good ol' days.

Credits
-------

99% of the work was done over at v86 by Copy aka Fabian Hemmer and his contributors.

Contributing
------------

Before you can run this from source, you'll need the disk image. It's not part of the repository, but you can grab it using the `Show Disk Image` button from the packaged release, which does include the disk image. You can find that button in the `Modify C: Drive` section.

Unpack the `images` folder into the `src` folder, creating this layout:

```
- /images/windows95.img
- /images/default-state.bin
- /assets/...
- /bios/...
- /docs/...
```

Once you've done so, run `npm install` and `npm start` to run your local build.

If you want to tinker with the image or make a new one, check out the QEMU docs.

Other Questions
---------------

-   MS-DOS seems to brick the screen
-   Windows 95 is stuck in a bad state
-   I want to install additional apps or games
-   Running in Docker
-   Running in an online VM with Kubernetes and Gitpod

License
-------

This project is provided for educational purposes only. It is not affiliated with and has not been approved by Microsoft.
