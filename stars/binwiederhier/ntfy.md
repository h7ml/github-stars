---
project: ntfy
stars: 26477
description: Send push notifications to your phone or desktop using PUT/POST
url: https://github.com/binwiederhier/ntfy
---

ntfy.sh | Send push notifications to your phone or desktop via PUT/POST
=======================================================================

**ntfy** (pronounced "_notify_") is a simple HTTP-based pub-sub notification service. With ntfy, you can **send notifications to your phone or desktop via scripts** from any computer, **without having to sign up or pay any fees**. If you'd like to run your own instance of the service, you can easily do so since ntfy is open source.

You can access the free version of ntfy at **ntfy.sh**. There is also an open-source Android app available on Google Play or F-Droid, as well as an open source iOS app available on the App Store.

ntfy Pro 💸 🎉
--------------

I now offer paid plans for ntfy.sh if you don't want to self-host, or you want to support the development of ntfy (→ Purchase via web app). You can **buy a plan for as low as $5/month**. You can also donate via GitHub Sponsors, and Liberapay. I would be very humbled by your sponsorship. ❤️

**Documentation**
-----------------

Getting started | Android/iOS | API | Install / Self-hosting | Building

Chat/forum
----------

There are a few ways to get in touch with me and/or the rest of the community. Feel free to use any of these methods. Whatever works best for you:

-   Discord server - direct chat with the community
-   Matrix room #ntfy (+ Matrix space) - same chat, bridged from Discord
-   GitHub issues - questions, features, bugs

Announcements/beta testers
--------------------------

For announcements of new releases and cutting-edge beta versions, please subscribe to the ntfy.sh/announcements topic. If you'd like to test the iOS app, join TestFlight. For Android betas, join Discord/Matrix (I'll eventually make a testing channel in Google Play).

Sponsors
--------

If you'd like to support the ntfy maintainers, please consider donating to GitHub Sponsors or and Liberapay. We would be humbled if you helped carry the server and developer account costs. Even small donations are very much appreciated.

Thank you to our commercial sponsors, who help keep the service running and the development going:

And a big fat **Thank You** to the individuals who have sponsored ntfy in the past, or are still sponsoring ntfy:

Contributing
------------

I welcome any contributions. Just create a PR or an issue. For larger features/ideas, please reach out on Discord/Matrix first to see if I'd accept them. To contribute code, check out the build instructions for the server and the Android app. Or, if you'd like to help translate 🇩🇪 🇺🇸 🇧🇬, you can start immediately in Hosted Weblate.

Code of Conduct
---------------

We as members, contributors, and leaders pledge to make participation in our community a harassment-free experience for everyone, regardless of age, body size, visible or invisible disability, ethnicity, sex characteristics, gender identity and expression, level of experience, education, socio-economic status, nationality, personal appearance, race, caste, color, religion, or sexual identity and orientation.

**We pledge to act and interact in ways that contribute to an open, welcoming, diverse, inclusive, and healthy community.**

_Please be sure to read the complete Code of Conduct._

License
-------

Made with ❤️ by Philipp C. Heckel.  
The project is dual licensed under the Apache License 2.0 and the GPLv2 License.

Third-party libraries and resources:

-   github.com/urfave/cli (MIT) is used to drive the CLI
-   Mixkit sounds (Mixkit Free License) are used as notification sounds
-   Sounds from notificationsounds.com (Creative Commons Attribution) are used as notification sounds
-   Roboto Font (Apache 2.0) is used as a font in everything web
-   React (MIT) is used for the web app
-   Material UI components (MIT) are used in the web app
-   MUI dashboard template (MIT) was used as a basis for the web app
-   Dexie.js (Apache 2.0) is used for web app persistence in IndexedDB
-   GoReleaser (MIT) is used to create releases
-   go-smtp (MIT) is used to receive e-mails
-   stretchr/testify (MIT) is used for unit and integration tests
-   github.com/mattn/go-sqlite3 (MIT) is used to provide the persistent message cache
-   Firebase Admin SDK (Apache 2.0) is used to send FCM messages
-   github/gemoji (MIT) is used for emoji support (specifically the emoji.json file)
-   Lightbox with vanilla JS as a lightbox on the landing page
-   HTTP middleware for gzip compression (MIT) is used for serving static files
-   Regex for auto-linking (MIT) is used to highlight links (the library is not used)
-   Statically linking go-sqlite3
-   Linked tabs in mkdocs
-   webpush-go (MIT) is used to send web push notifications
-   Sprig (MIT) is used to add template parsing functions
