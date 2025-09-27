---
project: Rin
stars: 2242
description: ⚡Dynamic blog based on Cloudflare Pages + Workers + D1 + R2
url: https://github.com/openRin/Rin
---

Rin
===

English | 简体中文

Introduction
============

Rin is a blog based on Cloudflare Pages + Workers + D1 + R2. It does not require a server to deploy. It can be deployed just with a domain name that resolves to Cloudflare.

Demo
----

xeu.life

Features
--------

1.  Support GitHub OAuth login. By default, the first logged-in user has management privileges, and other users are ordinary users
2.  Support article writing and editing
3.  Support local real-time saving of modifications/edits to any article without interfering between multiple articles
4.  Support setting it as visible only to yourself, which can serve as a draft box for cloud synchronization or record more private content
5.  Support dragging/pasting uploaded images to a bucket that supports the S3 protocol and generating links
6.  Support setting article aliases, and access articles through links such as https://xeu.life/about
7.  Support articles not being listed in the homepage list
8.  Support adding links of friends' blog, and the backend regularly checks and updates the accessible status of links every 20 minutes
9.  Support replying to comment articles/deleting comments
10.  Support sending comment notifications through Webhook
11.  Support automatic identification of the first picture in the article and display it as the header image in the article list
12.  Support inputting tag texts such as "#Blog #Cloudflare" and automatically parsing them into tags
13.  For more features, please refer to https://xeu.life

Documentation
=============

docs.openrin.org

Star History
------------

License
=======

```
MIT License

Copyright (c) 2024 Xeu

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
