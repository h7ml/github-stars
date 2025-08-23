---
project: farm
stars: 5449
description: Extremely fast Vite-compatible web build tool written in Rust
url: https://github.com/farm-fe/farm
---

### Extremely fast Vite-compatible web building tool written in Rust

English | 简体中文

  

* * *

Intro
-----

Farm is an extremely fast vite-compatible web-building tool written in Rust. It's designed to be fast, powerful and consistent, aims to provide best experience for web development, which is the real next generation build tool.

Online experience
-----------------

Why Farm?
---------

> See Why Farm for details.

In short, tools like webpack are too slow, but new tools like Vite are not perfect, Vite has a lot of drawbacks when comes to a large project:

-   **A huge number of requests during development**：when there are hundreds or thousands modules per page, loading performance severely degraded, it may takes seconds or more when refresh the page.
-   **Inconsistency between development and production**: Using different strategy and tools in development and production, it's really inconsistent and it's hard to debug online issues.
-   **Inflexible Code Splitting**: It's hard to control the output of your bundles.

Farm can solve these problems perfectly, and it's really fast cause it's written in Rust. Farm aims to be fast, consistent, flexible, which is the real next generation build tool.

Features
--------

Note

-   Since Farm v0.13, Vite plugins can be used directly in Farm. Refer to Using vite plugins in Farm
-   Since Farm v0.14, persistent disk cache enabled by default. Refer to Incremental Building
-   Now Farm is **1.0 stable** and **production ready!**. See Farm official website to get started.

-   ⚡ **Extremely Fast**: Written in Rust, start a React / Vue project in milliseconds and perform an HMR update within 20ms for most situations.
-   ⚡ **Incremental Building**: Support persistent cache, module level cache enabled by default, any module won't be compiled twice until it's changed!
-   🧰 **Fully Pluggable and Vite Compatible**: Everything inside Farm is powered by plugins, Support Vite Plugins out of box. Supports Farm compilation plugins(both Rust and JavaScript plugins, and SWC plugins), Farm runtime plugins and Farm server plugin.
-   ⚙️ **Powerful**: Compiles JS/TS/JSX/TSX, CSS, Css Modules, HTML, and static assets out of the box. Support official compilation plugins for Popular frameworks/tools like React, Vue, SolidJs, Sass, Less, Postcss and so on.
-   ⏱️ **Lazy Compilation**: Dynamically imported resources are compiled only when requested, speed up compilation for large scale project. Just write a `dynamic import` and the imported module won't be compiled when it is executed.
-   📦 **Partial Bundling**: Bundle your project into a few reasonable bundles automatically, speeding up resource loading without losing caching granularity. Refer to RFC-003 Partial Bundling for details.
-   🔒 **Consistency**: What you see in development will be the same as what you get in production.
-   🌳 **Compatibility**: Supports both legacy (ES5) and modern browsers.

  

> Farm has implemented all features of a web build tool, including production optimization like tree shake and minification. It's now 1.0 stable. We have already migrated enterprise projects to Farm, and it works great!

See RFC-001 Architecture for design motivation and architecture.

  

Getting Started
---------------

Create a new Farm(support both React and Vue) project with your favorite package manager:

# with npm
npm create farm@latest
# with yarn
yarn create farm@latest
# with pnpm
pnpm create farm@latest

Visit Farm Documentation to learn more about Farm.

Benchmark
---------

Farm is much faster than similar tool， **20x** faster than webpack and **10x** faster than Vite in the benchmark:

See Benchmark for details.

Contribution
------------

See Contributing Guide.

Chat With Us
------------

-   Author Twitter, Official Twitter
    
-   With Discord
    
-   Wechat group
    

  

-   QQ group

  

Contributors
------------

  
  
  

Credits
-------

Thanks to https://github.com/tmm who donated the farm npm package to the Farm team.

Thanks to projects:

-   The SWC project created by @kdy1, which powers Farm's code parsing, transformation and minification.
    
-   The NAPI-RS project created by @Brooooooklyn, which powers Farm's node-binding implementation.
    
-   The Rollup project created by @lukastaegert, which inspired Farm's plugin system implementation.
    
-   The Vite project created by Evan You, which inspired Farm's compatibility design of ecosystem.
    

Author & Maintainer
-------------------

Author:

-   brightwu（吴明亮），worked at bytedance. Twitter

Maintainer:

-   ErKeLost
-   shulandmimi
