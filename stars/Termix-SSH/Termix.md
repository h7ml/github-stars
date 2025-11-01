---
project: Termix
stars: 6146
description: Termix is a web-based server management platform with SSH terminal, tunneling, and file editing capabilities.
url: https://github.com/Termix-SSH/Termix
---

Repo Stats
==========

English | 中文

  
Achieved on September 1st, 2025

#### Top Technologies

  

If you would like, you can support the project here!  

Overview
========

Termix is an open-source, forever-free, self-hosted all-in-one server management platform. It provides a web-based solution for managing your servers and infrastructure through a single, intuitive interface. Termix offers SSH terminal access, SSH tunneling capabilities, and remote file management, with many more tools to come.

Features
========

-   **SSH Terminal Access** - Full-featured terminal with split-screen support (up to 4 panels) and tab system
-   **SSH Tunnel Management** - Create and manage SSH tunnels with automatic reconnection and health monitoring
-   **Remote File Manager** - Manage files directly on remote servers with support for viewing and editing code, images, audio, and video. Upload, download, rename, delete, and move files seamlessly.
-   **SSH Host Manager** - Save, organize, and manage your SSH connections with tags and folders and easily save reusable login info while being able to automate the deploying of SSH keys
-   **Server Stats** - View CPU, memory, and HDD usage on any SSH server
-   **User Authentication** - Secure user management with admin controls and OIDC and 2FA (TOTP) support
-   **Database Encryption** - SQLite database files encrypted at rest with automatic encryption/decryption
-   **Data Export/Import** - Export and import SSH hosts, credentials, and file manager data with incremental sync
-   **Automatic SSL Setup** - Built-in SSL certificate generation and management with HTTPS redirects
-   **Modern UI** - Clean desktop/mobile-friendly interface built with React, Tailwind CSS, and Shadcn
-   **Languages** - Built-in support for English, Chinese, and German
-   **Platform Support** - Available as a web app, desktop application (Windows & Linux), and dedicated mobile app for iOS and Android. macOS and iPadOS support is planned.

Planned Features
================

See Projects for all planned features. If you are looking to contribute, see Contributing.

Installation
============

Supported Devices:

-   Website (any modern browser like Google, Safari, and Firefox)
-   Windows (app)
-   Linux (app)
-   iOS (app)
-   Android (app)
-   iPadOS and macOS are in progress

Visit the Termix Docs for more information on how to install Termix on all platforms. Otherwise, view a sample Docker Compose file here:

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

Support
=======

If you need help or want to request a feature with Termix, visit the Issues page, log in, and press `New Issue`. Please be as detailed as possible in your issue, preferably written in English. You can also join the Discord server and visit the support channel, however, response times may be longer.

Show-off
========

2025-09-30.23-13-19.mp4

License
=======

Distributed under the Apache License Version 2.0. See LICENSE for more information.
