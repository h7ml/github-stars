---
project: deno
stars: 104194
description: A modern runtime for JavaScript and TypeScript.
url: https://github.com/denoland/deno
---

Deno
====

Deno (/ˈdiːnoʊ/, pronounced `dee-no`) is a JavaScript, TypeScript, and WebAssembly runtime with secure defaults and a great developer experience. It's built on V8, Rust, and Tokio.

Learn more about the Deno runtime in the documentation.

Installation
------------

Install the Deno runtime on your system using one of the commands below. Note that there are a number of ways to install Deno - a comprehensive list of installation options can be found here.

Shell (Mac, Linux):

curl -fsSL https://deno.land/install.sh | sh

PowerShell (Windows):

irm https://deno.land/install.ps1 | iex

Homebrew (Mac):

brew install deno

Chocolatey (Windows):

choco install deno

WinGet (Windows):

winget install \--id\=DenoLand.Deno

### Build and install from source

Complete instructions for building Deno from source can be found here.

Your first Deno program
-----------------------

Deno can be used for many different applications, but is most commonly used to build web servers. Create a file called `server.ts` and include the following TypeScript code:

Deno.serve((\_req: Request) \=> {
  return new Response("Hello, world!");
});

Run your server with the following command:

deno run --allow-net server.ts

This should start a local web server on http://localhost:8000.

Learn more about writing and running Deno programs in the docs.

Additional resources
--------------------

-   **Deno Docs**: official guides and reference docs for the Deno runtime, Deno Deploy, and beyond.
-   **Deno Standard Library**: officially supported common utilities for Deno programs.
-   **JSR**: The open-source package registry for modern JavaScript and TypeScript
-   **Developer Blog**: Product updates, tutorials, and more from the Deno team.

Contributing
------------

We appreciate your help! To contribute, please read our contributing instructions.
