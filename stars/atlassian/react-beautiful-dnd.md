---
project: react-beautiful-dnd
stars: 34055
description: Beautiful and accessible drag and drop for lists with React
url: https://github.com/atlassian/react-beautiful-dnd
---

🔒 Archived
-----------

This project is now archived and is deprecated on `npm`. If you are still using `react-beautiful-dnd`, we have put together some resources to help you move forward. To see our ongoing work in the drag and drop problem space, head to Pragmatic drag and drop.

We are so grateful to everybody who contributed in big and small ways to this project.

Cheers

  

* * *

react-beautiful-dnd (rbd)
=========================

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

Get started 👩‍🏫
-----------------

We have created a free course on `egghead.io` 🥚 to help you get started with `react-beautiful-dnd` as quickly as possible.

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
-   Server side rendering (SSR) compatible - see resetServerContext()
-   Plays well with nested interactive elements by default

Motivation 🤔
-------------

`react-beautiful-dnd` exists to create beautiful drag and drop for lists that anyone can use - even people who cannot see. For a good overview of the history and motivations of the project you can take a look at these external resources:

-   📖 Rethinking drag and drop
-   🎧 React podcast: fast, accessible and beautiful drag and drop

Not for everyone ✌️
-------------------

There are a lot of libraries out there that allow for drag and drop interactions within React. Most notable of these is the amazing `react-dnd`. It does an incredible job at providing a great set of drag and drop primitives which work especially well with the wildly inconsistent html5 drag and drop feature. `react-beautiful-dnd` is a higher level abstraction specifically built for lists (vertical, horizontal, movement between lists, nested lists and so on). Within that subset of functionality `react-beautiful-dnd` offers a powerful, natural and beautiful drag and drop experience. However, it does not provide the breadth of functionality offered by `react-dnd`. So `react-beautiful-dnd` might not be for you depending on what your use case is.

Documentation 📖
----------------

### About 👋

-   Installation
-   Examples and samples
-   Get started
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
-   `resetServerContext()` - _Utility for server side rendering (SSR)_

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
-   `TypeScript` and `flow`: type information
-   Dragging `<svg>`s
-   Avoiding image flickering
-   Non-visible preset styles
-   How we detect scroll containers
-   How we use dom events - _Useful if you need to build on top of `react-beautiful-dnd`_
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

Read this in other languages 🌎
-------------------------------

-   **한글/Korean**
-   **На русском/Russian**
-   **Português/Portuguese**
-   **Ελληνικά/Greek**
-   **日本語/Japanese**

Creator ✍️
----------

Alex Reardon @alexandereardon

> Alex is no longer personally maintaining this project. The other wonderful maintainers are carrying this project forward.

Maintainers
-----------

-   Daniel Del Core
-   Many other @Atlassian's!

Collaborators 🤝
----------------

-   Bogdan Chadkin @IAmTrySound
