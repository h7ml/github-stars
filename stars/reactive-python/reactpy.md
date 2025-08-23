---
project: reactpy
stars: 8127
description: It's React, but in Python
url: https://github.com/reactive-python/reactpy
---

ReactPy
=======

ReactPy is a library for building user interfaces in Python without Javascript. ReactPy interfaces are made from components that look and behave similar to those found in ReactJS. Designed with simplicity in mind, ReactPy can be used by those without web development experience while also being powerful enough to grow with your ambitions.

Supported Backends

Built-in

External

Flask, FastAPI, Sanic, Tornado

Django, Jupyter, Plotly-Dash

At a Glance
===========

To get a rough idea of how to write apps in ReactPy, take a look at this tiny _Hello World_ application.

from reactpy import component, html, run

@component
def hello\_world():
    return html.h1("Hello, World!")

run(hello\_world)

Resources
=========

Follow the links below to find out more about this project.

-   Try ReactPy (Jupyter Notebook)
-   Documentation
-   GitHub Discussions
-   Discord
-   Contributor Guide
-   Code of Conduct
