---
project: dockmon
stars: 126
description: DockMon - Modern Docker container monitoring with auto-restart and alerts
url: https://github.com/darthnorse/dockmon
---

DockMon
=======

A comprehensive Docker container monitoring and management platform with real-time monitoring, intelligent auto-restart, multi-channel alerting, and complete event logging.

Key Features
------------

-   **Multi-Host Monitoring** - Monitor containers across unlimited Docker hosts (local and remote)
-   **Real-Time Statistics** - Live CPU, memory, network, and disk I/O metrics for hosts and containers
-   **Real-Time Container Logs** - View logs from multiple containers simultaneously with live updates
-   **Event Viewer** - Comprehensive audit trail with filtering, search, and real-time updates
-   **Intelligent Auto-Restart** - Per-container auto-restart with configurable retry logic
-   **Advanced Alerting** - Discord, Slack, Telegram, Pushover, Gotify, SMTP with customizable templates
-   **Real-Time Dashboard** - Drag-and-drop customizable widgets with WebSocket updates
-   **Secure by Design** - Session-based auth, rate limiting, mTLS for remote hosts
-   **Mobile-Friendly** - Responsive design that works seamlessly on all devices

Documentation
-------------

-   **Complete User Guide** - Full documentation
-   **Quick Start** - Get started in 5 minutes
-   **Installation** - Docker, unRAID, Synology, QNAP
-   **Configuration** - Alerts, notifications, settings
-   **Security** - Best practices and mTLS setup
-   **Remote Monitoring** - Monitor remote Docker hosts
-   **Event Viewer** - Comprehensive audit trail with filtering
-   **Container Logs** - Real-time multi-container log viewer
-   **API Reference** - REST and WebSocket APIs
-   **FAQ** - Frequently asked questions
-   **Troubleshooting** - Common issues

Use Cases
---------

### Home Lab

-   Monitor all your Docker containers in one place
-   Get notified when critical services go down
-   Automatically restart failed containers
-   Track container events and changes

### Small Business

-   Centralized monitoring across multiple servers
-   Multi-channel alerting (Discord, Slack, Telegram, Pushover, Gotify, SMTP)
-   Schedule maintenance windows with blackout periods
-   Audit trail of all container operations

### Development Teams

-   Monitor dev, staging, and production environments
-   Quick container management (start, stop, restart, logs)
-   Test notifications before deploying to production
-   Share monitoring dashboard with team

Support & Community
-------------------

-   **Report Issues** - Found a bug?
-   **Discussions** - Ask questions, share ideas
-   **Wiki** - Complete documentation
-   **Star on GitHub** - Show your support!

Roadmap
-------

### Completed (v1.0)

-   Full backend API with FastAPI
-   WebSocket real-time updates
-   Multi-channel notifications
-   Comprehensive event logging
-   Event log viewer with filtering and search
-   Real-time container logs viewer (multi-container support)
-   Drag-and-drop dashboard
-   Auto-restart with retry logic

### Completed (v1.1)

-   Real-time performance metrics (CPU, memory, network, disk I/O)
-   Host-level and container-level statistics
-   TLS/mTLS support for secure remote Docker connections
-   Optimized streaming architecture with Go backend

### Planned (v1.5+)

-   Performance metrics dashboard with historical graphs
-   Container auto-update feature with version tracking
-   Configuration export/import
-   Automatic Proxmox LXC installation script

See the full roadmap for details.

Contributing
------------

Contributions are welcome! Here's how you can help:

-   Report bugs via GitHub Issues
-   Suggest features in Discussions
-   Improve documentation (edit the Wiki)
-   Submit pull requests (see Contributing Guide)

Development
-----------

Want to contribute code or run DockMon in development mode?

See Development Setup for:

-   Local development environment setup
-   Architecture overview
-   Running tests
-   Building from source

License
-------

MIT License - see LICENSE file for details.

Author
------

Created by darthnorse

Acknowledgments
---------------

This project has been developed with **vibe coding** and **AI assistance** using Claude Code. The codebase includes clean, well-documented code with proper error handling, comprehensive testing considerations, modern async/await patterns, robust database design, and production-ready deployment configurations.

* * *

**If DockMon helps you, please consider giving it a star!**

Documentation • Issues • Discussions
