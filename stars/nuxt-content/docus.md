---
project: docus
stars: 1897
description: Write beautiful documentations with Nuxt and Markdown.
url: https://github.com/nuxt-content/docus
---

> Create beautiful docs with Markdown & Vue components

🚀 Quick Start
--------------

Create a new documentation project in seconds:

# Create a new project
npx create-docus my-docs

# Or create with i18n template for multi-language docs
npx create-docus my-docs -t i18n

# Navigate to your project
cd my-docs

# Start development server
npm run dev

That's it! Your documentation site will be running at `http://localhost:3000`

🎯 What it creates
------------------

The CLI scaffolds a complete documentation project with:

-   ✨ **Beautiful Design** - Clean, modern documentation theme
-   📱 **Responsive** - Mobile-first responsive design
-   🌙 **Dark Mode** - Built-in dark/light mode support
-   🌍 **Internationalization** - Native i18n support for multi-language docs
-   🔍 **Search** - Full-text search functionality
-   📝 **Markdown Enhanced** - Extended markdown with custom components
-   🎨 **Customizable** - Easy theming and brand customization
-   ⚡ **Fast** - Optimized for performance with Nuxt 4
-   🔧 **TypeScript** - Full TypeScript support

Learn more on the Docus documentation.

📁 Project Structure
--------------------

### Generated project

```
my-docs/
├── content/              # Your markdown content
│   ├── index.md         # Homepage
│   └── docs/            # Documentation pages
├── public/              # Static assets
└── package.json         # Dependencies and scripts
```

### Optional files and folders

Docus uses a layer system, you can go further and use any feature or file of a classical Nuxt project:

```
my-docs/
├── app.config.ts        # App configuration
├── nuxt.config.ts       # Nuxt configuration (add extra modules, components, etc.)
├── app/                 # App directory
│   ├── components/      # Components (add your own components)
│   ├── layouts/         # Layouts (add your own layouts)
│   └── pages/           # Pages (add your own pages)
└── server/              # Server-side code (add your own server-side code)
```

### `/content` folder structure

**Single language structure:**

```
content/
├── index.md
├── getting-started.md
└── guide/
    ├── introduction.md
    └── configuration.md
```

**Multi-language structure (with i18n):**

```
content/
├── en/
│   ├── index.md
│   └── guide/
│       └── introduction.md
└── fr/
    ├── index.md
    └── guide/
        └── introduction.md
```

⚡ Built with
------------

Your project comes pre-configured with the best of the Nuxt ecosystem:

-   Nuxt 4 - The web framework
-   Nuxt Content - File-based CMS
-   Nuxt UI Pro - Premium UI components
-   Nuxt Image - Optimized images
-   Tailwind CSS 4 - Utility-first CSS
-   Docus Layer - Documentation theme
-   Nuxt i18n - Internationalization

📖 Documentation
----------------

For detailed documentation on customizing your Docus project, visit the Docus Documentation

🛠️ Development
---------------

This repository contains the CLI tool source code.

### Local Development

To contribute to the CLI tool:

# Clone this repository
git clone https://github.com/nuxt-content/docus

# Install dependencies
pnpm install

# Run the dev server to run the docus docs
pnpm run dev

### Package Structure

This is a monorepo containing:

-   **`/cli`** - CLI tool (`create-docus`)
-   **`/layer`** - Docus Nuxt layer (`docus`)
-   **`/docs`** - Official documentation
-   **`/.starters`** - Starters project

📄 License
----------

Published under the MIT license.

* * *

Docus has been entirely rewritten from scratch and is inspired from undocs made by @pi0 💚
