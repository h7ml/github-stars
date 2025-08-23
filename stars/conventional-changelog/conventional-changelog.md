---
project: conventional-changelog
stars: 8218
description: Generate changelogs and release notes from a project's commit messages and metadata.
url: https://github.com/conventional-changelog/conventional-changelog
---

Conventional Changelog
======================

Generate a CHANGELOG from git metadata.

Getting started
---------------

The original `conventional-changelog` package repo can be found in packages/conventional-changelog.

If you are new to Conventional Commits, we recommend to read The Complete Guide.

We recommend considering the following high level tools for automating versioning, tagging, and CHANGELOG generation:

-   commit-and-tag-version — a drop-in replacement for npm's `version` command, handles automated version bumping, tagging, and CHANGELOG generation.
-   semantic-release — fully automates the release process from CI/CD, including version determination, changelog generation, and publishing.
-   simple-release-action — a simple GitHub Action to automate version bumps, changelogs, and releases. Supports monorepos and extensibility via addons.

Modules Important to Conventional Changelog Ecosystem
-----------------------------------------------------

-   conventional-changelog - the full-featured command line interface
-   standard-changelog - command line interface for the angular commit format
-   conventional-recommended-bump - get a recommended version bump based on conventional commits
-   commitizen - simple commit conventions for internet citizens.
-   commitlint - lint commit messages

All Packages
------------

Package

Version

Dependencies

`conventional-changelog`

`conventional-changelog-angular`

`conventional-changelog-atom`

`conventional-changelog-codemirror`

`conventional-changelog-conventionalcommits`

`conventional-changelog-ember`

`conventional-changelog-eslint`

`conventional-changelog-express`

`conventional-changelog-jquery`

`conventional-changelog-jshint`

`conventional-changelog-preset-loader`

`conventional-changelog-writer`

`conventional-commits-filter`

`conventional-commits-parser`

`conventional-recommended-bump`

`@conventional-changelog/git-client`

`standard-changelog`

Node Support Policy
-------------------

We only support Long-Term Support versions of Node.

We specifically limit our support to LTS versions of Node, not because this package won't work on other versions, but because we have a limited amount of time, and supporting LTS offers the greatest return on that investment.

It's possible this package will work correctly on newer versions of Node. It may even be possible to use this package on older versions of Node, though that's more unlikely as we'll make every effort to take advantage of features available in the oldest LTS version we support.

As each Node LTS version reaches its end-of-life we will remove that version from the `node` `engines` property of our package's `package.json` file. Removing a Node version is considered a breaking change and will entail the publishing of a new major version of this package. We will not accept any requests to support an end-of-life version of Node. Any merge requests or issues supporting an end-of-life version of Node will be closed.

We will accept code that allows this package to run on newer, non-LTS, versions of Node. Furthermore, we will attempt to ensure our own changes work on the latest version of Node. To help in that commitment, our continuous integration setup runs against all LTS versions of Node in addition the most recent Node release; called _current_.

JavaScript package managers should allow you to install this package with any version of Node, with, at most, a warning if your version of Node does not fall within the range specified by our `node` `engines` property. If you encounter issues installing this package, please report the issue to your package manager.
