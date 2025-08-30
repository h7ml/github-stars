---
project: claude-setup
stars: 238
description: null
url: https://github.com/AizenvoltPrime/claude-setup
---

Claude Code Setup
=================

> A comprehensive configuration setup for Claude Code with Model Context Protocol (MCP) servers, custom commands, and automated workflows.

Table of Contents
-----------------

-   Overview
-   Quick Start
-   Prerequisites
-   Installation
-   Features
-   Commands
-   Configuration
-   Troubleshooting
-   Contributing
-   License

Overview
--------

This project provides a pre-configured environment for Claude Code with enhanced capabilities through:

-   **MCP Servers**: Context7, Puppeteer, Sequential Thinking, DeepWiki
-   **Custom Commands**: Intelligent workflows for commits, tasks, and problem-solving
-   **Hook System**: Automated directory management and workflow triggers
-   **Structured Workflows**: Organized task management with reporting and planning

Quick Start
-----------

# 1. Install dependencies
pip install uv

# 2. Clone this configuration
git clone <your-repo\> claude-setup
cd claude-setup

# 3. Start using commands
/task\_hard implement user authentication

Prerequisites
-------------

Before using this setup, ensure you have:

-   **Claude Code**: Installed and configured
-   **Python 3.8+**: For hook script execution
-   **uv**: Package manager for Python script execution
-   **Node.js**: For MCP server functionality (npx)

### Installation

#### 1\. Install uv (if not already installed)

# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# After installation, open a new terminal and verify:
uv --version

#### 2\. Setup Configuration

# Copy configuration files to your project
cp -r .claude/ /your/project/
cp .mcp.json /your/project/

# Ensure hook permissions
chmod +x .claude/hooks/task\_hard\_prep\_hook.py

Features
--------

### 🎯 Custom Commands

-   **`/commit`**: Intelligent commit workflow with conventional standards
-   **`/code-review`**: Reviews uncommitted changes before committing
-   **`/task_hard`**: Advanced problem-solving with automated directory management
-   **`/task_easy`**: Simplified task workflow for lighter needs

### 🤖 Custom Agents

-   **`investigator`**: Expert code investigator that tracks down related code to problems
    -   Uses sequential thinking and advanced search tools
    -   Prioritizes files containing specified keywords during investigation
    -   Generates comprehensive INVESTIGATION\_REPORT.md files with keyword match analysis
    -   Integrated with task\_hard workflow
-   **`code-flow-mapper`**: Expert code flow mapper that traces execution paths and file interconnections
    -   Maps code flow and analyzes file relationships
    -   Generates FLOW\_REPORT.md files
-   **`planner`**: Expert planner that takes into account investigation and flow analysis reports
    -   Creates detailed plans that solve all problems
    -   Generates comprehensive PLAN.md files
-   **`code-reviewer`**: Senior code review specialist for quality assurance
    -   Reviews changes for quality, security, and maintainability
    -   Provides prioritized feedback (critical, warnings, suggestions)
    -   Checks for best practices and potential issues

### 🔌 MCP Servers

-   **Context7**: Library documentation and code context
-   **Puppeteer**: Browser automation and web scraping
-   **Sequential Thinking**: Advanced reasoning and problem-solving
-   **DeepWiki**: Repository documentation fetching

### ⚡ Hook System

-   **UserPromptSubmit**: Automatic directory creation for task workflows
-   **Extensible**: Easy to add custom hooks for workflow automation
-   **Documentation**: Hooks Reference | Hooks Guide

Commands
--------

### `/task_hard` - Advanced Problem Solving

Automated workflow for complex problem-solving with structured investigation and planning.

**Usage:**

/task\_hard \[problem description\]

**Features:**

-   ✅ Automatic `claude-instance-{id}` directory creation
-   ✅ Sequential thinking for complex reasoning
-   ✅ Multi-agent workflow with specialized subagents
-   ✅ Automatically extracts keywords from problems when not explicitly provided
-   ✅ Prioritizes files containing relevant keywords during codebase analysis
-   ✅ Codebase investigation with INVESTIGATION\_REPORT.md generation
-   ✅ Code flow mapping with FLOW\_REPORT.md analysis
-   ✅ Structured planning with PLAN.md output
-   ✅ Incremental instance numbering
-   ✅ Edge case handling and best practices focus

**Examples:**

# Basic usage - keywords automatically detected
/task\_hard implement user authentication system

# Advanced usage - explicit keywords for better targeting
/task\_hard implement user dashboard
Keywords: dashboard, user, profile, settings

# Complex problem with specific focus areas
/task\_hard fix payment processing bugs
Keywords: payment, stripe, transaction, webhook

**Keyword Usage:**

-   **Automatic Detection**: The system automatically identifies relevant keywords from your problem description
-   **Manual Keywords**: Add Keywords: keyword1, keyword2, keyword3 on a new line after your problem statement for precise file targeting
-   **Priority Investigation**: Files containing these keywords are investigated first and flagged as high-priority in reports
-   **Better Results**: Explicit keywords help focus investigation on the most relevant code areas

**Workflow:**

1.  🔧 Hook detects `/task_hard` prompt
2.  📁 Creates `claude-code-storage/claude-instance-{id}/` directory
3.  🏷️ Extracts or detects relevant keywords from problem statement
4.  🔍 Investigator agent analyzes codebase using sequential thinking with keyword-based file prioritization
5.  📄 Generates comprehensive INVESTIGATION\_REPORT.md with keyword match analysis and related files
6.  🗺️ Code-flow-mapper agent traces execution paths and file interconnections
7.  📊 Generates detailed FLOW\_REPORT.md with code relationships
8.  📋 Planner agent reads both reports and creates comprehensive PLAN.md
9.  👤 User reviews and approves plan

### `/code-review` - Automated Code Review

Initiates code-reviewer agent to analyze uncommitted changes only.

**Usage:**

/code-review

**Features:**

-   Focuses exclusively on uncommitted changes
-   Reviews modified files for quality, security, and maintainability
-   Provides prioritized feedback:
    -   🚨 Critical issues (must fix)
    -   ⚠️ Warnings (should fix)
    -   💡 Suggestions (consider improving)
-   Includes specific fix examples

**Example:**

# After making changes
/code-review
# Fix any critical issues
/commit

### `/commit` - Intelligent Commits

Streamlined commit workflow following conventional commit standards.

**Features:**

-   Diff analysis and change summarization
-   Conventional commit message formatting
-   Clean, focused commits

**Important:** Run `/code-review` before committing to ensure code quality.

**Example:**

# Review changes first
/code-review
# After fixing issues
/commit

### `/task_easy` - Simplified Tasks

Lightweight task workflow for simpler problem-solving needs.

Configuration
-------------

### Working Directory Considerations

**Important:** When using this configuration in projects with nested directory structures (e.g., monorepos with `backend/`, `frontend/` subdirectories), you may start Claude Code from a subdirectory rather than the project root.

**Impact on hooks:**

-   Hooks using relative paths may fail if the working directory is not the project root
-   The `/status` command shows the current working directory
-   Use `$CLAUDE_PROJECT_DIR` environment variable or relative paths to ensure hooks work correctly

**Recommended hook configuration for nested projects:**

{
  "hooks": {
    "UserPromptSubmit": \[
      {
        "hooks": \[
          {
            "type": "command",
            "command": "uv run $CLAUDE\_PROJECT\_DIR/.claude/hooks/task\_hard\_prep\_hook.py"
          }
        \]
      }
    \]
  }
}

### Directory Structure

```
claude-setup/
├── .claude/
│   ├── settings.json          # Permissions and hook configuration
│   ├── agents/
│   │   ├── investigator.md    # Code investigation agent
│   │   ├── code-flow-mapper.md # Code flow mapping agent
│   │   ├── planner.md         # Planning agent
│   │   └── code-reviewer.md   # Code review specialist
│   ├── hooks/
│   │   └── task_hard_prep_hook.py  # Auto directory creation
│   └── commands/
│       ├── task_hard.md     # Advanced task workflow
│       ├── task_easy.md       # Simple task workflow
│       ├── code-review.md     # Code review workflow
│       └── commit.md          # Commit workflow
├── .mcp.json                  # MCP server configuration
├── claude-code-storage/       # Auto-generated task directories
└── README.md
```

### Settings Configuration

The `.claude/settings.json` file contains:

{
  "permissions": {
    "allow": \["WebFetch(domain:docs.anthropic.com)", ...\],
    "deny": \[...\]
  },
  "hooks": {
    "UserPromptSubmit": \[
      {
        "hooks": \[
          {
            "type": "command",
            "command": "uv run .claude/hooks/task\_hard\_prep\_hook.py"
          }
        \]
      }
    \]
  },
  "enabledMcpjsonServers": \["context7", "puppeteer", "sequential-thinking", ...\]
}

### MCP Configuration

The `.mcp.json` file defines server configurations:

{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": \["@context7/claude-dev", "\--minTokens", "1000"\]
    },
    "puppeteer": {
      "command": "npx",
      "args": \["@puppeteer/claude-dev"\]
    }
  }
}

Troubleshooting
---------------

### Common Issues

**Hook not triggering:**

-   Ensure `uv` is installed and in PATH
-   Check script permissions: `chmod +x .claude/hooks/task_hard_prep_hook.py`
-   Verify hook configuration in `.claude/settings.json`

**Hook path issues when working directory is not project root:**

When Claude Code's working directory is a subdirectory (e.g., `backend/` or `frontend/`), hooks may fail to find the correct path. This commonly happens in new projects with nested layouts.

**Solutions:**

1.  **Use environment variable (Recommended for cross-platform):**
    
    "command": "uv run $CLAUDE\_PROJECT\_DIR/.claude/hooks/task\_hard\_prep\_hook.py"
    
2.  **Use relative path from project root:**
    
    "command": "uv run ../../.claude/hooks/task\_hard\_prep\_hook.py"
    
3.  **Use absolute path (if known):**
    
    "command": "uv run /full/path/to/project/.claude/hooks/task\_hard\_prep\_hook.py"
    

**Note:** The `$CLAUDE_PROJECT_DIR` environment variable may not work on all systems. If you encounter issues, use the relative path approach or place the `.claude` directory in your working directory.

**Directory creation fails:**

-   Check file system permissions
-   Ensure `claude-code-storage/` parent directory exists
-   Review hook script logs for error details

**MCP servers not loading:**

-   Verify Node.js and npx are installed
-   Check `.mcp.json` configuration syntax
-   Ensure MCP packages are available via npx

### Debug Mode

Enable debug mode for detailed logging:

claude --debug

Contributing
------------

1.  Fork the repository
2.  Create a feature branch: `git checkout -b feature-name`
3.  Make your changes and test thoroughly
4.  Submit a pull request with detailed description

### Adding Custom Hooks

1.  Create script in `.claude/hooks/`
2.  Make executable: `chmod +x .claude/hooks/your_hook.py`
3.  Add configuration to `.claude/settings.json`
4.  Test with sample inputs

**Resources:**

-   Hooks Reference Documentation
-   Hooks Implementation Guide

Star History
------------

License
-------

This configuration setup is provided as-is for Claude Code enhancement.

* * *

**Need help?** Check the documentation:

-   Claude Code Main Docs
-   Hooks Reference
-   Hooks Implementation Guide

Or open an issue for project-specific questions.
