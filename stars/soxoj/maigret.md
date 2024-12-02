---
project: maigret
stars: 10367
description: 🕵️‍♂️ Collect a dossier on a person by username from thousands of sites
url: https://github.com/soxoj/maigret
---

Maigret
=======

_The Commissioner Jules Maigret is a fictional French police detective, created by Georges Simenon. His investigation method is based on understanding the personality of different people and their interactions._

**👉👉👉 Online Telegram bot**

About
-----

**Maigret** collects a dossier on a person **by username only**, checking for accounts on a huge number of sites and gathering all the available information from web pages. No API keys required. Maigret is an easy-to-use and powerful fork of Sherlock.

Currently supported more than 3000 sites (full list), search is launched against 500 popular sites in descending order of popularity by default. Also supported checking of Tor sites, I2P sites, and domains (via DNS resolving).

Main features
-------------

-   Profile pages parsing, extraction of personal info, links to other profiles, etc.
-   Recursive search by new usernames and other ids found
-   Search by tags (site categories, countries)
-   Censorship and captcha detection
-   Requests retries

See full description of Maigret features in the documentation.

Installation
------------

‼️ Maigret is available online via official Telegram bot.

Maigret can be installed using pip, Docker, or simply can be launched from the cloned repo.

Standalone EXE-binaries for Windows are located in Releases section of GitHub repository.

Also, you can run Maigret using cloud shells and Jupyter notebooks (see buttons below).

### Package installing

**NOTE**: Python 3.10 or higher and pip is required, **Python 3.11 is recommended.**

# install from pypi
pip3 install maigret

# usage
maigret username

### Cloning a repository

# or clone and install manually
git clone https://github.com/soxoj/maigret && cd maigret

# build and install
pip3 install .

# usage
maigret username

### Docker

# official image
docker pull soxoj/maigret

# usage
docker run -v /mydir:/app/reports soxoj/maigret:latest username --html

# manual build
docker build -t maigret .

Usage examples
--------------

# make HTML, PDF, and Xmind8 reports
maigret user --html
maigret user --pdf
maigret user --xmind #Output not compatible with xmind 2022+

# search on sites marked with tags photo & dating
maigret user --tags photo,dating

# search on sites marked with tag us
maigret user --tags us

# search for three usernames on all available sites
maigret user1 user2 user3 -a

Use `maigret --help` to get full options description. Also options are documented.

Contributing
------------

Maigret has open-source code, so you may contribute your own sites by adding them to `data.json` file, or bring changes to it's code!

For more information about development and contribution, please read the development documentation.

Demo with page parsing and recursive username search
----------------------------------------------------

### Video (asciinema)

### Reports

PDF report, HTML report

Full console output

### SOWEL classification

This tool uses the following OSINT techniques:

-   SOTL-2.2. Search For Accounts On Other Platforms
-   SOTL-6.1. Check Logins Reuse To Find Another Account
-   SOTL-6.2. Check Nicknames Reuse To Find Another Account

License
-------

MIT © Maigret  
MIT © Sherlock Project  
Original Creator of Sherlock Project - Siddharth Dushantha
