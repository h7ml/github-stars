---
project: ungoogled-chromium
stars: 23737
description: Google Chromium, sans integration with Google
url: https://github.com/ungoogled-software/ungoogled-chromium
---

ungoogled-chromium
==================

_A lightweight approach to removing Google web service dependency_

**Help is welcome!** See the docs/contributing.md document for more information.

Objectives
----------

In descending order of significance (i.e. most important objective first):

1.  **ungoogled-chromium is Google Chromium, sans dependency on Google web services**.
2.  **ungoogled-chromium retains the default Chromium experience as closely as possible**. Unlike other Chromium forks that have their own visions of a web browser, ungoogled-chromium is essentially a drop-in replacement for Chromium.
3.  **ungoogled-chromium features tweaks to enhance privacy, control, and transparency**. However, almost all of these features must be manually activated or enabled. For more details, see Feature Overview.

In scenarios where the objectives conflict, the objective of higher significance should take precedence.

Content Overview
----------------

-   Objectives
-   Motivation and Philosophy
-   Feature Overview
-   **Downloads**
-   Source Code
-   **FAQ**
-   Building Instructions
-   Design Documentation
-   **Contributing, Reporting, Contacting**
-   Credits
-   Related Projects
-   License

Motivation and Philosophy
-------------------------

Without signing in to a Google Account, Chromium does pretty well in terms of security and privacy. However, Chromium still has some dependency on Google web services and binaries. In addition, Google designed Chromium to be easy and intuitive for users, which means they compromise on transparency and control of internal operations.

ungoogled-chromium addresses these issues in the following ways:

1.  Remove all remaining background requests to any web services while building and running the browser
2.  Remove all code specific to Google web services
3.  Remove all uses of pre-made binaries from the source code, and replace them with user-provided alternatives when possible.
4.  Disable features that inhibit control and transparency, and add or modify features that promote them (these changes will almost always require manual activation or enabling).

These features are implemented as configuration flags, patches, and custom scripts. For more details, consult the Design Documentation.

Feature Overview
----------------

_This section overviews the features of ungoogled-chromium. For more detailed information, it is best to consult the source code._

Contents of this section:

-   Key Features
-   Enhancing Features
-   Borrowed Features
-   Supported Platforms and Distributions

### Key Features

_These are the core features introduced by ungoogled-chromium._

-   Disable functionality specific to Google domains (e.g. Google Host Detector, Google URL Tracker, Google Cloud Messaging, Google Hotwording, etc.)
    -   This includes disabling Safe Browsing. Consult the FAQ for the rationale.
-   Block internal requests to Google at runtime. This feature is a fail-safe measure for the above, in case Google changes or introduces new components that our patches do not disable. This feature is implemented by replacing many Google web domains in the source code with non-existent alternatives ending in `qjz9zk` (known as domain substitution; see docs/design.md for details), then modifying Chromium to block its own requests with such domains. In other words, no connections are attempted to the `qjz9zk` domain.
-   Strip binaries from the source code (known as binary pruning; see docs/design.md for details)

### Enhancing Features

_These are the non-essential features introduced by ungoogled-chromium._

-   Add many new command-line switches and `chrome://flags` entries to configure new features (which are disabled by default). See docs/flags.md for the exhaustive list.
-   Add _Suggestions URL_ text field in the search engine editor (`chrome://settings/searchEngines`) for customizing search engine suggestions.
-   Add more URL schemes allowed to save page schemes.
-   Add Omnibox search provider "No Search" to allow disabling of searching
-   Add a custom cross-platform build configuration and packaging wrapper for Chromium. It currently supports many Linux distributions, macOS, and Windows. (See docs/design.md for details on the system.)
-   Force all pop-ups into tabs
-   Disable automatic formatting of URLs in Omnibox (e.g. stripping `http://`, hiding certain parameters)
-   Disable intranet redirect detector (extraneous DNS requests)
    -   This breaks captive portal detection, but captive portals still work.
-   (Iridium Browser feature change) Prevent URLs with the `trk:` scheme from connecting to the Internet
    -   Also prevents any URLs with the top-level domain `qjz9zk` (as used in domain substitution) from attempting a connection.
-   (Windows-specific) Do not set the Zone Identifier on downloaded files

### Borrowed Features

In addition to the features introduced by ungoogled-chromium, ungoogled-chromium selectively borrows many features from the following projects (in approximate order of significance):

-   Inox patchset
-   Bromite
-   Debian
-   Iridium Browser

### Supported Platforms and Distributions

See docs/platforms.md for a list of supported platforms.

Other platforms are discussed and tracked in this repository's Issue Tracker. Learn more about using the Issue Tracker under the section Contributing, Reporting, Contacting.

Downloads
---------

### Automated or maintained builds

ungoogled-chromium is available in the following **software repositories**:

-   Arch: Available in the AUR, see instructions in ungoogled-chromium-archlinux
-   Debian & Ubuntu: Available in OBS, find your distribution specific instructions in the Installing section
-   Fedora: Available in COPR as `wojnilowicz/ungoogled-chromium`. Also available in RPM Fusion as `chromium-browser-privacy` (outdated).
-   Gentoo: Available in `::pf4public` overlay as `ungoogled-chromium` and `ungoogled-chromium-bin` ebuilds
-   OpenMandriva includes ungoogled-chromium as its main browser. The `chromium` package includes all ungoogling patches.
-   macOS: Available in Homebrew as `ungoogled-chromium`. Just run `brew install --cask ungoogled-chromium`. Chromium will appear in your `/Applications` directory.
-   FreeBSD: Available in pkg as `www/ungoogled-chromium`.

If your GNU/Linux distribution is not listed, there are distro-independent builds available via the following **package managers**:

-   Flatpak: Available in the Flathub repo as `io.github.ungoogled_software.ungoogled_chromium`
-   GNU Guix: Available as `ungoogled-chromium`
-   NixOS/nixpkgs: Available as `ungoogled-chromium`

### Third-party binaries

If your operating system is not listed above, you can also try to **Download binaries from here**

_NOTE: These binaries are provided by anyone who are willing to build and submit them. Because these binaries are not necessarily reproducible, authenticity cannot be guaranteed; In other words, there is always a non-zero probability that these binaries may have been tampered with. In the unlikely event that this has happened to you, please report it in a new issue._

These binaries are known as **contributor binaries**.

Source Code
-----------

This repository only contains the common code for all platforms; it does not contain all the configuration and scripts necessary to build ungoogled-chromium. Most users will want to use platform-specific repos, where all the remaining configuration and scripts are provided for specific platforms:

**Find the repo for a specific platform here**.

If you wish to include ungoogled-chromium code in your own build process, consider using the tags in this repo. These tags follow the format `{chromium_version}-{revision}` where

-   `chromium_version` is the version of Chromium used in `x.x.x.x` format, and
-   `revision` is a number indicating the version of ungoogled-chromium for the corresponding Chromium version.

Additionally, most platform-specific repos extend their tag scheme upon this one.

**Building the source code**: See docs/building.md

### Mirrors

List of mirrors:

-   Codeberg: main repo and ungoogled-software

FAQ
---

See the frequently-asked questions (FAQ) on the Wiki

Building Instructions
---------------------

See docs/building.md

Design Documentation
--------------------

See docs/design.md

Contributing, Reporting, Contacting
-----------------------------------

-   For reporting and contacting, see SUPPORT.md
-   If you're willing to help, check out the Issue Tracker and especially issues, which need help
-   For contributing (e.g. how to help, submitting changes, criteria for new features), see docs/contributing.md
-   If you have some small contributions that don't fit our criteria, consider adding them to ungoogled-software/contrib or our Wiki instead.

Credits
-------

-   The Chromium Project
-   Inox patchset
-   Debian
-   Bromite
-   Iridium Browser
-   The users for testing and debugging, contributing code, providing feedback, or simply using ungoogled-chromium in some capacity.

Related Projects
----------------

List of known projects that fork or use changes from ungoogled-chromium:

-   Bromite (Borrows some patches. Features builds for Android)
-   ppc64le fork (Fork with changes to build for ppc64le CPUs)

License
-------

BSD-3-clause. See LICENSE
