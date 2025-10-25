---
project: mcp-server-spec-driven-development
stars: 361
description: Spec-Driven Development MCP Server, not just Vibe Coding
url: https://github.com/formulahendry/mcp-server-spec-driven-development
---

Spec-Driven Development MCP Server
==================================

Model Context Protocol (MCP) server that facilitates spec-driven development workflows by providing structured prompts for generating requirements, design documents, and code following a systematic approach.

🎯 Purpose
----------

This MCP server enables developers to follow a structured spec-driven development approach by providing prompts that guide you through:

1.  **Requirements Generation** - Create detailed requirements documents using the EARS (Easy Approach to Requirements Syntax) format
2.  **Design Generation** - Generate design documents based on requirements
3.  **Code Generation** - Generate implementation code based on design documents

✨ Features
----------

-   **Structured Workflow**: Follows a clear progression from **requirements** → **design** → **code**
-   **EARS Format Support**: Uses industry-standard EARS format for requirements documentation
-   **MCP Protocol**: Integrates seamlessly with MCP-compatible tools and environments

🚀 Quick Start
--------------

### Prerequisites

-   Node.js 20+

### Installation

#### VS Code

Install the MCP server in VS Code using below buttons:

Alternatively, you can add configuration in `mcp.json`:

{
    "servers": {
        "spec-driven": {
            "command": "npx",
            "args": \[
                "\-y",
                "mcp-server-spec-driven-development@latest"
            \]
        }
    }
}

#### Cursor, Claude Code

Install the MCP server in Cursor using below button:

Alternatively, you can add configuration in `mcp.json`:

{
    "mcpServers": {
        "spec-driven": {
            "command": "npx",
            "args": \[
                "\-y",
                "mcp-server-spec-driven-development@latest"
            \]
        }
    }
}

📋 Available Prompts
--------------------

### 1\. Generate Requirements Document

-   **Name**: `generate-requirements`
-   **Description**: Generate requirements.md using EARS format
-   **Input**: High-level requirements of the application. Example: 'A Vue.js todo application with task creation, completion tracking, and local storage persistence'
-   **Output**: Structured requirements document in `specs/requirements.md`

### 2\. Generate Design from Requirements

-   **Name**: `generate-design-from-requirements`
-   **Description**: Generate design.md from requirements.md
-   **Input**: Reads from `specs/requirements.md`
-   **Output**: Design document in `specs/design.md`

### 3\. Generate Code from Design

-   **Name**: `generate-code-from-design`
-   **Description**: Generate code from design.md
-   **Input**: Reads from `specs/design.md`
-   **Output**: Implementation code in the root folder

📖 Workflow Example
-------------------

1.  **Start with Requirements**: Use the `generate-requirements` prompt with your initial requirements text
2.  **Create Design**: Use `generate-design-from-requirements` to create a design document based on your requirements
3.  **Generate Code**: Use `generate-code-from-design` to generate implementation code from your design

This creates a traceable path from requirements through design to implementation, ensuring consistency and completeness in your development process.

🤔 Why Spec-Driven Development?
-------------------------------

Moving beyond Vibe Coding to a structured, specification-driven approach brings clarity, consistency, and maintainability to your development workflow. Instead of coding by intuition alone, Spec-Driven Development provides a systematic foundation that scales with your project's complexity.

Learn more about the benefits: Goodbye, Vibe Coding! Hello, Spec-Driven Development MCP Server!
