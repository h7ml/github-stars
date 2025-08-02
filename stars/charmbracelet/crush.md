---
project: crush
stars: 5867
description: The glamourous AI coding agent for your favourite terminal 💘
url: https://github.com/charmbracelet/crush
---

Crush
=====

  

Your new coding bestie, now available in your favourite terminal.  
Your tools, your code, and your workflows, wired into your LLM of choice.

Features
--------

-   **Multi-Model:** choose from a wide range of LLMs or add your own via OpenAI- or Anthropic-compatible APIs
-   **Flexible:** switch LLMs mid-session while preserving context
-   **Session-Based:** maintain multiple work sessions and contexts per project
-   **LSP-Enhanced:** Crush uses LSPs for additional context, just like you do
-   **Extensible:** add capabilities via MCPs (`http`, `stdio`, and `sse`)
-   **Works Everywhere:** first-class support in every terminal on macOS, Linux, Windows (PowerShell and WSL), FreeBSD, OpenBSD, and NetBSD

Installation
------------

Use a package manager:

# Homebrew
brew install charmbracelet/tap/crush

# NPM
npm install -g @charmland/crush

# Arch Linux (btw)
yay -S crush-bin

# Nix
nix run github:numtide/nix-ai-tools#crush

**Nix (NUR)**

Crush is available via NUR in `nur.repos.charmbracelet.crush`.

You can also try out Crush via `nix-shell`:

# Add the NUR channel.
nix-channel --add https://github.com/nix-community/NUR/archive/main.tar.gz nur
nix-channel --update

# Get Crush in a Nix shell.
nix-shell -p '(import <nur> { pkgs = import <nixpkgs> {}; }).repos.charmbracelet.crush'

**Debian/Ubuntu**

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://repo.charm.sh/apt/gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/charm.gpg
echo "deb \[signed-by=/etc/apt/keyrings/charm.gpg\] https://repo.charm.sh/apt/ \* \*" | sudo tee /etc/apt/sources.list.d/charm.list
sudo apt update && sudo apt install crush

**Fedora/RHEL**

echo '\[charm\]
name=Charm
baseurl=https://repo.charm.sh/yum/
enabled=1
gpgcheck=1
gpgkey=https://repo.charm.sh/yum/gpg.key' | sudo tee /etc/yum.repos.d/charm.repo
sudo yum install crush

Or, download it:

-   Packages are available in Debian and RPM formats
-   Binaries are available for Linux, macOS, Windows, FreeBSD, OpenBSD, and NetBSD

Or just install it with Go:

```
go install github.com/charmbracelet/crush@latest
```

Warning

Productivity may increase when using Crush and you may find yourself nerd sniped when first using the application. If the symptoms persist, join the Discord and nerd snipe the rest of us.

Getting Started
---------------

The quickest way to get started is to grab an API key for your preferred provider such as Anthropic, OpenAI, Groq, or OpenRouter and just start Crush. You'll be prompted to enter your API key.

That said, you can also set environment variables for preferred providers.

Environment Variable

Provider

`ANTHROPIC_API_KEY`

Anthropic

`OPENAI_API_KEY`

OpenAI

`OPENROUTER_API_KEY`

OpenRouter

`GEMINI_API_KEY`

Google Gemini

`VERTEXAI_PROJECT`

Google Cloud VertexAI (Gemini)

`VERTEXAI_LOCATION`

Google Cloud VertexAI (Gemini)

`GROQ_API_KEY`

Groq

`AWS_ACCESS_KEY_ID`

AWS Bedrock (Claude)

`AWS_SECRET_ACCESS_KEY`

AWS Bedrock (Claude)

`AWS_REGION`

AWS Bedrock (Claude)

`AZURE_OPENAI_ENDPOINT`

Azure OpenAI models

`AZURE_OPENAI_API_KEY`

Azure OpenAI models (optional when using Entra ID)

`AZURE_OPENAI_API_VERSION`

Azure OpenAI models

### By the Way

Is there a provider you’d like to see in Crush? Is there an existing model that needs an update?

Crush’s default model listing is managed in Catwalk, an community-supported, open source repository of Crush-compatible models, and you’re welcome to contribute.

Configuration
-------------

Crush runs great with no configuration. That said, if you do need or want to customize Crush, configuration can be added either local to the project itself, or globally, with the following priority:

1.  `./.crush.json`
2.  `./crush.json`
3.  `$HOME/.config/crush/crush.json`

Configuration itself is stored as a JSON object:

{
   "this-setting": { }
   "that-setting": { }
}

### LSPs

Crush can use LSPs for additional context to help inform its decisions, just like you would. LSPs can be added manually like so:

{
  "$schema": "https://charm.land/crush.json",
  "lsp": {
    "go": {
      "command": "gopls"
    },
    "typescript": {
      "command": "typescript-language-server",
      "args": \["\--stdio"\]
    },
    "nix": {
      "command": "nil"
    }
  }
}

### MCPs

Crush also supports Model Context Protocol (MCP) servers through three transport types: `stdio` for command-line servers, `http` for HTTP endpoints, and `sse` for Server-Sent Events. Environment variable expansion is supported using `$(echo $VAR)` syntax.

{
  "$schema": "https://charm.land/crush.json",
  "mcp": {
    "filesystem": {
      "type": "stdio",
      "command": "node",
      "args": \["/path/to/mcp-server.js"\],
      "env": {
        "NODE\_ENV": "production"
      }
    },
    "github": {
      "type": "http",
      "url": "https://example.com/mcp/",
      "headers": {
        "Authorization": "$(echo Bearer $EXAMPLE\_MCP\_TOKEN)"
      }
    },
    "streaming-service": {
      "type": "sse",
      "url": "https://example.com/mcp/sse",
      "headers": {
        "API-Key": "$(echo $API\_KEY)"
      }
    }
  }
}

### Ignoring Files

Crush respects `.gitignore` files by default, but you can also create a `.crushignore` file to specify additional files and directories that Crush should ignore. This is useful for excluding files that you want in version control but don't want Crush to consider when providing context.

The `.crushignore` file uses the same syntax as `.gitignore` and can be placed in the root of your project or in subdirectories.

### Whitelisting Tools

By default, Crush will ask you for permission before running tool calls. If you'd like, you can whitelist tools to be executed without prompting you for permissions. Use this with care.

{
  "$schema": "https://charm.land/crush.json",
  "permissions": {
    "allowed\_tools": \[
      "view",
      "ls",
      "grep",
      "edit",
      "mcp\_context7\_get-library-doc"
    \]
  }
}

You can also skip all permission prompts entirely by running Crush with the `--yolo` flag. Be very, very careful with this feature.

### Custom Providers

Crush supports custom provider configurations for both OpenAI-compatible and Anthropic-compatible APIs.

#### OpenAI-Compatible APIs

Here’s an example configuration for Deepseek, which uses an OpenAI-compatible API. Don't forget to set `DEEPSEEK_API_KEY` in your environment.

{
  "$schema": "https://charm.land/crush.json",
  "providers": {
    "deepseek": {
      "type": "openai",
      "base\_url": "https://api.deepseek.com/v1",
      "api\_key": "$DEEPSEEK\_API\_KEY",
      "models": \[
        {
          "id": "deepseek-chat",
          "name": "Deepseek V3",
          "cost\_per\_1m\_in": 0.27,
          "cost\_per\_1m\_out": 1.1,
          "cost\_per\_1m\_in\_cached": 0.07,
          "cost\_per\_1m\_out\_cached": 1.1,
          "context\_window": 64000,
          "default\_max\_tokens": 5000
        }
      \]
    }
  }
}

#### Anthropic-Compatible APIs

Custom Anthropic-compatible providers follow this format:

{
  "$schema": "https://charm.land/crush.json",
  "providers": {
    "custom-anthropic": {
      "type": "anthropic",
      "base\_url": "https://api.anthropic.com/v1",
      "api\_key": "$ANTHROPIC\_API\_KEY",
      "extra\_headers": {
        "anthropic-version": "2023-06-01"
      },
      "models": \[
        {
          "id": "claude-sonnet-4-20250514",
          "name": "Claude Sonnet 4",
          "cost\_per\_1m\_in": 3,
          "cost\_per\_1m\_out": 15,
          "cost\_per\_1m\_in\_cached": 3.75,
          "cost\_per\_1m\_out\_cached": 0.3,
          "context\_window": 200000,
          "default\_max\_tokens": 50000,
          "can\_reason": true,
          "supports\_attachments": true
        }
      \]
    }
  }
}

Logging
-------

Sometimes you need to look at logs. Luckily, Crush logs all sorts of stuff. Logs are stored in `./.crush/logs/crush.log` relative to the project.

The CLI also contains some helper commands to make perusing recent logs easier:

# Print the last 1000 lines
crush logs

# Print the last 500 lines
crush logs --tail 500

# Follow logs in real time
crush logs --follow

Want more logging? Run `crush` with the `--debug` flag, or enable it in the config:

{
  "$schema": "https://charm.land/crush.json",
  "options": {
    "debug": true,
    "debug\_lsp": true
  }
}

Whatcha think?
--------------

We’d love to hear your thoughts on this project. Need help? We gotchu. You can find us on:

-   Twitter
-   Discord
-   Slack
-   The Fediverse

License
-------

FSL-1.1-MIT

* * *

Part of Charm.

Charm热爱开源 • Charm loves open source
