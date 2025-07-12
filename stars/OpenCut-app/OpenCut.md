---
project: OpenCut
stars: 15497
description: The open-source CapCut alternative
url: https://github.com/OpenCut-app/OpenCut
---

OpenCut (prev AppCut)
=====================

### A free, open-source video editor for web, desktop, and mobile.

Why?
----

-   **Privacy**: Your videos stay on your device
-   **Free features**: Every basic feature of CapCut is paywalled now
-   **Simple**: People want editors that are easy to use - CapCut proved that

Features
--------

-   Timeline-based editing
-   Multi-track support
-   Real-time preview
-   No watermarks or subscriptions
-   Analytics provided by Databuddy, 100% Anonymized & Non-invasive.

Project Structure
-----------------

-   `apps/web/` – Main Next.js web application
-   `src/components/` – UI and editor components
-   `src/hooks/` – Custom React hooks
-   `src/lib/` – Utility and API logic
-   `src/stores/` – State management (Zustand, etc.)
-   `src/types/` – TypeScript types

Getting Started
---------------

### Prerequisites

Before you begin, ensure you have the following installed on your system:

-   Bun
-   Docker and Docker Compose
-   Node.js (for `npm` alternative)

### Setup

Getting Started
---------------

1.  Fork the repository
2.  Clone your fork locally
3.  Navigate to the web app directory: `cd apps/web`
4.  Install dependencies: `bun install`
5.  Start the development server: `bun run dev`

Development Setup
-----------------

### Prerequisites

-   Node.js 18+
-   Bun (latest version)
-   Docker (for local database)

### Local Development

1.  Start the database and Redis services:
    
    # From project root
    docker-compose up -d
    
2.  Navigate to the web app directory:
    
    cd apps/web
    
3.  Copy `.env.example` to `.env.local`:
    
    # Unix/Linux/Mac
    cp .env.example .env.local
    
    # Windows Command Prompt
    copy .env.example .env.local
    
    # Windows PowerShell
    Copy-Item .env.example .env.local
    
4.  Configure required environment variables in `.env.local`:
    
    **Required Variables:**
    
    # Database (matches docker-compose.yaml)
    DATABASE\_URL="postgresql://opencut:opencutthegoat@localhost:5432/opencut"
    
    # Generate a secure secret for Better Auth
    BETTER\_AUTH\_SECRET="your-generated-secret-here"
    BETTER\_AUTH\_URL="http://localhost:3000"
    
    # Redis (matches docker-compose.yaml)
    UPSTASH\_REDIS\_REST\_URL="http://localhost:8079"
    UPSTASH\_REDIS\_REST\_TOKEN="example\_token"
    
    # Development
    NODE\_ENV="development"
    
    **Generate BETTER\_AUTH\_SECRET:**
    
    # Unix/Linux/Mac
    openssl rand -base64 32
    
    # Windows PowerShell (simple method)
    \[System.Web.Security.Membership\]::GeneratePassword(32, 0)
    
    # Cross-platform (using Node.js)
    node -e "console.log(require('crypto').randomBytes(32).toString('base64'))"
    
    # Or use an online generator: https://generate-secret.vercel.app/32
    
    **Optional Variables (for Google OAuth):**
    
    # Only needed if you want to test Google login
    GOOGLE\_CLIENT\_ID="your-google-client-id"
    GOOGLE\_CLIENT\_SECRET="your-google-client-secret"
    
5.  Run database migrations: `bun run db:migrate` from (inside apps/web)
    
6.  Start the development server: `bun run dev` from (inside apps/web)
    

The application will be available at http://localhost:3000.

Contributing
------------

**Note**: We're currently moving at an extremely fast pace with rapid development and breaking changes. While we appreciate the interest, it's recommended to wait until the project stabilizes before contributing to avoid conflicts and wasted effort.

Visit CONTRIBUTING.md
---------------------

We welcome contributions! Please see our Contributing Guide for detailed setup instructions and development guidelines.

**Quick start for contributors:**

-   Fork the repo and clone locally
-   Follow the setup instructions in CONTRIBUTING.md
-   Create a feature branch and submit a PR

Sponsors
--------

Thanks to Vercel for their support of open-source software.

License
-------

MIT LICENSE

* * *
