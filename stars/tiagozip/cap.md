---
project: cap
stars: 4175
description: Cap is a lightweight, modern open-source CAPTCHA alternative using SHA-256 proof-of-work
url: https://github.com/tiagozip/cap
---

Documentation   •   Quickstart   •   Demo   •   Issues  

### Read the docs →

What is Cap?
------------

Cap is a lightweight, modern open-source CAPTCHA alternative using SHA-256 proof-of-work. It's fast, private, and extremely simple to integrate. Learn more about proof-of-work here.

Cap is built into 2 main parts:

-   **@cap.js/widget**: A small JavaScript library that renders the CAPTCHA and handles solving it using Web Workers and WASM.
    
-   **@cap.js/server**: An extremely simple, zero-dependencies library that handles creating and validating challenges.
    

There are also some other helpful packages:

-   **M2M**: Server-side solver for Cap challenges, useful for protecting API endpoints that you still want public. This doesn't bypass the actual proof-of-work.
    
-   **@cap.js/cli**: Command-line interface for solving CAPTCHAs made with Cap. It's mainly designed for testing and when you need to solve these CAPTCHAs in a browser without JavaScript support.
    
-   **Standalone mode**: Docker image that helps you use Cap with any language or framework. It runs a simple REST API that can be used to create and validate challenges and an interactive UI to manage your keys.
    
-   **@cap.js/wasm**: Experimental WASM solvers built using Rust.
    

We also provide a middleware for a Cloudflare browser checkpoint-like experience:

-   @cap.js/checkpoint-hono
-   @cap.js/checkpoint-express
-   @cap.js/middleware-elysia
-   more coming soon!

It's designed to be a drop-in replacement for existing CAPTCHA solutions, with a focus on performance and UX.

Cap is built with JavaScript, runs on any JS runtime (Bun, Node.js, Deno), and has no dependencies. If you're not using any JS runtime, you can also use the standalone mode with Docker, which relies entirely on a simple REST API to create and validate challenges.

Why Cap?
--------

-   **250x smaller than hCaptcha**  
    `@cap.js/widget` is extremely small, only 12kb minified and brotli'd.
-   **Private**  
    Cap's usage of proof-of-work eliminates the need for any tracking, fingerprinting or data collection.
-   **Fully customizable**  
    Cap's self-hostable so you can customize both the backend & frontend — or you can just use CSS variables
-   **Proof-of-work**  
    Cap uses proof-of-work instead of complex puzzles, making it easier for humans and harder for bots
-   **Standalone mode**  
    Cap offers a standalone mode with Docker, allowing you to use it with languages other than JS.
-   **Invisible mode**  
    Cap can run invisibly in the background using a simple JS API.
-   **Floating mode**  
    Cap's floating mode keeps your CAPTCHA hidden until it's needed.
-   **Fully open-source**  
    Completely open source under the Apache license 2.0 license.

It's ideal for:

-   Protecting APIs from bots
-   Preventing spam on forms
-   Blocking automated login attempts
-   Securing free-tier abuse

Feature comparison
------------------

CAPTCHA

Open-source

Free

Private

Fast to solve

Easy for humans

Small error rate

Checkpoint support

GDPR/CCPA Compliant

Customizable

Hard for bots

Easy to integrate

**Cap**

✅

✅

✅

✅

✅

✅

✅

✅

✅

🟨

✅

Cloudflare Turnstile

❌

✅

🟨

🟨

✅

❌

🟨

✅

❌

🟨

✅

reCAPTCHA

❌

🟨

❌

✅

❌

🟨

❌

🟨

❌

❌

✅

hCAPTCHA

❌

🟨

🟨

❌

❌

🟨

❌

🟨

❌

🟨

✅

Altcha

✅

✅

✅

🟨

✅

✅

❌

✅

✅

🟨

🟨

FriendlyCaptcha

❌

❌

✅

🟨

✅

✅

❌

✅

✅

🟨

🟨

MTCaptcha

❌

🟨

🟨

❌

❌

🟨

❌

✅

❌

❌

🟨

GeeTest

❌

❌

❌

🟨

🟨

🟨

❌

✅

❌

🟨

🟨

Arkose Labs

❌

❌

❌

❌

❌

❌

❌

✅

🟨

❌

❌

Alternatives
------------

Cap is a modern alternative to:

-   reCAPTCHA
-   hCaptcha
-   Cloudflare Turnstile

But unlike them, Cap is **computation-bound, not tracking-bound**.

License
-------

Cap is licensed under the Apache License 2.0.

* * *
