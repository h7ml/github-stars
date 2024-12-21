---
project: quiver
stars: 2449
description: A modern commutative diagram editor for the web.
url: https://github.com/varkor/quiver
---

quiver: a modern commutative diagram editor
===========================================

**quiver** is a modern, graphical editor for commutative and pasting diagrams, capable of rendering high-quality diagrams for screen viewing, and exporting to LaTeX via tikz-cd.

Creating and modifying diagrams with **quiver** is orders of magnitude faster than writing the equivalent LaTeX by hand and, with a little experience, competes with pen-and-paper.

Try **quiver** out: q.uiver.app

Features & screenshots
----------------------

**quiver** features an efficient, intuitive interface for creating complex commutative diagrams and pasting diagrams. It's easy to draw diagrams involving pullbacks and pushouts,

adjunctions,

and higher cells.

Object placement is based on a flexible grid that resizes according to the size of the labels.

There is a wide range of composable arrow styles.

And full use of colour for labels and arrows.

**quiver** is intended to look good for screenshots, as well as to export LaTeX that looks as close as possible to the original diagram.

Diagrams may be created and modified using either the mouse, by clicking and dragging, or using the keyboard, with a complete set of keyboard shortcuts for performing any action.

When you export diagrams to LaTeX, **quiver** will embed a link to the diagram, which will allow you to return to it later if you decide it needs to be modified, or to share it with others.

### Other features

-   Multiple selection, making mass changes easy and fast.
-   A history system, allowing you to undo/redo actions.
-   Support for custom macro definitions: simply paste a URL corresponding to the file containing your `\newcommand`s.
-   Export embeddable diagrams to HTML.
-   Panning and zooming, for large diagrams.
-   Smart label alignment and edge offset.

Importing macros and colours
----------------------------

To use custom macros and colours in **quiver**, create a file containing the definitions, like the following.

\\newcommand{\\cat}{\\mathscr}
\\newcommand{\\psh}{\\widehat}
\\newcommand{\\smcat}{\\mathbb}
\\newcommand{\\yo}{よ}

Upload the file to a publicly accessible URL (for instance, gist.github.com), and paste the URL for the raw text into the "Macros" input at the bottom of **quiver**.

Currently, macros may be defined using `\newcommand`, `\newcommand*`, `\renewcommand`, `\renewcommand*`, `\DeclareMathOperator`, and `\DeclareMathOperator*`; and colours may be defined using `\definecolor` (using the colour modes: `rgb`, `RGB`, `HTML`, `gray`).

Editor integration
------------------

See Editor integration on the quiver wiki.

Building
--------

Run `make` from the command line, and then open `src/index.html` in your favourite web browser.

If this fails, you might be using an incompatible version of Make or Bash. In this case, you can manually download the latest release of KaTeX and place it under `src/` as `src/KaTeX/`. If KaTeX has not been given the correct path, you will get an error telling you that KaTeX failed to load.

**quiver** must be run through `localhost`. If you have Python installed, an easy solution is to run:

```
python3 -m http.server
```

in the **quiver** `src` directory and then open `localhost:8000` in browser.

If you have any other problems building **quiver**, open an issue detailing the problem and I'll try to help.

Thanks to
---------

-   S. C. Steenkamp, for helpful discussions regarding the aesthetic rendering of arrows.
-   AndréC, for the custom TikZ style for curves of a fixed height.
-   Nathan Corbyn, for adding the ability to export embeddable diagrams to HTML.
-   Paolo Brasolin, for adding offline support.
-   Carl Davidson, for discussing and prototyping loop rendering.
-   Everyone who has improved **quiver** by reporting issues or suggesting improvements.
