---
project: KaTeX
stars: 19368
description: Fast math typesetting for the web.
url: https://github.com/KaTeX/KaTeX
---

KaTeX is a fast, easy-to-use JavaScript library for TeX math rendering on the web.

-   **Fast:** KaTeX renders its math synchronously and doesn't need to reflow the page. See how it compares to a competitor in this speed test.
-   **Print quality:** KaTeX's layout is based on Donald Knuth's TeX, the gold standard for math typesetting.
-   **Self contained:** KaTeX has no dependencies and can easily be bundled with your website resources.
-   **Server side rendering:** KaTeX produces the same output regardless of browser or environment, so you can pre-render expressions using Node.js and send them as plain HTML.

KaTeX is compatible with all major browsers, including Chrome, Safari, Firefox, Opera, Edge, and IE 11.

KaTeX supports much (but not all) of LaTeX and many LaTeX packages. See the list of supported functions.

Try out KaTeX on the demo page!

Getting started
---------------

### Starter template

<!DOCTYPE html\>
<!-- KaTeX requires the use of the HTML5 doctype. Without it, KaTeX may not render properly -->
<html\>
  <head\>
    <link rel\="stylesheet" href\="https://cdn.jsdelivr.net/npm/katex@0.16.22/dist/katex.min.css" integrity\="sha384-5TcZemv2l/9On385z///+d7MSYlvIEw9FuZTIdZ14vJLqWphw7e7ZPuOiCHJcFCP" crossorigin\="anonymous"\>

    <!-- The loading of KaTeX is deferred to speed up page rendering -->
    <script defer src\="https://cdn.jsdelivr.net/npm/katex@0.16.22/dist/katex.min.js" integrity\="sha384-cMkvdD8LoxVzGF/RPUKAcvmm49FQ0oxwDF3BGKtDXcEc+T1b2N+teh/OJfpU0jr6" crossorigin\="anonymous"\></script\>

    <!-- To automatically render math in text elements, include the auto-render extension: -->
    <script defer src\="https://cdn.jsdelivr.net/npm/katex@0.16.22/dist/contrib/auto-render.min.js" integrity\="sha384-hCXGrW6PitJEwbkoStFjeJxv+fSOOQKOPbJxSfM6G5sWZjAyWhXiTIIAmQqnlLlh" crossorigin\="anonymous"
        onload\="renderMathInElement(document.body);"\></script\>
  </head\>
  ...
</html\>

You can also download KaTeX and host it yourself.

For details on how to configure auto-render extension, refer to the documentation.

### API

Call `katex.render` to render a TeX expression directly into a DOM element. For example:

katex.render("c = \\\\pm\\\\sqrt{a^2 + b^2}", element, {
    throwOnError: false
});

Call `katex.renderToString` to generate an HTML string of the rendered math, e.g., for server-side rendering. For example:

var html \= katex.renderToString("c = \\\\pm\\\\sqrt{a^2 + b^2}", {
    throwOnError: false
});
// '<span class="katex">...</span>'

Make sure to include the CSS and font files in both cases. If you are doing all rendering on the server, there is no need to include the JavaScript on the client.

The examples above use the `throwOnError: false` option, which renders invalid inputs as the TeX source code in red (by default), with the error message as hover text. For other available options, see the API documentation, options documentation, and handling errors documentation.

Demo and Documentation
----------------------

Learn more about using KaTeX on the website!

Contributors
------------

### Code Contributors

This project exists thanks to all the people who contribute code. If you'd like to help, see our guide to contributing code.

### Financial Contributors

Become a financial contributor and help us sustain our community.

#### Individuals

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website.

License
-------

KaTeX is licensed under the MIT License.
