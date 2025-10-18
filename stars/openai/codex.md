---
project: codex
stars: 48107
description: Lightweight coding agent that runs in your terminal
url: https://github.com/openai/codex
---

`npm i -g @openai/codex`  
or `brew install codex`

**Codex CLI** is a coding agent from OpenAI that runs locally on your computer.  
  
If you want Codex in your code editor (VS Code, Cursor, Windsurf), install in your IDE  
If you are looking for the _cloud-based agent_ from OpenAI, **Codex Web**, go to chatgpt.com/codex

* * *

Quickstart
----------

### Installing and running Codex CLI

Install globally with your preferred package manager. If you use npm:

npm install -g @openai/codex

Alternatively, if you use Homebrew:

brew install codex

Then simply run `codex` to get started:

codex

You can also go to the latest GitHub Release and download the appropriate binary for your platform.

Each GitHub Release contains many executables, but in practice, you likely want one of these:

-   macOS
    -   Apple Silicon/arm64: `codex-aarch64-apple-darwin.tar.gz`
    -   x86\_64 (older Mac hardware): `codex-x86_64-apple-darwin.tar.gz`
-   Linux
    -   x86\_64: `codex-x86_64-unknown-linux-musl.tar.gz`
    -   arm64: `codex-aarch64-unknown-linux-musl.tar.gz`

Each archive contains a single entry with the platform baked into the name (e.g., `codex-x86_64-unknown-linux-musl`), so you likely want to rename it to `codex` after extracting it.

### Using Codex with your ChatGPT plan

Run `codex` and select **Sign in with ChatGPT**. We recommend signing into your ChatGPT account to use Codex as part of your Plus, Pro, Team, Edu, or Enterprise plan. Learn more about what's included in your ChatGPT plan.

You can also use Codex with an API key, but this requires additional setup. If you previously used an API key for usage-based billing, see the migration steps. If you're having trouble with login, please comment on this issue.

### Model Context Protocol (MCP)

Codex can access MCP servers. To configure them, refer to the config docs.

### Configuration

Codex CLI supports a rich set of configuration options, with preferences stored in `~/.codex/config.toml`. For full configuration options, see Configuration.

* * *

### Docs & FAQ

-   **Getting started**
    -   CLI usage
    -   Running with a prompt as input
    -   Example prompts
    -   Memory with AGENTS.md
    -   Configuration
-   **Sandbox & approvals**
-   **Authentication**
    -   Auth methods
    -   Login on a "Headless" machine
-   **Automating Codex**
    -   GitHub Action
    -   TypeScript SDK
    -   Non-interactive mode (`codex exec`)
-   **Advanced**
    -   Tracing / verbose logging
    -   Model Context Protocol (MCP)
-   **Zero data retention (ZDR)**
-   **Contributing**
-   **Install & build**
    -   System Requirements
    -   DotSlash
    -   Build from source
-   **FAQ**
-   **Open source fund**

* * *

License
-------

This repository is licensed under the Apache-2.0 License.
