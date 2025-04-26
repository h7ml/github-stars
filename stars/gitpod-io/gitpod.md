---
project: gitpod
stars: 13253
description: The developer platform for on-demand cloud development environments to create software faster and more securely.
url: https://github.com/gitpod-io/gitpod
---

  
  

Gitpod’s developer platform provides on-demand, pre-configured environments that automatically integrate into any tool, library, or dependency required for creating software. Gitpod workspaces are the fastest and most secure way to ship software and are as easy as adding a `.gitpod.yml` file to the root of any repository.

📄 Read Cloud Development Environment white paper

Features
--------

-   **Dev environments as code** - Gitpod is like infrastructure-as-code, but for your development environment. Gitpod defines your editor extensions and requires dependencies in a declarative `.gitpod.yml` configuration. Spinning up dev environments is easily repeatable and reproducible empowering you to automate, version-control, and share dev environments across your team.
-   **Prebuilt dev environments** - Gitpod continuously prebuilds all your git branches similar to a CI server. Control how Gitpod pre-configures and initializes environments before you even start a workspace through tasks commands in your .gitpod.yml. No more watching apt-get or npm install again. 
-   **Secure** - Each Gitpod workspace or prebuild runs on a secured single-use container providing fast startup times without compromising on security. Gitpod generates SLSA level 1 compliant provenance. Gitpod is also GDPR and SOC2 compliant. And, of course, Gitpod is open-source and available for review by everyone.
-   **Workspaces based on Docker** - Gitpod instantly starts a container in the cloud based on an (optional) Docker image. If you’re already using Docker, you can easily re-use your Docker file. 
-   **GitLab, GitHub, Bitbucket and Azure DevOps integration** - Gitpod seamlessly integrates into your workflow and works with all major Git hosting platforms including GitHub, GitLab, Bitbucket, and Azure DevOps.
-   **Integrated code reviews** - with Gitpod you can do native code reviews on any PR/MR. No need to switch contexts anymore and clutter your local machine with your colleagues' PR/MR.
-   **Collaboration** - invite team members to your dev environment or snapshot of any state of your dev environment to share it with your team asynchronously. **Professional & customizable developer experience** - a Gitpod workspace gives you the same capabilities as your Linux machine - pre-configured and optimized for your development workflow. Install any VS Code extension with one click on a user and/or team level. You can also bring your dotfiles and customize your dev environment as you like.

Getting Started
---------------

-   **Browser**: 
    -   Using Gitpod dashboard gitpod.io/new.
    -   Add `gitpod.io/#` as a prefix to any of your GitHub/ GitLab/ Bitbucket repository, like this
-   **CLI**: You can also install the Gitpod CLI and create your first workspace directly from your terminal :)

Documentation
-------------

All documentation can be found on www.gitpod.io/docs. For example, see Gitpod tutorial and check the following helpful resources:

-   Workspace Lifecycle
-   Configure repositories
-   Organizations
-   IDE & Editors support
-   Video screencasts
-   Gitpod samples

Questions
---------

For questions and support please use Gitpod community Discord. Join the conversation, and connect with other community members. 💬 You can also follow @gitpod for announcements and updates from our team.

For enterprise deployment and customized solutions, please explore our **Enterprise offerings** to get started with a setup that meets your organization's needs.

Issues
------

The issue tracker is used for tracking bug reports and feature requests for the Gitpod open source project as well as planning current and future development efforts. 🗺️

You can upvote popular feature requests or create a new one.

Related Projects
----------------

During the development of Gitpod, we also developed some of our infrastructure toolings to make development easier and more efficient. To this end, we've developed many open-source projects including:

-   Workspace images: Ready to use docker images for Gitpod workspaces
-   OpenVSCode Server: Run the latest VS Code on a remote machine accessed through a browser
-   Gitpod browser extension: It adds a Gitpod button to the configured GitLab, GitHub, Bitbucket and Azure DevOps installations
-   Leeway - A heavily caching build system
-   Dazzle - An experimental Docker image builder
-   Werft - A Kubernetes native CI system

Code of Conduct
---------------

We want to create a welcoming environment for everyone interested in contributing to Gitpod or participating in discussions with the Gitpod community. This project has adopted the Contributor Covenant Code of Conduct, version 2.0.
