---
project: bus_car
stars: 17
description: A super simple Elasticsearch tool with its own DSL and Ecto-like use.
url: https://github.com/elbow-jason/bus_car
---

BusCar
======

**A super simple Elasticsearch tool with its own DSL and Ecto-like usage.**

Usage
-----

Make the Repo

defmodule Example.Repo do
  use BusCar.Repo, otp\_app: :some\_example
end

Make a Mapping

defmodule Example.Doge do
  use BusCar.Document

  document "animal", "dog" do
    property :name, :string
    property :age,  :integer

    timestamps
  end

end

Get all the Models (aliased names see `.iex.exs` for example)

iex\> Repo.all(Doge)
\[
  %Example.Doge{\_version: 1, age: 26, id: "33", inserted\_at: "2016-09-26T02:34:20.187264Z", name: "Moe Moe", updated\_at: "2016-09-26T02:34:20.187264Z"},
  %Example.Doge{\_version: 1, age: 10, id: "AVdkWj0\_-SwwFG-cHjcZ", inserted\_at: "2016-09-26T02:36:58.044176Z", name: "Dora", updated\_at: "2016-09-26T02:36:58.044176Z"}
\]

Insert a few Models

iex\> Repo.insert(%Doge{name: "Daisy May", age: 18})
%Example.Doge{\_version: 1, age: 18, id: "AVdkXSuf-SwwFG-cHjcd", inserted\_at: "2016-09-26T02:40:10.140185Z", name: "Daisy May", updated\_at: "2016-09-26T02:40:10.140185Z"}

iex\> Repo.insert(%Doge{id: 10, name: "Punky", age: 35})
%Example.Doge{\_version: 1, age: 35, id: "10", inserted\_at: "2016-09-26T02:50:21.290414Z", name: "Punky", updated\_at: "2016-09-26T02:50:21.290414Z"}

Go Bananas (Young Adult Doges only)

iex\> Repo.search(Doge, \[:query, :bool, :must, :range, :age, :gte, 18, :lt, 30\])
\[
  %Example.Doge{\_version: nil, age: 26, id: "33", inserted\_at: "2016-09-26T02:34:20.187264Z", name: "Moe Moe", updated\_at: "2016-09-26T02:34:20.187264Z"},
  %Example.Doge{\_version: nil, age: 18, id: "AVdkXSuf-SwwFG-cHjcd", inserted\_at: "2016-09-26T02:40:10.140185Z", name: "Daisy May", updated\_at: "2016-09-26T02:40:10.140185Z"}
\]

Installation
------------

If available in Hex, the package can be installed as:

1.  Add `bus_car` to your list of dependencies in `mix.exs`:

def deps do
  \[{:bus\_car, "~> 0.2.13"}\]
end

Features/Todos
--------------

-   Customizable Config
-   Bool Dsl
-   ConstantScore Dsl
-   Exists Dsl
-   Filter Dsl
-   Match Dsl
-   Query Dsl
-   MustNot Dsl
-   Must Dsl
-   Nested Dsl
-   Prefix Dsl
-   Query Dsl
-   Range Dsl
-   Should Dsl
-   Term Dsl
-   Document to DSL to Requests pipeline
-   Ecto-ish Interface
-   Make sure Repo uses `:otp_app` keyword arg
-   Request Tests
-   Api Tests
-   Repo Tests
-   Docs
-   Mappings Tests
-   Github Repo for Example Project and Advanced Examples
-   Optimistic "Locking" on update
-   Full Functional Tests
-   Geo Dsl
-   MoreLikeThis Query
-   Upsert
-   Hex.pm
-   DB Connection Pooling?
-   Extract BusCar DSL into its own Repo
