---
project: cap
stars: 4338
description: Cap is a lightweight, modern open-source CAPTCHA alternative using SHA-256 proof-of-work
url: https://github.com/tiagozip/cap
---

Cap
===

Cap is a lightweight, modern open-source CAPTCHA alternative using SHA-256 proof-of-work. It's fast, private, and extremely simple to integrate.

Documentation
-------------

Read the Cap docs, try the demo or read the feature comparison

What is Cap?
------------

Cap is the modern, open-source alternative to traditional CAPTCHAs that uses proof-of-work instead of annoying visual puzzles.

It's built with JavaScript and Rust and has no dependencies. You can either run it on any JavaScript runtime (Bun, Node.js, Deno), or use the standalone mode with Docker.

Cap is built into 2 main parts. The widget is a small client-side JavaScript library using custom components and WASM that renders the CAPTCHA and solves the challenge.

The Standalone Server is a Docker image that helps you use Cap with any language or framework. As an alternative, if your server-side uses JavaScript, you can use the lighter server library.

Cap also has a M2M library that implements a custom proof-of-work solver for protecting API endpoints that you still want public.

Why Cap?
--------

-   **250x smaller than hCaptcha**  
    ~20kb, zero dependencies, loads in milliseconds
-   **Privacy-first**  
    Cap doesn't send any telemetry back to our servers
-   **Fully customizable**  
    Change the colors, size, position, icons and more with CSS variables
-   **Proof-of-work**  
    Your users no longer have to waste time solving visual puzzles.
-   **Standalone mode**  
    Run Cap anywhere with a Docker container with analytics & more
-   **Invisible**  
    Hide Cap's widget and solve challenges in the background
-   **M2M**  
    Keep your APIs protected while accessible to friendly robots
-   **Open-source**  
    Completely free & open-source under the Apache 2.0 license

Cap is a great alternative to reCAPTCHA, hCaptcha and Cloudflare Turnstile

License
-------

Apache 2.0

Copyright (c) 2025–present tiago
