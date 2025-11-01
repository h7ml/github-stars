---
project: CloudBase-AI-ToolKit
stars: 845
description: 🪐 Instantly generate, deploy, and host your full-stack Web apps, mini-programs, databases, and backend services with AI IDE, launch your ideas at lightning speed 💫
url: https://github.com/TencentCloudBase/CloudBase-AI-ToolKit
---

CloudBase AI ToolKit
====================

**Instantly generate, deploy, and host your full-stack Web apps, mini-programs, databases, and backend services with AI IDE—no DevOps required, launch your ideas at lightning speed**

**Languages:** 中文 | **English**

When coding in **Cursor/VSCode GitHub Copilot/WinSurf/CodeBuddy/Augment Code/Claude Code/OpenAI Codex CLI** and other AI programming tools, it automatically helps you generate deployable full-stack apps + mini-programs, and publish them to Tencent CloudBase with one click.

**Full Video Demo**

**Core Capabilities**

**Supported Platforms**

**AI-Powered Development**: AI auto-generates code and architecture  
**Cloud Integration**: One-click access to database, cloud functions, static hosting  
**Rapid Deployment**: Full-stack apps online in minutes

**Web Apps**: Modern frontend + static hosting  
**WeChat Mini-Programs**: Cloud-native mini-program solutions  
**Backend Services**: Cloud database + serverless functions + cloud hosting

Quick Start | IDE Setup | Project Templates | Development Guide | Use Cases | Tutorials | Plugin System | MCP Tools | FAQ

Key Features
------------

-   **AI-Native** - Rule library designed for AI programming tools, generates code following CloudBase best practices
-   **One-Click Deploy** - MCP automated deployment to Tencent CloudBase platform, Serverless architecture without server management
-   **Full-Stack Apps** - Web + Mini-programs + Database + Backend integration, supports multiple app types and backend hosting
-   **Smart Debugging** - AI automatically reviews logs and fixes issues, reducing operational costs
-   **Lightning Fast** - Domestic CDN acceleration, faster access than overseas platforms
-   **Knowledge Retrieval** - Built-in intelligent vector search for CloudBase and WeChat Mini-Program professional knowledge bases
-   **Smart Upgrade** - Auto-detect version differences and provide upgrade guidance, ensuring users always use the latest features
-   **Flexible Workflow** - Support for /spec and /no\_spec commands, intelligently choose development mode based on task complexity

Tip

**Built-in Spec Workflow: Make AI programming more engineering-oriented**

-   Built-in Kiro-style Spec workflow, supports Cursor, Claude Code, and other mainstream AI IDEs
-   Clear requirements, design, and tasks, auto-generates requirements.md, design.md, tasks.md
-   Move beyond "slot machine" vibe coding, development process is controllable and traceable
-   Let AI assist in sorting out requirements, design solutions, and task breakdowns, while humans focus on decision-making and review

**Spec workflow is built into CloudBase AI rules**, download the latest template or let AI download CloudBase AI rules in the current project to get it

* * *

Get Started with CloudBase AI ToolKit
-------------------------------------

### Recommended: CloudBase AI CLI (Simplest)

CloudBase AI CLI is a unified command-line tool that integrates multiple mainstream AI programming tools, supporting built-in models and custom models. It allows you to use Claude Code, OpenAI Codex, aider, Qwen Code, and other AI programming assistants with a simple command, while built-in CloudBase AI Toolkit supports the complete workflow from development to deployment, and can run in any environment.

**Core Advantages:**

-   **Unified Management** - One command to manage multiple AI programming CLI tools, no need to switch between tools
-   **Multi-Model Support** - Support for built-in and custom large models, including Kimi K2, Zhipu GLM-4.5, etc.
-   **One-Click Development & Deployment** - Complete workflow from code generation to cloud deployment, supporting Web apps, mini-programs, and backend services
-   **Everywhere** - Can run in any environment, including mini-program developer tools, VS Code, GitHub Actions, etc.

**One-Click Installation**

# Mac/Linux/Windows WSL
curl https://static.cloudbase.net/cli/install/install.sh -fsS | bash

# Windows PowerShell
irm https://static.cloudbase.net/cli/install/install.ps1 | iex

**Start Using**

tcb ai

On first launch, the configuration wizard will guide you through AI tool selection and configuration. After configuration, you can start using AI tools for assisted development. You can run `tcb ai --setup` later to switch tools and models.

View complete usage documentation | Try Now | Full-Stack Mini-Program Development Case Tutorial

### Other IDE Configuration Methods

If you use other AI IDEs, please refer to the configuration guides below:

* * *

Quick Start
-----------

### 0\. Prerequisites

Install an AI development tool

For example, Cursor | WindSurf | CodeBuddy, etc. See the Supported AI IDE List.

Enable CloudBase Environment

Visit the Tencent CloudBase Console to enable your environment. New users can try it for free.

Install Node.js v18.15.0 or above

Make sure your computer has Node.js v18.15.0 or above. Download the latest version from the Node.js official site.

Optional: Set npm registry

To speed up dependency downloads, set npm registry to Tencent mirror. Run in your terminal:

npm config set registry https://mirrors.cloud.tencent.com/npm/

This will speed up downloads, especially in mainland China.

Optional: Clear npx cache Due to a bug in npx, you may need to clear its cache if you encounter installation issues. Run:

```
npx clear-npx-cache
```

### 1\. Initialize or Enhance Your Project

We provide project templates with best CloudBase practices and AI IDE rules. Two recommended ways:

#### For New Projects

Choose a template and initialize in one click:

-   **WeChat Mini-Program + CloudBase**  
    Download Code ｜ Source Code
    
-   **React Web App + CloudBase**  
    Download Code ｜ Source Code
    
-   **Vue Web App + CloudBase**  
    Download Code ｜ Source Code
    
-   **UniApp Cross-Platform + CloudBase**  
    Download Code ｜ Source Code
    
-   **Universal CloudBase Template**: Not limited to any language or framework, includes CloudBase AI rules and MCP, suitable for any CloudBase project
    
    Download Code ｜ Source Code
    

#### Enhance Existing Projects

If you already have a project, after configuring MCP, just tell the AI "Download CloudBase AI rules in the current project" to automatically download and complete the AI editor rule configuration in your project directory.

If you only want to download specific IDE config files to avoid project file confusion, you can specify the IDE type:

```
Download CloudBase AI rules in the current project, only include Cursor config
Download CloudBase AI rules in the current project, only include WindSurf config
Download CloudBase AI rules in the current project, only include Claude Code config
```

### 2\. Configure Your AI IDE

Tip

If you use a template project, all configs are preset. If not, follow the instructions below to add the required config manually.

All the following tools support CloudBase AI ToolKit. Choose your tool and follow the guide:

Tool

Platform

Guide

CloudBase AI CLI

CLI

Guide

Cursor

Standalone IDE

Guide

WindSurf

Standalone IDE, VSCode, JetBrains

Guide

CodeBuddy

Standalone IDE (CloudBase built-in), VS Code, JetBrains, WeChat DevTools

Guide

CLINE

VS Code

Guide

GitHub Copilot

VS Code

Guide

Trae

Standalone IDE

Guide

Tongyi Lingma

Standalone IDE, VS Code, JetBrains

Guide

RooCode

VS Code

Guide

Baidu Comate

VS Code, JetBrains

Guide

Augment Code

VS Code, JetBrains

Guide

Claude Code

CLI

Guide

Gemini CLI

CLI

Guide

OpenAI Codex CLI

CLI

Guide

OpenCode

CLI

Guide

Qwen Code

CLI

Guide

### 3\. Start Developing

Before you start, just tell the AI:

```
Login to CloudBase
```

The AI will automatically pop up the Tencent Cloud login and environment selection.

To switch environments later, say:

```
Logout CloudBase
```

The AI will clear the local config. You can ask the AI to login again anytime.

After login, you can confirm the AI is connected:

```
Query current CloudBase environment info
```

Describe your requirements to the AI and start developing:

```
Build a two-player online Gomoku game website, support online battle, and deploy it
```

The AI will automatically:

-   Generate frontend and backend code
-   Deploy to CloudBase
-   Return the online access link

If you encounter errors during development, send the error message to the AI for troubleshooting:

```
There was an error: xxxx
```

You can also ask the AI to debug and modify code using cloud function logs:

```
The cloud function code does not meet the requirements, the requirement is xxx, please check the logs and data for debugging and fix it
```

Plugin System
-------------

CloudBase MCP uses a plugin architecture. See detailed docs

### Quick Config

{
  "env": {
    "CLOUDBASE\_MCP\_PLUGINS\_ENABLED": "env,database,functions,hosting"
  }
}

Tutorials
---------

### Articles

#### CloudBase AI CLI Case Studies

-   Develop a Neighborhood Item Recycling Mini-Program with CloudBase AI CLI - Detailed case tutorial showing how to use CloudBase AI CLI to develop a complete mini-program project from scratch

#### Full-Stack Web Apps

-   One-stop development of card flip game with CodeBuddy IDE + CloudBase
-   Develop a WeChat mini-game in 1 hour with CloudBase AI Toolkit
-   AI Coding Power Combo: Cursor + Cloudbase-AI-Toolkit Game Dev
-   Launched a co-op Overcooked game in 2 days
-   CloudBase AI Toolkit: Build a hospital intern scheduling system, goodbye painful excel tables
-   No server, how to cloud deploy full-stack projects
-   Quickly create a programmer's exclusive business card website

#### Full-Stack Mini-Programs

-   I built a "hot words" mini-program with CloudBase AI ToolKit in one day
-   Use AI to create your exclusive "cloud library" mini-program!
-   One person challenges full-stack development resume mini-program
-   I used AI to develop and launch a mini-program: Worry Relief Box
-   From zero to full-stack dev in the AI era: Figma + Cursor + Cloudbase for WeChat mini-programs

### App Projects

-   Resume Assistant Mini-Program
-   Gomoku Online Game
-   Overcooked Co-op Game
-   E-commerce Admin Panel
-   Short Video Mini-Program
-   Dating Mini-Program

### Video Tutorials

-   CloudBase: Use AI to develop an Overcooked game
-   Software 3.0: Best AI Programming Partner CloudBase AI ToolKit, WeChat Mini-Program Example
-   Use AiCoding to challenge full-stack development resume mini-program
-   5 minutes to create a programmer's exclusive business card website locally

* * *

Use Cases
---------

### Case 1: Two-Player Online Gomoku

**Development Process:**

1.  Input requirement: "Build a two-player online Gomoku website, support online battle"
2.  AI generates: Web app + cloud database + real-time data push
3.  Auto-deploy and get access link

**Demo:** Gomoku Game

See development screenshots

Development

Final Result

Supports two-player online battle  
Real-time board sync

### Case 2: AI Pet Mini-Program

**Development Process:**

1.  Input: "Develop a pet-raising mini-program with AI-enhanced interaction"
2.  AI generates: Mini-program + cloud database + AI cloud function
3.  Import to WeChat DevTools to publish

See dev screenshots and mini-program preview

**Dev Screenshots**  
  

**Mini-Program Preview**  
  
  
**Experience QR Code**  

### Case 3: Smart Issue Diagnosis

When an app has issues:

1.  AI automatically checks cloud function logs
2.  Analyzes error causes and generates fix code
3.  Auto redeploys

See smart diagnosis process

  
_AI auto-analyzes logs and generates fixes_

* * *

Why Choose CloudBase?
---------------------

-   **Lightning Fast Deployment**: Domestic nodes, faster than overseas
-   **Stable & Reliable**: Trusted by 3.3 million developers
-   **Developer Friendly**: Full-stack platform for the AI era, supports auto environment config
-   **Cost-Effective**: Serverless architecture, free for new users during development

FAQ
---

For migration, integration, and other common questions, see the FAQ.

Community
---------

Need help or want to share? Join our community!

### WeChat Group

  
_Scan to join the WeChat tech group_

**In the group you can:**

-   Share your AI + CloudBase projects
-   Tech exchange and Q&A
-   Get the latest updates and best practices
-   Join product discussions and suggestions

### Other Channels

Platform

Link

Description

**Docs**

Docs

Full CloudBase docs

**Issue Feedback**

Submit Issue

Bug reports & feature requests

### Community Events

-   **Weekly Tech Sharing**: Best practices for AI + CloudBase
-   **Project Showcases**: Show off your AI-powered projects
-   **Q&A**: Tencent CloudBase team answers questions
-   **Feature Previews**: Try new features first

CloudBase MCP Tools Overview
----------------------------

There are **39 tools** covering environment management, database, cloud functions, hosting, mini-program publishing, and more.

**Full tool docs**: See MCP tool details | Tool spec JSON

### Tool Categories

Category

Count

Main Features

**Env Mgmt**

4

Login, env info, domain mgmt

**Database**

11

Collection mgmt, CRUD, indexes, data models

**Cloud Functions**

9

Create, update, invoke, logs, triggers

**Hosting**

5

File upload, domain config, site deploy

**File Ops**

2

Remote download, cloud storage upload

**Mini-Program**

7

Upload, preview, build, config, debug, QA

**Tool Support**

4

Templates, knowledge search, web search, dialogs

**HTTP Access**

1

HTTP function access

### Tool Highlights

Type

Name

Highlights

**Auth**

`login` / `logout`

One-click CloudBase login, auto env selection

**Env Query**

`envQuery`

**Merged Tool** - env list, info, domain in one

**Database**

`collectionQuery`

**Merged Tool** - existence, detail, list mgmt

**Cloud Functions**

`createFunction`

Full config, auto deps install, trigger setup

**Hosting**

`uploadFiles`

Batch upload, smart ignore, CDN acceleration

**AI Enhanced**

`searchKnowledgeBase`

Vector search CloudBase KB, smart Q&A

### Tool Optimization

We optimized from 40 to 36 tools, added 3 mini-program debug tools, now 39 tools in total, with better experience via merging and full mini-program toolchain.

**Want details for each tool?** See MCP tool docs

Architecture
------------

graph TD
    A\[Developer\] --> B\[AI IDE\]
    B -->|Use| C\[CloudBase AI Rules\]
    C --> D\[Generate Code\]
    B -->|Call| E\[CloudBase MCP\]
    E --> F{Deploy Check}
    F -->|Success| G\[CloudBase Platform\]
    F -->|Fail| H\[Return Logs\]
    H --> I\[AI Fix\]
    I --> E
    G --> J\[Online App\]
    J --> K\[Web/Mini-Program/API\]

Loading

Telemetry
---------

To improve product experience, CloudBase AI ToolKit collects anonymous usage stats:

-   **Collected**: Tool calls, basic env info (OS, Node.js version, etc.)
-   **Privacy**: No code or file paths collected, only for product improvement

Set `CLOUDBASE_MCP_TELEMETRY_DISABLED=true` to disable telemetry.

Contributing
------------

PRs and issues welcome! See our Contributing Guide for how to get involved.

License
-------

MIT © TencentCloudBase

* * *

If you find this project helpful, please give us a Star!
