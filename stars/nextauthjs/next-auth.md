---
project: next-auth
stars: 27702
description: Authentication for the Web.
url: https://github.com/nextauthjs/next-auth
---

  

### Auth.js

Authentication for the Web.

Open Source. Full Stack. Own Your Data.

Auth.js is a set of open-source packages that are built on standard Web APIs for authentication in modern applications with any framework on any platform in any JS runtime.

> Auth js is now part of Better Auth. We recommend new projects to start with Better Auth unless there are some very specific feature gaps (most notably stateless session management without a database).

Features
--------

### Flexible and easy to use

-   Designed to work with any OAuth service, it supports 2.0+, OIDC
-   Built-in support for many popular sign-in services
-   Email/Passwordless authentication
-   Passkeys/WebAuthn support
-   Bring Your Database - or none! - stateless authentication with any backend (Active Directory, LDAP, etc.)
-   Runtime-agnostic, runs anywhere! (Docker, Node.js, Serverless, etc.)

### Own your data

Auth.js can be used with or without a database.

-   An open-source solution that allows you to keep control of your data
-   Built-in support for MySQL, MariaDB, Postgres, Microsoft SQL Server, MongoDB, SQLite, GraphQL, etc.
-   Works great with databases from popular hosting providers

### Secure by default

-   Promotes the use of passwordless sign-in mechanisms
-   Designed to be secure by default and encourage best practices for safeguarding user data
-   Uses Cross-Site Request Forgery (CSRF) Tokens on POST routes (sign in, sign out)
-   Default cookie policy aims for the most restrictive policy appropriate for each cookie
-   When JSON Web Tokens are used, they are encrypted by default (JWE) with A256CBC-HS512
-   Features tab/window syncing and session polling to support short-lived sessions
-   Attempts to implement the latest guidance published by Open Web Application Security Project

Advanced configuration allows you to define your routines to handle controlling what accounts are allowed to sign in, for encoding and decoding JSON Web Tokens and to set custom cookie security policies and session properties, so you can control who can sign in and how often sessions have to be re-validated.

### TypeScript

Auth.js libraries are written with type safety in mind. Check out the docs for more information.

Security
--------

If you think you have found a vulnerability (or are not sure) in Auth.js or any of the related packages (i.e. Adapters), we ask you to read our Security Policy to reach out responsibly. Please do not open Pull Requests/Issues/Discussions before consulting with us.

Acknowledgments
---------------

Auth.js is made possible thanks to all of its contributors.

Contributing
------------

We're open to all community contributions! If you'd like to contribute in any way, please first read our Contributing Guide.

License
-------

ISC
