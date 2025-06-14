---
project: litestream
stars: 12234
description: Streaming replication for SQLite.
url: https://github.com/benbjohnson/litestream
---

Litestream
==========

Litestream is a standalone disaster recovery tool for SQLite. It runs as a background process and safely replicates changes incrementally to another file or S3. Litestream only communicates with SQLite through the SQLite API so it will not corrupt your database.

If you need support or have ideas for improving Litestream, please join the Litestream Slack or visit the GitHub Discussions. Please visit the Litestream web site for installation instructions and documentation.

If you find this project interesting, please consider starring the project on GitHub.

Acknowledgements
----------------

While the Litestream project does not accept external code patches, many of the most valuable contributions are in the forms of testing, feedback, and documentation. These help harden software and streamline usage for other users.

I want to give special thanks to individuals who invest much of their time and energy into the project to help make it better:

-   Thanks to Cory LaNou for giving early feedback and testing when Litestream was still pre-release.
-   Thanks to Michael Lynch for digging into issues and contributing to the documentation.
-   Thanks to Kurt Mackey for feedback and testing.
-   Thanks to Sam Weston for figuring out how to run Litestream on Kubernetes and writing up the docs for it.
-   Thanks to Rafael & Jungle Boogie for helping to get OpenBSD release builds working.
-   Thanks to Simon Gottschlag, Marin,Victor Björklund, Jonathan Beri Yuri, Nathan Probst, Yann Coleu, and Nicholas Grilly for frequent feedback, testing, & support.

Huge thanks to fly.io for their support and for contributing credits for testing and development!

Contribution Policy
-------------------

Initially, Litestream was closed to outside contributions. The goal was to reduce burnout by limiting the maintenance overhead of reviewing and validating third-party code. However, this policy is overly broad and has prevented small, easily testable patches from being contributed.

Litestream is now open to code contributions for bug fixes only. Features carry a long-term maintenance burden so they will not be accepted at this time. Please submit an issue if you have a feature you'd like to request.

If you find mistakes in the documentation, please submit a fix to the documentation repository.
