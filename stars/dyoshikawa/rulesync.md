---
project: rulesync
stars: 271
description: null
url: https://github.com/dyoshikawa/rulesync
---

rulesync
========

A Node.js CLI tool that automatically generates configuration files for various AI development tools from unified AI rule files. Features selective generation, comprehensive import/export capabilities, and supports 19+ AI development tools with rules, commands, MCP, ignore files, and subagents. Uses the recommended `.rulesync/rules/*.md` structure, with full backward compatibility for legacy `.rulesync/*.md` layouts.

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
    
    # Generate all features for all tools (recommended)
    npx rulesync generate --targets \* --features \*
    
    # Generate specific features for specific tools
    npx rulesync generate --targets copilot,cursor,cline --features rules,commands
    npx rulesync generate --targets claudecode --features rules,commands,subagents
    
    # Generate only rules (fastest option)
    npx rulesync generate --targets \* --features rules
    
    # Generate subagents for Claude Code
    npx rulesync generate --targets claudecode --features subagents
    
    # Generate specific tools with all features
    npx rulesync generate --targets claudecode,cursor --features \*
    

### Existing Project

If you already have AI tool configurations:

# Import existing configurations (to recommended structure)
npx rulesync import --targets claudecode    # From CLAUDE.md
npx rulesync import --targets cursor        # From .cursorrules
npx rulesync import --targets copilot       # From .github/copilot-instructions.md
npx rulesync import --targets amazonqcli    # From .amazonq/rules/\*.md
npx rulesync import --targets qwencode      # From QWEN.md
npx rulesync import --targets opencode      # From AGENTS.md
npx rulesync import --targets agentsmd      # From AGENTS.md + .agents/memories/\*.md
npx rulesync import --targets windsurf      # From .windsurf/rules/

# Import to legacy structure (for existing projects)
npx rulesync import --targets claudecode --legacy
npx rulesync import --targets cursor --legacy
npx rulesync import --targets copilot --legacy

# Generate unified configurations with all features
npx rulesync generate --targets \* --features \*

Supported Tools
---------------

rulesync supports both **generation** and **import** for **19 AI development tools**:

### Core AI Development Tools

-   **GitHub Copilot** - Custom Instructions (`.github/copilot-instructions.md` + `.github/instructions/*.instructions.md`)
-   **Cursor** - Project Rules (`.cursor/rules/*.mdc` + `.cursorrules` + custom commands)
-   **Cline** - Rules & Instructions (`.clinerules/*.md` + `.cline/instructions.md`)
-   **Claude Code** - Memory System (`CLAUDE.md` + `.claude/memories/*.md` + **Custom Slash Commands** `.claude/commands/*.md` + **🤖 Subagents** `.claude/subagents/*.md`)
-   **Amazon Q Developer CLI** - Rules & Context (`.amazonq/rules/*.md` + `.amazonq/mcp.json` + built-in commands + context management)
-   **Windsurf** - AI Code Editor (`.windsurf/rules/*.md` + `.windsurf/mcp.json` + `.codeiumignore`)

### Specialized AI Tools

-   **OpenCode** - Terminal AI (`AGENTS.md` + `opencode.json` + **🔐 Permission-Based Security**)
-   **OpenAI Codex CLI** - Advanced CLI (`AGENTS.md` + **File Splitting with XML** + `.codex/memories/*.md` + `.codex/mcp-config.json`)
-   **AugmentCode** - IDE Integration (`.augment/rules/*.md` + current & legacy formats)
-   **Roo Code** - VSCode Extension (`.roo/rules/*.md` + `.roo/instructions.md`)
-   **Gemini CLI** - Google AI (`GEMINI.md` + `.gemini/memories/*.md` + **Custom Slash Commands** `.gemini/commands/*.md`)
-   **Qwen Code** - Qwen Models (`QWEN.md` + `.qwen/memories/*.md` + **Git-Aware Filtering** + `.qwen/settings.json`)

### IDE-Integrated AI

-   **JetBrains Junie** - IntelliJ Family (`.junie/guidelines.md` + IDE integration)
-   **Kiro IDE** - AWS IDE (`.kiro/steering/*.md` + **AI Ignore Files** `.aiignore`)

### Standardized Formats

-   **AgentsMd** - Universal Format (`AGENTS.md` + `.agents/memories/*.md` for standardized AI agent instructions)
-   **AugmentCode Legacy** - Backward compatibility (`.augment-guidelines` format support)

Why rulesync?
-------------

### 🔧 **Tool Flexibility**

Team members can freely choose their preferred AI coding tools. Whether it's GitHub Copilot, Cursor, Cline, or Claude Code, each developer can use the tool that maximizes their productivity.

### 📈 **Future-Proof Development**

AI development tools evolve rapidly with new tools emerging frequently. With rulesync, switching between tools doesn't require redefining your rules from scratch.

### 🎯 **Multi-Tool Workflow**

Enable hybrid development workflows combining multiple AI tools:

-   **GitHub Copilot** for code completion and inline suggestions
-   **Cursor** for intelligent refactoring and project-wide changes
-   **Claude Code** for architecture design and complex problem solving
-   **Cline** for autonomous debugging and file system operations
-   **Amazon Q Developer CLI** for comprehensive chat-based development with built-in commands and MCP integration
-   **OpenCode** for secure terminal-based development with granular permission controls
-   **Windsurf** for comprehensive AI-assisted editing with Cascade AI
-   **Gemini CLI** for Google AI integration and custom workflows

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
npx rulesync import --targets cursor
npx rulesync import --targets amazonqcli
npx rulesync import --targets qwencode
npx rulesync import --targets agentsmd
npx rulesync import --targets claudecode  # Imports subagents too

# Import to legacy location (for existing projects)
npx rulesync import --targets cursor --legacy
npx rulesync import --targets amazonqcli --legacy
npx rulesync import --targets windsurf --legacy

# Validate rules
npx rulesync validate

# Generate all features for all tools (new preferred syntax)
npx rulesync generate --targets \* --features \*

# Generate specific features for specific tools
npx rulesync generate --targets copilot,cursor,cline --features rules,mcp
npx rulesync generate --targets claudecode --features rules,subagents

# Generate only rules (no MCP, ignore files, or subagents)
npx rulesync generate --targets \* --features rules

# Generate subagents for supported tools
npx rulesync generate --targets claudecode --features subagents

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
-   **Amazon Q Developer CLI** - Rules, MCP, and built-in commands
-   **OpenCode** - Permission-based configuration and MCP integration
-   **OpenAI Codex CLI** - Advanced file splitting with XML document references and memory files
-   **Gemini CLI** - Memory and commands
-   **Windsurf** - Rules and Cascade AI
-   **JetBrains Junie** - Guidelines and IDE integration
-   **Kiro IDE** - Custom steering documents
-   **AugmentCode** - Rule types and configuration
-   **Roo Code** - Instructions and rules
-   **Qwen Code** - Memory system with git-aware filtering
-   **AgentsMd** - Standardized AI agent instructions

### ⚡ Features

-   **Selective Generation** - Generate only what you need with --features option
-   **Custom Slash Commands** - Create unified commands for Claude Code and Gemini CLI
-   **MCP Integration** - Model Context Protocol server configuration
-   **Subagents System** - Create specialized AI assistants and workflows
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
