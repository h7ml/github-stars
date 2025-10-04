---
project: pkg-size.dev
stars: 863
description: 📦🔍 Find the true size of an npm package
url: https://github.com/privatenumber/pkg-size.dev
---

  
  
  

This repository serves as a place to file bug reports and feature requests for pkg-size.dev.

Currently, the project is in early stages of development and closed-source. But it may be open-sourced here in the future.

  

About
-----

The goal of pkg-size.dev is to make it easier for curious developers like you to explore the npm ecosystem. It allows you to browse projects in your dependency tree, discover new packages, and learn about their creators. Ultimately, it aims to foster a greater appreciation for the npm ecosystem.

#### For package users, _pkg-size_ helps you:

-   Uncover hidden dependencies and understand why they're installed.
-   Maintain control over your `node_modules` by being mindful of what you're installing and its impact on size.
-   Optimize web app performance by choosing smaller and optimized ESM packages.
-   Compare and evaluate similar packages to identify the best fit for your specific needs.
-   Discover the authors, developlment, and funding behind packages.

#### For package authors, _pkg-size_ helps you:

-   Evaluate installation bottlenecks to improve speed. Particularly important for CLI tools loaded with npx.
-   Ensure seamless downloads even in unideal conditions such as slow internet or low storage.
-   Minimize dependencies to reduce risks like breaking changes or malicious code.

  

FAQ
---

### Why care about package sizes?

Because they take up a lot of space on your disk. Even small packages can add up quickly. Try calculating the total size of all the `node_modules` on your disk.

When analyzing them, you may find some packages include unnecessary code and impact your app's performance.

> **Protip:** If you're interested in minimizing how much space `node_modules` consumes, check out pnpm. Not only do you regain a ton of disk space, it's also a huge DX improvement!

### What was this project inspired by?

This project draws inspiration from two amazing services: Package Phobia and Bundlephobia.

_pkg-size_ aims to improve upon these services in the following ways:

1.  **Consolidation**: _pkg-size_ combines insights from both services on one platform for a more cohesive analysis.
    
2.  **Dependency insights**: _pkg-size_ shows what was installed and why, providing valuable information for understanding the result, and helps with identifying large or duplicate dependencies. It also helps devs discover new packages.
    
3.  **Latest data**: _pkg-size_ does a fresh `npm install` each time, fetching the latest data and even reflecting updates in nested dependencies. In contrast, _Package Phobia_ and _Bundlephobia_ cache their results. For example, when calculating the installation size of `express`, if a nested dependency had a minor release that increased its size by 100MB, neither service would reflect the change in size because there's no version bump in `express`.
    
4.  **Peer Dependencies**: _pkg-size_ allows for the inclusion of peer dependencies in the size calculation, recognizing that they're essential for running packages.
    

### How does the website work?

This website operates entirely in your browser, from installing npm packages to bundling them!

At its core, the tool is built on WebContainers—a technology by StackBlitz that allows Node.js to run in-browser—, to run npm and install packages directly in your browser. It then analyzes the `node_modules` directory to gain insights into the installed packages and their stats. esbuild WASM is used to bundle the package.

The website is static (doesn't require a backend) and hosted on Vercel.

### Is it possible to show the import cost (tree shaking gains) of each named export?

In most cases, no.

In simple cases where each export is independent, you can easily see the cost of importing each one. For example:

export const A \= () \=> <10kb string\>;
export const B \= () \=> <20kb string\>;
export const C \= () \=> <30kb string\>;

However, in real-life examples, it's not always straightforward. For instance, in this slightly complex example:

const data \= \[
	<10kb string\>,
	<20kb string\>,
\];

export const A \= () \=> data\[0\];
export const B \= () \=> data\[1\];
export const C \= () \=> <30kb string\>;

Both `A` and `B` depend on `data`, so either importing `A` or `B` alone will pull in the 30kb `data`. To tree shake it, you need to remove both `A` and `B`. That's to say, neither `A` or `B` have individual import costs.

Determining whether an export has a clear import cost becomes more complex as the number of exports and code size increases.

Sponsors
--------
