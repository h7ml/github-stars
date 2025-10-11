---
project: vibetunnel
stars: 2353
description: Turn any browser into your terminal & command your agents on the go.
url: https://github.com/amantus-ai/vibetunnel
---

**Turn any browser into your Mac terminal.**  
VibeTunnel proxies your terminals right into the browser, so you can vibe-code anywhere.

Documentation • Releases • Discord • Twitter

Table of Contents
-----------------

-   Why VibeTunnel?
-   Installation Options
-   Quick Start
-   Features
-   Architecture
-   Remote Access Options
-   Git Follow Mode
-   Terminal Title Management
-   Authentication
-   npm Package
-   Building from Source
-   Development
-   Poltergeist Integration
-   Documentation
-   macOS Permissions
-   Contributing
-   Support VibeTunnel
-   Credits
-   License

Why VibeTunnel?
---------------

Ever wanted to check on your AI agents while you're away? Need to monitor that long-running build from your phone? Want to share a terminal session with a colleague without complex SSH setups? VibeTunnel makes it happen with zero friction.

Installation Options
--------------------

### macOS App (Recommended for Mac users)

The native macOS app provides the best experience with menu bar integration and automatic updates.

### npm Package (Linux & Headless Systems)

For Linux servers, Docker containers, or headless macOS systems, install via npm:

npm install -g vibetunnel

This gives you the full VibeTunnel server with web UI, just without the macOS menu bar app. See the npm Package section for detailed usage.

Quick Start
-----------

### Requirements

**macOS App**: Requires an Apple Silicon Mac (M1+). Intel Macs are not supported for the native app.

**npm Package**: Works on any system with Node.js 20+, including Intel Macs and Linux. Windows is not yet supported (#252).

### 1\. Download & Install

#### Option 1: Direct Download

Download VibeTunnel and drag it to your Applications folder.

#### Option 2: Homebrew

brew install --cask vibetunnel

### 2\. Launch VibeTunnel

VibeTunnel lives in your menu bar. Click the icon to start the server.

### 3\. Use the `vt` Command

The `vt` command is a smart wrapper that forwards your terminal sessions through VibeTunnel:

**How it works**:

-   `vt` is a bash script that internally calls `vibetunnel fwd` to forward terminal output
-   It provides additional features like shell alias resolution and session title management
-   Available from both the Mac app and npm package installations

**Installation sources**:

-   **macOS App**: Creates `/usr/local/bin/vt` symlink during installation
-   **npm Package**: Installs `vt` globally, with intelligent Mac app detection

**Smart detection**: When you run `vt` from the npm package, it:

1.  Checks if the Mac app is installed at `/Applications/VibeTunnel.app`
2.  If found, forwards to the Mac app's `vt` for the best experience
3.  If not found, uses the npm-installed `vibetunnel fwd`
4.  This ensures `vt` always uses the best available implementation

# Run any command in the browser
vt pnpm run dev
vt npm test
vt python script.py

# Monitor AI agents with automatic activity tracking
vt claude --dangerously-skip-permissions
vt --title-mode dynamic claude    # See real-time Claude status

# Use your shell aliases
vt gs              # Your 'git status' alias works!
vt claude-danger   # Custom aliases are resolved

# Open an interactive shell
vt --shell         # or vt -i

# Git follow mode
vt follow          # Follow current branch
vt follow main     # Switch to main and follow
vt unfollow       # Stop following

# For more examples and options, see "The vt Forwarding Command" section below

### Git Repository Scanning on First Session

When opening a new session for the first time, VibeTunnel's working directory scanner will look for Git repositories. By default, this scans your home directory, which may trigger macOS permission prompts for accessing protected folders (like Desktop, Documents, Downloads, iCloud Drive, or external volumes).

To avoid these prompts:

-   **Option 1**: Navigate to your actual projects directory before opening a session
-   **Option 2**: Accept the one-time permission prompts (they won't appear again)

This only happens on the first session when the scanner discovers your Git repositories. For more details about macOS privacy-protected folders, see this explanation.

### 4\. Open Your Dashboard

Visit http://localhost:4020 to see all your terminal sessions.

Features
--------

-   **🌐 Browser-Based Access** - Control your Mac terminal from any device with a web browser
-   **🚀 Zero Configuration** - No SSH keys, no port forwarding, no complexity
-   **🤖 AI Agent Friendly** - Perfect for monitoring Claude Code, ChatGPT, or any terminal-based AI tools
-   **📊 Dynamic Terminal Titles** - Real-time activity tracking shows what's happening in each session
-   **🔄 Git Follow Mode** - Terminal automatically follows your IDE's branch switching
-   **⌨️ Smart Keyboard Handling** - Intelligent shortcut routing with toggleable capture modes. When capture is active, use Cmd+1...9/0 (Mac) or Ctrl+1...9/0 (Linux) to quickly switch between sessions
-   **🔒 Secure by Design** - Multiple authentication modes, localhost-only mode, or secure tunneling via Tailscale/ngrok
-   **📱 Mobile Ready** - Native iOS app and responsive web interface for phones and tablets
-   **🎬 Session Recording** - All sessions recorded in asciinema format for later playback
-   **⚡ High Performance** - Optimized Node.js server with minimal resource usage
-   **🍎 Apple Silicon Native** - Optimized for Apple Silicon (M1+) Macs with ARM64-only binaries
-   **🐚 Shell Alias Support** - Your custom aliases and shell functions work automatically

> **Note**: The iOS app is still work in progress and not recommended for production use yet.

Architecture
------------

VibeTunnel consists of three main components:

1.  **macOS Menu Bar App** - Native Swift application that manages the server lifecycle
2.  **Node.js Server** - High-performance TypeScript server handling terminal sessions
3.  **Web Frontend** - Modern web interface using Lit components and xterm.js

The server runs as a standalone Node.js executable with embedded modules, providing excellent performance and minimal resource usage.

Remote Access Options
---------------------

### Option 1: Tailscale (Recommended)

Tailscale creates a secure peer-to-peer VPN network between your devices. It's the most secure option as traffic stays within your private network without exposing VibeTunnel to the public internet.

**How it works**: Tailscale creates an encrypted WireGuard tunnel between your devices, allowing them to communicate as if they were on the same local network, regardless of their physical location.

**Setup Guide**:

1.  Install Tailscale on your Mac: Download from Mac App Store or Direct Download
2.  Install Tailscale on your remote device:
    -   **iOS**: Download from App Store
    -   **Android**: Download from Google Play
    -   **Other platforms**: All Downloads
3.  Sign in to both devices with the same account
4.  Find your Mac's Tailscale hostname in the Tailscale menu bar app (e.g., `my-mac.tailnet-name.ts.net`)
5.  Access VibeTunnel at `http://[your-tailscale-hostname]:4020`

**Benefits**:

-   End-to-end encrypted traffic
-   No public internet exposure
-   Works behind NAT and firewalls
-   Zero configuration after initial setup

### Option 2: ngrok

ngrok creates secure tunnels to your localhost, making VibeTunnel accessible via a public URL. Perfect for quick sharing or temporary access.

**How it works**: ngrok establishes a secure tunnel from a public endpoint to your local VibeTunnel server, handling SSL/TLS encryption and providing a unique URL for access.

**Setup Guide**:

1.  Create a free ngrok account: Sign up for ngrok
2.  Copy your auth token from the ngrok dashboard
3.  Add the token in VibeTunnel settings (Settings → Remote Access → ngrok)
4.  Enable ngrok tunneling in VibeTunnel
5.  Share the generated `https://[random].ngrok-free.app` URL

**Benefits**:

-   Public HTTPS URL with SSL certificate
-   No firewall configuration needed
-   Built-in request inspection and replay
-   Custom domains available (paid plans)

**Note**: Free ngrok URLs change each time you restart the tunnel. You can claim one free static domain per user, or upgrade to a paid plan for multiple domains.

### Option 3: Local Network

1.  Configure authentication (see Authentication section)
2.  Switch to "Network" mode
3.  Access via `http://[your-mac-ip]:4020`

### Option 4: Cloudflare Quick Tunnel

1.  Install cloudflared
2.  Run `cloudflared tunnel --url http://localhost:4020`
3.  Access via the generated `*.trycloudflare.com` URL

Git Follow Mode
---------------

Git Follow Mode keeps your main repository checkout synchronized with the branch you're working on in a Git worktree. This allows agents to work in worktrees while your IDE, server, and other tools stay open on the main repository - they'll automatically update when the worktree switches branches.

### What is Follow Mode?

Follow mode creates a seamless workflow for agent-assisted development:

-   Agents work in worktrees → Main repository automatically follows their branch switches
-   Keep Xcode/IDE open → It updates automatically without reopening projects
-   Server stays running → No need to restart servers in different folders
-   Zero manual intervention → Main repo stays in sync with active development

### Quick Start

# From a worktree - enable follow mode for this worktree
vt follow

# From main repo - follow current branch's worktree (if it exists)
vt follow

# From main repo - follow a specific branch's worktree
vt follow feature/new-api

# From main repo - follow a worktree by path
vt follow ~/project-feature

# Disable follow mode
vt unfollow

### How It Works

1.  **Git Hooks**: VibeTunnel installs lightweight Git hooks (post-commit, post-checkout) in worktrees that detect branch changes
2.  **Main Repo Sync**: When you switch branches in a worktree, the main repository automatically checks out to the same branch
3.  **Smart Handling**: If the main repo has uncommitted changes, follow mode pauses to prevent data loss
4.  **Development Continuity**: Your IDE, servers, and tools running on the main repo seamlessly follow your active work
5.  **Clean Uninstall**: When you run `vt unfollow`, Git hooks are automatically removed and any original hooks are restored

### Common Workflows

#### Agent Development with Worktrees

# Create a worktree for agent development
git worktree add ../project-agent feature/new-feature

# Enable follow mode on the main repo
cd ../project && vt follow

# Agent works in the worktree while you stay in main repo
# When agent switches branches in worktree, your main repo follows!
# Your Xcode/IDE and servers stay running without interruption

### Technical Details

Follow mode stores the worktree path in your main repository's Git config:

# Check which worktree is being followed
git config vibetunnel.followWorktree

# Follow mode is active when this returns a path
# The config is managed by vt commands - manual editing not recommended

For more advanced Git worktree workflows, see our detailed worktree documentation.

Terminal Title Management
-------------------------

VibeTunnel provides intelligent terminal title management to help you track what's happening in each session:

### Title Modes

-   **Dynamic Mode** (default for web UI): Shows working directory, command, and real-time activity
    
    -   Generic activity: `~/projects — npm — •`
    -   Claude status: `~/projects — claude — ✻ Crafting (45s, ↑2.1k)`
-   **Static Mode**: Shows working directory and command
    
    -   Example: `~/projects/app — npm run dev`
-   **Filter Mode**: Blocks all title changes from applications
    
    -   Useful when you have your own terminal management system
-   **None Mode**: No title management - applications control their own titles
    

### Activity Detection

Dynamic mode includes real-time activity detection:

-   Shows `•` when there's terminal output within 5 seconds
-   Claude commands show specific status (Crafting, Transitioning, etc.)
-   Extensible system for future app-specific detectors

Authentication
--------------

VibeTunnel provides multiple authentication modes to secure your terminal sessions:

### Authentication Modes

#### 1\. System Authentication (Default)

Uses your operating system's native authentication:

-   **macOS**: Authenticates against local user accounts
-   **Linux**: Uses PAM (Pluggable Authentication Modules)
-   Login with your system username and password

#### 2\. Environment Variable Authentication

Simple authentication for deployments:

export VIBETUNNEL\_USERNAME=admin
export VIBETUNNEL\_PASSWORD=your-secure-password
npm run start

#### 3\. SSH Key Authentication

Use Ed25519 SSH keys from `~/.ssh/authorized_keys`:

# Enable SSH key authentication
npm run start -- --enable-ssh-keys

# Make SSH keys mandatory (disable password auth)
npm run start -- --enable-ssh-keys --disallow-user-password

#### 4\. No Authentication

For trusted environments only:

npm run start -- --no-auth

#### 5\. Local Bypass (Development Only)

Allow localhost connections to bypass authentication:

# Basic local bypass (DEVELOPMENT ONLY - NOT FOR PRODUCTION)
npm run start -- --allow-local-bypass

# With token for additional security (minimum for production)
npm run start -- --allow-local-bypass --local-auth-token mytoken

**Security Note**: Local bypass uses `req.socket.remoteAddress` which cannot be spoofed remotely due to TCP's three-way handshake. The implementation also rejects requests with proxy headers (`X-Forwarded-For`, etc.) to prevent header injection attacks. However:

-   **Development only**: Basic bypass without token should never be used in production
-   **Local processes**: Any process on the same machine can access the API
-   **Always use tokens**: In production, always require `--local-auth-token`
-   **Consider alternatives**: For production, use proper authentication instead of local bypass

### macOS App Authentication

The macOS menu bar app supports these authentication modes:

-   **No Authentication**: For trusted environments only
-   **System Authentication**: Uses your macOS user account credentials
-   **SSH Key Authentication**: Uses Ed25519 SSH keys from `~/.ssh/authorized_keys`
-   Configure via Settings → Security when in "Network" mode

### Security Best Practices

1.  **Always use authentication** when binding to network interfaces (`--bind 0.0.0.0`)
2.  **Use HTTPS** in production with a reverse proxy (nginx, Caddy)
3.  **Rotate credentials** regularly
4.  **Consider SSH keys** for stronger security
5.  **Never use local bypass without tokens** in production environments
6.  **Monitor access logs** for suspicious authentication patterns
7.  **Default to secure** - explicitly enable less secure options only when needed

### SSH Key Authentication Troubleshooting

If SSH key generation fails with crypto errors, see the detailed troubleshooting guide for solutions.

npm Package
-----------

The VibeTunnel npm package provides the full server functionality for Linux, Docker, CI/CD environments, and headless macOS systems.

### Installation

# Install globally via npm
npm install -g vibetunnel

# Or with yarn
yarn global add vibetunnel

# Or with pnpm
pnpm add -g vibetunnel

**Requirements**: Node.js 20.0.0 or higher

### Running the VibeTunnel Server

#### Basic Usage

# Start with default settings (localhost:4020)
vibetunnel

# Bind to all network interfaces
vibetunnel --bind 0.0.0.0

# Use a custom port
vibetunnel --port 8080

# With authentication
VIBETUNNEL\_USERNAME=admin VIBETUNNEL\_PASSWORD=secure vibetunnel --bind 0.0.0.0

# Enable debug logging
VIBETUNNEL\_DEBUG=1 vibetunnel

# Run without authentication (trusted networks only!)
vibetunnel --no-auth

#### Using the `vt` Command

The `vt` command wrapper makes it easy to forward terminal sessions:

# Monitor AI agents with automatic activity tracking
vt claude
vt claude --dangerously-skip-permissions
vt --title-mode dynamic claude    # See real-time Claude status

# Run any command and see it in the browser
vt npm test
vt python script.py
vt cargo build --release

# Open an interactive shell
vt --shell
vt -i  # short form

# Control terminal titles
vt --title-mode static npm run dev    # Shows path and command
vt --title-mode dynamic python app.py  # Shows path, command, and activity
vt --title-mode filter vim            # Blocks vim from changing title

# Control output verbosity
vt -q npm test         # Quiet mode - no console output
vt -v npm run dev      # Verbose mode - show more information
vt -vv cargo build     # Extra verbose - all except debug
vt -vvv python app.py  # Debug mode - show everything

# Shell aliases work automatically!
vt claude-danger  # Your custom alias for claude --dangerously-skip-permissions

# Update session title (inside a VibeTunnel session)
vt title "My Project - Testing"

### The `vt` Forwarding Command

The `vt` command is VibeTunnel's terminal forwarding wrapper that allows you to run any command while making its output visible in the browser. Under the hood, `vt` is a convenient shortcut for `vibetunnel fwd` - it's a bash script that calls the full command with proper path resolution and additional features like shell alias support. The `vt` wrapper acts as a transparent proxy between your terminal and the command, forwarding all input and output through VibeTunnel's infrastructure.

#### Command Syntax

vt \[options\] <command\> \[args...\]

#### Options

**Terminal Title Control:**

-   `--title-mode <mode>` - Control how terminal titles are managed:
    -   `none` - No title management, apps control their own titles (default)
    -   `filter` - Block all title changes from applications
    -   `static` - Show working directory and command in title
    -   `dynamic` - Show directory, command, and live activity status (auto-enabled for Claude)

**Verbosity Control:**

-   `-q, --quiet` - Quiet mode, no console output (logs to file only)
-   `-v, --verbose` - Verbose mode, show errors, warnings, and info messages
-   `-vv` - Extra verbose, show all messages except debug
-   `-vvv` - Debug mode, show all messages including debug

**Other Options:**

-   `--shell, -i` - Launch your current shell interactively
-   `--no-shell-wrap, -S` - Execute command directly without shell interpretation
-   `--log-file <path>` - Override default log file location (defaults to `~/.vibetunnel/log.txt`)
-   `--help, -h` - Show help message with all options

#### Verbosity Levels

VibeTunnel uses a hierarchical logging system where each level includes all messages from more severe levels:

Level

Flag

Environment Variable

Shows

SILENT

`-q`

`VIBETUNNEL_LOG_LEVEL=silent`

No console output (file logging only)

ERROR

(default)

`VIBETUNNEL_LOG_LEVEL=error`

Errors only

WARN

\-

`VIBETUNNEL_LOG_LEVEL=warn`

Errors and warnings

INFO

`-v`

`VIBETUNNEL_LOG_LEVEL=info`

Errors, warnings, and informational messages

VERBOSE

`-vv`

`VIBETUNNEL_LOG_LEVEL=verbose`

All messages except debug

DEBUG

`-vvv`

`VIBETUNNEL_LOG_LEVEL=debug`

Everything including debug traces

**Note:** All logs are always written to `~/.vibetunnel/log.txt` regardless of verbosity settings. The verbosity only controls terminal output.

#### Examples

# Basic command forwarding
vt ls -la                    # List files with VibeTunnel monitoring
vt npm run dev              # Run development server
vt python script.py         # Execute Python script

# With verbosity control
vt -q npm test              # Run tests silently
vt -v npm install           # See detailed installation progress
vt -vvv python debug.py     # Full debug output
vt --log-file debug.log npm run dev  # Write logs to custom file

# Terminal title management
vt --title-mode static npm run dev    # Fixed title showing command
vt --title-mode dynamic claude         # Live activity updates
vt --title-mode filter vim            # Prevent vim from changing title

# Shell handling
vt --shell                  # Open interactive shell
vt -S /usr/bin/python      # Run python directly without shell

#### How It Works

1.  **Command Resolution**: The `vt` wrapper first checks if your command is an alias, shell function, or binary
2.  **Session Creation**: It creates a new VibeTunnel session with a unique ID
3.  **PTY Allocation**: A pseudo-terminal is allocated to preserve terminal features (colors, cursor control, etc.)
4.  **I/O Forwarding**: All input/output is forwarded between your terminal and the browser in real-time
5.  **Process Management**: The wrapper monitors the process and handles signals, exit codes, and cleanup

#### Environment Variables

-   `VIBETUNNEL_LOG_LEVEL` - Set default verbosity level (silent, error, warn, info, verbose, debug)
-   `VIBETUNNEL_TITLE_MODE` - Set default title mode (none, filter, static, dynamic)
-   `VIBETUNNEL_DEBUG` - Legacy debug flag, equivalent to `VIBETUNNEL_LOG_LEVEL=debug`
-   `VIBETUNNEL_CLAUDE_DYNAMIC_TITLE` - Force dynamic title mode for Claude commands

#### Special Features

**Automatic Claude Detection**: When running Claude AI, `vt` automatically enables dynamic title mode to show real-time activity status (thinking, writing, idle).

**Shell Alias Support**: Your shell aliases and functions work transparently through `vt`:

alias gs='git status'
vt gs  # Works as expected

**Session Title Updates**: Inside a VibeTunnel session, use `vt title` to update the session name:

vt title "Building Production Release"

### Mac App Interoperability

The npm package is designed to work seamlessly alongside the Mac app:

#### Smart Command Routing

-   The `vt` command automatically detects if the Mac app is installed
-   If found at `/Applications/VibeTunnel.app`, it defers to the Mac app
-   If not found, it uses the npm-installed server
-   This ensures you always get the best available implementation

#### Installation Behavior

-   If `/usr/local/bin/vt` already exists (from another tool), npm won't overwrite it
-   You'll see a helpful warning with alternatives: `vibetunnel` or `npx vt`
-   The installation always succeeds, even if the `vt` symlink can't be created

#### When to Use Each Version

-   **Mac app only**: Best for macOS users who want menu bar integration
-   **npm only**: Perfect for Linux, Docker, CI/CD, or headless servers
-   **Both installed**: Mac app takes precedence, npm serves as fallback
-   **Development**: npm package useful for testing without affecting Mac app

### Package Contents

The npm package includes:

-   Full VibeTunnel server with web UI
-   CLI tools (`vibetunnel` and `vt` commands)
-   Native PTY support via node-pty
-   Pre-built binaries for common platforms
-   Complete feature parity with macOS app (minus menu bar)

### Building the npm Package

For maintainers who need to build the npm package:

#### Unified Build (Multi-Platform by Default)

# Build with prebuilt binaries for all platforms
# Requires Docker for Linux cross-compilation
npm run build:npm

This creates prebuilt binaries for:

-   macOS (x64, arm64) - Node.js 20, 22, 23, 24
-   Linux (x64, arm64) - Node.js 20, 22, 23, 24

#### Build Options

# Current platform only (faster for development)
node scripts/build-npm.js --current-only

# Specific platform/architecture
node scripts/build-npm.js --platform darwin --arch arm64

# Skip Docker builds
node scripts/build-npm.js --no-docker

#### Publishing

# Test the package locally
npm pack

# Publish to npm
npm publish

Building from Source
--------------------

### Prerequisites

-   macOS 14.0+ (Sonoma) on Apple Silicon (M1+)
-   Xcode 16.0+
-   Node.js 20+ (minimum supported version)

### Build Steps

# Clone the repository
git clone https://github.com/amantus-ai/vibetunnel.git
cd vibetunnel

# Set up code signing (required for macOS/iOS development)
# Create Local.xcconfig files with your Apple Developer Team ID
# Note: These files must be in the same directory as Shared.xcconfig
cat \> mac/VibeTunnel/Local.xcconfig << EOF
// Local Development Configuration
// DO NOT commit this file to version control
DEVELOPMENT\_TEAM = YOUR\_TEAM\_ID
CODE\_SIGN\_STYLE = Automatic
EOF

cat \> ios/VibeTunnel/Local.xcconfig << EOF
// Local Development Configuration  
// DO NOT commit this file to version control
DEVELOPMENT\_TEAM = YOUR\_TEAM\_ID
CODE\_SIGN\_STYLE = Automatic
EOF

# Build the web server
cd web
pnpm install
pnpm run build

# Optional: Build with custom Node.js for smaller binary (46% size reduction)
# export VIBETUNNEL\_USE\_CUSTOM\_NODE=YES
# node build-custom-node.js  # Build optimized Node.js (one-time, ~20 min)
# pnpm run build              # Will use custom Node.js automatically

# Build the macOS app
cd ../mac
./scripts/build.sh --configuration Release

### Custom Node.js Builds

VibeTunnel supports building with a custom Node.js for a 46% smaller executable (61MB vs 107MB):

# Build custom Node.js (one-time, ~20 minutes)
node build-custom-node.js

# Use environment variable for all builds
export VIBETUNNEL\_USE\_CUSTOM\_NODE=YES

# Or use in Xcode Build Settings
# Add User-Defined Setting: VIBETUNNEL\_USE\_CUSTOM\_NODE = YES

See Custom Node Build Flags for detailed optimization information.

Development
-----------

For development setup and contribution guidelines, see CONTRIBUTING.md.

### Key Files

-   **macOS App**: `mac/VibeTunnel/VibeTunnelApp.swift`
-   **Server**: `web/src/server/` (TypeScript/Node.js)
-   **Web UI**: `web/src/client/` (Lit/TypeScript)
-   **iOS App**: `ios/VibeTunnel/`

### Testing & Code Coverage

VibeTunnel has comprehensive test suites with code coverage enabled for all projects:

# Run all tests with coverage
./scripts/test-all-coverage.sh

# macOS tests with coverage (Swift Testing)
cd mac && swift test --enable-code-coverage

# iOS tests with coverage (using xcodebuild)
cd ios && ./scripts/test-with-coverage.sh

# Web tests with coverage (Vitest)
cd web && ./scripts/coverage-report.sh

**Coverage Requirements**:

-   macOS/iOS: 75% minimum (enforced in CI)
-   Web: 80% minimum for lines, functions, branches, and statements

### Development Server & Hot Reload

VibeTunnel includes a development server with automatic rebuilding for faster iteration:

#### Development Mode

cd web
pnpm run dev

**What this provides:**

-   **Automatic Rebuilds**: esbuild watches for file changes and rebuilds bundles instantly
-   **Fast Feedback**: Changes are compiled within seconds of saving
-   **Manual Refresh Required**: Browser needs manual refresh to see changes (no hot module replacement)

**How it works:**

-   esbuild watch mode detects file changes in `src/`
-   Automatically rebuilds JavaScript bundles and CSS
-   Express server serves updated files immediately
-   Visit `http://localhost:4020` and refresh to see changes

#### Testing on External Devices (iPad, iPhone, etc.)

When developing the web interface, you often need to test changes on external devices to debug browser-specific issues. Here's how to do it:

##### Quick Setup

1.  **Run the dev server with network access**:
    
    cd web
    pnpm run dev --port 4021 --bind 0.0.0.0
    
    This binds to all network interfaces, making it accessible from other devices.
    
2.  **Find your Mac's IP address**:
    
    -   System Preferences → Network → Wi-Fi → Details
    -   Or run: `ipconfig getifaddr en0`
3.  **Access from your external device**:
    
    ```
    http://[your-mac-ip]:4021
    ```
    

##### Important Notes

-   **Port conflict**: The Mac app runs on port 4020, so use a different port (e.g., 4021) for development
-   **Same network**: Ensure both devices are on the same Wi-Fi network
-   **Firewall**: macOS may prompt to allow incoming connections - click "Allow"
-   **Auto-rebuild**: Changes to the web code are automatically rebuilt, but you need to manually refresh the browser

##### Pasting on Mobile Devices

When using VibeTunnel on mobile browsers (Safari, Chrome), pasting works differently than on desktop:

**To paste on mobile:**

1.  Press the paste button on the keyboard toolbar
2.  A white input box will appear
3.  Long-press inside the white box to bring up the paste menu
4.  Select "Paste" from the menu
5.  The text will be pasted into your terminal session

**Note**: Due to browser security restrictions on non-HTTPS connections, the paste API is limited on mobile devices. The white input box is a workaround that allows clipboard access through the browser's native paste functionality.

#### Future: Hot Module Replacement

For true hot module replacement without manual refresh, see our Vite migration plan which would provide:

-   Instant updates without page refresh
-   Preserved application state during development
-   Sub-second feedback loops
-   Modern development tooling

#### Mac App Development Server Mode

The VibeTunnel Mac app includes a special development server mode that integrates with the web development workflow:

**Setup:**

1.  Open VibeTunnel Settings → Debug tab (enable Debug Mode first in General settings)
2.  Enable "Use Development Server"
3.  Set the path to your `web/` directory
4.  Restart the VibeTunnel server

**How it works:**

-   Instead of using the bundled production server, the Mac app runs `pnpm run dev` in your web directory
-   Provides hot reload and automatic rebuilding during development
-   Maintains all Mac app functionality (session management, logging, etc.)
-   Shows "Dev Server" in the menu bar and status indicators

**Benefits:**

-   No need to manually rebuild after code changes
-   Automatic esbuild watch mode for instant compilation
-   Full integration with Mac app features
-   Same terminal session management as production

**Alternative: Standalone Development**

If you prefer working outside the Mac app:

1.  Build the web project: `cd web && pnpm run build`
2.  In VibeTunnel settings, set Dashboard Access to "Network"
3.  Access from external device: `http://[your-mac-ip]:4020`

Note: This requires rebuilding after each change, so the dev server mode above is preferred for rapid iteration.

### Debug Logging

Enable debug logging for troubleshooting:

# Enable debug mode
export VIBETUNNEL\_DEBUG=1

# Or use inline
VIBETUNNEL\_DEBUG=1 vt your-command

Debug logs are written to `~/.vibetunnel/log.txt`.

### Using Development Builds with vt

When developing VibeTunnel, you can use the `VIBETUNNEL_PREFER_DERIVED_DATA` environment variable to make the `vt` command prefer development builds from Xcode's DerivedData folder:

# Enable DerivedData preference
export VIBETUNNEL\_PREFER\_DERIVED\_DATA=1

# vt will now search for and use the latest VibeTunnel build from DerivedData
vt your-command

When this environment variable is set, `vt` will:

1.  First search for VibeTunnel builds in `~/Library/Developer/Xcode/DerivedData`
2.  Use the most recently modified build found there
3.  Fall back to `/Applications/VibeTunnel.app` if no DerivedData build exists
4.  Log the exact binary location, version, and build timestamp being used

This is particularly useful for:

-   Testing changes without installing to `/Applications`
-   Working with multiple VibeTunnel builds simultaneously
-   Quickly switching between development and production versions
-   Debugging which version of VibeTunnel is being used

The version information is also:

-   Stored in `session.json` for each session
-   Displayed in `vt status` output
-   Shown in the initial log output when `VIBETUNNEL_PREFER_DERIVED_DATA` is set

### Verbosity Control

Control the amount of output from VibeTunnel commands:

# Command-line flags
vt -q npm test                # Quiet mode - no console output
vt npm test                   # Default - errors only
vt -v npm run dev            # Verbose - errors, warnings, and info
vt -vv cargo build           # Extra verbose - all except debug
vt -vvv python script.py     # Debug mode - everything

# Environment variable
export VIBETUNNEL\_LOG\_LEVEL=error    # Default
export VIBETUNNEL\_LOG\_LEVEL=warn     # Show errors and warnings
export VIBETUNNEL\_LOG\_LEVEL=info     # Show errors, warnings, and info
export VIBETUNNEL\_LOG\_LEVEL=verbose  # All except debug
export VIBETUNNEL\_LOG\_LEVEL=debug    # Everything

# Or use inline
VIBETUNNEL\_LOG\_LEVEL=silent vt npm test

**Note**: All logs are always written to `~/.vibetunnel/log.txt` regardless of verbosity level. The verbosity settings only control what's displayed in the terminal.

Poltergeist Integration
-----------------------

Poltergeist is an intelligent file watcher and auto-builder that can automatically rebuild VibeTunnel as you develop. This is particularly useful for native app development where manual rebuilds can interrupt your flow.

### Setting Up Poltergeist

1.  **Install Poltergeist** (if not already installed):
    
    npm install -g poltergeist
    
2.  **Start Poltergeist** in the VibeTunnel directory:
    
    cd /path/to/vibetunnel
    poltergeist
    
3.  **Make changes** - Poltergeist will automatically rebuild when it detects changes to:
    
    -   Swift files in `mac/` or `ios/`
    -   Xcode project files
    -   Configuration files

### Poltergeist Features

-   **Automatic Rebuilds**: Detects file changes and rebuilds instantly
-   **Smart Debouncing**: Prevents excessive rebuilds during rapid edits
-   **Build Notifications**: macOS notifications for build success/failure
-   **Menu Bar Integration**: Monitor build status from the macOS menu bar
-   **Parallel Builds**: Can build macOS and iOS targets simultaneously

### Configuration

VibeTunnel includes a `poltergeist.config.json` that configures:

-   **vibetunnel** target: Builds the macOS app in Debug configuration
-   **vibetunnel-ios** target: Builds the iOS app (disabled by default)

To enable iOS builds, edit `poltergeist.config.json` and set `"enabled": true` for the vibetunnel-ios target.

Documentation
-------------

-   Keyboard Shortcuts - Complete keyboard shortcut reference
-   Quick Reference Card - Printable shortcuts cheat sheet
-   Technical Specification - Detailed architecture and implementation
-   Contributing Guide - Development setup and guidelines
-   Architecture - System design overview
-   Build System - Build process details
-   Push Notifications - How web push notifications work

macOS Permissions
-----------------

macOS is finicky when it comes to permissions. The system will only remember the first path from where an app requests permissions. If subsequently the app starts somewhere else, it will silently fail. Fix: Delete the entry and restart settings, restart app and next time the permission is requested, there should be an entry in Settings again.

Important: You need to set your Developer ID in Local.xcconfig. If apps are signed Ad-Hoc, each new signing will count as a new app for macOS and the permissions have to be (deleted and) requested again.

**Debug vs Release Bundle IDs**: The Debug configuration uses a different bundle identifier (`sh.vibetunnel.vibetunnel.debug`) than Release (`sh.vibetunnel.vibetunnel`). This allows you to have both versions installed simultaneously, but macOS treats them as separate apps for permissions. You'll need to grant permissions separately for each version.

If that fails, use the terminal to reset:

```
# This removes Accessibility permission for a specific bundle ID:
sudo tccutil reset Accessibility sh.vibetunnel.vibetunnel
sudo tccutil reset Accessibility sh.vibetunnel.vibetunnel.debug  # For debug builds

sudo tccutil reset ScreenCapture sh.vibetunnel.vibetunnel
sudo tccutil reset ScreenCapture sh.vibetunnel.vibetunnel.debug  # For debug builds

# This removes all Automation permissions system-wide (cannot target specific apps):
sudo tccutil reset AppleEvents
```

Logging and Privacy
-------------------

VibeTunnel uses Apple's unified logging system with the subsystem `sh.vibetunnel.vibetunnel`. By default, macOS redacts sensitive runtime data in logs, showing `<private>` instead of actual values. This is a privacy feature to prevent accidental exposure of sensitive information.

### Bundle Identifiers

VibeTunnel uses the following bundle identifiers:

**Production:**

-   `sh.vibetunnel.vibetunnel` - Main macOS app and logging subsystem
-   `sh.vibetunnel.vibetunnel.debug` - Debug builds of the macOS app

**Testing:**

-   `sh.vibetunnel.vibetunnel.tests` - macOS test suite
-   `sh.vibetunnel.ios.tests` - iOS test suite

**iOS:**

-   `sh.vibetunnel.ios` - iOS keychain service and URL scheme

### Viewing Unredacted Logs

To see full log details for debugging, you have several options:

1.  **Install the Configuration Profile** (Recommended - easiest method):
    
    # Install the logging configuration profile
    open apple/logging/VibeTunnel-Logging.mobileconfig
    
    # This enables debug logging for all VibeTunnel components
    # To remove later: System Settings → Privacy & Security → Profiles
    
2.  **Use the vtlog script** (convenient log viewer):
    
    # View recent logs (requires configuration profile or sudo)
    ./scripts/vtlog.sh
    
    # Follow logs in real-time
    ./scripts/vtlog.sh -f
    
    # Show only errors
    ./scripts/vtlog.sh -e
    
    # Filter by category
    ./scripts/vtlog.sh -c ServerManager
    
3.  **Configure passwordless sudo** (alternative for vtlog with -p flag):
    
    # Add to sudoers (replace 'yourusername' with your actual username)
    sudo visudo
    # Add this line:
    yourusername ALL=(ALL) NOPASSWD: /usr/bin/log
    
    # Then use vtlog with private flag
    ./scripts/vtlog.sh -p
    
4.  **Enable private data logging** using a plist file (alternative):
    
    # Create the plist to enable private data for VibeTunnel
    sudo mkdir -p /Library/Preferences/Logging/Subsystems
    sudo tee /Library/Preferences/Logging/Subsystems/sh.vibetunnel.vibetunnel.plist \> /dev/null << 'EOF'
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Enable-Private-Data</key>
        <true/>
    </dict>
    </plist>
    EOF
    

### Why Logs Show `<private>`

Apple redacts dynamic values in logs by default to protect user privacy. This prevents accidental logging of passwords, tokens, or personal information. Our configuration profile or the methods above enable full visibility for development and debugging.

For more detailed information about logging privacy and additional methods, see apple/docs/logging-private-fix.md.

Contributing
------------

We welcome contributions! VibeTunnel is a community-driven project and we'd love to have you join us.

### Join Our Community

Connect with the VibeTunnel team and other contributors on our Discord server. It's the best place to:

-   Discuss new features and ideas
-   Get help with development setup
-   Coordinate on larger changes
-   Share your VibeTunnel use cases

### How to Contribute

1.  **Join Discord**: Start by joining our Discord server to say hello!
2.  **Check Issues**: Look for issues labeled `good first issue` or `help wanted`
3.  **Development Setup**: Follow our Contributing Guide for detailed setup instructions
4.  **Submit PRs**: Fork the repo, create a branch, and submit your changes

For technical details on building and developing VibeTunnel, see our Contributing Guide.

Support VibeTunnel
------------------

Love VibeTunnel? Help us keep the terminal vibes flowing! Your support helps us buy pizza and drinks while we keep hacking on your favorite AI agent orchestration platform.

All donations go directly to the development team. Choose your own amount - one-time or monthly! Visit our Polar page to support us.

Credits
-------

Created with ❤️ by:

-   @badlogic - Mario Zechner
-   @mitsuhiko - Armin Ronacher
-   @steipete - Peter Steinberger
-   @hjanuschka - Helmut Januschka
-   @manuelmaly - Manuel Maly

License
-------

VibeTunnel is open source software licensed under the MIT License. See LICENSE for details.

* * *

**Ready to vibe?** Download VibeTunnel and start tunneling!
