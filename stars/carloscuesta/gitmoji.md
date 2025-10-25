---
project: gitmoji
stars: 16539
description: An emoji guide for your commit messages. 😜 
url: https://github.com/carloscuesta/gitmoji
---

About
-----

Gitmoji is an initiative to standardize and explain **the use of emojis on GitHub commit messages**.

**Using emojis** on **commit messages** provides an **easy way** of **identifying the purpose or intention of a commit** with only looking at the emojis used. As there are a lot of different emojis I found the need of creating a guide that can help to use emojis easier.

The gitmojis are published on the following package in order to be used as a dependency 📦.

Using gitmoji-cli
-----------------

To use gitmojis from your command line install gitmoji-cli. A gitmoji interactive client for using emojis on commit messages.

npm i -g gitmoji-cli

Example of usage
----------------

In case you need some ideas to integrate gitmoji in your project, here's a practical way to use it:

```
<intention> [scope?][:?] <message>
```

-   `intention`: An emoji from the list.
-   `scope`: An optional string that adds contextual information for the scope of the change.
-   `message`: A brief explanation of the change.

Contributing to gitmoji
-----------------------

Contributing to gitmoji is a piece of 🍰, read the contributing guidelines. You can discuss emojis using the issues section. To add a new emoji to the list create an issue and send a pull request, see how to send a pull request and add a gitmoji.

Spread the word
---------------

Are you using Gitmoji on your project? Set the Gitmoji badge on top of your readme using this code:

<a href\="https://gitmoji.dev"\>
  <img
    src\="https://img.shields.io/badge/gitmoji-%20😜%20😍-FFDD67.svg?style=flat-square"
    alt\="Gitmoji"
  />
</a\>

License
-------

The code is available under the MIT license.
