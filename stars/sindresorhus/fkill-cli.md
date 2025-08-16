---
project: fkill-cli
stars: 6930
description: Fabulously kill processes. Cross-platform.
url: https://github.com/sindresorhus/fkill-cli
---

  
  
  
  

============

> Fabulously kill processes. Cross-platform.

Works on macOS, Linux, and Windows.

Install
-------

npm install --global fkill-cli

Usage
-----

```
$ fkill --help

	Usage
		$ fkill [<pid|name|:port> …]

	Options
		--force, -f                  Force kill
		--verbose, -v                Show process arguments
		--silent, -s                 Silently kill and always exit with code 0
		--force-timeout <N>, -t <N>  Force kill processes which didn't exit after N seconds

	Examples
		$ fkill 1337
		$ fkill safari
		$ fkill :8080
		$ fkill 1337 safari :8080
		$ fkill

	To kill a port, prefix it with a colon. For example: :8080.

	Run without arguments to use the interactive interface.
	In interactive mode, 🚦n% indicates high CPU usage and 🐏n% indicates high memory usage.
	Supports fuzzy search in the interactive mode.

	The process name is case insensitive.
```

Interactive UI
--------------

Run `fkill` without arguments to launch the interactive UI.

Related
-------

-   fkill - API for this module
-   alfred-fkill - Alfred workflow for this module
