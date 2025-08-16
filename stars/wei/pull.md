---
project: pull
stars: 6745
description: 🤖 Keep your forks up-to-date via automated PRs
url: https://github.com/wei/pull
---

Introduction
------------

> 🤖 a GitHub App that keeps your forks up-to-date with upstream via automated pull requests.

_Can you help keep this open source service alive? **💖 Please sponsor : )**_

Features
--------

-   🔄 **Automated Synchronization**: Ensures forks are updated by automatically creating pull requests to integrate new changes from upstream
-   ⚙️ **Flexible Configuration**: Customize sync behavior through `.github/pull.yml` configuration to accommodate different merge strategies, including merge, squash, rebase, and hard reset
-   🕒 **Scheduled Updates**: Regularly checks for upstream changes periodically to ensure forks are always up-to-date
-   👥 **Team Integration**: Facilitates collaboration by automatically adding assignees and reviewers to pull requests, honoring branch protection rules and working seamlessly with pull request checks and reviews
-   🚀 **Enterprise Ready**: Supports GitHub Enterprise Server, ensuring a smooth integration process for enterprise-level projects

### Prerequisites

-   Upstream must be in the same fork network.
-   ⚠️ _Make a backup if you've made changes._

Getting Started
---------------

**⭐ Star this project** (Highly recommended, starred users may receive priority over other users)

### Basic Setup

-   Just install **Pull app**.

Pull app will automatically watch and pull in upstream's default (master) branch to yours using **hard reset** periodically. You can also manually trigger it anytime.

### Advanced Configuration (with config file)

1.  Create a new branch.
    
2.  Setup the new branch as default branch under repository Settings > Branches.
    
3.  Add `.github/pull.yml` to your default branch.
    
    #### Most Common
    
    (behaves the same as Basic Setup)
    
    version: "1"
    rules:
      - base: master
        upstream: wei:master # change \`wei\` to the owner of upstream repo
        mergeMethod: hardreset
        mergeUnstable: true
    
    #### Advanced usage
    
    version: "1"
    rules: # Array of rules
      - base: master # Required. Target branch
        upstream: wei:master # Required. Must be in the same fork network.
        mergeMethod: hardreset # Optional, one of \[none, merge, squash, rebase, hardreset\], Default: none.
        mergeUnstable: false # Optional, merge pull request even when the mergeable\_state is not clean. Default: false
      - base: dev
        upstream: master # Required. Can be a branch in the same forked repo.
        assignees: # Optional
          - wei
        reviewers: # Optional
          - wei
        conflictReviewers: # Optional, on merge conflict assign a reviewer
          - wei
    label: ":arrow\_heading\_down: pull" # Optional
    conflictLabel: "merge-conflict" # Optional, on merge conflict assign a custom label, Default: merge-conflict
    
4.  Go to `https://pull.git.ci/check/${owner}/${repo}` to validate your `.github/pull.yml`.
    
5.  Install **Pull app**.
    

### Trigger Manually

You can manually trigger Pull by going to `https://pull.git.ci/process/${owner}/${repo}`.

### For Upstream Repository Owners

For the most common use case (a single `master` branch), you can just direct users to install Pull with no configurations. If you need a more advanced setup (such as a `docs` branch in addition to `master`), consider adding `.github/pull.yml` to your repository pointing to yourself (see example). This will allow forks to install Pull and stay updated automatically.

Example (assuming `owner` is your user or organization name):

version: "1"
rules:
  - base: master
    upstream: owner:master
    mergeMethod: hardreset
    mergeUnstable: true
  - base: docs
    upstream: owner:docs
    mergeMethod: hardreset
    mergeUnstable: true

Contributing
------------

See CONTRIBUTING.md

License
-------

MIT © Wei He

Support
-------

_Can you help keep this open source service alive? **💖 Please sponsor : )**_

* * *

Made with ❤️ by @wei
