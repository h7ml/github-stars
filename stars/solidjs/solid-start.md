---
project: solid-start
stars: 5707
description: SolidStart, the Solid app framework
url: https://github.com/solidjs/solid-start
---

-   For building apps with SolidStart, check the package README and our official docs
-   For contributing to codebase, check CONTRIBUTING.md
-   For creating a new template, please head over to solidjs/templates

Prerequisites
-------------

-   **Node.js**: Use the version specified in `.nvmrc`. To manage multiple versions across your system, we recommend a version manager such as fnm, or another of your choice.
-   **pnpm**: Install globally via `npm install -g pnpm`. Or let **Corepack** handle it in the setup step below.
-   **Git**: Ensure Git is installed for cloning and managing the repository.

Monorepo Structure
------------------

SolidStart is a pnpm-based monorepo with nested workspaces. Key directories include:

-   **`packages/start`**: The core `@solidjs/start` package.
-   **`apps/landing-page`**: The official landing page.
-   **`apps/tests`**: Unit and end-to-end (E2E) tests using Vitest and Cypress.
-   **`apps/fixtures`**: Fixture projects for testing.

Use pnpm filters (e.g. `pnpm --filter @solidjs/start ...`) to target specific packages.

Local Setup
-----------

1.  Clone the repository
    
    git clone https://github.com/solidjs/solid-start.git
    cd solid-start
    
2.  Enable the correct pnpm version specified in package.json
    
    corepack enable
    
3.  Install dependencies
    
    pnpm dedupe
    
    (`pnpm dedupe` will install dependencies _and_ clean the lockfile from duplicates, useful for preventing conflicts).
    
4.  Build all packages and the landing page
    
    pnpm run build:all
    

If you encounter issues (e.g. missing `node_modules`), clean the workspace

pnpm run clean:all

Then reinstall dependencies and rebuild.

Running Tests
-------------

End-to-end tests are located in `apps/tests` projects. For manual testing and development use the `apps/fixtures` apps, and finally, integration and unit tests live inside their respective packages.

1.  Install the Cypress binary (required only once)
    
    pnpm --filter tests exec cypress install
    
2.  For unit tests that check build artifacts, build the test app first
    
    pnpm --filter tests run build
    
3.  Run unit tests
    
    pnpm --filter tests run unit
    
    -   CI mode (run once): `pnpm --filter tests run unit:ci`
    -   UI mode: `pnpm --filter tests run unit:ui`
4.  Run E2E tests
    
    pnpm --filter tests run tests:run
    
    -   Interactive mode: `pnpm --filter tests run tests:open`
    -   With dev server: `pnpm --filter tests run tests`
5.  Clean test artifacts
    
    pnpm run clean:test
    

Development
-----------

1.  Make your changes in the relevant package (e.g. `packages/start`)
    
2.  Rebuild affected packages
    
    pnpm run packages:build
    
    For a full rebuild: `pnpm run build:all`
    
3.  Test your changes
    
    -   For fixtures, pick the name of the fixture and run the `dev` with workspace filtering.
        
        pnpm --filter fixture-basic dev
        
    -   For the landing page (from the root directory)
        
        pnpm run lp:dev
        
4.  Clean builds if needed
    
    pnpm run packages:clean # Cleans packages' node\_modules and dist folders
    pnpm run lp:clean # Cleans the landing page
    pnpm run clean:root # Cleans root-level caches
    

* * *

If you have read all the way here, you're already a champ! 🏆 Thank you.
