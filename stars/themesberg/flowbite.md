---
project: flowbite
stars: 8911
description: Open-source UI component library and front-end development framework based on Tailwind CSS
url: https://github.com/themesberg/flowbite
---

  
Build websites even faster with components on top of Tailwind CSS

* * *

Table of Contents
-----------------

-   Table of Contents
-   Documentation
-   Getting started
    -   Install using NPM
    -   Include via CDN
    -   Bundled JavaScript
    -   Data attributes
        -   Init functions
    -   ESM and CJS
    -   TypeScript
    -   RTL support
    -   JavaScript Frameworks
    -   Back-end Frameworks
-   Components
-   Figma Design System
-   Flowbite Blocks
-   Flowbite Icons
-   Flowbite GPT
-   Pro version
-   Hire us
-   Learn Design Concepts
-   Community
-   Copyright and license

Documentation
-------------

For full documentation, visit flowbite.com.

Getting started
---------------

Flowbite can be included as a plugin into an existing Tailwind CSS project and it is supposed to help you build websites faster by having a set of web components to work with built with the utility classes from Tailwind CSS.

### Install using NPM

Make sure that you have Node.js and Tailwind CSS installed. This guide works with Tailwind v4.

1.  Install Flowbite as a dependency using NPM by running the following command:

npm install flowbite

1.  Import Flowbite as a plugin inside your main Tailwind CSS file:

@plugin "flowbite/plugin";

1.  Make sure that you add the Flowbite JS source files to your CSS file:

@source "../node\_modules/flowbite";

1.  Include the JavaScript code that powers the interactive elements before the end of your `<body>` tag:

<script src\="../path/to/flowbite/dist/flowbite.min.js"\></script\>

Learn more about the Flowbite JavaScript API and functionalities in the JavaScript section.

If you have and old project with Tailwind CSS v3 then check out this guide to learn how to upgrade to v4.

### Include using CDN

The quickest way to get started working with Flowbite is to include the CSS and JS into your project via CDN.

Require the following minified stylesheet inside the `head` tag:

<link href\="https://cdn.jsdelivr.net/npm/flowbite@{{< current\_version >}}/dist/flowbite.min.css" rel\="stylesheet" />

And include the following JavaScript file before the end of the `body` element:

<script src\="https://cdn.jsdelivr.net/npm/flowbite@{{< current\_version >}}/dist/flowbite.min.js"\></script\>

Please remember that the best way to work with Tailwind CSS and Flowbite is by purging the CSS classes.

### Bundled JavaScript

One of the most popular way of using Flowbite is to include the bundled Javascript file which is UMD ready using a bundler such as Webpack or Parcel which makes sure that all of the data attributes and functionality will work out-of-the-box.

You can directly import the main JavaScript file inside your bundled `app-bundle.js` file like this:

import 'flowbite';

This file has access to all of the components and it automatically applies event listeners to the data attributes.

### Data attributes

The preferred way to use the interactive UI components from Flowbite is via the data attributes interface which allows us to add functionality via the HTML element attributes and most of the examples on our documentation applies this strategy.

For example, to set up a modal component all you need to do is use `data-modal-target` and `data-modal-{toggle|show|hide}` to toggle, show, or hide the component by clicking on any trigger element.

<button data-modal-target\="defaultModal" data-modal-toggle\="defaultModal" class\="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800" type\="button"\>
  Toggle modal
</button\>

<!-- Main modal -->
<div id\="defaultModal" tabindex\="\-1" aria-hidden\="true" class\="fixed top-0 left-0 right-0 z-50 hidden w-full p-4 overflow-x-hidden overflow-y-auto md:inset-0 h-\[calc(100%-1rem)\] max-h-full"\>
    <div class\="relative w-full max-w-2xl max-h-full"\>
        <!-- Modal content -->
        <div class\="relative bg-white rounded-lg shadow-sm dark:bg-gray-700"\>
            <!-- Modal header -->
            <div class\="flex items-start justify-between p-4 border-b rounded-t dark:border-gray-600 border-gray-200"\>
                <h3 class\="text-xl font-semibold text-gray-900 dark:text-white"\>
                    Terms of Service
                </h3\>
                <button type\="button" class\="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white" data-modal-hide\="defaultModal"\>
                    <svg aria-hidden\="true" class\="w-5 h-5" fill\="currentColor" viewBox\="0 0 20 20" xmlns\="http://www.w3.org/2000/svg"\><path fill-rule\="evenodd" d\="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule\="evenodd"\></path\></svg\>
                    <span class\="sr-only"\>Close modal</span\>
                </button\>
            </div\>
            <!-- Modal body -->
            <div class\="p-6 space-y-6"\>
                <p class\="text-base leading-relaxed text-gray-500 dark:text-gray-400"\>
                    With less than a month to go before the European Union enacts new consumer privacy laws for its citizens, companies around the world are updating their terms of service agreements to comply.
                </p\>
                <p class\="text-base leading-relaxed text-gray-500 dark:text-gray-400"\>
                    The European Union’s General Data Protection Regulation (G.D.P.R.) goes into effect on May 25 and is meant to ensure a common set of data rights in the European Union. It requires organizations to notify users as soon as possible of high-risk data breaches that could personally affect them.
                </p\>
            </div\>
            <!-- Modal footer -->
            <div class\="flex items-center p-6 space-x-2 border-t border-gray-200 rounded-b dark:border-gray-600"\>
                <button data-modal-hide\="defaultModal" type\="button" class\="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"\>I accept</button\>
                <button data-modal-hide\="defaultModal" type\="button" class\="text-gray-500 bg-white hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-blue-300 rounded-lg border border-gray-200 text-sm font-medium px-5 py-2.5 hover:text-gray-900 focus:z-10 dark:bg-gray-700 dark:text-gray-300 dark:border-gray-500 dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-gray-600"\>Decline</button\>
            </div\>
        </div\>
    </div\>
</div\>

#### Init functions

You can also use the init functions to set up the event listeners yourself. Here's an example how you can do it with Vue or Nuxt:

```
<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})
</script>

<template>
    // Modal HTML markup with data attributes from Flowbite
</template>
```

The `initFlowbite` function sets up all of the init functions for dropdowns, modals, navbars, tooltips and so on to hook onto the data attributes. Alternatively, you can also initialise each component category class separately with `initDropdowns` or `initModals`.

You can view more examples by browsing the components from Flowbite.

### ESM and CJS

Flowbite also offers an API for using the components programmatically and it supports both CJS and ESM for JavaScript which can be helpful if you need to expand the default capabilities of the data attributes interface and get access to function callbacks.

Here's an example how you can import and create a new Modal component inside JavaScript:

import { Modal } from 'flowbite'

const $modalElement \= document.querySelector('#modalEl');

const modalOptions \= {
    placement: 'bottom-right',
    backdrop: 'dynamic',
    backdropClasses: 'bg-gray-900/50 dark:bg-gray-900/80 fixed inset-0 z-40',
    onHide: () \=> {
        console.log('modal is hidden');
    },
    onShow: () \=> {
        console.log('modal is shown');
    },
    onToggle: () \=> {
        console.log('modal has been toggled');
    }
}

const modal \= new Modal($modalElement, modalOptions);

modal.show();

Check out the JavaScript behaviour section of each component's page to learn how you can use this.

### TypeScript

Flowbite supports type declarations for the interactive UI components including object interfaces and parameter types. Check out the following examples to learn how you can use types with Flowbite.

Additionally to our code above, we will now import some relevant types from the Flowbite package, namely the `ModalOptions` and `ModalInterface`:

import { Modal } from 'flowbite'
import type { ModalOptions, ModalInterface } from 'flowbite'

// other code

Generally speaking, all of the components have an interface definition that you can use whenever you create a new object to make sure that you're using the correct types of parameters and methods.

When creating a new modal you can set the `ModalInterface` as the main type:

const modal: ModalInterface \= new Modal($modalElement, modalOptions);

Flowbite also supports type definitions for the options object so if you want to set the placement of the modal based on types, here's how you would do that:

const modalOptions: ModalOptions \= {
    placement: 'top-right'
}

const modal: ModalInterface \= new Modal($modalElement, modalOptions);

Learn more about Flowbite and TypeScript in the quickstart guide.

### RTL support

All of the Flowbite UI components have native RTL support and you can easily set it up by using the `dir="rtl"` attribute on the HTML element. Read more about Flowbite and RTL support here.

### JavaScript Frameworks

The awesome open-source community also built and currently maintains the following standalone libraries for React, Vue, Svelte, Angular and Qwik:

-   🌀 Flowbite React Library
-   🍀 Flowbite Vue Library
-   🎸 Flowbite Svelte Library
-   📕 Flowbite Angular Library
-   👿 Flowbite Qwik Library

We also wrote integration guides for the following front-end frameworks and libraries:

-   📝 Flowbite with React guide
-   📝 Flowbite with Next.js guide
-   📝 Flowbite with Remix guide
-   📝 Flowbite with Vue guide
-   📝 Flowbite with Nuxt guide
-   📝 Flowbite with Svelte guide
-   📝 Flowbite with Astro guide
-   📝 Flowbite with MeteorJS guide
-   📝 Flowbite with Gatsby guide
-   📝 Flowbite with SolidJS guide
-   📝 Flowbite with Qwik guide

### Back-end Frameworks

Flowbite has a great integration with most of the back-end frameworks because it relies on vanilla JavaScript:

-   📚 Using Flowbite with Laravel
-   🎼 Using Flowbite with Symfony
-   🚊 Using Flowbite with Ruby on Rails 7
-   🐉 Using Flowbite with Phoenix (Elixir)
-   🐸 Using Flowbite with Django
-   🌶 Using Flowbite with Flask

Components
----------

Flowbite is an open source collection of UI components built with the utility classes from Tailwind CSS that you can use as a starting point when coding user interfaces and websites.

Alerts

Badge

Breadcrumbs

Buttons

Button group

Cards

Dropdown

Forms

List group

Typography

Modal

Tabs

Navbar

Pagination

Timeline

Progress bar

Tables

Toast

Tooltips

Datepicker

Spinner

Footer

Accordion

Sidebar

Carousel

Avatar

Rating

Input Field

File Input

Search Input

Select

Textarea

Checkbox

Radio

Toggle

Range Slider

Floating Label

Mega Menu

Skeleton

KBD (keyboard)

Drawer (offcanvas)

Popover

Video

Heading

Paragraph

Blockquote

Image

List

Link

Text

Horizontal line (HR)

Speed Dial

Stepper

Indicators

Bottom Navigation

Sticky Banner

Gallery (Masonry)

Jumbotron

Device mockups

Charts

Number Input

Phone Input

Chat Bubble

Copy to Clipboard

Timepicker

DataTables

WYSIWYG Editor

Figma Design System
-------------------

If you need the Figma files for the components you can check out our website for more information:

🎨 Get access to the Figma design files

Flowbite Blocks
---------------

Check out Flowbite Blocks to get access to over 400+ website sections coded in Tailwind CSS and Flowbite:

📦 Check out Flowbite Blocks

Flowbite Icons
--------------

Start using over 450+ free and open-source collection of solid and outline SVG icons built for Tailwind CSS and with support for Figma and JSX (React):

🔍 Check out the icons

Flowbite GPT
------------

We've developed a custom trained ChatGPT model that you can use to generate website sections and pages based on the resources from Flowbite and Tailwind CSS.

🤖 Generate with Flowbite GPT

Pro version
-----------

Get access to all premium features including the Figma design system, access to all Flowbite Block sections and a dashboard UI interface:

💎 Check out Flowbite Pro

Hire us
-------

If you're ready to take your application to the next level you can work with us on your project with developers who have been using Flowbite and Tailwind CSS.

🙋‍♂️ Work with us

Learn Design Concepts
---------------------

If you want to create even better Flowbite pages, learn design fundamentals from Teach Me Design - Enhance UI, a book that covers color theory, typography, UI and UX so you can make the most to implement the Flowbite Ecosystem!

📖 Learn with Enhance UI

Community
---------

If you need help or just want to discuss about the library join the community on Github:

⌨️ Discuss about Flowbite on GitHub

For casual chatting with others using the library:

💬 Join the Flowbite Discord Server

Video tutorials and presentations using Flowbite:

🎥 Subscribe to our YouTube channel

Copyright and license
---------------------

The Flowbite name and logos are trademarks of Bergside Inc.

-   📝 Read about the licensing terms
-   📀 Brand guideline and trademark usage agreement
