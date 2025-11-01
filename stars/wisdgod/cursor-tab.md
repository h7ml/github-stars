---
project: cursor-tab
stars: 72
description: Protocol Buffers definitions for Cursor Tab
url: https://github.com/wisdgod/cursor-tab
---

Cursor Tab Protocol Buffers
===========================

A reverse-engineered Protocol Buffers definition project that enables Cursor Tab functionality for other platforms.

Overview
--------

This project provides Protocol Buffers definitions for integrating Cursor Tab features into third-party applications and platforms through reverse engineering efforts.

**Current Version**: 1.6.14

> **Important Notice**
> 
> -   This project is based on reverse engineering
> -   Updates are provided on an irregular basis
> -   The project may be discontinued at any time without notice

Deprecation Notice
------------------

> **Note**
> 
> `cpp.proto` and `fs.proto` are deprecated and will no longer be updated. All updates will be made to `unite.proto` only.

Installation
------------

# Clone the repository
git clone https://github.com/wisdgod/cursor-tab.git
cd cursor-tab

Usage
-----

Choose a Protocol Buffers library for your preferred programming language and compile the `.proto` files according to your language's documentation.

File Structure
--------------

-   `unite.proto` - Main Protocol Buffers definition file
-   `cpp.proto` - **\[DEPRECATED\]** Copilot++ (old name for Cursor Tab) related definitions
-   `fs.proto` - **\[DEPRECATED\]** File system related definitions

License
-------

This project is dual-licensed under:

-   MIT License
-   Apache License 2.0

You may choose either license for your use case.

Contributing
------------

While Pull Requests are not accepted, you are welcome to report issues or suggestions through GitHub Issues.

Disclaimer
----------

This is an unofficial project based on reverse engineering. Use at your own risk. The maintainers are not responsible for any issues that may arise from using these Protocol Buffers definitions.

Support
-------

As this is a reverse-engineered project with irregular updates, support is provided on a best-effort basis through GitHub issues.
