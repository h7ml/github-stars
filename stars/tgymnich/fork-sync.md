---
project: fork-sync
stars: 444
description: 🔄 Github action to sync your forks
url: https://github.com/tgymnich/fork-sync
---

Fork Sync
=========

Github action to sync your Forks. This action uses octokit and the GitHub API to automatically create and merge a pull request with the head defined by `head` into the base defined by `base`. The head branch owner is defined by `owner`. If you create a PR in the same repository you can omit the `owner` parameter.

Example Workflow
================

name: Sync Fork

on:
  schedule:
    - cron: '\*/30 \* \* \* \*' # every 30 minutes
  workflow\_dispatch: # on button click

jobs:
  sync:

    runs-on: ubuntu-latest

    steps:
      - uses: tgymnich/fork-sync@v1.8
        with:
          owner: llvm
          base: master
          head: master

Auto approve
------------

If you use a workflow which does not allow to merge pull requests without a review ("Require pull request reviews before merging" in your repo settings) you can set `auto_approve` to `true`. In that case you'll have to provide a personal access token for a user which is allowed to review the pull requests changes. Make sure the token has at least `public_repo` permissions and store the token inside of the repository secrets.

An example workflow would then look like this:

name: Sync Fork

on:
  schedule:
    - cron: '\*/30 \* \* \* \*' # every 30 minutes
  workflow\_dispatch: # on button click

jobs:
  sync:

    runs-on: ubuntu-latest

    steps:
      - uses: tgymnich/fork-sync@v2.0
        with:
          token: ${{ secrets.PERSONAL\_TOKEN }}
          owner: llvm
          base: master
          head: master

Parameters
==========

name

Optional

Default

description

owner

✅

$current\_repo\_owner

Owner of the forked repository

repo

✅

$current\_repo\_name

Name of the forked repository

token

✅

${{ github.token }}

Token to access the Github API

head

✅

master

Head branch

base

✅

master

Base branch

merge\_method

✅

merge

merge, rebase or squash

pr\_title

✅

Fork Sync

Title of the created pull request

pr\_message

✅

Message of the created pull request

ignore\_fail

✅

Ignore Exceptions

⚠️ $current\_repo\_owner is your own username! ⚠️ $current\_repo\_name is the name of the current repository!

⚠️ Only provide the branch name for `head` and `base`. `user:branch` will not work!

⚠️ \* if `auto_approve` is set to `true` you must provide a personal access token in `token` the default github token won't work!

Alternatives
============

Pull Github App - https://github.com/wei/pull
