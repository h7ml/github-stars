---
project: LSPosed
stars: 21343
description: LSPosed Framework
url: https://github.com/LSPosed/LSPosed
---

LSPosed Framework
=================

Introduction
------------

A Riru / Zygisk module trying to provide an ART hooking framework which delivers consistent APIs with the OG Xposed, leveraging LSPlant hooking framework.

> Xposed is a framework for modules that can change the behavior of the system and apps without touching any APKs. That's great because it means that modules can work for different versions and even ROMs without any changes (as long as the original code was not changed too much). It's also easy to undo. As all changes are done in the memory, you just need to deactivate the module and reboot to get your original system back. There are many other advantages, but here is just one more: multiple modules can do changes to the same part of the system or app. With modified APKs, you have to choose one. No way to combine them, unless the author builds multiple APKs with different combinations.

Supported Versions
------------------

Android 8.1 ~ 14

Install
-------

1.  Install Magisk v24+
2.  (For Riru flavor) Install Riru v26.1.7+
3.  Download and install LSPosed in Magisk app
4.  Reboot
5.  Open LSPosed manager from notification
6.  Have fun :)

Download
--------

-   For stable releases, please go to Github Releases page
-   For canary build, please check Github Actions

Note: debug builds are only available in Github Actions.

Get Help
--------

**Only bug reports from THE LATEST DEBUG BUILD will be accepted.**

-   GitHub issues: Issues
-   (For Chinese speakers) 本项目只接受英语**标题**的issue。如果您不懂英语，请使用翻译工具

For Developers
--------------

Developers are welcome to write Xposed modules with hooks based on LSPosed Framework. A module based on LSPosed framework is fully compatible with the original Xposed Framework, and vice versa, a Xposed Framework-based module will work well with LSPosed framework too.

-   Xposed Framework API

We use our own module repository. We welcome developers to submit modules to our repository, and then modules can be downloaded in LSPosed.

-   LSPosed Module Repository

Community Discussion
--------------------

-   Telegram: @LSPosed

Notice: These community groups don't accept any bug report, please use Get help to report.

Translation Contributing
------------------------

You can contribute translation here.

Credits
-------

-   Magisk: makes all these possible
-   Riru: provides a way to inject code into zygote process
-   XposedBridge: the OG Xposed framework APIs
-   Dobby: used for inline hooking
-   LSPlant: the core ART hooking framework
-   EdXposed: fork source
-   SandHook: ART hooking framework for SandHook variant
-   YAHFA: previous ART hooking framework
-   dexmaker and dalvikdx: to dynamically generate YAHFA hooker classes
-   DexBuilder: to dynamically generate YAHFA hooker classes

License
-------

LSPosed is licensed under the **GNU General Public License v3 (GPL-3)** (http://www.gnu.org/copyleft/gpl.html).
