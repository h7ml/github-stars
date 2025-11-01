---
project: utoo
stars: 2208
description: An unified toolchain for web development.
url: https://github.com/utooland/utoo
---

> ⚠️ Notice: we are working on making a better bundler on top of Turbopack, see #1872.
> 
> If you encountered some critical problems when using current Mako, you can report issues at Mako 0.x Feedback in discussions.

* * *

#### 🌖 /juːtuː/ Unified Toolchain

Utoo is a modern frontend toolchain that provides a unified command-line interface for frontend development. It comes with built-in package management capabilities and can be extended with additional tools like the bundler.

-   `utoo`: Built-in package manager for dependency resolution and installation
-   `@utoo/pack`: High-performance bundler (requires separate installation)

🚀 Installation
---------------

### 📦 Core Tools

Install the core tools (`ut` and `utoo`) globally:

npm install -g utoo

### 🛠️ Bundler

Install the bundler globally if you need build capabilities:

npm install -g @utoo/pack

You can track features progress at `@utoo/pack features list`

✨ Features
----------

-   🚀 Fast package management
-   🔧 Flexible configuration system
-   📦 Smart dependency resolution
-   🛠️ Powerful build toolchain

🔌 Command Mounting
-------------------

Utoo provides a powerful command mounting system through the `ut` command. This system allows you to:

1.  **Mount Custom Commands**: Map any command to a custom alias
2.  **Configure Global/Local Commands**: Set commands at global or project level
3.  **Use Wildcard Commands**: Define default behavior for unknown commands

### ⚙️ Configuration

Commands can be configured using the `ut config` command:

# Set a global command
ut config set install.cmd "utoo install" --global

# Set a local command (project-specific)
ut config set build.cmd "utoo-pack build"

# Set a wildcard command (default behavior)
ut config set \*.cmd "utoo" --global

### 🔍 Command Resolution

When you run a command through `ut`, it follows this resolution order:

1.  Check for a specific command configuration
2.  If not found, check for a wildcard command
3.  If no wildcard is configured, default to `utoo`

For example:

# These commands are equivalent if configured as shown above
ut install
utoo install

# Custom command mapping
ut build
# Executes: utoo-pack build

# Unknown command with wildcard
ut unknown-command
# Executes: utoo unknown-command

### 📁 Configuration Files

Command configurations are stored in:

-   Global config: `~/.utoo/config.toml`
-   Local config: `.utoo.toml` (project root)

Example configuration:

\[values\]
"install.cmd" = "utoo install"
"build.cmd" = "utoo-pack build"
"\*.cmd" = "utoo"

### 📋 Available Commands

# Show help and available commands
ut --help

# List all configured commands
ut config list

# Get specific command configuration
ut config get install.cmd

# Set command configuration
ut config set install.cmd "utoo install" --global

🔌 Command Mounting
-------------------

Utoo provides a powerful command mounting system that allows you to extend the toolchain with custom commands. This is particularly useful for project-specific scripts and workflows.

### 📜 Package.json Scripts

Any script defined in your `package.json` can be executed directly through `ut`:

{
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "test": "jest"
  }
}

You can run these scripts using:

# Using the run command
ut run dev
# or shorthand
ut r dev

# Direct command execution
ut dev
ut build
ut test

### 🛠️ Custom Commands

You can create custom commands by adding them to your project's configuration. These commands can be:

1.  **Shell Scripts**: Simple shell commands or scripts
2.  **Node.js Scripts**: JavaScript/TypeScript files
3.  **Binary Executables**: Any executable in your project

### 🌍 Command Execution Environment

When executing commands, Utoo provides:

-   Access to all project dependencies
-   Environment variables from your project
-   Proper working directory context
-   Node.js binary path resolution

### ⚡ Command Hooks

Utoo supports various command hooks that can be used to extend command behavior:

-   `preinstall`: Run before package installation
-   `install`: Run during package installation
-   `postinstall`: Run after package installation
-   `prepare`: Run before package preparation
-   `preprepare`: Run before package preparation
-   `postprepare`: Run after package preparation

📋 Commands
-----------

### 📦 Package Management Commands

#### 📥 Install Dependencies

# Install project dependencies
ut install
# or shorthand
ut i

# Install specific package
ut install <package-name\>
# Example: install lodash
ut install lodash

# Install as dev dependency
ut install <package-name\> --save-dev

# Install as peer dependency
ut install <package-name\> --save-peer

# Install as optional dependency
ut install <package-name\> --save-optional

# Global installation
ut install <package-name\> -g

#### 🗑️ Uninstall Dependencies

# Uninstall specific package
ut uninstall <package-name\>
# or shorthand
ut un <package-name\>

#### 🔄 Update Dependencies

# Update all dependencies
ut update
# or shorthand
ut u

### 🏗️ Build Commands

#### 🔨 Rebuild Dependencies

# Rebuild all dependencies
ut rebuild
# or shorthand
ut rb

#### 🧹 Clean Cache

# Clean all cache
ut clean

# Clean specific package cache
ut clean <package-pattern\>
# Example: clean all react related packages
ut clean "react\*"

#### 📊 Dependency Analysis

# Analyze project dependencies
ut deps
# or shorthand
ut d

# Only analyze workspace dependencies
ut deps --workspace-only

### 🛠️ Bundler

Utoo includes a high-performance bundler that supports various build scenarios:

#### 🚀 Basic Usage

# Start development server
ut dev

# Build production version
ut build

#### 📚 Example Projects

We provide several example projects to demonstrate different usage scenarios:

-   `examples/with-antd`: Ant Design component library integration
-   `examples/with-sass`: Sass style processing
-   `examples/with-less`: Less style processing
-   `examples/with-style-loader`: CSS Modules usage
-   `examples/with-library`: Library mode build
-   `more to come ...`

### ⚙️ Common Options

All commands support the following common options:

-   `--verbose`: Show detailed output
-   `--registry <url>`: Set npm registry URL
-   `--legacy-peer-deps`: Use legacy peer dependency handling
-   `--ignore-scripts`: Skip running dependency scripts

🔨 Build from Source
--------------------

# Build project
cargo build --release

# Add binary to PATH
export PATH=$PATH:$(pwd)/target/release

### 📦 Install Dependencies

# Install project dependencies
ut

### 🏃 Run Bundler

# Build local development environment
cd packages/pack
ut build:local

# Build by native
cargo run --bin pack-cli -- --mode build  --project-dir examples/with-antd --root-dir .
cargo run --bin pack-cli -- --mode dev --watch true --project-dir examples/with-antd --root-dir .

# Build the napi package
cd packages/pack
npm run build:local

cd ../../examples/with-antd
npm run build
npm run dev

📁 Project Structure
--------------------

```
.
├── crates/          # Rust core libraries
│   ├── cli/         # Command line tools
│   ├── core/        # Core functionality
│   ├── pack-*       # Bundler related modules
├── packages/        # Package management code
├── examples/        # Example projects
└── vendor/          # Third-party dependencies
```
