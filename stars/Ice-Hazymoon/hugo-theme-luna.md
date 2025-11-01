---
project: hugo-theme-luna
stars: 298
description: A simple, performance-first, SEO-friendly Hugo theme / 一个轻量，快速，SEO 友好的 Hugo 主题
url: https://github.com/Ice-Hazymoon/hugo-theme-luna
---

Hugo Theme Luna
===============

### _A simple, performance-first, SEO-friendly Hugo theme_

👉 Example | 中文文档

Table of Contents

-   👋 Introduction
-   💻 Usage
    -   \- 📋 Requirements
    -   \- 📥 Install as git submodule
    -   \- 🔄 Update theme
    -   \- 🚀 Deploy to GitHub Pages
    -   \- ☁️ Deploy to Netlify
    -   \- ⚡ Deploy to Vercel
    -   \- 🌩️ Deploy to Cloudflare Pages
    -   \- ⚙️ Configuration
    -   \- 💬 Comments
    -   \- 📜 Shortcodes
    -   \- 🔒 Encryption
-   📝 Note:
-   🐙 GitHub Action
-   🎨 Custom
-   🛠️ Development
-   📈 Performance tests
-   👏 Acknowledgements
-   📜 License

👋 Introduction
---------------

-   Using Tailwindcss
-   Dynamic import of JS modules、
-   LaTeX, use KaTeX
-   Custom Themes and Fonts
-   Carousel
-   Many shortcodes
-   Dark mode
-   Bionic Reading
-   Image gallery
-   Responsive images
-   Article encryption (please do not encrypt important content under any circumstances)
-   Multilingual
-   Google Translate
-   PWA
-   Pjax, use swup.js
-   Lazy load images
-   <noscript>
-   Table of contents
-   Local search, use flexsearch
-   GitHub page template
-   Archive page template
-   GitHub Actions
-   and more......

💻 Usage
--------

### \- 📋 Requirements

-   **hugo-extended** >= 0.146.0
-   **NodeJs** >= 20.0.0
-   **postcss-cli**, Install using `npm install postcss-cli -g`

### \- 📥 Install as git submodule

git submodule add -b master https://github.com/Ice-Hazymoon/hugo-theme-luna themes/hugo-theme-luna
cd themes/hugo-theme-luna
npm install --omit=dev

There is a `hugo.yaml` file in the `exampleSite` directory, copy the file to your site directory and modify the contents.

### \- 🔄 Update theme

cd themes/hugo-theme-luna
git pull

or use git submodule

git submodule update --remote

### \- 🚀 Deploy to GitHub Pages

Refer to GitHub Actions

### \- ☁️ Deploy to Netlify

Refer to netlify.toml

### \- ⚡ Deploy to Vercel

Refer to vercel.json

### \- 🌩️ Deploy to Cloudflare Pages

Environment variables

```
HUGO_VERSION: 0.150.1
NODE_VERSION: 22.20.0
```

Build command

cd themes/hugo-theme-luna && npm install postcss-cli -g && npm install --omit=dev && cd ../../ && hugo --gc --minify --cleanDestinationDir --enableGitInfo

Build output directory

```
/public
```

### \- ⚙️ Configuration

See `hugo.yaml` file to configure your site

If you prefer to use toml, you can convert it here

You can find all available icons at Eva icons

You can create your website icons by adjusting the assets/icon.png file

### \- 💬 Comments

You can set `comments: false` to turn off comments for some pages

Comment system provider. Available options:

-   giscus

Custom comments at layouts/partials/comments/provider/custom.html

### \- 📜 Shortcodes

The luna theme supports many shortcodes, see: Shortcodes

### \- 🔒 Encryption

**⚠️Do not encrypt any important content with the encryption function⚠️**

Please be careful with functions such as `.RawContent` to avoid exposing the body

If you're not using GitHub Actions and you need to use encryption, run the `hugo-encrypt.js` script in the theme directory after each site generation

{{% hugo-encrypt 2022 %}}

Here is what needs to be encrypted

!\[some text\](test.jpg)

{{% /hugo-encrypt %}}

📝 Note:
--------

The images in the blog use Hugo's Image Processing feature, which automatically crops them to the right size to optimize page load speed, and can be time-consuming to generate the first time.

The local search function removes the shortcode and code blocks in order to reduce the size of the json file, but you can modify it here if necessary

If you have pjax enabled and have added additional `<script>` tags, add the `data-swup-reload-script` attribute to the tags, see: https://swup.js.org/plugins/scripts-plugin

🐙 GitHub Action
----------------

Copy the `.github/workflows/main_example.yml` file in the theme root directory to your blog's `.github/workflows` directory

Modify the `external_repository`, `user_name`, `user_email`, etc. fields in the main\_example.yml file, see: actions-gh-pages

**Note: If you need to enable encryption, you need to have two GitHub repositories, a private repository for your source code and a public repository for your blog, `external_repository` should be set as the public repository for your blog**

If you only have one repository, modify the `Deploy` script section

Create a Token for deployment at https://github.com/settings/tokens, save the Token

Add a `TOKEN` field to **github.com/{username}/{project}/settings/secrets/actions** and enter the token you just generated

🎨 Custom
---------

-   custom.ts
-   custom.scss
-   custom/head.html
-   custom/footer.html
-   custom/script.html
-   custom/icons.html

If you don't want to modify the theme file, you can create a file with the same name in the root of your website to modify it, e.g. `myblog/layouts/partials/custom/head.html`

🛠️ Development
---------------

git clone https://github.com/Ice-Hazymoon/hugo-theme-luna/
cd hugo-theme-luna
npm install
hugo server -s ./exampleSite -D --themesDir "../.."

📈 Performance tests
--------------------

> https://imiku.me
> 
> with pjax and katex turned off

Lighthouse

GTmetrix

👏 Acknowledgements
-------------------

-   Unsplash
-   hugo-theme-even
-   hugo-theme-stack
-   hugo-encrypt
-   Some shortcodes
-   Carousel component

📜 License
----------

The theme uses the GPL V3.0 protocol open source, please comply with this agreement for secondary development and so on.
