---
project: doko-blog
stars: 1
description: My new blog. Content will be migrated from Wordpress. Powered by Docusaurus V2.
url: https://github.com/Doko-Demo-Doa/doko-blog
---

doko-blog
=========

This is my new personal blog. I'm migrating away from Wordpress since it's too slow and inefficient. This website is built using Docusaurus 3, and is deployed automatically with DigitalOcean's App Platform.

### Installation

```
$ npm ci
```

### Local Development

```
$ npm run start
```

This command starts a local development server and open up a browser window. Most changes are reflected live without having to restart the server.

### Build

```
$ npm run build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

### Deployment

```
$ GIT_USER=<Your GitHub username> USE_SSH=true npm run deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.

### Continuous Integration

Some common defaults for linting/formatting have been set for you. If you integrate your project with an open source Continuous Integration system (e.g. Travis CI, CircleCI), you may check for issues using the following command.

```
$ npm run ci
```
