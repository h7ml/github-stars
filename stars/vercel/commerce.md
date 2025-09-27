---
project: commerce
stars: 13499
description: Next.js Commerce
url: https://github.com/vercel/commerce
---

Next.js Commerce
================

A high-performance, server-rendered Next.js App Router ecommerce application.

This template uses React Server Components, Server Actions, `Suspense`, `useOptimistic`, and more.

> Note: Looking for Next.js Commerce v1? View the code, demo, and release notes.

Providers
---------

Vercel will only be actively maintaining a Shopify version as outlined in our vision and strategy for Next.js Commerce.

Vercel is happy to partner and work with any commerce provider to help them get a similar template up and running and listed below. Alternative providers should be able to fork this repository and swap out the `lib/shopify` file with their own implementation while leaving the rest of the template mostly unchanged.

-   Shopify (this repository)
-   BigCommerce (Demo)
-   Ecwid by Lightspeed (Demo)
-   Geins (Demo)
-   Medusa (Demo)
-   Prodigy Commerce (Demo)
-   Saleor (Demo)
-   Shopware (Demo)
-   Swell (Demo)
-   Umbraco (Demo)
-   Wix (Demo)
-   Fourthwall (Demo)

> Note: Providers, if you are looking to use similar products for your demo, you can download these assets.

Integrations
------------

Integrations enable upgraded or additional functionality for Next.js Commerce

-   Orama (Demo)
    
    -   Upgrades search to include typeahead with dynamic re-rendering, vector-based similarity search, and JS-based configuration.
    -   Search runs entirely in the browser for smaller catalogs or on a CDN for larger.
-   React Bricks (Demo)
    
    -   Edit pages, product details, and footer content visually using React Bricks visual headless CMS.

Running locally
---------------

You will need to use the environment variables defined in `.env.example` to run Next.js Commerce. It's recommended you use Vercel Environment Variables for this, but a `.env` file is all that is necessary.

> Note: You should not commit your `.env` file or it will expose secrets that will allow others to control your Shopify store.

1.  Install Vercel CLI: `npm i -g vercel`
2.  Link local instance with Vercel and GitHub accounts (creates `.vercel` directory): `vercel link`
3.  Download your environment variables: `vercel env pull`

pnpm install
pnpm dev

Your app should now be running on localhost:3000.

Expand if you work at Vercel and want to run locally and / or contribute

1.  Run `vc link`.
2.  Select the `Vercel Solutions` scope.
3.  Connect to the existing `commerce-shopify` project.
4.  Run `vc env pull` to get environment variables.
5.  Run `pnpm dev` to ensure everything is working correctly.

Vercel, Next.js Commerce, and Shopify Integration Guide
-------------------------------------------------------

You can use this comprehensive integration guide with step-by-step instructions on how to configure Shopify as a headless CMS using Next.js Commerce as your headless Shopify storefront on Vercel.
