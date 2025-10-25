---
project: claude-code-templates
stars: 9391
description: CLI tool for configuring and monitoring Claude Code
url: https://github.com/davila7/claude-code-templates
---

Claude Code Templates (aitmpl.com)
==================================

**Ready-to-use configurations for Anthropic's Claude Code.** A comprehensive collection of AI agents, custom commands, settings, hooks, external integrations (MCPs), and project templates to enhance your development workflow.

Browse & Install Components and Templates
-----------------------------------------

**Browse All Templates** - Interactive web interface to explore and install 100+ agents, commands, settings, hooks, and MCPs.

🚀 Quick Installation
---------------------

# Install a complete development stack
npx claude-code-templates@latest --agent development-team/frontend-developer --command testing/generate-tests --mcp development/github-integration

# Browse and install interactively
npx claude-code-templates@latest

# Install specific components
npx claude-code-templates@latest --agent business-marketing/security-auditor
npx claude-code-templates@latest --command performance/optimize-bundle
npx claude-code-templates@latest --setting performance/mcp-timeouts
npx claude-code-templates@latest --hook git/pre-commit-validation
npx claude-code-templates@latest --mcp database/postgresql-integration

What You Get
------------

Component

Description

Examples

**🤖 Agents**

AI specialists for specific domains

Security auditor, React performance optimizer, database architect

**⚡ Commands**

Custom slash commands

`/generate-tests`, `/optimize-bundle`, `/check-security`

**🔌 MCPs**

External service integrations

GitHub, PostgreSQL, Stripe, AWS, OpenAI

**⚙️ Settings**

Claude Code configurations

Timeouts, memory settings, output styles

**🪝 Hooks**

Automation triggers

Pre-commit validation, post-completion actions

**📦 Templates**

Complete project configurations with CLAUDE.md, .claude/\* files and .mcp.json

Framework-specific setups, project best practices

🛠️ Additional Tools
--------------------

Beyond the template catalog, Claude Code Templates includes powerful development tools:

### 📊 Claude Code Analytics

Monitor your AI-powered development sessions in real-time with live state detection and performance metrics.

npx claude-code-templates@latest --analytics

### 💬 Conversation Monitor

Mobile-optimized interface to view Claude responses in real-time with secure remote access.

# Local access
npx claude-code-templates@latest --chats

# Secure remote access via Cloudflare Tunnel
npx claude-code-templates@latest --chats --tunnel

### 🔍 Health Check

Comprehensive diagnostics to ensure your Claude Code installation is optimized.

npx claude-code-templates@latest --health-check

### 🔌 Plugin Dashboard

View marketplaces, installed plugins, and manage permissions from a unified interface.

npx claude-code-templates@latest --plugins

📖 Documentation
----------------

**📚 docs.aitmpl.com** - Complete guides, examples, and API reference for all components and tools.

Contributing
------------

We welcome contributions! **Browse existing templates** to see what's available, then check our contributing guidelines to add your own agents, commands, MCPs, settings, or hooks.

**Please read our Code of Conduct before contributing.**

Attribution
-----------

This collection includes components from multiple sources:

**Agents Collection:**

-   **wshobson/agents Collection** by wshobson - Licensed under MIT License (48 agents)

**Commands Collection:**

-   **awesome-claude-code Commands** by hesreallyhim - Licensed under CC0 1.0 Universal (21 commands)

📄 License
----------

This project is licensed under the MIT License - see the LICENSE file for details.

🔗 Links
--------

-   **🌐 Browse Templates**: aitmpl.com
-   **📚 Documentation**: docs.aitmpl.com
-   **💬 Community**: GitHub Discussions
-   **🐛 Issues**: GitHub Issues

⭐ Star History
--------------

* * *

**⭐ Found this useful? Give us a star to support the project!**
