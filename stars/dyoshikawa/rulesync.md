---
project: rulesync
stars: 254
description: null
url: https://github.com/dyoshikawa/rulesync
---

rulesync
========

A Node.js CLI tool that automatically generates configuration files for various AI development tools from unified AI rule files. Uses the recommended `.rulesync/rules/*.md` structure, with backward compatibility for legacy `.rulesync/*.md` layouts. Also imports existing AI tool configurations into the unified format.

Installation
------------

npm install -g rulesync
# or
pnpm add -g rulesync
# or  
yarn global add rulesync

Getting Started
---------------

### New Project

1.  **Initialize your project:**
    
    # Recommended: Use new organized structure
    npx rulesync init
    
    # Legacy: Use backward-compatible structure
    npx rulesync init --legacy
    
2.  **Edit the generated rule files:**
    
    -   **Recommended**: Edit files in `.rulesync/rules/` directory
    -   **Legacy**: Edit files in `.rulesync/` directory
3.  **Generate tool-specific configuration files:**
    
    npx rulesync generate
    

### Existing Project

If you already have AI tool configurations:

# Import existing configurations (to recommended structure)
npx rulesync import --claudecode  # From CLAUDE.md
npx rulesync import --cursor      # From .cursorrules
npx rulesync import --copilot     # From .github/copilot-instructions.md

# Import to legacy structure (for existing projects)
npx rulesync import --claudecode --legacy
npx rulesync import --cursor --legacy
npx rulesync import --copilot --legacy

# Generate unified configurations
npx rulesync generate

Supported Tools
---------------

rulesync supports both **generation** and **import** for the following AI development tools:

-   **GitHub Copilot Custom Instructions** (`.github/copilot-instructions.md` + `.github/instructions/*.instructions.md`)
-   **Cursor Project Rules** (`.cursor/rules/*.mdc` + `.cursorrules`)
-   **Cline Rules** (`.clinerules/*.md` + `.cline/instructions.md`)
-   **Claude Code Memory** (`./CLAUDE.md` + `.claude/memories/*.md` + **Custom Slash Commands** `.claude/commands/*.md`)
-   **OpenAI Codex CLI** (`codex.md` + `.codex/mcp-config.json` + `.codexignore`)
-   **AugmentCode Rules** (`.augment/rules/*.md`)
-   **Roo Code Rules** (`.roo/rules/*.md` + `.roo/instructions.md`)
-   **Gemini CLI** (`GEMINI.md` + `.gemini/memories/*.md` + **Custom Slash Commands** `.gemini/commands/*.md`)
-   **JetBrains Junie Guidelines** (`.junie/guidelines.md`)
-   **Kiro IDE Custom Steering Documents** (`.kiro/steering/*.md`) + **AI Ignore Files** (`.aiignore`)
-   **Windsurf AI Code Editor** (`.windsurf/rules/*.md` + `.windsurf/mcp.json` + `.codeiumignore`)

Why rulesync?
-------------

### 🔧 **Tool Flexibility**

Team members can freely choose their preferred AI coding tools. Whether it's GitHub Copilot, Cursor, Cline, or Claude Code, each developer can use the tool that maximizes their productivity.

### 📈 **Future-Proof Development**

AI development tools evolve rapidly with new tools emerging frequently. With rulesync, switching between tools doesn't require redefining your rules from scratch.

### 🎯 **Multi-Tool Workflow**

Enable hybrid development workflows combining multiple AI tools:

-   GitHub Copilot for code completion
-   Cursor for refactoring
-   Claude Code for architecture design
-   Cline for debugging assistance
-   Windsurf for comprehensive AI-assisted editing

### 🔓 **No Vendor Lock-in**

Avoid vendor lock-in completely. If you decide to stop using rulesync, you can continue using the generated rule files as-is.

### 🎯 **Consistency Across Tools**

Apply consistent rules across all AI tools, improving code quality and development experience for the entire team.

### 📁 **Organized Structure**

New organized directory structure (`.rulesync/rules/`) keeps rules well-organized, while maintaining full backward compatibility with legacy layouts (`.rulesync/*.md`) for existing projects.

Quick Commands
--------------

# Initialize new project (recommended: organized rules structure)
npx rulesync init

# Initialize with legacy layout (backward compatibility)
npx rulesync init --legacy

# Add new rule file to recommended location
npx rulesync add typescript-rules

# Add rule file to legacy location (for existing projects)
npx rulesync add typescript-rules --legacy

# Import existing configurations (to .rulesync/rules/ by default)
npx rulesync import --cursor

# Import to legacy location (for existing projects)
npx rulesync import --cursor --legacy

# Validate rules
npx rulesync validate

# Generate configurations
npx rulesync generate

# Watch for changes
npx rulesync watch

# Show project status
npx rulesync status

# Add generated files to .gitignore
npx rulesync gitignore

Documentation
-------------

### 📖 Core Documentation

-   **Commands Reference** - Complete CLI commands guide
-   **Configuration Guide** - Rule files and configuration options

### 🛠️ Tool Integrations

-   **Claude Code** - Memory system and custom commands
-   **Cursor** - Rule types and MDC format
-   **GitHub Copilot** - Custom instructions
-   **Cline** - Plain Markdown rules
-   **OpenAI Codex CLI** - Hierarchical memory system
-   **Gemini CLI** - Memory and commands
-   **Windsurf** - Rules and Cascade AI
-   **JetBrains Junie** - Guidelines and IDE integration
-   **Kiro IDE** - Custom steering documents
-   **AugmentCode** - Rule types and configuration
-   **Roo Code** - Instructions and rules

### ⚡ Features

-   **Custom Slash Commands** - Create unified commands for Claude Code and Gemini CLI
-   **MCP Integration** - Model Context Protocol server configuration
-   **Import System** - Import existing AI tool configurations
-   **Rule Validation** - Validate rule files and configuration

### 📚 Guides

-   **Getting Started** - Comprehensive setup guide
-   **Best Practices** - Proven strategies and patterns
-   **Migration Guide** - Migrate from existing AI tool configurations
-   **Troubleshooting** - Common issues and solutions
-   **Real-World Examples** - Practical implementation examples

License
-------

MIT License

Contributing
------------

Issues and Pull Requests are welcome!

For development setup and contribution guidelines, see CONTRIBUTING.md.
