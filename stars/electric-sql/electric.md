---
project: electric
stars: 7047
description: Sync little subsets of your Postgres data into local apps and services.
url: https://github.com/electric-sql/electric
---

Electric
========

Your Postgres data, in sync, wherever you need it.

**Table of Contents:**

-   Quick links
-   What is Electric?
-   Getting Started
-   HTTP API Docs
-   Developing Electric
    -   Mac setup
-   Contributing
-   Support

Quick links
-----------

-   Quickstart
-   About
-   Docs
-   Examples

What is Electric?
-----------------

Electric provides an HTTP API for syncing Shapes of data from Postgres. This can be used directly or via client libraries and integrations.

### This looks a bit different than the last time I visited?

We started a clean rebuild of the sync engine in July 2024. One that's informed by the lessons learned building the previous system. See James' blog post for background on the change.

Getting Started
---------------

See the Quickstart guide to get up and running. In short, you need to:

1.  have a Postgres database with logical replication enabled; and then to
2.  run Electric in front of it, connected via `DATABASE_URL`

For example, using Docker Compose from the root of this repo:

docker compose -f .support/docker-compose.yml up

You can then use the HTTP API to sync data from your Postgres. For example, to start syncing the whole `foo` table:

curl -i 'http://localhost:3000/v1/shape?table=foo&offset=-1'

Or use one of the clients or integrations, such as the `useShape` React hook:

import { useShape } from "@electric-sql/react"

function Component() {
  const { data } \= useShape({
    url: \`http://localhost:3000/v1/shape\`,
    params: {
      table: \`foo\`,
      where: \`title LIKE 'foo%'\`,
    },
  })

  return JSON.stringify(data)
}

Again, see the Quickstart and the Docs for more details.

HTTP API Docs
-------------

The HTTP API is defined in an OpenAPI spec in website/electric-api.yaml.

Developing Electric
-------------------

We're using asdf to install Elixir, Erlang, and Node.js. Versions are defined in .tool-versions.

### Mac setup

brew install asdf
asdf plugin-add nodejs elixir erlang
asdf install

You'll probably need to fiddle with your bash/zsh/etc rc file to load the right tool into your environment.

Contributing
------------

See the:

-   Guide to Contributing
-   Contributor License Agreement
-   Community Guidelines

Support
-------

We have an open community Discord. Come and say hello and let us know if you have any questions or need any help getting things running.

It's also super helpful if you leave the project a star here at the top of the page☝️
