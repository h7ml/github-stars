---
project: preact
stars: 38120
description: ⚛️ Fast 3kB React alternative with the same modern API. Components & Virtual DOM.
url: https://github.com/preactjs/preact
---

Note

This is the branch for the upcoming release, for patches to v10 you need the v10.x branch

Fast **4kB** alternative to React with the same modern API.

**All the power of Virtual DOM components, without the overhead:**

-   Familiar React API & patterns: ES6 Class, hooks, and Functional Components
-   Extensive React compatibility via a simple preact/compat alias
-   Everything you need: JSX, VDOM, DevTools, HMR, SSR.
-   Highly optimized diff algorithm and seamless hydration from Server Side Rendering
-   Supports all modern browsers
-   Transparent asynchronous rendering with a pluggable scheduler

### 💁 More information at the Preact Website ➞

You can find some awesome libraries in the awesome-preact list 😎

* * *

Getting Started
---------------

> 💁 _**Note:** You don't need ES2015 to use Preact... but give it a try!_

#### Tutorial: Building UI with Preact

With Preact, you create user interfaces by assembling trees of components and elements. Components are functions or classes that return a description of what their tree should output. These descriptions are typically written in JSX (shown underneath), or HTM which leverages standard JavaScript Tagged Templates. Both syntaxes can express trees of elements with "props" (similar to HTML attributes) and children.

To get started using Preact, first look at the render() function. This function accepts a tree description and creates the structure described. Next, it appends this structure to a parent DOM element provided as the second argument. Future calls to render() will reuse the existing tree and update it in-place in the DOM. Internally, render() will calculate the difference from previous outputted structures in an attempt to perform as few DOM operations as possible.

import { h, render } from 'preact';
// Tells babel to use h for JSX. It's better to configure this globally.
// See https://babeljs.io/docs/en/babel-plugin-transform-react-jsx#usage
// In tsconfig you can specify this with the jsxFactory
/\*\* @jsx h \*/

// create our tree and append it to document.body:
render(
	<main\>
		<h1\>Hello</h1\>
	</main\>,
	document.body
);

// update the tree in-place:
render(
	<main\>
		<h1\>Hello World!</h1\>
	</main\>,
	document.body
);
// ^ this second invocation of render(...) will use a single DOM call to update the text of the <h1>

Hooray! render() has taken our structure and output a User Interface! This approach demonstrates a simple case, but would be difficult to use as an application grows in complexity. Each change would be forced to calculate the difference between the current and updated structure for the entire application. Components can help here – by dividing the User Interface into nested Components each can calculate their difference from their mounted point. Here's an example:

import { render, h } from 'preact';
import { useState } from 'preact/hooks';

/\*\* @jsx h \*/

const App \= () \=> {
	const \[input, setInput\] \= useState('');

	return (
		<div\>
			<p\>Do you agree to the statement: "Preact is awesome"?</p\>
			<input value\={input} onInput\={e \=> setInput(e.target.value)} />
		</div\>
	);
};

render(<App />, document.body);

* * *

Sponsors
--------

Become a sponsor and get your logo on our README on GitHub with a link to your site. \[Become a sponsor\]

           

Backers
-------

Support us with a monthly donation and help us continue our activities. \[Become a backer\]

* * *

License
-------

MIT
