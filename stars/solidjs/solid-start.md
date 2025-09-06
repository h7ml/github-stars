---
project: solid-start
stars: 5621
description: SolidStart, the Solid app framework
url: https://github.com/solidjs/solid-start
---

**SolidStart** brings fine-grained reactivity fullstack with full flexibility. Built with features like unified rendering and isomorphic code execution, SolidStart enables you to create highly performant and scalable web applications.

Explore the official documentation for detailed guides and examples.

Core Features
-------------

-   **All Rendering Modes**:
    -   Server-Side Rendering _(SSR)_ with sync, async, and stream modes
    -   Client-Side Rendering _(CSR)_
    -   Static Site Generation _(SSG)_ with route pre-rendering
-   **TypeScript**: Full integration for robust, type-safe development
-   **File-Based Routing**: Intuitive routing based on your project’s file structure
-   **API Routes**: Dedicated server-side endpoints for seamless API development
-   **Streaming**: Efficient data rendering for faster page loads
-   **Build Optimizations**: Code splitting, tree shaking, and dead code elimination
-   **Deployment Adapters**: Easily deploy to platforms like Vercel, Netlify, Cloudflare, and more

Getting Started
---------------

### Installation

Create a SolidStart template project with your preferred package manager

# using npm
npm create solid@latest -- -s

# using pnpm
pnpm create solid@latest -s

# using bun
bun create solid@latest --s

### Project Structure

-   `public/`: Static assets like icons, images, and fonts
-   `src/`: Core application (aliased to `~/`)
    -   `routes/`: File-based routing for pages and APIs
    -   `app.tsx`: Root component of your application
    -   `entry-client.tsx`: Handles client-side hydration
    -   `entry-server.tsx`: Manages server-side request handling
-   **Configuration Files**: `app.config.ts`, `package.json`, and more

Learn more about routing

Adapters
--------

Configure adapters in `app.config.ts` to deploy to platforms like Vercel, Netlify, Cloudflare, and others

import { defineConfig } from "@solidjs/start/config";

export default defineConfig({
  ssr: true, // false for client-side rendering only
  server: { preset: "vercel" }
});

Presets also include runtimes like Node.js, Bun or Deno. For example, a preset like `node-server` enables hosting on your server.  
Learn more about `defineConfig`

Building
--------

Generate production-ready bundles

npm run build # or pnpm build or bun build

After the build completes, you’ll be guided through deployment for your specific preset.
