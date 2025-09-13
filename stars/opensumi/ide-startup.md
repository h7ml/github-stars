---
project: ide-startup
stars: 226
description: Quick starter for OpenSumi Web
url: https://github.com/opensumi/ide-startup
---

OpenSumi Web Sample
===================

This project is used to show how to run OpenSumi on Web.

English | 简体中文

Quick Start
-----------

$ git clone git@github.com:opensumi/ide-startup.git
$ cd ide-startup
$ yarn
$ yarn start

Open http://127.0.0.1:8080.

You can add `workspaceDir` to the URL to open the specified directory, for example `http://0.0.0.0:8080?workspaceDir=/path/to/dir`.

Project Structure
-----------------

.
├── extensions                  # The Buit-in extensions
├── configs                     # Build configuration
├── src
│   ├── browser
│   └── node
├── tsconfig.json
├── package.json
└── README.md

Use Docker
----------

# Pull the image
docker pull ghcr.io/opensumi/opensumi-web:latest

# Run
docker run --init --rm -d  -p 8080:8000/tcp ghcr.io/opensumi/opensumi-web:latest

Open `http://0.0.0.0:8080`

License
-------

Copyright (c) 2019-present Alibaba Group Holding Limited, Ant Group Co. Ltd.

Licensed under the MIT license.
