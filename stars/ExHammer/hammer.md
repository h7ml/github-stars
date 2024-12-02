---
project: hammer
stars: 758
description: An Elixir rate-limiter with pluggable backends
url: https://github.com/ExHammer/hammer
---

Hammer
======

A rate-limiter for Elixir, with pluggable storage backends.

Hammer-Plug
-----------

We have a helper-library to make adding rate-limiting to your Phoenix (or other plug-based) application even easier: Hammer.Plug.

Installation
------------

Hammer is available in Hex, the package can be installed by adding `:hammer` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:hammer, "~> 6.1"}
  \]
end

Documentation
-------------

On HexDocs: https://hexdocs.pm/hammer/frontpage.html

The Tutorial is an especially good place to start.

Usage
-----

Example:

defmodule MyApp.VideoUpload do

  def upload(video\_data, user\_id) do
    case Hammer.check\_rate("upload\_video:#{user\_id}", 60\_000, 5) do
      {:allow, \_count} \->
        \# upload the video, somehow
      {:deny, \_limit} \-\>
        \# deny the request
    end
  end

end

The `Hammer` module provides the following functions:

-   `check_rate(id, scale_ms, limit)`
-   `check_rate_inc(id, scale_ms, limit, increment)`
-   `inspect_bucket(id, scale_ms, limit)`
-   `delete_buckets(id)`

Backends are configured via `Mix.Config`:

config :hammer,
  backend: {Hammer.Backend.ETS, \[expiry\_ms: 60\_000 \* 60 \* 4,
                                 cleanup\_interval\_ms: 60\_000 \* 10\]}

See the Tutorial for more.

See the Hammer Testbed app for an example of using Hammer in a Phoenix application.

Available Backends
------------------

-   Hammer.Backend.ETS (provided with Hammer for testing and dev purposes, not very good for production use)
-   Hammer.Backend.Redis
-   Hammer.Backend.Mnesia (beta)

Getting Help
------------

If you're having trouble, either open an issue on this repo

Acknowledgements
----------------

Hammer was inspired by the ExRated library, by grempe.

License
-------

Copyright (c) 2023 June Kelly

This library is MIT licensed. See the LICENSE for details.
