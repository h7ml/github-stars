---
project: artus-cli
stars: 49
description: CLI framework with modern features
url: https://github.com/artus-cli/artus-cli
---

@artus-cli/artus-cli
====================

`artus-cli` aims to provide a modern command-line-apps framework.

-   **Powerful**, powered by artusjs.
-   **Modern**, TypeScript and IoC ready.
-   **Customizable**, command inheritance, and support Plugin and Framework (wrap it as a upper layer CLI).
-   **Community**, enjoy the eco-friendliness, use the same plugin with your artusjs web apps.

How it looks
------------

import { DefineCommand, Option, Command } from '@artus-cli/artus-cli';

@DefineCommand({
  command: 'dev',
  description: 'Run the development server',
  alias: \[ 'd' \],
})
export class DevCommand extends Command {
  @Option({
    alias: 'p',
    default: 3000,
    description: 'server port',
  })
  port: number;

  async run() {
    console.info('port: %s', this.port);
  }
}

Run it with:

$ my-cli dev --port 8080

Document
--------

https://artus-cli.github.io
