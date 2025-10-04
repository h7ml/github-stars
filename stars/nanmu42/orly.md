---
project: orly
stars: 812
description: :football: Generate your own O'RLY animal book cover to troll your colleagues | 生成你自己的O'RLY动物书封面，让你的同事惊掉下巴
url: https://github.com/nanmu42/orly
---

**English** | 中文

O'RLY Cover Generator
=====================

O'RLY Cover Generator is a parody book cover generator, implemented in Golang and Vue.js, supporting a wide range of language including CJK.

Go to the living demo to build your own O'RLY cover and troll your friends and colleagues.

Docker images can be found here.

Docker Image
============

docker pull nanmu42/orly:\[tag\]

Refer to https://hub.docker.com/r/nanmu42/orly/tags for available tags.

Example config:

CoverImageDir = "cover-images"
Debug = false
MaxImageID = 41
Port = ":3000"
TitleFont = "fonts/SourceHanSerif-Bold.ttc"
NormalFont = "fonts/SourceHanSans-Medium.ttc"
ORLYFont = "fonts/SourceSansPro-Black.ttf"
QueueLen = 20
WorkerNum = 2
Width = 1000

Save as `rly.toml`, mount it into `/app/config`, and run docker image with param `/app/rly -config config/rly.toml`.

Develop O'RLY
=============

O'RLY can be built in following commands:

make assets
make all

O'RLY consists of an API instance and a static frontend:

-   API source lies in `cmd/rly`;
-   Frontend source lies in `frontend`

Animal images and font files are in `coverimage` and `font` respectively.

More documentations can be found in their directory.

Contributes O'RLY
=================

Contributions are always welcome!

Here are a few directions if you are interested:

-   Help translating the frontend(we are using Vue i18n)
-   Improve O'RLY
-   Add New Features
-   Raise a bug report

Or simply...

-   Sharing the fun 😉

Contributors
============

Many thanks 🤗 to following contributors:

-   TahsinGokalp (Turkish translation)
-   wooogi123 (Korean translation)
-   cauldnz (Adding new animal)
-   Jessica Sachs (Project maintainer!)
-   Hervé (French translation)

Projects in Brotherhood
=======================

There are several projects which share the idea:

-   O RLY Cover Generator on dev.to, where this project gets idea, supporting English only(partial reason for me to build O'RLY), there is also a slack integration.
-   Japanese O'Reilly Generator, with really good user experience, covers are generated in your browser

Paperwork
=========

"O'RLY Cover Generator" is just a parody, and it has no concern with O'Reilly Media.

This work uses Source Han Serif and Source Han Sans from Adobe and Google, with participation from partner foundries Changzhou SinoType in China, Iwata Corporation in Japan, and Sandoll Communications in Korea.

This work uses TrueType version of Source Sans Pro from Adobe by Paul D. Hunt.

The animal(well, not all of them are animal) images are from the USF ClipArt ETC project.

Acknowledgements
================

The author would like to thank JetBrains for providing a JetBrains Open Source license for his open source developments.

License
=======

Use of this work is governed by the MIT License.

You may find a license copy in project root.
