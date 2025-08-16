---
project: remix-ide
stars: 2318
description: Documentation for Remix IDE
url: https://github.com/ethereum/remix-ide
---

Remix
=====

This repository contain only Remix's official Read the Docs documentation source code. The documentation can be found on the Remix IDE documentation site.

Remix Project Codebases
-----------------------

Remix Docs (this repo)

-   GitHub repo: https://github.com/ethereum/remix-ide/
-   Website URL: https://remix-ide.readthedocs.io/en/latest/

Remix IDE

-   GitHub repo: https://github.com/ethereum/remix-project
-   Website URL: https://remix.ethereum.org

Remix About page

-   GitHub repo: https://github.com/ethereum/remix-website/
-   Website URL: https://remix-project.org

About Remix Project
-------------------

The **Remix Project** is a platform for development tools that use a plugin architecture. It encompasses sub-projects including Remix Plugin Engine, Remix Libraries, and of course Remix IDE.

The **Remix IDE** is an open source web and desktop application. It fosters a fast development cycle and has a rich set of plugins with intuitive GUIs. Remix is used for the entire journey of contract development with Solidity language as well as a playground for learning and teaching Ethereum.

You can start developing with Remix on the browser by visiting: https://remix.ethereum.org. If you prefer a desktop version, check out: https://github.com/remix-project-org/remix-desktop.

The built-in plugins in Remix IDE are built on top of **Remix libraries**, which handle core operations like compiling and interacting with smart contracts.. Explore the Remix libraries README to learn more.

Setup the Documentation Locally
-------------------------------

Steps to build this project are as follows:

First, you need to set up a Python virtual environment. This is a self-contained environment where you can install Python packages without interfering with your system's Python installation. Here's how you can create and activate a Python virtual environment:

# Create a virtual environment
# By placing in \`.vscode\` these will be git ignored, and not committed
python3 -m venv .vscode/venv

# Activate the virtual environment
# On Windows:
.vscode\\venv\\Scripts\\activate

# On Unix or MacOS:
source venv/bin/activate

Once the virtual environment is activated, you can install the necessary Python packages:

pip3 install sphinx sphinx\_rtd\_theme
pip3 install myst-parser

Then, you can clone the repository and build the project:

git clone https://github.com/ethereum/remix-ide.git
cd remix-ide/docs/ # into /docs subfolder
make html

Go to `docs/_build/html` and start a Python HTTP server to serve the HTML files:

cd \_build/html
python3 -m http.server

View by visiting `http://localhost:8000` in your web browser.

When you're done, you can deactivate the virtual environment:

deactivate

Contributing
------------

We wholeheartedly welcome everyone to contribute. Suggestions, issues, queries and feedback are our pleasure. Please join our Discord server.

### Translating

The site is internationalized. **Do not make any corrections to .po or .pot files.** These get handled in our translation management platform Crowdin. To help with the translation of our documentation, please visit https://crowdin.com/project/remix-translation. To help with our translations of Remix's UI, please visit https://crowdin.com/project/remix-ui.

Custom theming
--------------

The documentation is built using Sphinx and the Read the Docs theme as a base. The theme has been customized using CSS overrides and JavaScript to built on top of the base theme.

**conf.py**

html\_js\_files \= \[
    "js/constants.js",
    "js/utils.js",
    "js/loaders.js",
    "js/initialize.js"
\]

html\_css\_files \= \["css/fonts.css", "css/tokens.css", "css/custom.css"\]

These `js` and `css` files are been declared to run once the initial theming has been applied.

File (`docs/_static/`)

Description

**constants.js**

Contains all JavaScript constants to be used throughout the other scripts.

**utils.js**

Contains all utility/helper functions to be used throughout the other scripts.

**loaders.js**

Contains primary logic for all the loading scripts, organized by `initialize.js`.

**initialize.js**

Contains high-level script logic. Declares order of `loader.js` functions to be run during `onDOMContentLoaded` (immediately after the initial DOM content has been loaded)

**css/fonts.css**

Contains all font imports and declarations.

**css/tokens.css**

Contains all CSS theming variables and tokens used throughout the other CSS files.

**css/custom.css**

Contains all custom CSS overrides and theming. This uses existing CSS selectors from the Sphinx theming to select and override various styling.
