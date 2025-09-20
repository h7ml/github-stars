---
project: liquidjs
stars: 1697
description: A simple, expressive, safe and Shopify compatible template engine in pure JavaScript.
url: https://github.com/harttle/liquidjs
---

liquidjs
========

A simple, expressive and safe Shopify / GitHub Pages compatible template engine in pure JavaScript. **The purpose of this repo** is to provide a standard Liquid implementation for the JavaScript community so that Jekyll sites, GitHub Pages and Shopify templates can be ported to Node.js without pain.

-   Documentation
-   Please star LiquidJS on GitHub!
-   Financial support via GitHub Sponsors.

What's it like?
---------------

Basically there're two types of Liquid syntax: tags enclosed by `{% %}` and outputs enclosed by `{{ }}`. A Liquid template looks like:

{% if username %}
  {{ username | append: ", welcome to LiquidJS!" | capitalize }}
{% endif %}

A live demo is also available and here's a quick tutorial for Liquid syntax.

Installation
------------

Install from npm in Node.js:

npm install liquidjs

Or use the UMD bundle from jsDelivr:

<script src\="https://cdn.jsdelivr.net/npm/liquidjs/dist/liquid.browser.min.js"\></script\>

Or render directly from CLI using npx:

npx liquidjs --template 'Hello, {{ name }}!' --context '{"name": "Snake"}'

For more details, refer to the Setup Guide.

Who's Using LiquidJS?
---------------------

-   Eleventy: Eleventy, a simpler static site generator.
-   Github Docs: The open-source repo for docs.github.com.
-   Opensense: The smarter way to send email.
-   Directus: an instant REST+GraphQL API and intuitive no-code data collaboration app for any SQL database.
-   Semgrep: Lightweight static analysis for many languages.
-   Rock: An open source CMS, Relationship Management System (RMS) and Church Management System (ChMS) all rolled into one.
-   Mitosis: Write components once, run everywhere. Compiles to React, Vue, Qwik, Solid, Angular, Svelte, and more.
-   Pattern Lab: a frontend workshop environment that helps you build, view, test, and showcase your design system's UI components.
-   Builder.io: the first and only headless CMS with a visual editor that lets you drag and drop with your components, directly within your current site or app. Completely API-driven, for cleaner code and simpler workflows.
-   Microsoft Power Pages: a secure, enterprise-grade, low-code software as a service (SaaS) platform for creating, hosting, and administering modern external-facing business websites.
-   Azure API Management developer portal: an automatically generated, fully customizable website with the documentation of your APIs.
-   WISMOlabs: Post Purchase Experience platform for eCommerce retailers enhancing customer satisfaction by using LiquidJS to provide customizable post-purchase experiences through programmable email, SMS, order tracking pages, and webhooks.

Feel free to create a PR or contact me to add your use case into this list!

Financial Support
-----------------

If you personally love LiquidJS or it's benefiting your business, please consider financially support us via GitHub Sponsors. Special thanks to our sponsors!

  
**Opensense**

  
**Eleventy**

  
**Peter deHaan**

  
**Touchless**

  
**Dropkiq**

  
**Dailycontributors**

  
**Serkan Holat**

  
**amit777**

  
**Khaled Salem**

  
**Sentry**

  
**Checkout Blocks**

  
**Customer IO**

  
**Emmanuel Cartelli**  

  
**Microsoft**  

  
**PakStyle.pk**

  
**Syntax Podcast**

  
**Cartelli Emmanuel**

  
**EscortA.com**

  
**Chudovo**

Contributors ✨
--------------

Want to contribute? see Contribution Guidelines. Thanks goes to these wonderful people:

  
**Jun Yang**  
🚧 💻

  
**chenos**  
💻

  
**Zach Leatherman**  
🐛

  
**Tim Hardy**  
💻

  
**Paul Robert Lloyd**  
💻 🐛

  
**Alec Larson**  
💻

  
**Patrick Malouin**  
💻 📖

  
**jaswrks**  
💻

  
**三三**  
💻 🤔

  
**ssendev**  
💻 📖

  
**wojtask9**  
💻

  
**Andrew Barclay**  
💻

  
**Cory Mawhorter**  
💻

  
**Mehdi Jaffery**  
💻

  
**Robin Bijlani**  
💻 🐛

  
**Ryan Kennedy**  
💻

  
**Sami Kukkonen**  
💻

  
**Scott Santucci**  
💻

  
**Steven**  
💡 💻

  
**azu**  
📖

  
**Joonas**  
💻

  
**Jamel A.**  
💻

  
**Brandon Pittman**  
💻

  
**tgrandgent**  
💻

  
**Martin Schuster**  
💻

  
**Ray**  
⚠️ 💻

  
**Cristofer Gonzales**  
💻

  
**Raymond Camden**  
📖

  
**Steve Stedman**  
📖

  
**Anthony Ciccarello**  
📖

  
**Bogdan Chadkin**  
💻

  
**Tejas Manohar**  
💻

  
**Peter deHaan**  
📖

  
**amit777**  
💻

  
**Steffen Schuldenzucker**  
💻

  
**Pixcell**  
💻

  
**Jason Etcovitch**  
💻

  
**ZC**  
📖

  
**Memmie Lenglet**  
💻

  
**ilhamdev0**  
📖

  
**一饮一啄皆是人生**  
📖

  
**Amit Agarwal**  
📖

  
**Laurin Quast**  
💻

  
**Matt Vague**  
💻

  
**Liam Bigelow**  
💻

  
**Jason Kurian**  
📖

  
**d pham (they/them)**  
📖

  
**Aleksandr Hovhannisyan**  
💻

  
**jg-rp**  
💻

  
**Ameya Apte**  
💻

  
**tbdrz**  
📖

  
**Santi Albo**  
📖 💻

  
**Yahang Wu**  
📖

  
**hongl**  
📖

  
**zxx-457**  
📖

  
**prassie**  
📖

  
**Slav Ivanov**  
💻

  
**Daniel Rosenberg**  
💻

  
**bobgubko**  
💻

  
**BaNgan**  
📖

  
**Mahyar Pasarzangene**  
📖

  
**Tomáš Hübelbauer**  
💻 📖

  
**Jason Garber**  
💻

  
**Nick Reilingh**  
📖

  
**Francisco Soto**  
💻

  
**David LJ**  
📖

  
**Rasmus Wriedt Larsen**  
📖

  
**Bruno Carvalho**  
💻

  
**傅鹏**  
💻

  
**Joel Hamilton**  
💻

  
**Max Medve**  
💻

  
**Cosmin Popovici**  
📖

  
**Adam Tanner**  
💻

  
**Guillermo Casal Caro**  
💻

  
**Josh Soref**  
📖

  
**Koen**  
💻

  
**Matthieu Bacconnier**  
📖

  
**Tim van Dam**  
💻

  
**Ed Hanton**  
📖

  
**Vlad GURDIGA**  
📖

  
**裸奔狂甩丁丁**  
📖
