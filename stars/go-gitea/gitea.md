---
project: gitea
stars: 45397
description: Git with a cup of tea! Painless self-hosted all-in-one software development service, including Git hosting, code review, team collaboration, package registry and CI/CD
url: https://github.com/go-gitea/gitea
---

Gitea
=====

View this document in Chinese

Purpose
-------

The goal of this project is to make the easiest, fastest, and most painless way of setting up a self-hosted Git service.

As Gitea is written in Go, it works across **all** the platforms and architectures that are supported by Go, including Linux, macOS, and Windows on x86, amd64, ARM and PowerPC architectures. This project has been forked from Gogs since November of 2016, but a lot has changed.

For online demonstrations, you can visit demo.gitea.com.

For accessing free Gitea service (with a limited number of repositories), you can visit gitea.com.

To quickly deploy your own dedicated Gitea instance on Gitea Cloud, you can start a free trial at cloud.gitea.com.

Building
--------

From the root of the source tree, run:

```
TAGS="bindata" make build
```

or if SQLite support is required:

```
TAGS="bindata sqlite sqlite_unlock_notify" make build
```

The `build` target is split into two sub-targets:

-   `make backend` which requires Go Stable, the required version is defined in go.mod.
-   `make frontend` which requires Node.js LTS or greater.

Internet connectivity is required to download the go and npm modules. When building from the official source tarballs which include pre-built frontend files, the `frontend` target will not be triggered, making it possible to build without Node.js.

More info: https://docs.gitea.com/installation/install-from-source

Using
-----

```
./gitea web
```

Note

If you're interested in using our APIs, we have experimental support with documentation.

Contributing
------------

Expected workflow is: Fork -> Patch -> Push -> Pull Request

Note

1.  **YOU MUST READ THE CONTRIBUTORS GUIDE BEFORE STARTING TO WORK ON A PULL REQUEST.**
2.  If you have found a vulnerability in the project, please write privately to **security@gitea.io**. Thanks!

Translating
-----------

Translations are done through Crowdin. If you want to translate to a new language ask one of the managers in the Crowdin project to add a new language there.

You can also just create an issue for adding a language or ask on discord on the #translation channel. If you need context or find some translation issues, you can leave a comment on the string or ask on Discord. For general translation questions there is a section in the docs. Currently a bit empty but we hope to fill it as questions pop up.

https://docs.gitea.com/contributing/localization

Further information
-------------------

For more information and instructions about how to install Gitea, please look at our documentation. If you have questions that are not covered by the documentation, you can get in contact with us on our Discord server or create a post in the discourse forum.

We maintain a list of Gitea-related projects at gitea/awesome-gitea.

The official Gitea CLI is developed at gitea/tea.

Authors
-------

-   Maintainers
-   Contributors
-   Translators

Backers
-------

Thank you to all our backers! 🙏 \[Become a backer\]

Sponsors
--------

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. \[Become a sponsor\]

FAQ
---

**How do you pronounce Gitea?**

Gitea is pronounced /ɡɪ’ti:/ as in "gi-tea" with a hard g.

**Why is this not hosted on a Gitea instance?**

We're working on it.

License
-------

This project is licensed under the MIT License. See the LICENSE file for the full license text.

Screenshots
-----------

Looking for an overview of the interface? Check it out!
