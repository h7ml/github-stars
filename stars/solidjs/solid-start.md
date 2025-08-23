---
project: solid-start
stars: 5601
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
    -   Static Site Generation _(SSG)_
-   **TypeScript**: Full integration for robust, type-safe development
-   **File-Based Routing**: Intuitive routing based on your project’s file structure
-   **API Routes**: Dedicated server-side endpoints for seamless API development
-   **Streaming**: Efficient data rendering for faster page loads
-   **Build Optimizations**: Code splitting, tree shaking, and dead code elimination
-   **Deployment Adapters**: Easily deploy to platforms like Vercel, Netlify, Cloudflare, and more

Getting Started
---------------

### Installation

Create a template project with your preferred package manager

# using npm
npm create solid@latest -- --solidstart

# using pnpm
pnpm create solid@latest --solidstart

# using bun
bun create solid@latest --solidstart

1.  Follow the CLI prompts to set up your project
2.  Navigate to your project directory and install the dependencies

cd <project-name\>
npm install # or pnpm install or bun install

1.  Start the development server

npm run dev # or pnpm dev or bun dev

### Project Structure

-   `public/`: Static assets like icons, images, and fonts
-   `src/`: Core application (aliased to `~/`)
    -   `routes/`: File-based routing for pages and APIs
    -   `app.tsx`: Root component of your application
    -   `entry-client.tsx`: Handles client-side hydration
    -   `entry-server.tsx`: Manages server-side request handling
-   **Configuration Files**: `app.config.ts`, `package.json`, and more

Learn more about routing in the documentation.

Adapters
--------

Configure adapters in `app.config.ts` to deploy to platforms like Vercel, Netlify, Cloudflare, and others

import { defineConfig } from "@solidjs/start/config";

export default defineConfig({
  ssr: true, // false for client-side rendering only
  server: { preset: "vercel" },
});

Presets also include runtimes like Node.js, Bun or Deno. For example, the `node-server` preset enables hosting on your server. Learn more about `defineConfig`.

Building for Production
-----------------------

Generate production-ready bundles

npm run build # or pnpm build or bun build

After the build completes, you’ll be guided through deployment for your specific preset.

Contributing
------------

Join the SolidJS community and contribute!

-   Discord: Ask for help and discuss ideas
-   Issues: Report bugs or suggest features
-   Docs Issues: Report documentation issues

### Development Setup

Use a Node.js version manager compatible with `.node-version`. We recommend asdf-vm for macOS and Linux users.

### Monorepo & Package Manager

SolidStart uses `pnpm` as the package manager. Install it globally:

npm install -g pnpm

Install dependencies for the monorepo:

pnpm install

Build the project:

pnpm build

### Monorepo & `package.json` Workspaces

If using a monorepo with `package.json` `"workspaces"` (e.g., Yarn Workspaces), ensure `@solidjs/start` is not hoisted. Add it to the `"nohoist"` field in the workspace root or project root:

**Workspace Root Example**:

{
  "workspaces": {
    "packages": \[
      /\* ... \*/
    \],
    "nohoist": \["\*\*/@solidjs/start"\]
  }
}

**Project Root Example**:

{
  "workspaces": {
    "nohoist": \["@solidjs/start"\]
  }
}

For **Yarn v2+**, use `installConfig` to prevent hoisting:

{
  "installConfig": {
    "hoistingLimits": "dependencies"
  }
}

**Note**: Add `@solidjs/start` as a `devDependency` in the child `package.json` to ensure the `/node_modules/@solidjs/start/runtime/entry.jsx` script is available.
