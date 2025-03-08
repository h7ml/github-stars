---
project: nx-console
stars: 1316
description: Nx Console is the user interface for Nx & Lerna.
url: https://github.com/nrwl/nx-console
---

The UI for Nx & Lerna
=====================

**Spend less time looking up command line arguments and more time shipping incredible products.**

* * *

Why Nx Console?
---------------

Developers use both command-line tools and user interfaces. They commit in the terminal, but resolve conflicts in Visual Studio Code or WebStorm. They use the right tool for the job.

Nx is a command-line tool, which works great when you want to serve an application or generate a simple component. But it falls short once you start doing advanced things.

For instance:

-   Exploring custom generator collections is hard in the terminal, but it's easy using Nx Console.
-   Using rarely-used flags is challenging. Do you pass absolute or relative paths? You don't have to remember any flags, names or paths - Nx Console will help you by providing autocompletion and validating your inputs.
-   Context-switching between your IDE and the browser is annoying. With Nx Console, you can view the nx graph right in VSCode!

Nx Console does all that and more!

Download
--------

You can install Nx Console in the following places:

-   Nx Console for Visual Studio Code from the Visual Studio Marketplace.
-   Nx Console for JetBrains from the JetBrains Marketplace

True UI for Nx & Lerna
----------------------

Nx Console is the UI for all Nx workspaces. It works for any generator or any architect commands. Nx Console does not have a specific UI for, say, generating a component. Instead, Nx Console does what the command-line version of Nx does - it analyzes the same meta information to create the needed UI. This means that anything you can do with Nx, you can do with Nx Console. After all, Nx Console is the UI for Nx.

Useful for Both Experts and Beginners
-------------------------------------

Even though we started building Nx Console as a tool for experts, we also aimed to make Nx Console a great tool for developers who are new to development or Nx. You can create projects, interact with your editor, run generators and commands and install extensions without ever touching the terminal or having to install any node packages globally. Also, Nx Console highlights the properties you are likely to use for built-in generators and commands, so if you haven't used the CLI, you don't get overwhelmed.

Compatibility
-------------

The latest version of Nx Console supports all Nx versions starting at Nx 15. For older versions, we cannot guarantee compatibility or full functionality. However, we welcome contributions! If you encounter specific issues with older versions, please consider submitting a PR. Of course, if you discover any problems with newer versions of Nx, please report these issues to help us improve Nx Console.

If you're looking to upgrade your version of Nx easily, refer to the Nx migrate documentation.

Learn More
==========

-   Documentation - Official documentation with video tutorials
-   nx.dev - Documentation, Guides and Interactive Tutorials on Nx
-   Join the community - Chat about Nx & Nx Console on the official discord server
-   Learn more about the team at Nx - The team at Nx led the development of Nx Console, after working with many Enterprise clients.

Contributing
============

Please read the contributing guidelines. Pick one of the issues from the good first issue list to get started.

### Jetbrains WSL support

The Node interpreter under **Languages & Frameworks** > **Node.js** needs to be configured to use the Node executable within the WSL distribution. You can read more on the official Jetbrains docs page.
