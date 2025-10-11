---
project: rclone-manager
stars: 374
description: Rclone Manager is a cross-platform GUI application designed to help users manage Rclone remotes efficiently.
url: https://github.com/RClone-Manager/rclone-manager
---

  
RClone Manager
=================

**A powerful, cross-platform GUI for managing Rclone remotes with style and ease.**  
_Built with Angular 20 + Tauri 2 · Linux • Windows • macOS • ARM Support_

* * *

🌐 Overview
-----------

**RClone Manager** is a **modern, cross-platform GUI** that makes managing Rclone remotes effortless. Whether you're syncing files across cloud storage providers, mounting remote drives, or performing complex file operations, RClone Manager provides an intuitive interface that simplifies even the most advanced Rclone features.

> ⚠️ **Actively developed** – Regular updates with new features and improvements. Check out our roadmap to see what's coming next!

* * *

🎨 Design Philosophy
--------------------

💡 **Beautiful by design.** A unique blend of **GTK styling**, **Angular Material**, and **FontAwesome icons** creates a clean, minimalist interface that feels at home on any platform while maintaining a modern, responsive experience.

* * *

📸 Screenshots
--------------

**💻 Desktop Interface**  

**🏠 Home & Overview**  

**⚙️ Mount Control & Job Monitoring**  

**📱 Mobile Support**  

_Seamlessly switches between light and dark modes to match your system preferences._

* * *

🚀 Features
-----------

### 🎯 Core Functionality

-   🛠 **Complete Remote Management** – Add, edit, delete, and clone remotes with an intuitive wizard
-   🔐 **OAuth & Interactive Configuration** – Seamless authentication with providers like OneDrive, Google Drive, and iCloud
-   🔑 **Encrypted Configuration Support** – Secure password storage using system keyring/credential store
-   💾 **Import/Export** – Backup and restore your entire configuration, with optional 7z encryption

### ⚡ File Operations

-   📁 **Mount Remotes** – Access cloud storage as local drives with multiple mount types (mount, mount2, NFS)
-   🔄 **Sync & Copy** – One-way synchronization and file copying between remotes or local folders
-   ↔️ **Bidirectional Sync (Bisync)** – Keep two locations perfectly synchronized in both directions
-   🚚 **Move Operations** – Transfer files between locations without leaving duplicates
-   🎯 **Primary Actions** – Set up to 3 quick-access actions per remote for instant operations

### 🎨 User Experience

-   🌗 **Adaptive Themes** – Beautiful light and dark modes with GTK-inspired design
-   🖥 **System Tray Integration** – Quick access to mounts and operations from your taskbar
-   📊 **Real-time Monitoring** – Live job status, transfer speeds, and progress tracking
-   🔔 **Smart Notifications** – Stay informed with non-intrusive alerts
-   ⚙️ **Advanced Options** – Full access to VFS settings, bandwidth limits, and flag configurations

### 🌍 Platform Support

-   🐧 **Linux** – Full support including ARM architecture
-   🪟 **Windows** – Native support with WinFsp integration, including ARM
-   🍎 **macOS** – Complete functionality with automatic mount plugin installation
-   📱 **Responsive Design** – Optimized interface for desktop and mobile viewports

### 🔧 Advanced Features

-   🔄 **Auto-Update** – Built-in updater keeps you on the latest version
-   🖥️ **Native Terminal Support** – Open remote config in your preferred terminal
-   📡 **Metered Connection Detection** – Smart warnings when on limited networks
-   🎮 **Global Shortcuts** – Keyboard shortcuts for power users (e.g., Ctrl+Shift+M to force-check mounts)
-   🔍 **Mount Watcher** – Automatic detection and updates of mount status

### ☁️ Supported Cloud Providers

Nearly all Rclone remotes are supported, including:

-   **Google Drive** – Full OAuth support with team drives
-   **Microsoft OneDrive** – Personal and Business accounts
-   **Dropbox** – Complete integration
-   **Amazon S3** – And all S3-compatible services
-   **iCloud Drive** – Interactive configuration support
-   **SFTP/FTP** – Secure file transfer protocols
-   **WebDAV** – Generic WebDAV support
-   **And 40+ more providers!**

* * *

🔧 Tech Stack
-------------

-   **Frontend**: Angular 20 + Angular Material + FontAwesome
-   **Backend**: Tauri 2 (Rust)
-   **Styling**: Custom GTK-inspired theming with responsive design
-   **Architecture**: Modern component-based with reactive state management

* * *

📦 Downloads
------------

### 🎯 Latest Release

Get the latest version for your platform:

**Available for:**

-   🐧 Linux (x86\_64, ARM64) – AppImage, Deb, RPM
-   🪟 Windows (x86\_64, ARM64) – MSI Installer, Portable
-   🍎 macOS (Intel, Apple Silicon) – DMG

> 📋 See the full release notes for changelog and installation instructions

* * *

🛠️ Installation
----------------

### 📋 Runtime Requirements

**RClone Manager** will guide you through installing any missing dependencies on first run. However, you can pre-install:

#### Required

-   **Rclone** – The core tool for remote management (can be installed via the app)

#### Optional (for mounting)

-   **Linux/macOS:** FUSE – Usually pre-installed on most distributions
-   **Windows:** WinFsp – Automatically prompted for installation if missing
-   **macOS:** Mount plugin – Automatically installed by the app when needed

#### Optional (for encrypted exports)

-   **7-Zip** – For password-protected configuration backups

### 🚀 Quick Start

1.  **Download** the appropriate package for your OS from releases
2.  **Install** using your platform's standard method:

-   **Linux:**
    -   **Debian/Ubuntu:** `sudo dpkg -i rclone-manager_*.deb` or run the AppImage
    -   **Fedora/openSUSE (RPM):** `sudo rpm -i rclone-manager-*.rpm`
    -   **Arch Linux:** Install from AUR via your AUR helper, e.g. `yay -S rclone-manager`
-   **Windows:** Run the MSI installer or extract the portable version
-   **macOS:** Open the DMG and drag to Applications

1.  **Launch** RClone Manager and follow the onboarding wizard
2.  **Add your first remote** using the guided setup

> 💡 **First-time users?** The app includes an interactive onboarding that will help you set up Rclone and create your first remote!

* * *

🛠️ Development
---------------

### Prerequisites for Building

-   **Node.js** (v18 or later)
-   **Rust** (latest stable)
-   **Cargo** (comes with Rust)
-   Platform-specific build tools (see Tauri prerequisites)

### Development Setup

# Clone the repository
git clone https://github.com/RClone-Manager/rclone-manager.git
cd rclone-manager

# Install dependencies
npm install

# Start development server
npm run tauri dev

⚠️ **Important:** Always use `npm run tauri dev` instead of `ng serve`, as the app requires Tauri APIs.

### Building for Production

# Build for your current platform
npm run tauri build

# The built application will be in src-tauri/target/release/

### Linting & Formatting

# Frontend (Angular)
npm run lint          # ESLint check
npm run format        # Prettier format

# Backend (Rust)
npm run lint:rust     # Clippy check
npm run format:rust   # Rustfmt format

* * *

🐞 Known Issues
---------------

Known bugs and technical limitations are tracked in two places:

-   📄 See **ISSUES.md** for detailed explanations of platform-specific issues (e.g. Windows terminal flash)
-   📌 Visit our **GitHub Project Board** for open bugs and upcoming fixes

* * *

🗺️ Roadmap
-----------

We organize development on our **GitHub Project Board** — track features, bugs, and long-term goals.

### Current Focus Areas

-   🔜 **Near-Term Goals**
    
    -   Enhanced job monitoring with detailed progress tracking
    -   Additional filter configuration options
    -   Performance optimizations for large remote lists
-   🚀 **Long-Term Vision**
    
    -   Multi-language support (i18n/l10n)
    -   Mobile app versions
    -   Advanced scheduling and automation
    -   Plugin system for custom integrations
-   🧩 **Community Driven**
    
    -   Feature requests and suggestions
    -   UI/UX improvements
    -   Platform-specific enhancements

> 🧠 **Want to influence the direction?** Star the repo, watch the project board, and share your ideas in Discussions or Issues!

* * *

🤝 Contributing
---------------

We welcome contributions from developers of all skill levels! Here's how you can help:

### Ways to Contribute

-   🐛 **Report Bugs** – Found an issue? Open a bug report
-   💡 **Suggest Features** – Have an idea? Share it with us
-   � **Improve Documentation** – Help make our docs clearer and more comprehensive
-   🔧 **Submit Pull Requests** – Fix bugs or implement features (see development setup above)
-   🌍 **Translate** – Help make RClone Manager available in your language (coming soon)
-   ⭐ **Spread the Word** – Star the repo, share with friends, write blog posts

### Contribution Guidelines

1.  Fork the repository and create a feature branch
2.  Follow the existing code style and linting rules
3.  Test your changes thoroughly on your target platform
4.  Write clear commit messages
5.  Submit a pull request with a detailed description

> 📝 See our CONTRIBUTING.md guide (coming soon) for detailed guidelines

* * *

📜 License
----------

Licensed under the **GNU GPLv3**.

You are free to use, modify, and distribute this software under the terms of the GPL v3 license. See the LICENSE file for full details.

* * *

📬 Support & Contact
--------------------

### Get Help

-   💬 GitHub Discussions – Ask questions and chat with the community
-   🐛 Issue Tracker – Report bugs or request features
-   📖 Documentation – Guides and tutorials (coming soon)

### Stay Updated

-   ⭐ Star the repository to get notifications about new releases
-   👀 Watch the repo for all updates and discussions
-   🔔 Enable release notifications to be the first to know about new versions

* * *

Made with ❤️ by the RClone Manager Team  
Powered by Rclone | Built with Angular & Tauri
