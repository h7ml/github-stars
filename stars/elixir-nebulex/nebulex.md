---
project: nebulex
stars: 1288
description: In-memory and distributed caching toolkit for Elixir.
url: https://github.com/elixir-nebulex/nebulex
---

Nebulex 🌌
==========

> In-memory and distributed caching toolkit for Elixir.

Nebulex provides support for transparently adding caching into an existing Elixir application. Similar to Ecto, the caching abstraction allows consistent use of various caching solutions with minimal impact on the code.

Nebulex cache abstraction shields developers from directly dealing with the underlying caching implementations, such as Redis or even other Elixir cache implementations like Cachex. Additionally, it provides totally out-of-box features such as cache usage patterns, declarative annotation-based caching, and distributed cache topologies, among others.

See the getting started guide and the online documentation for more information.

Usage
-----

You need to add `nebulex` as a dependency to your `mix.exs` file. However, in the case you want to use an external (a non built-in adapter) cache adapter, you also have to add the proper dependency to your `mix.exs` file.

The supported caches and their adapters are:

Cache

Nebulex Adapter

Dependency

Generational Local Cache

Nebulex.Adapters.Local

Built-In

Partitioned

Nebulex.Adapters.Partitioned

Built-In

Replicated

Nebulex.Adapters.Replicated

Built-In

Multilevel

Nebulex.Adapters.Multilevel

Built-In

Nil (special adapter that disables the cache)

Nebulex.Adapters.Nil

Built-In

Cachex

Nebulex.Adapters.Cachex

nebulex\_adapters\_cachex

Redis

NebulexRedisAdapter

nebulex\_redis\_adapter

Distributed with Horde

Nebulex.Adapters.Horde

nebulex\_adapters\_horde

Multilevel with cluster broadcasting

NebulexLocalMultilevelAdapter

nebulex\_local\_multilevel\_adapter

Ecto Postgres table

Nebulex.Adapters.Ecto

nebulex\_adapters\_ecto

For example, if you want to use a built-in cache, add to your `mix.exs` file:

def deps do
  \[
    {:nebulex, "~> 2.6"},
    {:shards, "~> 1.1"},     #=> When using :shards as backend
    {:decorator, "~> 1.4"},  #=> When using Caching Annotations
    {:telemetry, "~> 1.0"}   #=> When using the Telemetry events (Nebulex stats)
  \]
end

In order to give more flexibility and fetch only needed dependencies, Nebulex makes all dependencies optional. For example:

-   For intensive workloads, you may want to use `:shards` as the backend for the local adapter and having partitioned tables. In such a case, you have to add `:shards` to the dependency list.
    
-   For enabling the usage of declarative annotation-based caching via decorators, you have to add `:decorator` to the dependency list.
    
-   For enabling Telemetry events to be dispatched when using Nebulex, you have to add `:telemetry` to the dependency list. See telemetry guide.
    
-   If you want to use an external adapter (e.g: Cachex or Redis adapter), you have to add the adapter dependency too.
    

Then run `mix deps.get` in your shell to fetch the dependencies. If you want to use another cache adapter, just choose the proper dependency from the table above.

Finally, in the cache definition, you will need to specify the `adapter:` respective to the chosen dependency. For the local built-in cache it is:

defmodule MyApp.Cache do
  use Nebulex.Cache,
    otp\_app: :my\_app,
    adapter: Nebulex.Adapters.Local
end

Quickstart example
------------------

Assuming you are using `Ecto` and you want to use declarative caching:

\# In the config/config.exs file
config :my\_app, MyApp.PartitionedCache,
  primary: \[
    gc\_interval: :timer.hours(12),
    backend: :shards,
    partitions: 2
  \]

\# Defining a Cache with a partitioned topology
defmodule MyApp.PartitionedCache do
  use Nebulex.Cache,
    otp\_app: :my\_app,
    adapter: Nebulex.Adapters.Partitioned,
    primary\_storage\_adapter: Nebulex.Adapters.Local
end

\# Some Ecto schema
defmodule MyApp.Accounts.User do
  use Ecto.Schema

  schema "users" do
    field(:username, :string)
    field(:password, :string)
    field(:role, :string)
  end

  def changeset(user, attrs) do
    user
    |> cast(attrs, \[:username, :password, :role\])
    |> validate\_required(\[:username, :password, :role\])
  end
end

\# The Accounts context
defmodule MyApp.Accounts do
  use Nebulex.Caching

  alias MyApp.Accounts.User
  alias MyApp.PartitionedCache, as: Cache
  alias MyApp.Repo

  @ttl :timer.hours(1)

  @decorate cacheable(cache: Cache, key: {User, id}, opts: \[ttl: @ttl\])
  def get\_user!(id) do
    Repo.get!(User, id)
  end

  @decorate cacheable(cache: Cache, key: {User, username}, opts: \[ttl: @ttl\])
  def get\_user\_by\_username(username) do
    Repo.get\_by(User, \[username: username\])
  end

  @decorate cache\_put(
              cache: Cache,
              keys: \[{User, user.id}, {User, user.username}\],
              match: &match\_update/1,
              opts: \[ttl: @ttl\]
            )
  def update\_user(%User{} \= user, attrs) do
    user
    |> User.changeset(attrs)
    |> Repo.update()
  end

  @decorate cache\_evict(
              cache: Cache,
              keys: \[{User, user.id}, {User, user.username}\]
            )
  def delete\_user(%User{} \= user) do
    Repo.delete(user)
  end

  def create\_user(attrs \\\\ %{}) do
    %User{}
    |> User.changeset(attrs)
    |> Repo.insert()
  end

  defp match\_update({:ok, value}), do: {true, value}
  defp match\_update({:error, \_}), do: false
end

See more Nebulex examples.

Important links
---------------

-   Getting Started
-   Documentation
-   Cache Usage Patterns
-   Instrumenting the Cache with Telemetry
-   Migrating to v2.x
-   Examples

Testing
-------

Testing by default spawns nodes internally for distributed tests. To run tests that do not require clustering, exclude the `clustered` tag:

```
$ mix test --exclude clustered
```

If you have issues running the clustered tests try running:

```
$ epmd -daemon
```

before running the tests.

Benchmarks
----------

Nebulex provides a set of basic benchmark tests using the library benchee, and they are located within the directory benchmarks.

To run a benchmark test you have to run:

```
$ MIX_ENV=test mix run benchmarks/{BENCH_TEST_FILE}
```

Where `BENCH_TEST_FILE` can be any of:

-   `local_with_ets_bench.exs`: benchmark for the local adapter using `:ets` backend.
-   `local_with_shards_bench.exs`: benchmark for the local adapter using `:shards` backend.
-   `partitioned_bench.exs`: benchmark for the partitioned adapter.

For example, for running the benchmark for the local adapter using `:shards` backend:

```
$ MIX_ENV=test mix run benchmarks/local_with_shards_bench.exs
```

Additionally, you can also run performance tests using `:basho_bench`. See nebulex\_bench example for more information.

Contributing
------------

Contributions to Nebulex are very welcome and appreciated!

Use the issue tracker for bug reports or feature requests. Open a pull request when you are ready to contribute.

When submitting a pull request you should not update the CHANGELOG.md, and also make sure you test your changes thoroughly, include unit tests alongside new or changed code.

Before to submit a PR it is highly recommended to run `mix check` and ensure all checks run successfully.

Copyright and License
---------------------

Copyright (c) 2017, Carlos Bolaños.

Nebulex source code is licensed under the MIT License.
