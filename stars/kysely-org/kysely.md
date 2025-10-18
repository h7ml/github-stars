---
project: kysely
stars: 12834
description: A type-safe TypeScript SQL query builder
url: https://github.com/kysely-org/kysely
---

###### Join the discussion ⠀⠀⠀⠀⠀⠀⠀

###### Get started

& more!

Kysely
======

Kysely (pronounce “Key-Seh-Lee”) is a type-safe and autocompletion-friendly TypeScript SQL query builder. Inspired by Knex.js. Mainly developed for Node.js but also runs on all other JavaScript environments like Deno, Bun, Cloudflare Workers and web browsers.

Kysely makes sure you only refer to tables and columns that are visible to the part of the query you're writing. The result type only has the selected columns with correct types and aliases. As an added bonus you get autocompletion for all that stuff.

As shown in the gif above, through the pure magic of modern TypeScript, Kysely is even able to parse the alias given to `pet.name` and add the `pet_name` column to the result row type. Kysely is able to infer column names, aliases and types from selected subqueries, joined subqueries, `with` statements and pretty much anything you can think of.

Of course there are cases where things cannot be typed at compile time, and Kysely offers escape hatches for these situations. See the sql template tag and the DynamicModule for more info.

All API documentation is written in the typing files and you can simply hover over the module, class or method you're using to see it in your IDE. The same documentation is also hosted here.

If you start using Kysely and can't find something you'd want to use, please open an issue or join our Discord server.

Getting started
===============

Please visit our documentation site kysely.dev to get started. We also have a comprehensive API documentation hosted here, but you can access the same documentation in your IDE by hovering over a class/method/property/whatever.

Core team
=========

Project leads
-------------

Responsible for project direction, API design, maintenance, code reviews, community support, documentation, and working on some of the most impactful/challenging things.

  
Sami Koskimäki  
(the author)

  
Igal Klebanov  
(the dynamo)

Honorable mentions
------------------

People who had special impact on the project and its growth.

  
Fernando Hurtado  
(1st docs)

  
Wirekang  
(playground)

  
Tim Griesser  
(Knex)

  
Robin Blomberg  
(codegen)

  
Shoubhit Dash  
(prisma idea)

  
Valtýr Örn Kjartansson  
(prisma impl)

  
Dax Raad  
(early adopter)

  
Theo Browne  
(early promoter)

  
Lee Robinson  
(early promoter)

  
Ethan Resnick  
(timely feedback)

  
Harminder Virk  
(dope writeup)

  
Johan Eliasson  
(promoter/educator)

All contributors
----------------

  
Want to contribute? Check out our contribution guidelines.
