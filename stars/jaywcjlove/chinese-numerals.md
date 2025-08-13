---
project: chinese-numerals
stars: 6
description: Chinese Numerals
url: https://github.com/jaywcjlove/chinese-numerals
---

Chinese Numerals
================

Lowercase Chinese numerals

0

1

2

3

4

5

6

7

8

9

10

100

1000

10000

108

1012

1016

1020

1024

1028

1032

1036

1040

1044

1048

〇

一

二

三

四

五

六

七

八

九

十

百

千

萬

億

兆

京

垓

秭

穰

溝

澗

正

載

極

Uppercase Chinese numerals

0

1

2

3

4

5

6

7

8

9

10

100

1000

10000

108

1012

1016

1020

1024

1028

1032

1036

1040

1044

1048

零

壹

貳

參

肆

伍

陸

柒

捌

玖

拾

佰

仟

萬

億

兆

京

垓

秭

穰

溝

澗

正

載

極

Heavenly Dry(天干地支)

1

2

3

4

5

6

7

8

9

10

甲

乙

丙

丁

戊

己

庚

辛

壬

癸

Installation
------------

This package is ESM only: Node 12+ is needed to use it and it must be import instead of require.

npm install @wcj/chinese-numerals

Usage
-----

import { lowercase, uppercase, heavenlyDry } from "@wcj/chinese-numerals";

console.log(lowercase)     // => \['〇', '一', '二', '三', '四', ... \]
console.log(lowercase\[3\])  // => '三'

console.log(uppercase)     // => \['零', '壹', '貳', '參', '肆', ... \]
console.log(uppercase\[2\])  // => '貳'

console.log(heavenlyDry)   // => \['甲', '乙', '丙', '丁', '戊', '己', ... \]
console.log(heavenlyDry\[2 \- 1\])  // => '乙'

import lowercase from "@wcj/chinese-numerals/lowercase.json";
import uppercase from "@wcj/chinese-numerals/uppercase.json";
import heavenlyDry from "@wcj/chinese-numerals/heavenly-dry.json";

console.log(lowercase)     // => \['〇', '一', '二', '三', '四', ... \]
console.log(lowercase\[3\])  // => '三'
console.log(uppercase)     // => \['零', '壹', '貳', '參', '肆', ... \]
console.log(uppercase\[2\])  // => '貳'
console.log(heavenlyDry\[2 \- 1\])  // => '乙'

Contributors
------------

As always, thanks to our amazing contributors!

Made with contributors.

License
-------

Licensed under the MIT License.
