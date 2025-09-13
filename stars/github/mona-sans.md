---
project: mona-sans
stars: 3875
description: Mona Sans, a variable font from GitHub
url: https://github.com/github/mona-sans
---

Mona Sans
=========

Download Mona Sans • Typeface microsite ↗️

A strong and versatile typeface, designed together with Degarism and inspired by industrial-era grotesques. Mona Sans works well across product, web, and print. Made to work well together with Mona Sans's sidekick, Hubot Sans.

Mona Sans is a variable font. Variable fonts enable different variations of a typeface to be incorporated into one single file, and are supported by all major browsers, allowing for performance benefits and granular design control of the typeface's weight, width, and slant.

Usage
-----

For web, we recommend using `Mona Sans.woff2`. Define the font with a `@font-face` rule, set its **weight** and **stretch** ranges, and use it:

@font-face {
  font-family: 'Mona Sans';
  src:
    url('Mona-Sans.woff2') format('woff2 supports variations'),
    url('Mona-Sans.woff2') format('woff2-variations');
  font-weight: 200 900;
  font-stretch: 75% 125%;
}

html {
  font-family: 'Mona Sans';
}

To reduce CLS, you can preload the font in the `head` of your document:

<link rel\="preload" href\="Mona-Sans.woff2" as\="font" type\="font/woff2" crossorigin\>

Styles
------

Style Name

Italic Name

Weight

Width

UltraLight Condensed

UltraLight Condensed Italic

200

75

Light Condensed

Light Condensed Italic

300

75

Regular Condensed

Regular Condensed Italic

400

75

Medium Condensed

Medium Condensed Italic

500

75

SemiBold Condensed

SemiBold Condensed Italic

600

75

Bold Condensed

Bold Condensed Italic

700

75

ExtraBold Condensed

ExtraBold Condensed Italic

800

75

Black Condensed

Black Condensed Italic

900

75

UltraLight SemiCondensed

UltraLight SemiCondensed Italic

200

87.5

Light SemiCondensed

Light SemiCondensed Italic

300

87.5

Regular SemiCondensed

Regular SemiCondensed Italic

400

87.5

Medium SemiCondensed

Medium SemiCondensed Italic

500

87.5

SemiBold SemiCondensed

SemiBold SemiCondensed Italic

600

87.5

Bold SemiCondensed

Bold SemiCondensed Italic

700

87.5

ExtraBold SemiCondensed

ExtraBold SemiCondensed Italic

800

87.5

Black SemiCondensed

Black SemiCondensed Italic

900

87.5

UltraLight

UltraLight Italic

200

100

Light

Light Italic

300

100

Regular

Regular Italic

400

100

Medium

Medium Italic

500

100

SemiBold

SemiBold Italic

600

100

Bold

Bold Italic

700

100

ExtraBold

ExtraBold Italic

800

100

Black

Black Italic

900

100

UltraLight SemiExpanded

UltraLight SemiExpanded Italic

200

112.5

Light SemiExpanded

Light SemiExpanded Italic

300

112.5

Regular SemiExpanded

Regular SemiExpanded Italic

400

112.5

Medium SemiExpanded

Medium SemiExpanded Italic

500

112.5

SemiBold SemiExpanded

SemiBold SemiExpanded Italic

600

112.5

Bold SemiExpanded

Bold SemiExpanded Italic

700

112.5

ExtraBold SemiExpanded

ExtraBold SemiExpanded Italic

800

112.5

Black SemiExpanded

Black SemiExpanded Italic

900

112.5

UltraLight Expanded

UltraLight Expanded Italic

200

125

Light Expanded

Light Expanded Italic

300

125

Regular Expanded

Regular Expanded Italic

400

125

Medium Expanded

Medium Expanded Italic

500

125

SemiBold Expanded

SemiBold Expanded Italic

600

125

Bold Expanded

Bold Expanded Italic

700

125

ExtraBold Expanded

ExtraBold Expanded Italic

800

125

Black Expanded

Black Expanded Italic

900

125

Stylistic sets
--------------

Mona Sans has eight stylistic sets:

Set

Description

Example

ss01

Square diacritical marks

ss02

Wide uppercase I

ss03

Lowercase l with tail

ss04

Lowercase l with top serif

ss05

Double-storey a

ss06

Double-storey g

ss07

Round G

ss08

Tabular zero with straight bar

When using Mona Sans on the web, you can control each stylistic set with the syntax `"ssXX" on/off`, e.g.:

html {
  font-family: 'Mona Sans';
  font-feature-settings: "ss01" on, "ss03" on, "ss05" on; /\* Turns on square diacritical marks, small letter L distinct from capital I, and alternative small letter g \*/
}

Ligatures
---------

Mona Sans comes with seven ligatures:

Ligature

Example

ff

ffi

fy

fi

fl

ti

tt

License
-------

Mona Sans is licensed under the SIL Open Font License v1.1.
