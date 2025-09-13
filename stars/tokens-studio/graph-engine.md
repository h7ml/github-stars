---
project: graph-engine
stars: 63
description: Graph engine for resolvers and generators
url: https://github.com/tokens-studio/graph-engine
---

Tokens Studio Graph Engine Monorepo
===================================

This is the monorepo for the full Tokens Studio ecosystem powered by Turborepo

See the Graph-Engine library here

### Documentation

See the hosted documentation here

Development
-----------

### Quickstart

Run yarn to install dependencies

yarn

Run the appropriate dev script for you app or library.

### Docker

To setup a docker development environment you can use the provided `docker-compose.yaml` file via a `docker-compose up` command

Note that we do use images from ghcr.io which means you will need to authenticate there. Follow this guide to logging into ghcr.

Running `docker-compose up` will create the following services

To use these services, make sure to open the necessary ports on your computer. It's important to consistently use either `localhost` or `127.0.0.1` to refer to your local machine. We recommend using `127.0.0.1`.

### Graph Engine

The graph engine can be run independently of the UI through

yarn run dev:engine

### UI for the Engine

yarn run dev:ui

This builds the required deps and then runs the development server for studio. In the case that you might be changing the dependencies of Studio whilst using studio, you can use

yarn run dev:ui:live

which will run live dev for studio and its deps and update the dependencies

Developer documentation
-----------------------

See additional developer documentation here for specifics on how the graph engine works

API
---

See the developer API here

Dependency graphs
-----------------

You should be able to run the `dev:<APP_OR_LIB>:graph` script to generate a dependency graph pdf in the `./graphs` directory.

Notes
-----

We use yarn as our package manager. Pnpm causes some issues with libraries that rely on being relative to their source without symlinks

Useful Links
------------

Learn more about the power of Turborepo:

-   Pipelines
-   Caching
-   Remote Caching
-   Filtering
-   Configuration Options
-   CLI Usage
