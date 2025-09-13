---
project: etherpad-lite
stars: 17723
description: Etherpad: A modern really-real-time collaborative document editor.
url: https://github.com/ether/etherpad-lite
---

Etherpad: A real-time collaborative editor for the web
======================================================

About
-----

Etherpad is a real-time collaborative editor scalable to thousands of simultaneous real time users. It provides full data export capabilities, and runs on _your_ server, under _your_ control.

Try it out
----------

Wikimedia provide a public Etherpad instance for you to Try Etherpad out. or use another public Etherpad instance to see other features

Project Status
--------------

We're looking for maintainers and have some funding available. Please contact John McLear if you can help.

### Code Quality

### Testing

### Engagement

Installation
------------

### Docker-Compose

services:
  app:
    user: "0:0"
    image: etherpad/etherpad:latest
    tty: true
    stdin\_open: true
    volumes:
      - plugins:/opt/etherpad-lite/src/plugin\_packages
      - etherpad-var:/opt/etherpad-lite/var
    depends\_on:
      - postgres
    environment:
      NODE\_ENV: production
      ADMIN\_PASSWORD: ${DOCKER\_COMPOSE\_APP\_ADMIN\_PASSWORD:-admin}
      DB\_CHARSET: ${DOCKER\_COMPOSE\_APP\_DB\_CHARSET:-utf8mb4}
      DB\_HOST: postgres
      DB\_NAME: ${DOCKER\_COMPOSE\_POSTGRES\_DATABASE:-etherpad}
      DB\_PASS: ${DOCKER\_COMPOSE\_POSTGRES\_PASSWORD:-admin}
      DB\_PORT: ${DOCKER\_COMPOSE\_POSTGRES\_PORT:-5432}
      DB\_TYPE: "postgres"
      DB\_USER: ${DOCKER\_COMPOSE\_POSTGRES\_USER:-admin}
      # For now, the env var DEFAULT\_PAD\_TEXT cannot be unset or empty; it seems to be mandatory in the latest version of etherpad
      DEFAULT\_PAD\_TEXT: ${DOCKER\_COMPOSE\_APP\_DEFAULT\_PAD\_TEXT:- }
      DISABLE\_IP\_LOGGING: ${DOCKER\_COMPOSE\_APP\_DISABLE\_IP\_LOGGING:-false}
      SOFFICE: ${DOCKER\_COMPOSE\_APP\_SOFFICE:-null}
      TRUST\_PROXY: ${DOCKER\_COMPOSE\_APP\_TRUST\_PROXY:-true}
    restart: always
    ports:
      - "${DOCKER\_COMPOSE\_APP\_PORT\_PUBLISHED:-9001}:${DOCKER\_COMPOSE\_APP\_PORT\_TARGET:-9001}"

  postgres:
    image: postgres:15-alpine
    environment:
      POSTGRES\_DB: ${DOCKER\_COMPOSE\_POSTGRES\_DATABASE:-etherpad}
      POSTGRES\_PASSWORD: ${DOCKER\_COMPOSE\_POSTGRES\_PASSWORD:-admin}
      POSTGRES\_PORT: ${DOCKER\_COMPOSE\_POSTGRES\_PORT:-5432}
      POSTGRES\_USER: ${DOCKER\_COMPOSE\_POSTGRES\_USER:-admin}
      PGDATA: /var/lib/postgresql/data/pgdata
    restart: always
    # Exposing the port is not needed unless you want to access this database instance from the host.
    # Be careful when other postgres docker container are running on the same port
    # ports:
    #   - "5432:5432"
    volumes:
      - postgres\_data:/var/lib/postgresql/data

volumes:
  postgres\_data:
  plugins:
  etherpad-var:

### Requirements

Node.js >= **18.18.2**.

### Windows, macOS, Linux

1.  Download the latest Node.js runtime from nodejs.org.
2.  Install pnpm: `npm install -g pnpm` (Administrator privileges may be required).
3.  Clone the repository: `git clone -b master`
4.  Run `pnpm i`
5.  Run `pnpm run build:etherpad`
6.  Run `pnpm run prod`
7.  Visit `http://localhost:9001` in your browser.

### Docker container

Find here information on running Etherpad in a container.

Plugins
-------

Etherpad is very customizable through plugins.

### Available Plugins

For a list of available plugins, see the plugins site.

### Plugin Installation

You can install plugins from the admin web interface (e.g., http://127.0.0.1:9001/admin/plugins).

Alternatively, you can install plugins from the command line:

cd /path/to/etherpad-lite
pnpm run plugins i ep\_${plugin\_name}

Also see the plugin wiki article.

### Suggested Plugins

Run the following command in your Etherpad folder to get all of the features visible in the above demo gif:

pnpm run plugins i \\
  ep\_align \\
  ep\_comments\_page \\
  ep\_embedded\_hyperlinks2 \\
  ep\_font\_color \\
  ep\_headings2 \\
  ep\_markdown \\
  ep\_webrtc

For user authentication, you are encouraged to run an OpenID Connect identity provider (OP) and install the following plugins:

-   ep\_openid\_connect to authenticate against your OP.
-   ep\_guest to create a "guest" account that has limited access (e.g., read-only access).
-   ep\_user\_displayname to automatically populate each user's displayed name from your OP.
-   ep\_stable\_authorid so that each user's chosen color, display name, comment ownership, etc. is strongly linked to their account.

### Upgrade Etherpad

Run the following command in your Etherpad folder to upgrade

1.  Stop any running Etherpad (manual, systemd ...)
2.  Get present version

git -P tag --contains

1.  List versions available

git -P tag --list "v\*" --merged

1.  Select the version

git checkout v2.2.5
git switch -c v2.2.5

1.  Upgrade Etherpad

./bin/run.sh

1.  Stop with \[CTRL-C\]
2.  Restart your Etherpad service

Next Steps
----------

### Tweak the settings

You can modify the settings in `settings.json`. If you need to handle multiple settings files, you can pass the path to a settings file to `bin/run.sh` using the `-s|--settings` option: this allows you to run multiple Etherpad instances from the same installation. Similarly, `--credentials` can be used to give a settings override file, `--apikey` to give a different APIKEY.txt file and `--sessionkey` to give a non-default `SESSIONKEY.txt`. **Each configuration parameter can also be set via an environment variable**, using the syntax `"${ENV_VAR}"` or `"${ENV_VAR:default_value}"`. For details, refer to `settings.json.template`. Once you have access to your `/admin` section, settings can be modified through the web browser.

If you are planning to use Etherpad in a production environment, you should use a dedicated database such as `mysql`, since the `dirtyDB` database driver is only for testing and/or development purposes.

### Secure your installation

If you have enabled authentication in `users` section in `settings.json`, it is a good security practice to **store hashes instead of plain text passwords** in that file. This is _especially_ advised if you are running a production installation.

Please install ep\_hash\_auth plugin and configure it. If you prefer, `ep_hash_auth` also gives you the option of storing the users in a custom directory in the file system, without having to edit `settings.json` and restart Etherpad each time.

### Customize the style with skin variants

Open http://127.0.0.1:9001/p/test#skinvariantsbuilder in your browser and start playing!

Helpful resources
-----------------

The wiki is your one-stop resource for Tutorials and How-to's.

Documentation can be found in `doc/`.

Development
-----------

### Things you should know

You can debug Etherpad using `bin/debugRun.sh`.

You can run Etherpad quickly launching `bin/fastRun.sh`. It's convenient for developers and advanced users. Be aware that it will skip the dependencies update, so remember to run `bin/installDeps.sh` after installing a new dependency or upgrading version.

If you want to find out how Etherpad's `Easysync` works (the library that makes it really realtime), start with this PDF (complex, but worth reading).

### Contributing

Read our **Developer Guidelines**

### HTTP API

Etherpad is designed to be easily embeddable and provides a HTTP API that allows your web application to manage pads, users and groups. It is recommended to use the available client implementations in order to interact with this API.

OpenAPI (previously swagger) definitions for the API are exposed under `/api/openapi.json`.

### jQuery plugin

There is a jQuery plugin that helps you to embed Pads into your website.

### Plugin Framework

Etherpad offers a plugin framework, allowing you to easily add your own features. By default your Etherpad is extremely light-weight and it's up to you to customize your experience. Once you have Etherpad installed you should visit the plugin page and take control.

### Translations / Localizations (i18n / l10n)

Etherpad comes with translations into all languages thanks to the team at TranslateWiki.

If you require translations in plugins please send pull request to each plugin individually.

FAQ
---

Visit the **FAQ**.

Get in touch
------------

The official channel for contacting the development team is via the GitHub issues.

For **responsible disclosure of vulnerabilities**, please write a mail to the maintainers (a.mux@inwind.it and contact@etherpad.org).

Join the official Etherpad Discord Channel.

License
-------

Apache License v2
