---
project: answer
stars: 14754
description: A Q&A platform software for teams at any scales. Whether it's a community forum, help center, or knowledge management platform, you can always count on Apache Answer.
url: https://github.com/apache/answer
---

Apache Answer - Build Q&A platform
==================================

A Q&A platform software for teams at any scales. Whether it’s a community forum, help center, or knowledge management platform, you can always count on Answer.

To learn more about the project, visit answer.apache.org.

Screenshots
-----------

Quick start
-----------

### Running with docker

docker run -d -p 9080:80 -v answer-data:/data --name answer apache/answer:1.6.0

For more information, see Installation.

### Plugins

Answer provides a plugin system for developers to create custom plugins and expand Answer’s features. You can find the plugin documentation here.

We value your feedback and suggestions to improve our documentation. If you have any comments or questions, please feel free to contact us. We’re excited to see what you can create using our plugin system!

You can also check out the plugins here.

Building from Source
--------------------

### Prerequisites

-   Golang >= 1.23
-   Node.js >= 20
-   pnpm >= 9
-   mockgen >= 1.6.0
-   wire >= 0.5.0

### Build

# Install wire and mockgen for building. You can run \`make check\` to check if they are installed.
$ make generate
# Install frontend dependencies and build
$ make ui
# Install backend dependencies and build
$ make build

Contributing
------------

Contributions are always welcome!

See CONTRIBUTING for ways to get started.

License
-------

Apache License 2.0
