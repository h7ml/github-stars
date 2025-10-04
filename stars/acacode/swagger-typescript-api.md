---
project: swagger-typescript-api
stars: 3922
description: Generate the API Client for Fetch or Axios from an OpenAPI Specification
url: https://github.com/acacode/swagger-typescript-api
---

Swagger TypeScript API
======================

-   Support for OpenAPI 3.0, 2.0, JSON and YAML
-   Generate the API Client for Fetch or Axios from an OpenAPI Specification

Any questions you can ask here: https://github.com/acacode/swagger-typescript-api/discussions

Examples
--------

All examples you can find here: https://github.com/acacode/swagger-typescript-api/tree/main/tests

Usage
-----

You can use this package in two ways:

### CLI

npx swagger-typescript-api generate --path ./swagger.json

Or install locally in your project:

npm install --save-dev swagger-typescript-api
npx swagger-typescript-api generate --path ./swagger.json

### Library

npm install --save-dev swagger-typescript-api

import \* as path from "node:path";
import \* as process from "node:process";
import { generateApi } from "swagger-typescript-api";

await generateApi({ input: path.resolve(process.cwd(), "./swagger.json") });

For more detailed configuration options, please consult the documentation.

Mass media
----------

-   5 Lessons learned about swagger-typescript-api
-   Why Swagger schemes are needed in frontend development ?
-   Migration en douceur vers TypeScript (French)
-   swagger-typescript-api usage (Japanese)

License
-------

Licensed under the MIT License.
