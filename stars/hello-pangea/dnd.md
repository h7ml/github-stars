---
project: dnd
stars: 3628
description: 💅 Beautiful and accessible drag and drop for lists with React. ⭐️ Star to support our work!
url: https://github.com/hello-pangea/dnd
---

@hello-pangea/dnd
=================

**Beautiful** and **accessible** drag and drop for lists with `React`

Play with this example if you want!

Core characteristics
--------------------

-   Beautiful and natural movement of items 💐
-   Accessible: powerful keyboard and screen reader support ♿️
-   Extremely performant 🚀
-   Clean and powerful api which is simple to get started with
-   Plays extremely well with standard browser interactions
-   Unopinionated styling
-   No creation of additional wrapper dom nodes - flexbox and focus management friendly!

Star History
------------

Get started 👩‍🏫
-----------------

Alex Reardon has created a free course on `egghead.io` 🥚 (using react-beautiful-dnd) to help you get started with `@hello-pangea/dnd` as quickly as possible.

Currently supported feature set ✅
---------------------------------

-   Vertical lists ↕
-   Horizontal lists ↔
-   Movement between lists (▤ ↔ ▤)
-   Virtual list support 👾 - unlocking 10,000 items @ 60fps
-   Combining items
-   Mouse 🐭, keyboard 🎹♿️ and touch 👉📱 (mobile, tablet and so on) support
-   Multi drag support
-   Incredible screen reader support ♿️ - we provide an amazing experience for english screen readers out of the box 📦. We also provide complete customisation control and internationalisation support for those who need it 💖
-   Conditional dragging and conditional dropping
-   Multiple independent lists on the one page
-   Flexible item sizes - the draggable items can have different heights (vertical lists) or widths (horizontal lists)
-   Add and remove items during a drag
-   Compatible with semantic `<table>` reordering - table pattern
-   Auto scrolling - automatically scroll containers and the window as required during a drag (even with keyboard 🔥)
-   Custom drag handles - you can drag a whole item by just a part of it
-   Able to move the dragging item to another element while dragging (clone, portal) - Reparenting your `<Draggable />`
-   Create scripted drag and drop experiences 🎮
-   Allows extensions to support for any input type you like 🕹
-   🌲 Tree support through the `@atlaskit/tree` package
-   A `<Droppable />` list can be a scroll container (without a scrollable parent) or be the child of a scroll container (that also does not have a scrollable parent)
-   Independent nested lists - a list can be a child of another list, but you cannot drag items from the parent list into a child list
-   Server side rendering (SSR) compatible
-   Plays well with nested interactive elements by default

Motivation 🤔
-------------

`@hello-pangea/dnd` exists to create beautiful drag and drop for lists that anyone can use - even people who cannot see. For a good overview of the history and motivations of the project you can take a look at these external resources:

-   📖 Rethinking drag and drop
-   🎧 React podcast: fast, accessible and beautiful drag and drop

Not for everyone ✌️
-------------------

There are a lot of libraries out there that allow for drag and drop interactions within React. Most notable of these is the amazing `react-dnd`. It does an incredible job at providing a great set of drag and drop primitives which work especially well with the wildly inconsistent html5 drag and drop feature. `@hello-pangea/dnd` is a higher level abstraction specifically built for lists (vertical, horizontal, movement between lists, nested lists and so on). Within that subset of functionality `@hello-pangea/dnd` offers a powerful, natural and beautiful drag and drop experience. However, it does not provide the breadth of functionality offered by `react-dnd`. One shortcoming is that grid layouts are not supported (yet). So `@hello-pangea/dnd` might not be for you depending on what your use case is.

Documentation 📖
----------------

### About 👋

-   Installation
-   Examples and samples
-   Get started (This is using react-beautiful-dnd)
-   Design principles
-   Animations
-   Accessibility
-   Browser support

### Sensors 🔉

> The ways in which somebody can start and control a drag

-   Mouse dragging 🐭
-   Touch dragging 👉📱
-   Keyboard dragging 🎹♿️
-   Create your own sensor (allows for any input type as well as scripted experiences)

### API 🏋️‍

-   `<DragDropContext />` - _Wraps the part of your application you want to have drag and drop enabled for_
-   `<Droppable />` - _An area that can be dropped into. Contains `<Draggable />`s_
-   `<Draggable />` - _What can be dragged around_

### Guides 🗺

-   `<DragDropContext />` responders - _`onDragStart`, `onDragUpdate`, `onDragEnd` and `onBeforeDragStart`_
-   Combining `<Draggable />`s
-   Common setup issues
-   Using `innerRef`
-   Setup problem detection and error recovery
-   Rules for `draggableId` and `droppableId`s
-   Browser focus retention
-   Customising or skipping the drop animation
-   Auto scrolling
-   Controlling the screen reader
-   Use the html5 `doctype`
-   `TypeScript`: type information
-   Dragging `<svg>`s
-   Avoiding image flickering
-   Non-visible preset styles
-   How we detect scroll containers
-   How we use dom events - _Useful if you need to build on top of `@hello-pangea/dnd`_
-   Adding `<Draggable />`s during a drag (11.x behaviour) - _⚠️ Advanced_
-   Setting up Content Security Policy

### Patterns 👷‍

-   Virtual lists 👾
-   Multi drag
-   Tables
-   Reparenting a `<Draggable />` - _Using our cloning API or your own portal_

### Support 👩‍⚕️

-   Engineering health
-   Community and addons
-   Release notes and changelog
-   Upgrading
-   Road map
-   Media

Creator ✍️
----------

Alex Reardon @alexandereardon

> Alex is no longer personally maintaning this project. The other wonderful maintainers are carrying this project forward.

Maintainers 🛠️
---------------

-   Gabriel Santerre @100terres
-   Reece Carolan @Xhale1
-   Many @Atlassian's have contributed to the original `react-beautiful-dnd`. _Atlassian is no longer involved with this project._

Collaborators 🤝
----------------

-   Bogdan Chadkin @IAmTrySound

Thanks 🤗
---------

Thanks to Chromatic for providing the visual testing platform that helps us review UI changes and catch visual regressions.
