---
project: Next-Bootstrap-ts
stars: 12
description: React project scaffold based on TypeScript, Next.js & Bootstrap
url: https://github.com/idea2app/Next-Bootstrap-ts
---

Next-Bootstrap-ts
=================

React project scaffold based on TypeScript, Next.js, Bootstrap & Workbox. And this project bootstrapped with `create-next-app`.

Technology stack
----------------

-   Language: TypeScript v5 + MDX v3
-   Component engine: Next.js v15
-   Component suite: Bootstrap v5
-   PWA framework: Workbox v6
-   State management: MobX v6
-   API router: Koa 2
-   CI / CD: GitHub Actions + Vercel
-   Monitor service: Sentry

Major examples
--------------

1.  Markdown articles
2.  Editor components
3.  Pagination table
4.  Scroll list
5.  Not Found page (NGO)
    -   Global: https://notfound.org/
    -   Chinese: https://www.dnpw.org/cn/pa-notfound.html

Best practice
-------------

1.  Install GitHub apps in your organization or account:
    
    1.  Probot settings: set up Issue labels & Pull Request rules
    2.  PR badge: set up Online VS Code editor entries in Pull Request description
2.  Click the **Use this template button** on the top of this GitHub repository's home page, then create your own repository in the app-installed namespace above
    
3.  Click the **Open in GitHub codespaces button** on the top of ReadMe file, then an **online VS Code development environment** will be started immediately
    
4.  Set Vercel variables as Repository secrets, then every commit will get an independent **Preview URL**
    
5.  Recommend to add a Notification step in GitHub actions for your Team IM app
    
6.  Remind the PMs & users of your product to submit **Feature/Enhancement** requests or **Bug** reports with Issue forms instead of IM messages or Mobile Phone calls
    
7.  Collect all these issues into Project kanbans, then create **Pull requests** & add `closes #issue_number` into its description for automation
    

Getting Started
---------------

First, run the development server:

npm i pnpm -g
pnpm dev

Open http://localhost:3000 with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

API routes can be accessed on http://localhost:3000/api/hello. This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as API routes instead of React pages.

Learn More
----------

To learn more about Next.js, take a look at the following resources:

-   Next.js Documentation - learn about Next.js features and API.
-   Learn Next.js - an interactive Next.js tutorial.

You can check out the Next.js GitHub repository - your feedback and contributions are welcome!

Deployment
----------

### Environment variables

name

file

description

`SENTRY_AUTH_TOKEN`

`.env.local`

Official document

`SENTRY_ORG`

`.env`

Official document

`SENTRY_PROJECT`

`.env`

Official document

`NEXT_PUBLIC_SENTRY_DSN`

`.env`

Official document

### Vercel

The easiest way to deploy your Next.js app is to use the Vercel Platform from the creators of Next.js.

Check out our Next.js deployment documentation for more details.

### Docker

pnpm pack-image
pnpm container
