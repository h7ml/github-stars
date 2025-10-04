---
project: CCometixLine
stars: 616
description: Claude Code statusline tool written in Rust
url: https://github.com/Haleclipse/CCometixLine
---

CCometixLine
============

English | 中文

A high-performance Claude Code statusline tool written in Rust with Git integration, usage tracking, interactive TUI configuration, and Claude Code enhancement utilities.

Screenshots
-----------

The statusline shows: Model | Directory | Git Branch Status | Context Window Information

Features
--------

### Core Functionality

-   **Git integration** with branch, status, and tracking info
-   **Model display** with simplified Claude model names
-   **Usage tracking** based on transcript analysis
-   **Directory display** showing current workspace
-   **Minimal design** using Nerd Font icons

### Interactive TUI Features

-   **Interactive main menu** when executed without input
-   **TUI configuration interface** with real-time preview
-   **Theme system** with multiple built-in presets
-   **Segment customization** with granular control
-   **Configuration management** (init, check, edit)

### Claude Code Enhancement

-   **Context warning disabler** - Remove annoying "Context low" messages
-   **Verbose mode enabler** - Enhanced output detail
-   **Robust patcher** - Survives Claude Code version updates
-   **Automatic backups** - Safe modification with easy recovery

Installation
------------

### Quick Install (Recommended)

Install via npm (works on all platforms):

# Install globally
npm install -g @cometix/ccline

# Or using yarn
yarn global add @cometix/ccline

# Or using pnpm
pnpm add -g @cometix/ccline

Use npm mirror for faster download:

npm install -g @cometix/ccline --registry https://registry.npmmirror.com

After installation:

-   ✅ Global command `ccline` is available everywhere
-   ⚙️ Follow the configuration steps below to integrate with Claude Code
-   🎨 Run `ccline -c` to open configuration panel for theme selection

### Claude Code Configuration

Add to your Claude Code `settings.json`:

**Linux/macOS:**

{
  "statusLine": {
    "type": "command", 
    "command": "~/.claude/ccline/ccline",
    "padding": 0
  }
}

**Windows:**

{
  "statusLine": {
    "type": "command", 
    "command": "%USERPROFILE%\\\\.claude\\\\ccline\\\\ccline.exe",
    "padding": 0
  }
}

**Fallback (npm installation):**

{
  "statusLine": {
    "type": "command", 
    "command": "ccline",
    "padding": 0
  }
}

_Use this if npm global installation is available in PATH_

### Update

npm update -g @cometix/ccline

Manual Installation (Click to expand)

Alternatively, download from Releases:

#### Linux

#### Option 1: Dynamic Binary (Recommended)

mkdir -p ~/.claude/ccline
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-linux-x64.tar.gz
tar -xzf ccline-linux-x64.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

_Requires: Ubuntu 22.04+, CentOS 9+, Debian 11+, RHEL 9+ (glibc 2.35+)_

#### Option 2: Static Binary (Universal Compatibility)

mkdir -p ~/.claude/ccline
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-linux-x64-static.tar.gz
tar -xzf ccline-linux-x64-static.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

_Works on any Linux distribution (static, no dependencies)_

#### macOS (Intel)

mkdir -p ~/.claude/ccline
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-macos-x64.tar.gz
tar -xzf ccline-macos-x64.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

#### macOS (Apple Silicon)

mkdir -p ~/.claude/ccline  
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-macos-arm64.tar.gz
tar -xzf ccline-macos-arm64.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

#### Windows

# Create directory and download
New-Item \-ItemType Directory \-Force \-Path "$env:USERPROFILE\\.claude\\ccline"
Invoke-WebRequest \-Uri "https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-windows-x64.zip" \-OutFile "ccline-windows-x64.zip"
Expand-Archive \-Path "ccline-windows-x64.zip" \-DestinationPath "."
Move-Item "ccline.exe" "$env:USERPROFILE\\.claude\\ccline\\"

### Build from Source

git clone https://github.com/Haleclipse/CCometixLine.git
cd CCometixLine
cargo build --release

# Linux/macOS
mkdir -p ~/.claude/ccline
cp target/release/ccometixline ~/.claude/ccline/ccline
chmod +x ~/.claude/ccline/ccline

# Windows (PowerShell)
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\\.claude\\ccline"
copy target\\release\\ccometixline.exe "$env:USERPROFILE\\.claude\\ccline\\ccline.exe"

Usage
-----

### Configuration Management

# Initialize configuration file
ccline --init

# Check configuration validity  
ccline --check

# Print current configuration
ccline --print

# Enter TUI configuration mode
ccline --config

### Theme Override

# Temporarily use specific theme (overrides config file)
ccline --theme cometix
ccline --theme minimal
ccline --theme gruvbox
ccline --theme nord
ccline --theme powerline-dark

# Or use custom theme files from ~/.claude/ccline/themes/
ccline --theme my-custom-theme

### Claude Code Enhancement

# Disable context warnings and enable verbose mode
ccline --patch /path/to/claude-code/cli.js

# Example for common installation
ccline --patch ~/.local/share/fnm/node-versions/v24.4.1/installation/lib/node\_modules/@anthropic-ai/claude-code/cli.js

Default Segments
----------------

Displays: `Directory | Git Branch Status | Model | Context Window`

### Git Status Indicators

-   Branch name with Nerd Font icon
-   Status: `✓` Clean, `●` Dirty, `⚠` Conflicts
-   Remote tracking: `↑n` Ahead, `↓n` Behind

### Model Display

Shows simplified Claude model names:

-   `claude-3-5-sonnet` → `Sonnet 3.5`
-   `claude-4-sonnet` → `Sonnet 4`

### Context Window Display

Token usage percentage based on transcript analysis with context limit tracking.

Configuration
-------------

CCometixLine supports full configuration via TOML files and interactive TUI:

-   **Configuration file**: `~/.claude/ccline/config.toml`
-   **Interactive TUI**: `ccline --config` for real-time editing with preview
-   **Theme files**: `~/.claude/ccline/themes/*.toml` for custom themes
-   **Automatic initialization**: `ccline --init` creates default configuration

### Available Segments

All segments are configurable with:

-   Enable/disable toggle
-   Custom separators and icons
-   Color customization
-   Format options

Supported segments: Directory, Git, Model, Usage, Time, Cost, OutputStyle

Requirements
------------

-   **Git**: Version 1.5+ (Git 2.22+ recommended for better branch detection)
-   **Terminal**: Must support Nerd Fonts for proper icon display
    -   Install a Nerd Font (e.g., FiraCode Nerd Font, JetBrains Mono Nerd Font)
    -   Configure your terminal to use the Nerd Font
-   **Claude Code**: For statusline integration

Development
-----------

# Build development version
cargo build

# Run tests
cargo test

# Build optimized release
cargo build --release

Roadmap
-------

-   TOML configuration file support
-   TUI configuration interface
-   Custom themes
-   Interactive main menu
-   Claude Code enhancement tools

Contributing
------------

Contributions are welcome! Please feel free to submit issues or pull requests.

Related Projects
----------------

-   tweakcc - Command-line tool to customize your Claude Code themes, thinking verbs, and more.

License
-------

This project is licensed under the MIT License.

Star History
------------
