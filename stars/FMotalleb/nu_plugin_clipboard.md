---
project: nu_plugin_clipboard
stars: 52
description: A nushell plugin to copy text into clipboard or get text from it. supports json<->object/table conversion out of box
url: https://github.com/FMotalleb/nu_plugin_clipboard
---

📋 nu\_plugin\_clipboard
========================

A nushell plugin for interacting with the clipboard, allowing you to copy/paste text, objects, and tables.

✨ Features
----------

-   **`clipboard copy`**: Copies input text to the clipboard.
    
    -   **Daemon Behavior:** Since version **0.100.1**, the daemon is always enabled on Linux. To disable it, set:
        
        $env.config.plugins.clipboard.NO\_DAEMON = true
        
    -   To make this setting permanent, add it to your `config env`. (I do not recommend changing this unless needed, please create an issue)
-   **`clipboard paste`**: Retrieves the current clipboard content.
    

📌 Usage Examples
-----------------

### Copying a string (supports only strings for now)

echo "test value" | clipboard copy 

### Using clipboard content

clipboard paste | echo $in

### Copying tables and objects

-   Tables and objects are internally converted to **JSON**.
-   When pasting, `clipboard paste` tries to parse JSON into a table or object.
-   If parsing fails, the content is returned as a string.

$env | clipboard copy
clipboard paste

ps | clipboard copy
clipboard paste

🔧 Installation
---------------

### 🚀 Recommended: Using nupm

This method automatically handles dependencies and features:

git clone https://github.com/FMotalleb/nu\_plugin\_clipboard.git
nupm install --path nu\_plugin\_clipboard -f

### ⚙️ Supported Features

-   **`use-wayland`**: Prioritizes the Wayland API, but falls back to X11 if needed.
-   **`enforce-daemon`**: _(Deprecated)_ Now always enabled on Linux. Disable with:
    
    $env.config.plugins.clipboard.NO\_DAEMON = true
    

### 🛠️ Manual Compilation

git clone https://github.com/FMotalleb/nu\_plugin\_clipboard.git
cd nu\_plugin\_clipboard
cargo build -r
plugin add target/release/nu\_plugin\_clipboard

### 📦 Install via Cargo (using git)

cargo install --git https://github.com/FMotalleb/nu\_plugin\_clipboard.git
plugin add ~/.cargo/bin/nu\_plugin\_clipboard

### 📦 Install via Cargo (crates.io) _Not Recommended_

-   Since I live in Iran and crates.io won't let me update my packages like a normal person, most of the time crates.io is outdated.

cargo install nu\_plugin\_clipboard
plugin add ~/.cargo/bin/nu\_plugin\_clipboard
