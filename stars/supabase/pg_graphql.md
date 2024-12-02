---
project: pg_graphql
stars: 2918
description: GraphQL support for PostgreSQL 
url: https://github.com/supabase/pg_graphql
---

`pg_graphql`
============

* * *

**Documentation**: https://supabase.github.io/pg\_graphql

**Source Code**: https://github.com/supabase/pg\_graphql

* * *

`pg_graphql` adds GraphQL support to your PostgreSQL database.

-   **Performant**
-   **Consistent**
-   **Serverless**
-   **Open Source**

### Overview

`pg_graphql` reflects a GraphQL schema from the existing SQL schema.

The extension keeps schema translation and query resolution neatly contained on your database server. This enables any programming language that can connect to PostgreSQL to query the database via GraphQL with no additional servers, processes, or libraries.

### TL;DR

The SQL schema

create table account(
    id serial primary key,
    email varchar(255) not null,
    created\_at timestamp not null,
    updated\_at timestamp not null
);

create table blog(
    id serial primary key,
    owner\_id integer not null references account(id),
    name varchar(255) not null,
    description varchar(255),
    created\_at timestamp not null,
    updated\_at timestamp not null
);

create type blog\_post\_status as enum ('PENDING', 'RELEASED');

create table blog\_post(
    id uuid not null default uuid\_generate\_v4() primary key,
    blog\_id integer not null references blog(id),
    title varchar(255) not null,
    body varchar(10000),
    status blog\_post\_status not null,
    created\_at timestamp not null,
    updated\_at timestamp not null
);

Translates into a GraphQL schema displayed below.

Each table receives an entrypoint in the top level `Query` type that is a pageable collection with relationships defined by its foreign keys. Tables similarly recieve entrypoints in the `Mutation` schema that enable bulk operations for insert, update, and delete.

### Contributing

Please refer to the contributing docs for more information.
