---
project: Termix
stars: 4353
description: Termix is a web-based server management platform with SSH terminal, tunneling, and file editing capabilities.
url: https://github.com/LukeGus/Termix
---

Repo Stats
==========

English | 中文

  
Achieved on September 1st, 2025

#### Top Technologies

  

If you would like, you can support the project here!  

Overview
========

Termix is an open-source, forever-free, self-hosted all-in-one server management platform. It provides a web-based solution for managing your servers and infrastructure through a single, intuitive interface. Termix offers SSH terminal access, SSH tunneling capabilities, and remote file editing, with many more tools to come.

Features
========

-   **SSH Terminal Access** - Full-featured terminal with split-screen support (up to 4 panels) and tab system
-   **SSH Tunnel Management** - Create and manage SSH tunnels with automatic reconnection and health monitoring
-   **Remote File Editor** - Edit files directly on remote servers with syntax highlighting, file management features ( uploading, removing, renaming, deleting files)
-   **SSH Host Manager** - Save, organize, and manage your SSH connections with tags and folders
-   **Server Stats** - View CPU, memory, and HDD usage on any SSH server
-   **User Authentication** - Secure user management with admin controls and OIDC and 2FA (TOTP) support
-   **Modern UI** - Clean desktop/mobile friendly (in progress) interface built with React, Tailwind CSS, and Shadcn
-   **Languages** - Built-in support for English and Chinese
-   **Improved Platform Support** - Now includes an installable Electron app (in progress) for desktop, with a dedicated mobile app also planned.

Planned Features
================

See Projects. If you are looking to contribute, see Contributing,

Installation
============

Visit the Termix Docs for more information on how to install Termix. Otherwise, view a sample docker-compose file here:

services:
  termix:
    image: ghcr.io/lukegus/termix:latest
    container\_name: termix
    restart: unless-stopped
    ports:
      - "8080:8080"
    volumes:
      - termix-data:/app/data
    environment:
      PORT: "8080"

volumes:
  termix-data:
    driver: local

Pre-built binaries are now available for download, including a Windows installer/portable app and a Linux portable app ( built with Electron). See Docs for details. A native iOS/Android app is planned.

Support
=======

If you need help with Termix, you can join the Discord server and visit the support channel. You can also open an issue or open a pull request on the GitHub repo.

Show-off
========

Termix.Show.Off.Video.mov

License
=======

Distributed under the Apache License Version 2.0. See LICENSE for more information.
