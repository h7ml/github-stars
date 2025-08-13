---
project: http-api-design
stars: 13693
description: HTTP API design guide extracted from work on the Heroku Platform API
url: https://github.com/interagent/http-api-design
---

HTTP API Design Guide
=====================

This guide describes a set of HTTP+JSON API design practices, originally extracted from work on the Heroku Platform API.

This guide informs additions to that API and also guides new internal APIs at Heroku. We hope it’s also of interest to API designers outside of Heroku.

Our goals here are consistency and focusing on business logic while avoiding design bikeshedding. We’re looking for _a good, consistent, well-documented way_ to design APIs, not necessarily _the only/ideal way_.

We assume you’re familiar with the basics of HTTP+JSON APIs and won’t cover all of the fundamentals of those in this guide.

Available for online reading and in multiple formats at gitbook.

We welcome contributions to this guide.

See Summary for Table of Contents.

For the best reading experience, we recommend reading via GitBook.

### Gitbook Translations

-   English
-   Italian (based on f12db3e), by @diegomariani
-   Simplified Chinese (based on 40d114b), by @ZhangBohan

### Git Translations

-   Korean (based on f38dba6), by @yoondo
-   Portuguese (based on fba98f08b5), by @Gutem
-   Simplified Chinese (based on 337c4a0), by @ZhangBohan
-   Spanish (based on 2a74f45), by @jmnavarro
-   Traditional Chinese (based on 232f8dc), by @kcyeu
-   Turkish (based on c03842f), by @hkulekci
