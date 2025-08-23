---
project: CCometixLine
stars: 353
description: Claude Code statusline tool written in Rust
url: https://github.com/Haleclipse/CCometixLine
---

CCometixLine
============

English | 中文

A high-performance Claude Code statusline tool written in Rust with Git integration and real-time usage tracking.

Screenshots
-----------

The statusline shows: Model | Directory | Git Branch Status | Context Window Information

Features
--------

-   **High performance** with Rust native speed
-   **Git integration** with branch, status, and tracking info
-   **Model display** with simplified Claude model names
-   **Usage tracking** based on transcript analysis
-   **Directory display** showing current workspace
-   **Minimal design** using Nerd Font icons
-   **Simple configuration** via command line options

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
-   ✅ Automatically configured for Claude Code at `~/.claude/ccline/ccline`
-   ✅ Ready to use immediately!

### Update

npm update -g @cometix/ccline

### Manual Installation

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

### macOS (Intel)

mkdir -p ~/.claude/ccline
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-macos-x64.tar.gz
tar -xzf ccline-macos-x64.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

### macOS (Apple Silicon)

mkdir -p ~/.claude/ccline  
wget https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-macos-arm64.tar.gz
tar -xzf ccline-macos-arm64.tar.gz
cp ccline ~/.claude/ccline/
chmod +x ~/.claude/ccline/ccline

### Windows

# Create directory and download
New-Item \-ItemType Directory \-Force \-Path "$env:USERPROFILE\\.claude\\ccline"
Invoke-WebRequest \-Uri "https://github.com/Haleclipse/CCometixLine/releases/latest/download/ccline-windows-x64.zip" \-OutFile "ccline-windows-x64.zip"
Expand-Archive \-Path "ccline-windows-x64.zip" \-DestinationPath "."
Move-Item "ccline.exe" "$env:USERPROFILE\\.claude\\ccline\\"

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

# Basic usage (displays all enabled segments)
ccline

# Show help
ccline --help

# Print default configuration  
ccline --print-config

# TUI configuration mode (planned)
ccline --configure

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

Configuration support is planned for future releases. Currently uses sensible defaults for all segments.

Performance
-----------

-   **Startup time**: < 50ms (vs ~200ms for TypeScript equivalents)
-   **Memory usage**: < 10MB (vs ~25MB for Node.js tools)
-   **Binary size**: ~2MB optimized release build

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
-   Plugin system
-   Cross-platform binaries

Contributing
------------

Contributions are welcome! Please feel free to submit issues or pull requests.

License
-------

This project is licensed under the MIT License.

Star History
------------
