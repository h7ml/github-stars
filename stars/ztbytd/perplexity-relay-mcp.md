---
project: perplexity-relay-mcp
stars: 2
description: The official MCP server implementation for the Perplexity API Platform
url: https://github.com/ztbytd/perplexity-relay-mcp
---

Perplexity Relay MCP Server
===========================

An extended MCP server implementation for the Perplexity API Platform with **custom base URL support** for relay/proxy services. This fork adds the ability to use custom API endpoints, making it perfect for users who need to access Perplexity API through relay services or proxies.

Key Features
------------

-   ✅ Full compatibility with official Perplexity API
-   🌐 **Custom base URL support** via `PERPLEXITY_BASE_URL` environment variable
-   🔄 Perfect for relay/proxy services and regional access
-   ⚙️ Configurable timeout settings
-   🚀 All official Perplexity tools included (Search, Ask, Research, Reason)

Based on the official Perplexity MCP server with enhanced flexibility for different network environments.

Available Tools
---------------

### **perplexity\_search**

Direct web search using the Perplexity Search API. Returns ranked search results with metadata, perfect for finding current information.

### **perplexity\_ask**

General-purpose conversational AI with real-time web search using the `sonar-pro` model. Great for quick questions and everyday searches.

### **perplexity\_research**

Deep, comprehensive research using the `sonar-deep-research` model. Ideal for thorough analysis and detailed reports.

### **perplexity\_reason**

Advanced reasoning and problem-solving using the `sonar-reasoning-pro` model. Perfect for complex analytical tasks.

Configuration
-------------

### Get Your API Key

1.  Get your Perplexity API Key from the API Portal
2.  Set it as an environment variable: `PERPLEXITY_API_KEY=your_key_here`
3.  (Optional) Set a custom base URL for relay/proxy services: `PERPLEXITY_BASE_URL=https://your-relay-service.com`
4.  (Optional) Set a timeout for requests: `PERPLEXITY_TIMEOUT_MS=600000`. The default is 5 minutes.

### Claude Code

Run in your terminal:

claude mcp add perplexity-relay --transport stdio --env PERPLEXITY\_API\_KEY=your\_key\_here --env PERPLEXITY\_BASE\_URL=https://your-relay-service.com -- npx -y perplexity-relay-mcp

Or add to your `claude.json`:

"mcpServers": {
  "perplexity-relay": {
    "type": "stdio",
    "command": "npx",
    "args": \[
      "\-y",
      "perplexity-relay-mcp"
    \],
    "env": {
      "PERPLEXITY\_API\_KEY": "your\_key\_here",
      "PERPLEXITY\_BASE\_URL": "https://your-relay-service.com",
      "PERPLEXITY\_TIMEOUT\_MS": "600000"
    }
  }
}

### Cursor

Add to your `mcp.json`:

{
  "mcpServers": {
    "perplexity-relay": {
      "command": "npx",
      "args": \["\-y", "perplexity-relay-mcp"\],
      "env": {
        "PERPLEXITY\_API\_KEY": "your\_key\_here",
        "PERPLEXITY\_BASE\_URL": "https://your-relay-service.com",
        "PERPLEXITY\_TIMEOUT\_MS": "600000"
      }
    }
  }
}

### Codex

Run in your terminal:

codex mcp add perplexity-relay --env PERPLEXITY\_API\_KEY=your\_key\_here --env PERPLEXITY\_BASE\_URL=https://your-relay-service.com -- npx -y perplexity-relay-mcp

### Claude Desktop

Add to your `claude_desktop_config.json`:

{
  "mcpServers": {
    "perplexity-relay": {
      "command": "npx",
      "args": \["\-y", "perplexity-relay-mcp"\],
      "env": {
        "PERPLEXITY\_API\_KEY": "your\_key\_here",
        "PERPLEXITY\_BASE\_URL": "https://your-relay-service.com",
        "PERPLEXITY\_TIMEOUT\_MS": "600000"
      }
    }
  }
}

### Other MCP Clients

For any MCP-compatible client, use:

npx perplexity-relay-mcp

Troubleshooting
---------------

-   **API Key Issues**: Ensure `PERPLEXITY_API_KEY` is set correctly
-   **Connection Errors**: Check your internet connection and API key validity
-   **Tool Not Found**: Make sure the package is installed and the command path is correct
-   **Timeout Errors**: For very long research queries, set `PERPLEXITY_TIMEOUT_MS` to a higher value

For support, file an issue or visit the official Perplexity community.

Differences from Official Version
---------------------------------

This fork extends the official `@perplexity-ai/mcp-server` with:

-   Custom base URL support for relay/proxy services
-   Enhanced documentation for relay service configuration
-   Optimized for users in regions requiring API proxies

Credits
-------

Based on the official Perplexity MCP Server by Perplexity AI.

Repository
----------

GitHub: https://github.com/ztbytd/perplexity-relay-mcp

* * *
