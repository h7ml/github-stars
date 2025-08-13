---
project: swing
stars: 2638
description: A swipeable cards interface. The swipe-left/swipe-right for yes/no input. As seen in apps like Jelly and Tinder.
url: https://github.com/gajus/swing
---

Swing
=====

A swipeable cards interface. The swipe-left/swipe-right for yes/no input. As seen in apps like Jelly and Tinder, and many others.

Give it a swing! and please tweet it if you like it. : )

Contents
--------

-   Usage Examples
    -   Use Case
        -   Single-Handed Navigation
        -   Digestible Unit of Information
        -   Data
-   Quick Start
-   Configuration
-   Methods
    -   Throwing Card Out of the Stack
-   Events
    -   Event Object
-   Download
    -   Browser Bundle
-   Dependencies

Usage Examples
--------------

-   Card stack.
-   Card stack using angular-swing module.
-   Card-stack using angular2-swing module.
-   Programmatically control the state of the card.
-   Indicate the state of the drop using `throwConfidence` and `direction` event object properties.

The code for all of the examples is in the ./examples/ folder.

Raise an issue if you are missing an example.

Use Case
--------

A collection of observations about the extended use case of the swipeable cards interface, that I found useful when considering the implementation.

### Single-Handed Navigation

> Mobile devices are frequently used on-the-go, which drastically increases the probability that you'll attempt to navigate apps using just one hand, with the key digit being the mighty thumb. Instead of browsing endless lists for the hidden perfect piece of data — be it the right music for the moment, what to do tonight, or your next potential hookup — card-swiping turns decision making into a highly engaging Choose-Your-Own-Adventure game.

– https://medium.com/@janel\_az/small-data-why-tinder-like-apps-are-the-way-of-the-future-1a4d5703b4b

### Digestible Unit of Information

> \[..\] the "card" on a mobile device becomes more and more important as a digestible unit of information on a small screen for users who are on the go and mostly glancing through their apps before settling into the ones that truly engage them.

– http://techcrunch.com/2013/09/22/mobile-apps-card-interfaces-and-our-opposable-thumbs/

### Data

> More than a scroll and perhaps even more than discrete taps themselves, cards create repetitive, deliberate, discrete decision moments over and over. And as the user swipes, you can learn. The time they swipe, the speed they swipe, what they swiped, the geolocation where they swiped, and even how similar the results of that swipe are vs. a swipe earlier that session are all possibilities that are yielding smarter apps for you and me every day.

– http://www.itsmakeable.com/unconventional-wisdom/good-user-experience-design-ux-can-do-what-now/

Quick Start
-----------

<ul\>
  <li\></li\>
  <li\></li\>
  <li\></li\>
</ul\>

// Prepare the cards in the stack for iteration.
const cards \= \[\].slice.call(document.querySelectorAll('ul li'));

// An instance of the Stack is used to attach event listeners.
const stack \= Swing.Stack();

cards.forEach((targetElement) \=> {
  // Add card element to the Stack.
  stack.createCard(targetElement);
});

// Add event listener for when a card is thrown out of the stack.
stack.on('throwout', (event) \=> {
  // e.target Reference to the element that has been thrown out of the stack.
  // e.throwDirection Direction in which the element has been thrown (Direction.LEFT, Direction.RIGHT).

  console.log('Card has been thrown out of the stack.');
  console.log('Throw direction: ' + (event.throwDirection \== Direction.LEFT ? 'left' : 'right'));
});

// Add event listener for when a card is thrown in the stack, including the spring back into place effect.
stack.on('throwin', () \=> {
  console.log('Card has snapped back to the stack.');
});

Configuration
-------------

const config \= {
  /\*\*
   \* Invoked in the event of dragmove.
   \* Returns a value between 0 and 1 indicating the completeness of the throw out condition.
   \* Ration of the absolute distance from the original card position and element width.
   \*
   \* @param {number} xOffset Distance from the dragStart.
   \* @param {number} yOffset Distance from the dragStart.
   \* @param {HTMLElement} element Element.
   \* @returns {number}
   \*/
  throwOutConfidence: (xOffset, yOffset, element) \=> {
    const xConfidence \= Math.min(Math.abs(xOffset) / element.offsetWidth, 1);
    const yConfidence \= Math.min(Math.abs(yOffset) / element.offsetHeight, 1);

    return Math.max(xConfidence, yConfidence);
  }
};

const stack \= stack \= Swing.Stack(config);

Name

Description

Default

`isThrowOut`

Invoked in the event of `dragend`. Determines if element is being thrown out of the stack.

Element is considered to be thrown out when `throwOutConfidence` is equal to 1.

`allowedDirections`

Array of directions in which cards can be thrown out.

\[Direction.DOWN, Direction.LEFT, Direction.RIGHT, Direction.UP\].

`throwOutConfidence`

Invoked in the event of `dragmove`. Returns a value between 0 and 1 indicating the completeness of the throw out condition.

Ration of the absolute distance from the original card position and element width.

`throwOutDistance`

Invoked when card is added to the stack. The card is thrown to this offset from the stack.

The value is a random number between `minThrowOutDistance` and `maxThrowOutDistance`.

`minThrowOutDistance`

In effect when `throwOutDistance` is not overwritten.

450.

`maxThrowOutDistance`

In effect when `throwOutDistance` is not overwritten.

500.

`rotation`

Invoked in the event of `dragmove`. Determine the rotation of the element.

Rotation is equal to the proportion of horizontal and vertical offset times the `maximumRotation` constant.

`maxRotation`

In effect when `rotation` is not overwritten.

20.

`transform`

Invoked in the event of `dragmove` and every time the physics solver is triggered.

Uses CSS transform to translate element position and rotation.

`allowMovement`

Function that determines if movement is allowed when a movement event is fired. It has two arguments, the `event` object and a `boolean` set to true if on a touch device.

A function that returns true for all movement events.

All of the configuration parameters are optional. Refer to the source code of the card module to learn the parameters associated with every callback.

Methods
-------

const stack \= Swing.Stack();
const card \= stack.createCard(HTMLElement);

Name

Description

`stack.createCard(element, prepend)`

Creates an instance of Card and associates it with the element. If prepend is true, the card is prepended to the stack, instead of appended \[default: false\].

`stack.getCard(element)`

Returns card associated with an element.

`stack.on(event, listener)`

Attaches an event listener.

`card.on(event, listener)`

Attaches an event listener.

`card.throwIn(coordinateX, coordinateY)`

Throws a card into the stack from an arbitrary position. `coordinateX, coordinateY` is the position at the start of the throw.

`card.throwOut(coordinateX, coordinateY)`

Throws a card out of the stack in the direction away from the original offset. `coordinateX, coordinateY` is the position at the start of the throw.

`card.destroy()`

Unbinds all Hammer.Manager events. Removes the listeners from the physics simulation.

### Throwing Card Out of the Stack

Use the `card.throwOut(coordinateX, coordinateY)` method to throw the card out of the stack. Offset the position to whatever direction you want to throw the card, e.g.

card.throwOut(Direction.LEFT, 0);
card.throwOut(Direction.RIGHT, 0);

To make the animation more diverse, use random value for the `coordinateY` parameter.

Events
------

Event listener can be attached to an instance of `Swing.Stack` or `Swing.Card` using the `on` method:

const stack \= Swing.Stack();

const card \= stack.createCard(HTMLElement);

card.on('throwout', () \=> {});
stack.on('throwout', () \=> {});

Name

Description

`throwout`

When card has been thrown out of the stack.

`throwoutend`

When card has been thrown out of the stack and the animation has ended.

`throwoutdown`

Shorthand for `throwout` event in the `Direction.DOWN` direction.

`throwoutleft`

Shorthand for `throwout` event in the `Direction.LEFT` direction.

`throwoutright`

Shorthand for `throwout` event in the `Direction.RIGHT` direction.

`throwoutup`

Shorthand for `throwout` event in the `Direction.UP` direction.

`throwin`

When card has been thrown into the stack.

`throwinend`

When card has been thrown into the stack and the animation has ended.

`dragstart`

Hammer panstart.

`dragmove`

Hammer panmove.

`dragend`

Hammer panend.

`destroyCard`

When card.destroy calls stack.destroyCard.

### Event Object

Event listener is invoked with a single `eventObject` parameter:

const stack \= Swing.Stack();

stack.on('throwout', (eventObject) \=> {});

Name

Value

`target`

The element being dragged.

`direction`

The direction in which the element is being dragged: `Direction.DOWN`, `Direction.LEFT`, `Direction.RIGHT` or `Direction.UP`.

`throwOutConfidence`

A value between 0 and 1 indicating the completeness of the throw out condition.
