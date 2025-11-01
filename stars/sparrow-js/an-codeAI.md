---
project: an-codeAI
stars: 727
description: AI generate code
url: https://github.com/sparrow-js/an-codeAI
---

needware.dev
============

**An open-source AI-powered full-stack development platform that generates, previews, and deploys web applications directly in your browser.**

Demo • Documentation • Features • Getting Started

* * *

📖 Table of Contents
--------------------

-   About
-   Video Demo
-   Features
-   Tech Stack
-   Getting Started
    -   Prerequisites
    -   Installation
    -   Environment Variables
    -   Database Setup
-   Project Structure
-   AI Agents
-   Usage
-   Development
-   Deployment
-   Contributing
-   License
-   Acknowledgments

* * *

🎯 About
--------

needware.dev is a cutting-edge AI-powered development platform that revolutionizes how you build web applications. Leveraging multiple AI models and an intelligent agent system, it transforms ideas, screenshots, or URLs into fully functional web applications - all within your browser's isolated sandbox environment.

### Key Highlights

-   🤖 **Multi-Agent System**: Intelligent agents for different code generation tasks
-   🎨 **Visual-to-Code**: Convert screenshots directly into working code
-   🔗 **Clone-to-Code**: Analyze and replicate websites from URLs
-   💡 **Idea-to-Code**: Transform text descriptions into complete applications
-   🏗️ **Real-time Preview**: Instant preview with WebContainer technology
-   🗄️ **Database Integration**: Built-in Supabase support for database operations
-   🎭 **Multi-Model Support**: Works with OpenAI, Anthropic, Google, DeepSeek, and more

* * *

🎬 Video Demo
-------------

Here's a feature demonstration video of needware.dev:

output.mov

output.mov

* * *

✨ Features
----------

### Core Capabilities

-   🧠 **AI-Powered Code Generation**: Full-stack web development for Node.js applications directly in your browser
-   📸 **Screenshot to Code**: Upload design mockups and convert them to working code
-   🔗 **URL Cloning**: Analyze existing websites and generate similar implementations
-   💭 **Natural Language**: Describe your idea and watch it come to life
-   🖼️ **Image Context**: Attach images to prompts for better contextual understanding
-   🎨 **Visual Editor**: Built-in code editor with syntax highlighting and autocomplete

### Development Tools

-   🔄 **Real-time Preview**: Instant preview with hot reload in isolated sandbox
-   📦 **Project Export**: Download projects as ZIP files for easy portability
-   🗂️ **File Management**: Complete file system with create, edit, and delete operations
-   🐚 **Integrated Terminal**: Built-in terminal for running commands
-   🔍 **Code Diff View**: Visual comparison of code changes
-   📝 **Markdown Support**: Rich text rendering with syntax highlighting

### Database & Backend

-   🗄️ **Supabase Integration**: Built-in database management and operations
-   🔐 **Authentication**: Secure user authentication with NextAuth.js
-   📊 **Data Visualization**: Charts and analytics for your data
-   🔒 **Encryption**: Database field encryption for sensitive data

### Deployment & Collaboration

-   🚀 **One-Click Deploy**: Deploy to Cloudflare, Netlify, or Vercel
-   ☁️ **Cloud Storage**: Save and sync projects to the cloud
-   📜 **Version History**: Track changes with artifact snapshots
-   👥 **Multi-User Support**: User management and project isolation

### AI & Models

-   🤖 **Multiple AI Providers**: OpenAI, Anthropic, Google, DeepSeek, Mistral, Cohere, and more
-   🎯 **LangGraph Agents**: Sophisticated multi-agent workflows
-   🧩 **Firecrawl Integration**: Advanced web scraping for URL analysis
-   📚 **Context-Aware**: Maintains conversation history for better results

* * *

🛠️ Tech Stack
--------------

### Frontend

-   **Framework**: Next.js 15 (App Router)
-   **UI Library**: React 19
-   **Styling**: Tailwind CSS 4, SCSS
-   **Components**: Radix UI, shadcn/ui
-   **Code Editor**: CodeMirror 6
-   **Terminal**: xterm.js
-   **Animation**: Framer Motion

### Backend & AI

-   **AI SDK**: Vercel AI SDK
-   **Agent Framework**: LangChain, LangGraph
-   **AI Providers**:
    -   OpenAI, Anthropic (Claude), Google (Gemini)
    -   DeepSeek, Mistral, Cohere
    -   AWS Bedrock, OpenRouter
-   **Web Scraping**: Firecrawl

### Database & ORM

-   **Database**: Supabase (PostgreSQL)
-   **ORM**: Drizzle ORM
-   **Authentication**: NextAuth.js 5

### Sandbox & Runtime

-   **Browser Runtime**: WebContainer API
-   **File System**: Custom virtual file system
-   **Package Manager**: pnpm

### Deployment & Storage

-   **Hosting**: Vercel, Cloudflare Pages, Netlify
-   **Storage**: Supabase Storage, Vercel Blob
-   **Version Control**: isomorphic-git

* * *

🚀 Getting Started
------------------

### Prerequisites

Before you begin, ensure you have the following installed:

-   **Node.js**: v18.17 or higher
-   **pnpm**: v8.0 or higher
-   **Git**: Latest version

### Installation

1.  **Clone the repository**:
    
    git clone https://github.com/yourusername/genfly.git
    cd genfly
    
2.  **Install pnpm** (if not already installed):
    
    npm install -g pnpm
    
3.  **Install dependencies**:
    
    pnpm install
    

### Environment Variables

Create a `.env.local` file in the root directory:

# Copy and edit the environment variables
touch .env.local

Then add the following variables to your `.env.local` file:

# ====================
# App Configuration
# ====================
NEXT\_PUBLIC\_APP\_URL\=http://localhost:3000

# ====================
# Database (Supabase)
# ====================
# PostgreSQL connection string
DATABASE\_URL\=postgresql://user:password@host:port/database

# Supabase project URL (found in your Supabase project settings)
NEXT\_PUBLIC\_SUPABASE\_URL\=your\_supabase\_project\_url

# Supabase anonymous key (found in your Supabase project settings)
NEXT\_PUBLIC\_SUPABASE\_ANON\_KEY\=your\_supabase\_anon\_key

# Supabase service role key (found in your Supabase project settings)
SUPABASE\_SERVICE\_ROLE\_KEY\=your\_supabase\_service\_role\_key

# Supabase access token (for management API operations)
SUPABASE\_ACCESS\_TOKEN\=your\_supabase\_access\_token

# Database encryption key (generate a random 32-character string)
DB\_ENCRYPTION\_KEY\=your\_random\_32\_character\_encryption\_key

# ====================
# Authentication (NextAuth v5)
# ====================
# Generate with: openssl rand -base64 32
AUTH\_SECRET\=your\_random\_secret\_string

# Auth URL (same as NEXT\_PUBLIC\_APP\_URL in development)
AUTH\_URL\=http://localhost:3000

# Optional: Enable auth debugging
# AUTH\_DEBUG=true

# GitHub OAuth (optional, for GitHub login)
GITHUB\_ID\=your\_github\_oauth\_app\_client\_id
GITHUB\_SECRET\=your\_github\_oauth\_app\_client\_secret

# Google OAuth (optional, for Google login)
GOOGLE\_CLIENT\_ID\=your\_google\_oauth\_client\_id
GOOGLE\_CLIENT\_SECRET\=your\_google\_oauth\_client\_secret

# Notion OAuth (optional, for Notion login)
AUTH\_NOTION\_ID\=your\_notion\_oauth\_client\_id
AUTH\_NOTION\_SECRET\=your\_notion\_oauth\_client\_secret
AUTH\_NOTION\_REDIRECT\_URI\=http://localhost:3000/api/auth/callback/notion

# ====================
# AI Model API Keys
# ====================
# Configure at least one AI provider

# OpenAI (GPT-3.5, GPT-4, GPT-4o, etc.)
OPENAI\_API\_KEY\=your\_openai\_api\_key

# Anthropic (Claude models)
ANTHROPIC\_API\_KEY\=your\_anthropic\_api\_key

# DeepSeek
DEEPSEEK\_API\_KEY\=your\_deepseek\_api\_key

# OpenRouter (access to multiple models)
OPEN\_ROUTER\_API\_KEY\=your\_openrouter\_api\_key

# ====================
# Optional Services
# ====================
# Firecrawl API for URL cloning feature
FIRECRAWL\_API\_KEY\=your\_firecrawl\_api\_key

# Vercel Blob Storage for file uploads
BLOB\_READ\_WRITE\_TOKEN\=your\_vercel\_blob\_token

# GitHub Personal Access Token (for template fetching and deployment)
NEXT\_PUBLIC\_GITHUB\_TOKEN\=your\_github\_personal\_access\_token

# Fly.io API Token (for Fly.io deployment)
FLY\_API\_TOKEN\=your\_fly\_api\_token

# Cloudflare API credentials (for Cloudflare Pages deployment)
CLOUDFLARE\_API\_TOKEN\=your\_cloudflare\_api\_token
CLOUDFLARE\_ACCOUNT\_ID\=your\_cloudflare\_account\_id

# Google Site Verification (for Google Search Console)
GOOGLE\_SITE\_VERIFICATION\=your\_google\_verification\_code

# ====================
# Admin Configuration
# ====================
# Comma-separated list of admin email addresses
ADMIN\_EMAIL\=admin@example.com,admin2@example.com

# Set to "true" to disable new user signups (admin-only mode)
# DISABLE\_SIGNUP=true

#### 📋 Configuration Notes

**Required (Minimum Setup):**

-   `NEXT_PUBLIC_APP_URL` - Your application URL
-   `DATABASE_URL` - PostgreSQL connection string
-   `NEXT_PUBLIC_SUPABASE_URL` - Supabase project URL
-   `NEXT_PUBLIC_SUPABASE_ANON_KEY` - Supabase anonymous key
-   `SUPABASE_SERVICE_ROLE_KEY` - Supabase service role key
-   `AUTH_SECRET` - NextAuth secret (generate with `openssl rand -base64 32`)
-   At least one AI provider API key (OpenAI, Anthropic, Google, or DeepSeek)

**Optional (Enhanced Features):**

-   OAuth providers (GitHub, Google, Notion) - for social login
-   `FIRECRAWL_API_KEY` - for URL cloning feature
-   `BLOB_READ_WRITE_TOKEN` - for file uploads via Vercel Blob
-   `NEXT_PUBLIC_GITHUB_TOKEN` - for GitHub template fetching
-   `FLY_API_TOKEN` - for Fly.io deployment
-   `CLOUDFLARE_API_TOKEN` & `CLOUDFLARE_ACCOUNT_ID` - for Cloudflare deployment
-   `ADMIN_EMAIL` - to designate admin users
-   `DB_ENCRYPTION_KEY` - for database field encryption

**How to get API keys:**

-   **OpenAI**: platform.openai.com/api-keys
-   **Anthropic**: console.anthropic.com
-   **Google AI**: makersuite.google.com/app/apikey
-   **DeepSeek**: platform.deepseek.com
-   **OpenRouter**: openrouter.ai/keys
-   **Firecrawl**: firecrawl.dev
-   **Supabase**: supabase.com - create a project and find keys in Settings → API

### Database Setup

1.  **Set up Supabase**:
    
    -   Create a new project at supabase.com
    -   Copy your project URL and API keys to `.env.local`
2.  **Run database migrations**:
    
    pnpm run migrate
    
    Or generate new migrations:
    
    pnpm run generate
    

### Running the Application

1.  **Start the development server**:
    
    pnpm run dev
    
2.  **Open your browser**:
    
    Navigate to http://localhost:3000
    
3.  **Build for production**:
    
    pnpm run build
    pnpm start
    

* * *

📁 Project Structure
--------------------

```
genfly/
├── agent/                      # AI Agent System
│   ├── clone-url-to-code/     # URL to code conversion agent
│   ├── idea-to-code/          # Natural language to code agent
│   ├── screenshot-to-code/    # Image to code agent
│   ├── supervisor/            # Agent orchestration
│   └── utils/                 # Shared agent utilities
├── app/                       # Next.js App Router
│   ├── api/                   # API routes
│   ├── (auth)/                # Authentication pages
│   └── layout.tsx             # Root layout
├── components/                # React components
│   ├── chat/                  # Chat interface
│   ├── editor/                # Code editor
│   ├── workbench/             # Main workbench UI
│   ├── sidebar/               # Navigation sidebar
│   └── shadui/                # UI components
├── db/                        # Database configuration
│   ├── schema.ts              # Drizzle ORM schema
│   └── index.ts               # Database client
├── lib/                       # Utility libraries
│   ├── modules/               # Core modules
│   ├── stores/                # State management (zustand)
│   ├── hooks/                 # Custom React hooks
│   └── persistence/           # Data persistence layer
├── types/                     # TypeScript type definitions
├── utils/                     # Utility functions
├── migrations/                # Database migrations
├── public/                    # Static assets
└── styles/                    # Global styles

```

* * *

🤖 AI Agents
------------

The platform uses a multi-agent architecture powered by LangGraph:

### Agent Types

1.  **Idea to Code Agent** (`agent/idea-to-code/`)
    
    -   Converts natural language descriptions into code
    -   Understands project context and requirements
    -   Generates full-stack applications
2.  **Screenshot to Code Agent** (`agent/screenshot-to-code/`)
    
    -   Analyzes UI design screenshots
    -   Extracts layout, styling, and component structure
    -   Generates responsive HTML/CSS/JavaScript
3.  **Clone URL to Code Agent** (`agent/clone-url-to-code/`)
    
    -   Scrapes and analyzes target websites
    -   Uses Firecrawl for content extraction
    -   Replicates functionality and styling
4.  **Supervisor Agent** (`agent/supervisor/`)
    
    -   Orchestrates multiple agents
    -   Routes requests to appropriate agents
    -   Manages workflow state and transitions

### Agent Workflow

```
User Input → Supervisor → Route to Specific Agent → Generate Code → Preview → Deploy
                ↓
         Context Management
                ↓
         Multi-Model Selection
```

* * *

📘 Usage
--------

### Creating a Project

1.  **From an Idea**:
    
    -   Describe your application in natural language
    -   The AI will generate a complete project structure
    -   Preview and iterate on the result
2.  **From a Screenshot**:
    
    -   Upload a design mockup or UI screenshot
    -   The AI analyzes and converts it to code
    -   Customize the generated components
3.  **From a URL**:
    
    -   Paste the URL of a website you want to clone
    -   The AI scrapes and analyzes the site
    -   Generates a similar implementation

### Editing Code

-   Use the built-in **CodeMirror editor** with syntax highlighting
-   **Hot reload** preview updates automatically
-   Access the **integrated terminal** for commands
-   View **file tree** for easy navigation

### Managing Database

-   Create and manage **Supabase tables** directly
-   Execute **SQL queries** from the UI
-   View and edit **table data**
-   Configure **authentication** and **storage**

### Deploying

1.  Click the **Deploy** button in the workbench
2.  Choose your platform (Vercel, Cloudflare, Netlify)
3.  Configure deployment settings
4.  Deploy with one click

* * *

🔧 Development
--------------

### Available Scripts

# Development
pnpm dev              # Start dev server with Turbo
pnpm build            # Build for production
pnpm start            # Start production server

# Database
pnpm generate         # Generate Drizzle migrations
pnpm migrate          # Push migrations to database

# Code Quality
pnpm lint             # Run ESLint

### Code Style

-   **TypeScript** for type safety
-   **ESLint** for code linting
-   **Prettier** (recommended) for formatting
-   Follow the existing code structure and patterns

* * *

🚢 Deployment
-------------

### Self-Hosting

1.  **Build the application**:
    
    pnpm build
    
2.  **Set up your database**:
    
    -   Configure PostgreSQL or Supabase
    -   Run migrations
3.  **Configure environment variables** on your hosting platform
    
4.  **Deploy** to your preferred platform:
    
    -   Vercel
    -   Cloudflare Pages
    -   Netlify
    -   Your own VPS

* * *

🤝 Contributing
---------------

We welcome contributions from the community! Here's how you can help:

1.  **Fork the repository**
2.  **Create a feature branch**: `git checkout -b feature/amazing-feature`
3.  **Commit your changes**: `git commit -m 'Add amazing feature'`
4.  **Push to the branch**: `git push origin feature/amazing-feature`
5.  **Open a Pull Request**

### Contribution Guidelines

-   Write clear, descriptive commit messages
-   Follow the existing code style
-   Add tests for new features
-   Update documentation as needed
-   Be respectful and constructive in discussions

* * *

📄 License
----------

This project is licensed under the **Apache License 2.0** - see the LICENSE file for details.

* * *

🙏 Acknowledgments
------------------

This project builds upon amazing open-source technologies:

-   WebContainer API - Browser-based runtime
-   LangChain & LangGraph - Agent orchestration
-   Vercel AI SDK - Multi-model AI integration
-   Next.js - React framework
-   Supabase - Backend infrastructure
-   shadcn/ui - UI components

Special thanks to all contributors and the open-source community!

* * *

**Built with ❤️ by the needware.dev team**

Website • Issues • Discussions
