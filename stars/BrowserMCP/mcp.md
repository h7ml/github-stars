---
project: mcp
stars: 3609
description: Browser MCP is a Model Context Provider (MCP) server that allows AI applications to control your browser
url: https://github.com/BrowserMCP/mcp
---

### Browser MCP

Automate your browser with AI.  
**Website** • **Docs**

About
-----

Browser MCP is an MCP server + Chrome extension that allows you to automate your browser using AI applications like VS Code, Claude, Cursor, and Windsurf.

Features
--------

-   ⚡ Fast: Automation happens locally on your machine, resulting in better performance without network latency.
-   🔒 Private: Since automation happens locally, your browser activity stays on your device and isn't sent to remote servers.
-   👤 Logged In: Uses your existing browser profile, keeping you logged into all your services.
-   🥷🏼 Stealth: Avoids basic bot detection and CAPTCHAs by using your real browser fingerprint.

Contributing
------------

This repo contains all the core MCP code for Browser MCP, but currently cannot yet be built on its own due to dependencies on utils and types from the monorepo where it's developed.

Credits
-------

Browser MCP was adapted from the Playwright MCP server in order to automate the user's browser rather than creating new browser instances. This allows using the user's existing browser profile to use logged-in sessions and avoid bot detection mechanisms that commonly block automated browser use.
