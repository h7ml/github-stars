---
project: infinite
stars: 372
description: Help you to create interactive command line applications in Go.
url: https://github.com/fzdwx/infinite
---

infinite
========

Help you to create interactive command line applications in Go.

Features
--------

-   multi/single select
-   progress-bar group
-   spinner
-   confirm(input/selection)
-   input

Install
-------

go get github.com/fzdwx/infinite@main

Examples
--------

func main() {
	input := components.NewInput()
	input.Prompt \= "Filtering: "
	input.PromptStyle \= style.New().Bold().Italic().Fg(color.LightBlue)

	keymap := components.DefaultMultiKeyMap()
	keymap.Choice \= key.NewBinding(
		key.WithKeys(tea.KeySpace.String()),
	)
	\_, \_ \= inf.NewMultiSelect(\[\]string{
		"a", "b", "c",
		"d", "e",
		"f",
		"g",
		"h",
	},
		multiselect.WithKeyMap(keymap),
		multiselect.WithHintSymbol("x"),
		multiselect.WithUnHintSymbol("√"),
		multiselect.WithPageSize(3),
		multiselect.WithFilterInput(input),
	).
		Display("select your items!")
}

More: https://github.com/fzdwx/infinite/tree/main/\_examples

License
-------

MIT
