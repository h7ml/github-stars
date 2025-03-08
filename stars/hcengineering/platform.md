---
project: platform
stars: 19544
description: Huly — All-in-One Project Management Platform (alternative to Linear, Jira, Slack, Notion, Motion)
url: https://github.com/hcengineering/platform
---

Huly Platform
=============

⭐️ Your star shines on us. Star us on GitHub!

About
-----

The Huly Platform is a robust framework designed to accelerate the development of business applications, such as CRM systems. This repository includes several applications, such as Chat, Project Management, CRM, HRM, and ATS. Various teams are building products on top of the Platform, including Huly and TraceX.

Self-Hosting
------------

If you're primarily interested in self-hosting Huly without the intention to modify or contribute to its development, please use huly-selfhost. This project offers a convenient method to host Huly using `docker`, designed for ease of use and quick setup. Explore this option to effortlessly enjoy Huly on your own server.

Activity
--------

API Client
----------

If you want to interact with Huly programmatically, check out our API Client documentation. The API client provides a typed interface for all Huly operations and can be used to build integrations and custom applications.

You can find API usage examples in the Huly examples repository.

Table of Contents
-----------------

-   Huly Platform
    -   About
    -   Self-Hosting
    -   Activity
    -   API Client
    -   Table of Contents
    -   Pre-requisites
    -   Verification
    -   Fast start
    -   Branches & Contributing
    -   Installation
    -   Build and run
    -   Run in development mode
    -   Update project structure and database
    -   Troubleshooting
    -   Build & Watch
    -   Tests
        -   Unit tests
        -   UI tests
    -   Package publishing
    -   Additional testing

Pre-requisites
--------------

-   Before proceeding, ensure that your system meets the following requirements:
    -   Node.js (v20.11.0 is required)
    -   Docker
    -   Docker Compose

Verification
------------

To verify the installation, perform the following checks in your terminal:

-   Ensure that the `docker` commands are available:

docker --version
docker compose version

Fast start
----------

sh ./scripts/fast-start.sh

Branches & Contributing
-----------------------

-   The `main` branch is the default branch used for production deployments. Changes to this branch are made from the `staging` branch once a version is ready for community use.
    
-   The `staging` branch is used for pre-release testing. It is stable enough for testing but not yet ready for production deployment.
    
-   The `develop` branch is used for development and is the default branch for contributions.
    

We periodically merge `develop` into `staging` to perform testing builds. Once we are satisfied with the build quality in our pre-release deployment, we merge changes into `main` and release a new version to the community.

Installation
------------

You need Microsoft's rush to install the application.

1.  Install Rush globally using the command:

npm install -g @microsoft/rush

1.  Navigate to the repository root and run the following commands:

rush install
rush build

Alternatively, you can just execute:

sh ./scripts/presetup-rush.sh

Build and run
-------------

Development environment setup requires Docker to be installed on system.

Support is available for both amd64 and arm64 containers on Linux and macOS.

cd ./dev/
rush build    # Will build all the required packages.
# rush rebuild  # could be used to omit build cache.
rush bundle   # Will prepare bundles.
rush package  # Will build all webpack packages.
rush validate # Will validate all sources with typescript and generate d.ts files required for ts-node execution.
rush svelte-check # Optional. svelte files validation using svelte-check.
rush docker:build   # Will build Docker containers for all applications in the local Docker environment.
rush docker:up # Will set up all the containers

Be aware `rush docker:build` will automatically execute all required phases like build, bundle, package.

Alternatively, you can just execute:

sh ./scripts/build.sh

By default, Docker volumes named dev\_db, dev\_elastic, and dev\_files will be created for the MongoDB, Elasticsearch, and MinIO instances.

Before you can begin, you need to create a workspace and an account and associate it with the workspace.

cd ./tool # dev/tool in the repository root
rushx run-local create-account user1 -p 1234 -f John -l Appleseed # Create account
rushx run-local create-workspace ws1 email:user1 # Create workspace
rushx run-local configure ws1 --list --enable '\*' # Enable all modules, even if they are not yet intended to be used by a wide audience
rushx run-local assign-workspace user1 ws1 # Assign user to workspace

Alternatively, you can just execute:

sh ./scripts/create-workspace.sh

Add the following line to your /etc/hosts file

```
127.0.0.1 huly.local
```

Accessing the URL http://huly.local:8087 will lead you to the app in development mode.

Limitations:

-   Local installation does not support sending emails, thus disabling functionalities such as password recovery and email notifications.

Run in development mode
-----------------------

Development mode allows for live reloading and a smoother development process.

cd dev/prod
rush validate
rushx dev-server

Then go to http://localhost:8080

Click on "Login with password" link on the bottom of the right panel and use the following login credentials:

```
Email: user1
Password: 1234
Workspace: ws1
```

Update project structure and database
-------------------------------------

If the project's structure is updated, it may be necessary to relink and rebuild the projects.

rush update
rush build

Troubleshooting
---------------

If a build fails, but the code is correct, try to delete the build cache and retry.

# from the project root
rm -rf common/temp/build-cache

Build & Watch
-------------

For development purpose `rush build:watch` action could be used.

It includes build and validate phases in watch mode.

Tests
-----

### Unit tests

rush test # To execute all tests

rushx test # For individual test execution inside a package directory

### UI tests

cd ./tests
rush build
rush bundle
rush docker:build
#\# creates test Docker containers and sets up test database
./prepare.sh
#\# runs UI tests
rushx uitest

To execute tests in the development environment, please follow these steps:

cd ./tests
./create-local.sh #\# use ./restore-local.sh if you only want to restore the workspace to a predefined initial state for sanity.
cd ./sanity
rushx dev-uitest # To execute all tests against the development environment.
rushx dev-debug -g 'pattern' # To execute tests in debug mode with only the matching test pattern.

Package publishing
------------------

node ./common/scripts/bump.js -p projectName

Additional testing
------------------

This project is tested with BrowserStack.

© 2025 Hardcore Engineering Inc.
