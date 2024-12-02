---
project: R2-Explorer
stars: 336
description: A Google Drive Interface for your Cloudflare R2 Buckets!
url: https://github.com/G4brym/R2-Explorer
---

Read this in other languages: Español, Português, Français

R2-Explorer
===========

_A Google Drive Interface for your Cloudflare R2 Buckets!_

This project is deployed/self-hosted in your own Cloudflare Account as a Worker, and no credential/token is required to start using it.

* * *

**Documentation**: https://r2explorer.dev

**Live Demo**: https://demo.r2explorer.dev

* * *

Features
--------

-   PWA support (install this app on your phone)
-   Email Explorer (using Cloudflare Email Routing)
-   Basic Auth
-   Cloudflare Access Authentication
-   Very quick bucket/folder navigation
-   pdf, image, txt, markdown, csv, etc in-browser preview
-   Drag-and-Drop upload
-   Multiple files and folder uploads
-   Create folders
-   Upload/Rename/Download/Delete files
-   Right click in file for extra options
-   Multipart upload for big files
-   File editing

Getting Started
---------------

Run this command to get an example project setup

npm create cloudflare@latest r2-explorer -- --template "G4brym/R2-Explorer/template"

Upgrading your installation
---------------------------

In order to update to the latest version you just need to install the latest r2-explorer package from npm and re-deploy your application

npm install r2-explorer@latest --save

wrangler publish

TODO
----

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
