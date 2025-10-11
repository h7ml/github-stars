---
project: raycast-multi-translate
stars: 480
description: A Raycast extension that translates text to multiple languages at once
url: https://github.com/antfu/raycast-multi-translate
---

  
  

MultiTranslate
==============

A Raycast extension that translates text to multiple languages at once.

Motivation
----------

I speak Chinese, work in English, live in France, and sometimes also consume Japanese content. I do language-switching all the time. For example, I'd like to know what's the meaning of a new English word, find the English translation of a Chinese word, or verify if my French sentence is correct, etc. Most of the time I just need a quick answer, but I found I spend quite a lot of time telling the translator which language **from** and **to**, which should be detected automatically. So instead of setting the language manually every time, let's translate it to all languages we use at once.

Features
--------

Installation
------------

Currently, you need to clone this repo and install it locally in developer mode.

You will need to have Node.js and pnpm installed.

1.  Clone this repo `git clone https://github.com/antfu/raycast-multi-translate`
2.  Go to the folder `cd raycast-multi-translate`
3.  Install dependencies `pnpm install`
4.  Go to Raycast, run `Import Extension` and select the folder

There is **no plan** to publish to the bloated raycast/extensions until they make a decentralized publishing system.

Features
--------

### Multiple Translations Targets

Support translating up to 7 languages at once. Options can be found in the extensions tab of Raycast settings.

### Spellcheck

When you misspell some words, an additional item will be listed, with diffing support to help you find the correct spelling easier.

### Source Language Detection

By default we send the text to Google Translate and let it detect the source language automatically. In some cases, it might not be accurate because different works in different languages can spell the same. For example, `ours` in French means `bear`, but in English, it means `belonging to us`. In this case, if you want to translate `ours` in French, you can add `>fr` to the end of the text to force the source language to be French.

Credits
-------

Originally forked from https://github.com/raycast/extensions/tree/main/extensions/google-translate, thanks to @gebeto et al.

Changes from the original extension

-   Support translating for any language to multiple languages at once
-   Removed the representation of flag emojis, as languages are not countries
-   Removed the `Translate From` command, and the language selection dropdown, as they are automatized
-   Show details view by default
-   Cache translation results
-   Make "Use current selection" passive and don't interfere the input field
-   Added spellcheck functionality

License
-------

MIT License
