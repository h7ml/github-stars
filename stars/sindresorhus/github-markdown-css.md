---
project: github-markdown-css
stars: 8582
description: The minimal amount of CSS to replicate the GitHub Markdown style
url: https://github.com/sindresorhus/github-markdown-css
---

github-markdown-css
===================

> The minimal amount of CSS to replicate the GitHub Markdown style

**The CSS is generated. Contributions should go to this repo.**

Demo
----

Install
-------

Download manually, from CDNJS, or with npm:

npm install github-markdown-css

Usage
-----

Import the `github-markdown.css` file and add a `markdown-body` class to the container of your rendered Markdown and set a width for it. GitHub uses `980px` width and `45px` padding, and `15px` padding for mobile.

<meta name\="viewport" content\="width=device-width, initial-scale=1"\>
<link rel\="stylesheet" href\="github-markdown.css"\>
<style\>
	.markdown-body {
		box-sizing: border-box;
		min-width: 200px;
		max-width: 980px;
		margin: 0 auto;
		padding: 45px;
	}

	@media (max-width: 767px) {
		.markdown-body {
			padding: 15px;
		}
	}
</style\>
<article class\="markdown-body"\>
	<h1\>Unicorns</h1\>
	<p\>All the things</p\>
</article\>

You can use GitHub's `/markdown` API to turn Markdown into the HTML that GitHub generates, which works well with the CSS in this repo. Other Markdown parsers will mostly work with these styles too. To mimic how GitHub highlights code, you can use `starry-night` with your Markdown parser of choice.

There are 3 themes provided in this package:

-   **github-markdown.css**: (default) Automatically switches between light and dark through `@media (prefers-color-scheme)`.
-   **github-markdown-light.css**: Light-only.
-   **github-markdown-dark.css**: Dark-only.

You may know that now GitHub supports more than 2 themes including `dark_dimmed`, `dark_high_contrast` and `colorblind` variants. If you want to try these themes, you can generate them on your own! See next section.

How
---

See `generate-github-markdown-css` for how it's generated and ability to generate your own.

Troubleshooting
---------------

If you encounter styling issues, like tables in dark mode rendering their fonts in black, the browser might uses quirks mode by accident.

To avoid quirks mode, always include a doctype at the top of your page.

<!doctype html\>
<html lang\="en"\><head\></head\><body\></body\></html\>

Dev
---

Run `npm run make` to update the CSS.
