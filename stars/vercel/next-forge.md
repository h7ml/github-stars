---
project: next-forge
stars: 6563
description: Production-grade Turborepo template for Next.js apps.
url: https://github.com/vercel/next-forge
---

▲ / next-forge
==============

**Production-grade Turborepo template for Next.js apps.**

Overview
--------

next-forge is a production-grade Turborepo template for Next.js apps. It's designed to be a comprehensive starting point for building SaaS applications, providing a solid, opinionated foundation with minimal configuration required.

Built on a decade of experience building web applications, next-forge balances speed and quality to help you ship thoroughly-built products faster.

### Philosophy

next-forge is built around five core principles:

-   **Fast** — Quick to build, run, deploy, and iterate on
-   **Cheap** — Free to start with services that scale with you
-   **Opinionated** — Integrated tooling designed to work together
-   **Modern** — Latest stable features with healthy community support
-   **Safe** — End-to-end type safety and robust security posture

Demo
----

Experience next-forge in action:

-   Web — Marketing website
-   App — Main application
-   Storybook — Component library
-   API — API health check

Features
--------

next-forge comes with batteries included:

### Apps

-   **Web** — Marketing site built with Tailwind CSS and TWBlocks
-   **App** — Main application with authentication and database integration
-   **API** — RESTful API with health checks and monitoring
-   **Docs** — Documentation site powered by Mintlify
-   **Email** — Email templates with React Email
-   **Storybook** — Component development environment

### Packages

-   **Authentication** — Powered by Clerk
-   **Database** — Type-safe ORM with migrations
-   **Design System** — Comprehensive component library with dark mode
-   **Payments** — Subscription management via Stripe
-   **Email** — Transactional emails via Resend
-   **Analytics** — Web (Google Analytics) and product (Posthog)
-   **Observability** — Error tracking (Sentry), logging, and uptime monitoring (BetterStack)
-   **Security** — Application security (Arcjet), rate limiting, and secure headers
-   **CMS** — Type-safe content management for blogs and documentation
-   **SEO** — Metadata management, sitemaps, and JSON-LD
-   **AI** — AI integration utilities
-   **Webhooks** — Inbound and outbound webhook handling
-   **Collaboration** — Real-time features with avatars and live cursors
-   **Feature Flags** — Feature flag management
-   **Cron** — Scheduled job management
-   **Storage** — File upload and management
-   **Internationalization** — Multi-language support
-   **Notifications** — In-app notification system

Getting Started
---------------

### Prerequisites

-   Node.js 20+
-   pnpm (or npm/yarn/bun)
-   Stripe CLI for local webhook testing

### Installation

Create a new next-forge project:

npx next-forge@latest init

### Setup

1.  Configure your environment variables
2.  Set up required service accounts (Clerk, Stripe, Resend, etc.)
3.  Run the development server

For detailed setup instructions, read the documentation.

Structure
---------

next-forge uses a monorepo structure managed by Turborepo:

```
next-forge/
├── apps/           # Deployable applications
│   ├── web/        # Marketing website (port 3001)
│   ├── app/        # Main application (port 3000)
│   ├── api/        # API server
│   ├── docs/       # Documentation
│   ├── email/      # Email templates
│   └── storybook/  # Component library
└── packages/       # Shared packages
    ├── design-system/
    ├── database/
    ├── auth/
    └── ...
```

Each app is self-contained and independently deployable. Packages are shared across apps for consistency and maintainability.

Documentation
-------------

Full documentation is available at next-forge.com/docs, including:

-   Detailed setup guides
-   Package documentation
-   Migration guides for swapping providers
-   Deployment instructions
-   Examples and recipes

Contributing
------------

We welcome contributions! See the contributing guide for details.

Contributors
------------

Made with contrib.rocks.

License
-------

MIT
