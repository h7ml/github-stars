---
project: R2-Explorer
stars: 351
description: A Google Drive Interface for your Cloudflare R2 Buckets!
url: https://github.com/G4brym/R2-Explorer
---

_A Google Drive Interface for your Cloudflare R2 Buckets!_

* * *

**Documentation**: r2explorer.dev

**Demo**: demo.r2explorer.dev

**Source Code**: github.com/G4brym/R2-Explorer

* * *

Read this in other languages: Español, Português, Français

Features
--------

-   Self-hosted/Deployed on your own Cloudflare Account
-   Receive and read emails (via Cloudflare Email Routing)
-   Security:
    -   Basic Auth
    -   Cloudflare Access
-   Managing files:
    -   In-browser File preview (pdf, image, txt, markdown, csv, logpush...)
    -   In-browser File editing
    -   Drag-and-Drop upload
    -   Upload files or folders with files
    -   Multipart upload for big files
    -   HTTP/Custom metadata edit
-   Organization:
    -   Create folders
    -   Upload/Rename/Download/Delete files
    -   Right click in file for extra options

Installation
------------

1.  Method: Github Action
2.  Method: Create Cloudflare CLI
3.  Method: Template

Learn more about keeping your instance updated in the Updating your project docs.

Coming soon
-----------

-   allow bucket names with spaces
-   Search files
-   Rename folders
-   Image thumbnail's ?
-   Object detection on images using workers-ai ?
-   Tooltip when hovering a file with absolute time in "x days time ago" format
-   support for responding to emails
-   More advanced file editing with more validations per file type

Known issues
------------

-   Email inline images and assets don't load when using basic auth
