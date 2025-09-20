---
project: Termino.js
stars: 627
description: Create a web based terminal on any website - great for games, animations and real world apps!
url: https://github.com/MarketingPipeline/Termino.js
---

Termino.js ·
============

**User Showcase** | **Live Demo** | **Getting Started** | **Documentation** | **GitHub**

Termino.js is a highly customizable front-end component written in pure JavaScript that is great for making web based terminal animations, games & apps on any website including support for curses-based apps, custom functions on user commands, key-code & mouse events & much more!

_ie:_ You can use this JavaScript library to create web based terminals on any website.

Learn how to use Termino.js in your project.

Features
--------

-   **Fast**: Termino.js is _lightweight_ - being built in pure JavaScript
-   **Self-contained**: Requires zero dependencies to work.
-   **Great for animations**: You can make terminal animations with ease & bring your favourite typewriter library in or etc!
-   **Customizable**: Bring your own HTML, CSS & customize / create a terminal to your liking!
-   **Inputs**: Supports inputs for questions returned via a promised / await based value
-   **Multiple instances**: Create more than one custom terminal in a page!
-   **HTML support**: Add HTML elements such as links and more to your terminal!
-   **Custom functions**: Create your own custom functions with ease (including user-command functions, key-code functions & your own mouse event functions)
-   **And much more**: the options are endless!

Termino.js is not
-----------------

-   Termino.js is not a executable application that you can download and use on your computer. It is a JavaScript library you use in the **browser**.
-   Termino.js is not a `bash` emulator etc. Termino.js can be connected to processes like `bash` or a `SSH` instance via API etc or any process that lets you interact with them by providing input & receiving output.

Documentation
-------------

You can find the Termino.js documentation here.

Check out the Getting Started for a quick overview.

You can improve it by sending pull requests to this repository.

Example and usage
-----------------

You can view a demo of Termino.js in use here.

How to use **_Termino.js_**:

<!doctype html\>
  <html\>
    <head\>
    <title\>Termino.js Basic Example</title\>
    </head\>
    <body\>
      <div id\="terminal"\>
      <pre\><code class\="termino-console"\></code\></pre\>
      <textarea class\="termino-input" rows\="1" wrap\="hard"\></textarea\>
      </div\>
      <script type\="module"\>
        import {Termino} from 'https://cdn.jsdelivr.net/gh/MarketingPipeline/Termino.js@latest/dist/termino.min.js';
        let term\= Termino(document.getElementById("terminal"))
        term.echo("Hello world from https://github.com/MarketingPipeline")
      </script\>
    </body\>
  </html\>

For more advanced usage such as adding your own commands, creating animations & etc. See the live examples here or you can find the Termino.js documentation here.

Contributing
------------

> The main purpose of this repository is to continue evolving Termino.js, making it faster and easier to use. Development of Termino.js happens in the open on GitHub, and we are grateful to the community for contributing bugfixes and improvements.

Want to improve this? Create a pull request with detailed changes / improvements! If approved you will be added to the list of contributors of this awesome project!

Looking for a task to work on? Check the tasks that need improved in the to-do list.

See also the list of contributors who participate in this project.

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.
