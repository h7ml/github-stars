---
project: PySimpleGUI
stars: 13523
description: Python GUIs for Humans! PySimpleGUI is the top-rated Python application development environment. Launched in 2018 and actively developed, maintained, and supported in 2024. Transforms tkinter, Qt, WxPython, and Remi into a simple, intuitive, and fun experience for both hobbyists and expert users.
url: https://github.com/PySimpleGUI/PySimpleGUI
---

  
For more information visit PySimpleGUI.com

User Interfaces for HumansTM
----------------------------

Welcome to PySimpleGUI 5 !!
===========================

Do you use PySimpleGUI 4? Here is what you need to know.

**PySimpleGUI creates desktop applications easily**, enhancing the tkinter, Qt, WxPython, and Remi frameworks with a much simpler programming interface:

1.  PySimpleGUI user interfaces are defined using core Python data types (lists and dictionaries) that are easily understood by beginners.
2.  PySimpleGUI event handling changes from a complex callback-based model to a simple message passing one.
3.  PySimpleGUI uses simple Python code and has no requirement for object oriented architecture.

PySimpleGUI is more than a GUI library: PySimpleGUI simplifies much of your Python development process. Sure, it makes developing user interfaces much easier, but PySimpleGUI also tames advanced Python functionality (such as threading) and makes it easy for all users to take their Python applications to the next level. PySimpleGUI is a robust toolkit.

Introducing PySimpleGUI 5
-------------------------

For the last 5 years, PySimpleGUI offered free software with the hope of sustaining the company by donations. We appreciate the support we received, but the amount has been too small to support the PySimpleGUI project. For this reason, PySimpleGUI is switching to a commercial model, where commercial users are expected to pay a nominal license fee.

PySimpleGUI is now part of PySimpleSoft, Inc., whose mission is to make the best Python application development environment much, much better. Since launching in 2018, PySimpleGUI has helped hobbyists and professionals alike create Python GUIs in a fraction of the time. PySimpleGUI 5 takes PySimpleGUI to the next level, providing hundreds of improvements, including new features, enhanced security, and priority support.

PySimpleGUI 5 is licensed software. As the License Agreement explains, after a trial period, all PySimpleGUI 5 users must register at PySimpleGUI.com to obtain a Developer Key. For most users (Hobbyist Users), the license is at NO COST. If you are a Commercial User, you must buy a license.

Register Now and help support the PySimpleGUI community.

Examples
--------

PySimpleGUI users have created thousands of amazing desktop applications. Here are a few screen shots. For more examples, see the PySimpleGUI gallery.

Get Started at No Cost
----------------------

Whether you are a Hobbyist User or Commercial User, you can start using PySimpleGUI at no cost. To get started with a 30-day trial period, first install Python and then

```
python -m pip install pysimplegui
```

and run some code, like

```
import PySimpleGUI as sg
layout = [ [sg.Text('Hello, world!')] ]
window = sg.Window('Hello Example', layout)
while True:
    event, values = window.read()
    if event == sg.WIN_CLOSED:
        break
window.close()
```

(You might need to use `python3` instead of `python`.)

You can try PySimpleGUI for 30 days, after which you will need to register. Hobbyist users register at no cost, and Commercial Users must buy a license. For more details, see PySimpleGUI.com/pricing.

Documentation
-------------

PySimpleGUI provides extensive documentation. Here are some starting points, depending on your needs and expertise:

-   FAQ - Frequently Asked Questions
-   Documentation - Extensive PySimpleGUI documentation\*
-   Examples - Hundreds of sample PySimpleGUI applications.
-   SDK Reference - details for each PySimpleGUI element
-   Home Website - New PySimpleGUI home page
-   GitHub Repo - Informational only. Download from PyPi with pip.
-   Updated Documentation - Everything you need to know about the latest and best PySimpleGUI
    -   Cookbook - Hundreds of basic PySimpleGUI examples. Find a starting point that is close to what you need.
    -   Call Reference - Just the facts, Ma'am
-   Udemy Course - Become a PySimpleGUI expert in no time. Bundled with Commercial Developer License.
