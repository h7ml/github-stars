---
project: nu_plugin_clipboard
stars: 47
description: A nushell plugin to copy text into clipboard or get text from it.
url: https://github.com/FMotalleb/nu_plugin_clipboard
---

nu\_plugin\_clipboard
=====================

A nushell plugin to copy text into clipboard or get text from it.

-   `clipboard copy`: copy a text that's given as input
    -   `--{disable or enable}-daemon` (`-d`): spawn a daemon that manages clipboard (if copy is not working try using this flag)
    -   Since version 0.100.1> this method is now always enabled in linux environments, to disable this behavior set `$env.config.plugins.clipboard.NO_DAEMON` to `true`, to make it permanent add `$env.config.plugins.clipboard.NO_DAEMON = true` to `config env`
-   `clipboard paste`: returns current text value of clipboard

Examples
--------

-   to copy a string (ONLY string for now)

~\> echo "test value" | clipboard copy 

-   to use a string that is in clipboard

~\> clipboard paste | echo $in

-   in order to copy tables please convert them to text format like JSON, YAML, ...
    -   you are able to paste them as tables again using `clipboard paste | from json`

~\> $env | to json | clipboard copy
~\> clipboard paste | from json

~\> ps | to json | clipboard copy
~\> clipboard paste | from json

Installing
----------

-   using nupm **Recommended!**
    -   this way you don't need to mess with features and it will install required features

git clone https://github.com/FMotalleb/nu\_plugin\_clipboard.git
nupm install --path nu\_plugin\_clipboard -f

-   supported features:
    -   **use-wayland**: will prioritize wayland api but will falls back to X11 protocol on error
    -   **enforce-daemon**: Deprecation notice: this method is now always enabled in linux environments, to disable this behavior set `$env.config.plugins.clipboard.NO_DAEMON` to `true`, to make it permanent add `$env.config.plugins.clipboard.NO_DAEMON = true` to `config env`
-   or compile manually

git clone https://github.com/FMotalleb/nu\_plugin\_clipboard.git
cd nu\_plugin\_clipboard
cargo build -r
plugin add target/release/nu\_plugin\_clipboard

-   or using cargo

cargo install nu\_plugin\_clipboard
plugin add ~/.cargo/bin/nu\_plugin\_clipboard
