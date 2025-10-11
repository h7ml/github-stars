---
project: mastra
stars: 17279
description: The TypeScript AI agent framework. ⚡ Assistants, RAG, observability. Supports any LLM: GPT-4, Claude, Gemini, Llama.
url: https://github.com/mastra-ai/mastra
---

Mastra
======

Mastra is the Typescript framework for building AI agents and assistants. It’s used by some of the largest companies in the world to build internal AI automation tooling and customer-facing agents.

You can run Mastra on your local machine, bundle it into a Node.js server with Hono, or deploy to a serverless cloud.

The main Mastra features are:

Features

Description

LLM Models

Mastra uses the Vercel AI SDK for model routing, providing a unified interface to interact with any LLM provider including OpenAI, Anthropic, and Google Gemini. You can choose the specific model and provider, and decide whether to stream the response.

Agents

Agents are systems where the language model chooses a sequence of actions. In Mastra, agents provide LLM models with tools, workflows, and synced data. Agents can call your own functions or APIs of third-party integrations and access knowledge bases you build.

Tools

Tools are typed functions that can be executed by agents or workflows, with built-in integration access and parameter validation. Each tool has a schema that defines its inputs, an executor function that implements its logic, and access to configured integrations.

Workflows

Workflows are durable graph-based state machines. They have loops, branching, wait for human input, embed other workflows, do error handling, retries, parsing and so on. They can be built in code or with a visual editor. Each step in a workflow has built-in OpenTelemetry tracing.

RAG

Retrieval-augmented generation (RAG) lets you construct a knowledge base for agents. RAG is an ETL pipeline with specific querying techniques, including chunking, embedding, and vector search.

Integrations

In Mastra, integrations are auto-generated, type-safe API clients for third-party services that can be used as tools for agents or steps in workflows.

Evals

Evals are automated tests that evaluate LLM outputs using model-graded, rule-based, and statistical methods. Each eval returns a normalized score between 0-1 that can be logged and compared. Evals can be customized with your own prompts and scoring functions.

Quick Start
-----------

### Prerequisites

-   Node.js (v20.0+)

Get an LLM provider API key
---------------------------

If you don't have an API key for an LLM provider, you can get one from the following services:

-   OpenAI
-   Anthropic
-   Google Gemini
-   Groq
-   Cerebras

If you don't have an account with these providers, you can sign up and get an API key. Anthropic require a credit card to get an API key. Some OpenAI models and Gemini do not and have a generous free tier for its API.

Create a new project
--------------------

The easiest way to get started with Mastra is by using `create-mastra`. This CLI tool enables you to quickly start building a new Mastra application, with everything set up for you.

npx create-mastra@latest

### Run the script

Finally, run `mastra dev` to open the Mastra playground.

npm run dev

If you're using Anthropic, set the `ANTHROPIC_API_KEY`. If you're using Gemini, set the `GOOGLE_GENERATIVE_AI_API_KEY`.

MCP Server (@mastra/mcp-docs-server)
====================================

Use our MCP server @mastra/mcp-docs-server to teach your LLM how to use Mastra.

This is a Model Context Protocol (MCP) server that provides AI assistants with direct access to Mastra.ai's complete knowledge base.

In Cursor
---------

Create or update .cursor/mcp.json in your project root:

### MacOS/Linux

```
{
  "mcpServers": {
    "mastra": {
      "command": "npx",
      "args": ["-y", "@mastra/mcp-docs-server"]
    }
  }
}
```

### Windows

```
{
  "mcpServers": {
    "mastra": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@mastra/mcp-docs-server"]
    }
  }
}
```

This will make all Mastra documentation tools available in your Cursor workspace. Note that the MCP server wont be enabled by default. You'll need to go to Cursor settings -> MCP settings and click "enable" on the Mastra MCP server.

In Windsurf
-----------

Create or update ~/.codeium/windsurf/mcp\_config.json:

### MacOS/Linux

```
{
  "mcpServers": {
    "mastra": {
      "command": "npx",
      "args": ["-y", "@mastra/mcp-docs-server"]
    }
  }
}
```

For more installation options visit https://www.npmjs.com/package/@mastra/mcp-docs-server

### In Claude Code

After installing Claude Code run:

claude mcp add mastra-docs -- npx -y @mastra/mcp-docs-server

Contributing
------------

Looking to contribute? All types of help are appreciated, from coding to testing and feature specification.

If you are a developer and would like to contribute with code, please open an issue to discuss before opening a Pull Request.

Information about the project setup can be found in the development documentation

Support
-------

We have an open community Discord. Come and say hello and let us know if you have any questions or need any help getting things running.

It's also super helpful if you leave the project a star here at the top of the page

Security
--------

We are committed to maintaining the security of this repo and of Mastra as a whole. If you discover a security finding we ask you to please responsibly disclose this to us at security@mastra.ai and we will get back to you.
