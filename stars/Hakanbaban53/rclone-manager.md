---
project: rclone-manager
stars: 233
description: Rclone Manager is a cross-platform GUI application designed to help users manage Rclone remotes efficiently.
url: https://github.com/Hakanbaban53/rclone-manager
---

  
RClone Manager
=================

**Cross-platform GUI for managing Rclone remotes with style.**  
_Built with Angular + Tauri · Cross-platform support_

* * *

🌐 Overview
-----------

**RClone Manager** is a **cross-platform** GUI application to help users manage Rclone remotes with a modern interface.

> ⚠️ **Actively developed** – Expect frequent updates and improvements.

* * *

🎨 Design Philosophy
--------------------

💡 A unique mix of **GTK styling**, **Angular Material**, and **FontAwesome**, creating a minimalist yet modern look.

* * *

📸 Screenshots
--------------

**💻 Desktop**  

**📱 Mobile**  

_Both light and dark modes are shown with a diagonal split for visual comparison._

* * *

🚀 Features
-----------

-   🎨 **User-Friendly Theme** – Enjoy a clean, intuitive interface designed for ease of use, making remote management accessible for everyone.
-   🛠 **Remote Management** – Add, edit, and delete remotes easily.
-   🔐 **OAuth Support** – Authenticate with popular providers effortlessly.
-   ☁️ **Supported Remotes** – Nearly all Rclone remotes are supported, including:
    -   Google Drive
    -   Dropbox
    -   OneDrive
    -   S3-compatible services
    -   And many more!
-   ⚙️ **Advanced VFS Options** – Tune caching, read sizes, and other performance options.
-   🖥 **Tray Icon Support** – Quick access to your remotes from the system tray.
-   🌗 **Light & Dark Modes** – GTK-inspired themes with a modern, responsive layout.
-   🧪 **Cross-Platform Architecture** – Tauri + Angular. **Cross-platform** support for Linux, Windows, and macOS.

* * *

🔧 Tech Stack
-------------

-   **Frontend**: Angular + Angular Material + FontAwesome
-   **Backend**: Tauri (Rust)
-   **Styling**: GTK-inspired custom theming

* * *

📦 Downloads
------------

👉 Get the latest release from:

-   🔗 GitHub Releases

* * *

🛠️ Installation
----------------

### 🔍 Prerequisites

Make sure you have the following installed:

-   **Rclone:** Required for remote management.
-   **Fuse:** Needed for mounting remotes on Linux/macOS.
-   **WinFsp:** Needed for mounting remotes on Windows.
-   **Node.js:** Required for Angular development and running the frontend.
-   **Rust:** Required for Tauri (backend) development.
-   **Cargo:** Rust’s package manager, required for Tauri.

### 💻 Development Setup

# Clone from GitHub
git clone https://github.com/Hakanbaban53/rclone-manager.git
cd rclone-manager

# Install dependencies
npm install

# Run the app
npm run tauri dev

⚠️ **Note:** Do not use `ng serve` — the app depends on **Tauri APIs**.

### 📦 Build for Production

npm run tauri build

* * *

🐞 Known Issues
---------------

Known bugs and technical limitations are tracked in two places:

-   📄 See **ISSUES.md** for detailed explanations of platform-specific issues (e.g. Windows terminal flash)
-   📌 Visit our **GitHub Project Board** for open bugs and upcoming fixes

* * *

🗺️ Roadmap
-----------

We organize development on **GitHub Projects** — including features, bugs, and long-term goals.

The board includes:

-   🔜 **Short-Term Goals** (UI improvements, packaging, sync/copy GUI)
-   🚀 **Long-Term Features** (mobile support, performance, localization)
-   🧩 **Open Tasks & Suggestions** from the community
-   🐛 **Known Issues & Workarounds** not yet fixed

> 🧠 Want to follow progress or help shape direction? Watch the board and leave your ideas!

* * *

🤝 Contributing
---------------

We welcome contributors of all experience levels! You can help by:

-   🐛 Reporting bugs & submitting suggestions in **GitHub Issues**
-   🛠️ Submitting pull requests — see the CONTRIBUTING.md guide (coming soon)

* * *

📜 License
----------

Licensed under the **GNU GPLv3**.

* * *

📬 Contact
----------

Reach out via **GitHub Issues** — we’d love your feedback!
