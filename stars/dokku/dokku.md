---
project: dokku
stars: 31009
description: A docker-powered PaaS that helps you build and manage the lifecycle of applications
url: https://github.com/dokku/dokku
---

Dokku
=====

Docker powered mini-Heroku. The smallest PaaS implementation you've ever seen.

Sponsors
--------

Become a sponsor and get your logo on our README on GitHub with a link to your site. \[Become a sponsor\]

Backers
-------

Support us with a monthly donation and help us continue our activities. \[Become a backer\]

Requirements
------------

A fresh VM running any of the following operating systems:

-   Ubuntu 22.04 / 24.04 (amd64/arm64) - Any currently supported release
-   Debian 11+ (amd64/arm64)

An SSH keypair that can be used for application deployment. If this exists before installation, it will be automatically imported into dokku. Otherwise, you will need to import the keypair manually after installation using `dokku ssh-keys:add`.

Installation
------------

To install the latest stable release, run the following commands as a user who has access to `sudo`:

wget -NP . https://dokku.com/install/v0.36.0/bootstrap.sh
sudo DOKKU\_TAG=v0.36.0 bash bootstrap.sh

You can then proceed to configure your server domain (via `dokku domains:set-global`) and user access (via `dokku ssh-keys:add`) to complete the installation.

If you wish for a more unattended installation method, see these docs.

### Upgrade

View the docs for upgrading from an older version of Dokku.

Documentation
-------------

Full documentation - including advanced installation docs - are available online at https://dokku.com/docs/getting-started/installation/.

Support
-------

You can use GitHub Issues, check Troubleshooting in the documentation, or join us on Gliderlabs Slack in the #dokku channel.

Contribution
------------

After checking GitHub Issues, the Troubleshooting Guide or having a chat with us on Gliderlabs Slack in the #dokku channel, feel free to fork and create a Pull Request.

While we may not merge your PR as is, they serve to start conversations and improve the general Dokku experience for all users.

License
-------

MIT License © Jeff Lindsay
