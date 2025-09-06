---
project: rulesync
stars: 289
description: null
url: https://github.com/dyoshikawa/rulesync
---

rulesync
========

Important

Starting from v0.68.0, we have implemented a major refactoring by the maintainers. If the behavior is unstable, please specify and run v0.67.0. Additionally, as a result, we have deprecated some features, support, and backward compatibility. If you wish to see any of these features restored, please create an Issue. As background, this tool has been built using Vibe Coding up until now, but the codebase had become extremely complex, making future extensions difficult, so we had to discard the existing codebase. We plan to continue active development going forward. Thank you for your continued support of rulesync.

A Node.js CLI tool that automatically generates configuration files for various AI development tools from unified AI rule files. Features selective generation, comprehensive import/export capabilities, and supports 19+ AI development tools with rules, commands, MCP, ignore files, and subagents. Uses the recommended `.rulesync/rules/*.md` structure, with full backward compatibility for legacy `.rulesync/*.md` layouts.

Installation
------------

npm install -g rulesync
# or
pnpm add -g rulesync
# or  
yarn global add rulesync
# or
bun add -g rulesync

# And then
rulesync --version
rulesync --help

Getting Started
---------------

# Create necessary directories and sample rule files
npx rulesync init
# Create a new configuration file
npx rulesync config --init

On the other hand, if you already have AI tool configurations:

# Import existing files (to .rulesync/\*\*/\*)
npx rulesync import --targets claudecode    # From CLAUDE.md
npx rulesync import --targets cursor        # From .cursorrules
npx rulesync import --targets copilot       # From .github/copilot-instructions.md
npx rulesync import --targets claudecode --features rules,mcp,commands,subagents

# And more tool supports

# Generate unified configurations with all features
npx rulesync generate --targets "\*" --features "\*"

Supported Tools and Features
----------------------------

rulesync supports both **generation** and **import** for All of the major AI coding tools:

Tool

rules

ignore

mcp

commands

subagents

AGENTS.md

✅

Claude Code

✅

✅

✅

✅

Codex CLI

✅

✅

Gemini CLI

✅

✅

✅

GitHub Copilot

✅

✅

Cursor

✅

✅

✅

OpenCode

✅

Cline

✅

✅

✅

Roo Code

✅

✅

✅

✅

Qwen Code

✅

✅

Kiro IDE

✅

✅

Amazon Q Developer CLI

✅

✅

JetBrains Junie

✅

✅

AugmentCode

✅

✅

Windsurf

✅

✅

Why rulesync?
-------------

### 🔧 **Tool Flexibility**

Team members can freely choose their preferred AI coding tools. Whether it's GitHub Copilot, Cursor, Cline, or Claude Code, each developer can use the tool that maximizes their productivity.

### 📈 **Future-Proof Development**

AI development tools evolve rapidly with new tools emerging frequently. With rulesync, switching between tools doesn't require redefining your rules from scratch.

### 🎯 **Multi-Tool Workflow**

Enable hybrid development workflows combining multiple AI tools.

### 🔓 **No Lock-in**

Avoid lock-in completely. If you decide to stop using rulesync, you can continue using the generated rule files as-is.

### 🎯 **Consistency Across Tools**

Apply consistent rules across all AI tools, improving code quality and development experience for the entire team.

Quick Commands
--------------

# Initialize new project (recommended: organized rules structure)
npx rulesync init

# Import existing configurations (to .rulesync/rules/ by default)
npx rulesync import --targets claudecode --features rules,ignore,mcp,commands,subagents

# Generate all features for all tools (new preferred syntax)
npx rulesync generate --targets "\*" --features "\*"

# Generate specific features for specific tools
npx rulesync generate --targets copilot,cursor,cline --features rules,mcp
npx rulesync generate --targets claudecode --features rules,subagents

# Generate only rules (no MCP, ignore files, commands, or subagents)
npx rulesync generate --targets "\*" --features rules

# Add generated files to .gitignore
npx rulesync gitignore

Configuration
-------------

You can configure rulesync by creating a `rulesync.jsonc` file in the root of your project.

Example:

// rulesync.jsonc
{
  // List of tools to generate configurations for. You can specify "\*" to generate all tools.
  "targets": \["cursor", "claudecode", "geminicli", "opencode", "codexcli"\],

  // Features to generate. You can specify "\*" to generate all features.
  "features": \["rules", "ignore", "mcp", "commands", "subagents"\],
  
  // Base directory or directories for generation
  "baseDir": ".",
  
  // Delete existing files before generating
  "delete": true,

  // Verbose output
  "verbose": false
}

Each File Format
----------------

### `rulesync/rules/*.md`

Example:

\---
root: true # true that is less than or equal to one file for overview such as AGENTS.md, false for details such as .agents/memories/\*.md
targets: \["\*"\] # \* = all, or specific tools
description: "rulesync project overview and development guidelines for unified AI rules management CLI tool"
globs: \["\*\*/\*"\] # file patterns to match (e.g., \["\*.md", "\*.txt"\])
cursor: # for cursor-specific rules
  alwaysApply: true
  description: "rulesync project overview and development guidelines for unified AI rules management CLI tool"
  globs: \["\*"\]
\---

\# rulesync Project Overview

This is rulesync, a Node.js CLI tool that automatically generates configuration files for various AI development tools from unified AI rule files. The project enables teams to maintain consistent AI coding assistant rules across multiple tools.

...

### `rulesync/commands/*.md`

Example:

\---
description: 'Review a pull request' # command description
targets: \["\*"\] # \* = all, or specific tools
\---

target\_pr = $ARGUMENTS

If target\_pr is not provided, use the PR of the current branch.

Execute the following in parallel:

...

### `rulesync/subagents/*.md`

Example:

\---
name: planner # subagent name
targets: \["\*"\] # \* = all, or specific tools
description: \>- # subagent description
  This is the general-purpose planner. The user asks the agent to plan to
  suggest a specification, implement a new feature, refactor the codebase, or
  fix a bug. This agent can be called by the user explicitly only.
claudecode: # for claudecode-specific rules
  model: opus # opus, sonnet, haiku or inherit
\---

You are the planner for any tasks.

Based on the user's instruction, create a plan while analyzing the related files. Then, report the plan in detail. You can output files to @tmp/ if needed.

Attention, again, you are just the planner, so though you can read any files and run any commands for analysis, please don't write any code.

### `.rulesync/.mcp.json`

Example:

{
  "mcpServers": {
    "serena": {
      "type": "stdio",
      "command": "uvx",
      "args": \[
        "\--from",
        "git+https://github.com/oraios/serena",
        "serena",
        "start-mcp-server",
        "\--context",
        "ide-assistant",
        "\--enable-web-dashboard",
        "false",
        "\--project",
        "."
      \],
      "env": {}
    },
    "context7": {
      "type": "stdio",
      "command": "npx",
      "args": \[
        "\-y",
        "@upstash/context7-mcp"
      \],
      "env": {}
    }
  }
}

### `.rulesyncignore`

Example:

tmp/
credentials/

License
-------

MIT License

Contributing
------------

Issues and Pull Requests are welcome!

For development setup and contribution guidelines, see CONTRIBUTING.md.
