---
project: typedoc
stars: 8198
description: Documentation generator for TypeScript projects.
url: https://github.com/TypeStrong/typedoc
---

TypeDoc
=======

Documentation generator for TypeScript projects.

Documentation
-------------

For more detailed documentation, the changelog, and TypeDoc documentation rendered with TypeDoc, see https://typedoc.org.

Installation
------------

TypeDoc runs on Node.js and is available as a NPM package.

```
npm install typedoc --save-dev
```

Usage
-----

To generate documentation TypeDoc needs to know your project entry point and TypeScript compiler options. It will automatically try to find your `tsconfig.json` file, so you can just specify the entry point of your library:

```
typedoc src/index.ts
```

If you have multiple entry points, specify each of them.

```
typedoc package1/index.ts package2/index.ts
```

If you specify a directory, TypeDoc will use the `entryPointStrategy` option to determine how to resolve it. By default, TypeDoc will search for a file called `index` under the directory.

### Monorepos / Workspaces

If your codebase is comprised of one or more npm packages, you can build documentation for each of them individually and merge the results together into a single site by setting `entryPointStrategy` to `packages`. In this mode TypeDoc requires configuration to be present in each directory to specify the entry points. For an example setup, see https://github.com/Gerrit0/typedoc-packages-example

### Arguments

For a complete list of the command line arguments run `typedoc --help` or visit our website.

-   `--out <path/to/documentation/>`  
    Specifies the location the documentation should be written to. Defaults to `./docs`
-   `--json <path/to/output.json>`  
    Specifies the location and file name a json file describing the project is written to. When specified no documentation will be generated unless `--out` is also specified.
-   `--options`  
    Specify a json option file that should be loaded. If not specified TypeDoc will look for 'typedoc.json' in the current directory.
-   `--tsconfig <path/to/tsconfig.json>`  
    Specify a typescript config file that should be loaded. If not specified TypeDoc will look for 'tsconfig.json' in the current directory.
-   `--exclude <pattern>`  
    Exclude files by the given pattern when a path is provided as source. Supports standard minimatch patterns.

#### Theming

-   `--theme <default|plugin defined theme>`  
    Specify the theme that should be used.
-   `--name <Documentation title>`  
    Set the name of the project that will be used in the header of the template.
-   `--readme <path/to/readme|none>`  
    Path to the readme file that should be displayed on the index page. Pass `none` to disable the index page and start the documentation on the globals page.

#### Miscellaneous

-   `--version`  
    Display the version number of TypeDoc.
-   `--help`  
    Display all TypeDoc options.

Contributing
------------

This project is maintained by a community of developers. Contributions are welcome and appreciated. You can find TypeDoc on GitHub; feel free to open an issue or create a pull request: https://github.com/TypeStrong/typedoc

For more information, read the contribution guide.
