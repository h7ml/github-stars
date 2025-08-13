---
project: npkill
stars: 8732
description: List any node_modules 📦 dir in your system and how heavy they are. You can then select which ones you want to erase to free up space 🧹
url: https://github.com/voidcosmos/npkill
---

### Easily find and **remove** old and heavy **node\_modules** folders ✨

This tool allows you to list any _node\_modules_ directories in your system, as well as the space they take up. You can then select which ones you want to erase to free up space. Yay!

i18n
----

We're making an effort to internationalize the Npkill docs. Here's a list of the available translations:

-   Español
-   Indonesian
-   Português
-   Turkish

Table of Contents
-----------------

-   Features
-   Installation
-   Usage
    -   Multi-Select Mode
    -   Options
    -   Examples
    -   JSON Output
-   Set Up Locally
-   API
-   Roadmap
-   Known bugs
-   Contributing
-   Buy us a coffee
-   License

✔️ Features
===========

-   **Clear space:** Get rid of old and dusty _node\_modules_ cluttering up your machine.
    
-   **Last Workspace Usage**: Check when was the last time you modified a file in the workspace (indicated in the **last\_mod** column).
    
-   **Very fast:** NPKILL is written in TypeScript, but searches are performed at a low level, improving performance greatly.
    
-   **Easy to use:** Say goodbye to lengthy commands. Using npkill is as simple as reading a list of your node\_modules, and pressing Del to get rid of them. Could it be any easier? ;)
    
-   **Minified:** It barely has any dependencies.
    

☁️ Installation
===============

You don't really need to install it to use it! Simply use the following command:

$ npx npkill

Or if for some reason you really want to install it:

$ npm i -g npkill
# Unix users may need to run the command with sudo. Go carefully

> NPKILL does not support node<v14. If this affects you you can use `npkill@0.8.3`

📋 Usage
========

$ npx npkill
# or just npkill if installed globally

By default, npkill will scan for node\_modules starting at the path where `npkill` command is executed.

Move between the listed folders with ↓ ↑, and use Space or Del to delete the selected folder. You can also use j and k to move between the results.

You can open the directory where the selected result is placed by pressing o.

To exit, Q or Ctrl + c if you're brave.

**Important!** Some applications installed on the system need their node\_modules directory to work and deleting them may break them. NPKILL will highlight them by displaying a ⚠️ to be careful.

Multi-Select Mode
-----------------

This mode allows you to select and delete multiple folders at once, making it more efficient when cleaning up many directories.

### Entering Multi-Select Mode

Press T to toggle multi-select mode. When active, you'll see a selection counter and additional instructions at the top of the results.

### Controls

-   **Space**: Toggle selection of the current folder.
-   **V**: Start/end range selection mode.
-   **A**: Toggle select/unselect all folders.
-   **Enter**: Delete all selected folders.
-   **T**: Unselect all and back to normal mode.

### Range Selection

After pressing V to enter range selection mode:

-   Move the cursor with arrow keys, j/k, Home/End, or page up/down
-   All folders between the starting position and current cursor position will be selected/deselected
-   Press V again to exit range selection mode

Options
-------

ARGUMENT

DESCRIPTION

\-c, --bg-color

Change row highlight color. _(Available: **blue**, cyan, magenta, white, red and yellow)_

\-d, --directory

Set the directory from which to begin searching. By default, starting-point is .

\-D, --delete-all

Automatically delete all node\_modules folders that are found. Suggested to be used together with `-x`.

\-e, --hide-errors

Hide errors if any

\-E, --exclude

Exclude directories from search (directory list must be inside double quotes "", each directory separated by ',' ) Example: "ignore1, ignore2"

\-f, --full

Start searching from the home of the user (example: "/home/user" in linux)

\--size-unit

Set the unit for displaying folder sizes. _(Available: **auto**, mb, gb)_. With auto, sizes < 1024MB are shown in MB (rounded), larger sizes in GB (with decimals).

\-h, --help, ?

Show this help page and exit

\-nu, --no-check-update

Don't check for updates on startup

\-s, --sort

Sort results by: `size`, `path` or `last-mod`

\-t, --target

Specify the name of the directories you want to search for (by default, it's 'node\_modules'). You can define multiple targets separating with comma. Ej. `-t node_modules,.cache,`.

\-x, --exclude-hidden-directories

Exclude hidden directories ("dot" directories) from search.

\--dry-run

It does not delete anything (will simulate it with a random delay).

\--json

Output results in JSON format at the end of the scan. Useful for automation and scripting.

\--json-stream

Output results in streaming JSON format (one JSON object per line as results are found). Useful for real-time processing.

\-v, --version

Show npkill version

**Warning:** _In future versions some commands may change_

Examples
--------

-   Search **node\_modules** directories in your _projects_ directory:

npkill -d ~/projects

# other alternative:
cd ~/projects
npkill

-   List directories named "dist" and show errors if any occur:

npkill --target dist -e

-   Displays the magenta color cursor... because I like magenta!

npkill --bg-color magenta

-   List **vendor** directories in your _projects_ directory, sort by size, and show size in gb:

npkill -d '~/more projects' --size-unit gb --sort size --target vendor

-   List **node\_modules** in your _projects_ directory, excluding the ones in _progress_ and _ignore-this_ directories:

npkill -d 'projects' --exclude "progress, ignore-this"

-   Automatically delete all node\_modules that have sneaked into your backups:

npkill -d ~/backups/ --delete-all

-   Get results in JSON format for automation or further processing:

npkill --json \> results.json

-   Stream results in real-time as JSON (useful for monitoring or piping to other tools):

npkill --json-stream | jq '.'

-   Save only successful results to a file, ignoring errors:

npkill --json-stream 2>/dev/null | jq -s '.' \> clean-results.json

JSON Output
-----------

Npkill supports JSON output formats for automation and integration with other tools:

-   **`--json`**: Output all results as a single JSON object at the end of the scan
-   **`--json-stream`**: Output each result as a separate JSON object in real-time

For detailed documentation, examples, and TypeScript interfaces, see JSON Output Documentation.

**Quick Examples:**

# Get all results as JSON
npkill --json \> results.json

# Process results in real-time
npkill --json-stream | jq '.result.path'

# Find directories larger than 100MB
npkill --json | jq '.results\[\] | select(.size > 104857600)'

📟 Set Up Locally
=================

# -- First, clone the repository
git clone https://github.com/voidcosmos/npkill.git

# -- Navigate to the dir
cd npkill

# -- Install dependencies
npm install

# -- And run!
npm run start

# -- If you want to run it with some parameter, you will have to add "--" as in the following example:
npm run start -- -f -e

📑 API
======

The api allows you to interact with npkill from node to create your own implementations in your scripts (automations, for example).

You can check the basic API here or on the web (comming soon).

🔮 Roadmap
==========

-   Release 0.1.0 !
-   Improve code
    -   Improve performance
    -   Improve performance even more!
-   Sort results by size and path
-   Allow the search for other types of directories (targets)
-   Reduce dependencies to be a more minimalist module
-   Allow to filter by directories that have not been used in a period of time
-   Create option for displaying directories in tree format
-   Add some menus
-   Add log service
-   Periodic and automatic cleaning (?)

🐛 Known bugs 🐛
================

-   Sometimes, CLI is blocked while folder is deleting.
-   Some terminals that do not use TTY (like git bash in windows) do not work.
-   Sorting, especially by routes, can slow down the terminal when there are many results at the same time.
-   Sometimes, size calculations are higher than they should be.
-   (SOLVED) Performance issues when searching from high level directories (like / in linux).
-   (SOLVED) Sometimes text collapses when updating the cli.
-   (SOLVED) Analyzing the size of the directories takes longer than it should.

> If you find any bugs, don't hesitate and open an issue :)

💞 Contributing
===============

If you want to contribute check the CONTRIBUTING.md

☕ Buy us a coffee
=================

We have developed npkill in our free time, because we are passionate about the programming sector. Tomorrow we would like to dedicate ourselves to this, but first, we have a long way to go.

We will continue to do things anyway, but donations are one of the many ways to support what we do.

### Thanks!!

A huge thank you to our backers ❤️
----------------------------------

* * *

### Crypto alternative

-   btc: 1ML2DihUoFTqhoQnrWy4WLxKbVYkUXpMAX
-   bch: 1HVpaicQL5jWKkbChgPf6cvkH8nyktVnVk
-   eth: 0x7668e86c8bdb52034606db5aa0d2d4d73a0d4259

📜 License
==========

MIT © Nya García Gallardo and Juan Torres Gómez

🐱🐤

* * *
