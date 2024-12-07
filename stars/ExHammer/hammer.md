---
project: hammer
stars: 762
description: An Elixir rate-limiter with pluggable backends
url: https://github.com/ExHammer/hammer
---

Hammer
======

**Hammer** is a rate-limiter for Elixir with pluggable storage backends. Hammer enables users to set limits on actions performed within specified time intervals, applying per-user or global limits on API requests, file uploads, and more.

* * *

Note

This README is for the unreleased master branch, please reference the official documentation on hexdocs for the latest stable release.

* * *

Installation
------------

Hammer is available in Hex. Install by adding `:hammer` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:hammer, "~> 7.0"}
  \]
end

Default Algorithm
-----------------

By default, Hammer uses a **fixed window counter** to track actions within set time windows, resetting the count at the start of each new window. For example, with a limit of 10 uploads per minute, a user could upload up to 10 files between 12:00:00 and 12:00:59, and up to 10 more between 12:01:00 and 12:01:59. Notice that the user can upload 20 videos in a second if the uploads are timed at the window edges. If this is an issue, it can be worked around with a "bursty" counter which can be implemented with the current API by making two checks, one for the original interval with the total limit, and one for a shorter interval with a fraction of the limit. That would smooth out the number of requests allowed.

Core Concepts
-------------

-   **Limit:** Maximum number of actions allowed in a window.
-   **Scale:** Duration of the time window (in milliseconds).
-   **Key:** Unique identifier (e.g., user ID) to scope the rate limiting.

Example Usage
-------------

defmodule MyApp.RateLimit do
  use Hammer, backend: :ets
end

MyApp.RateLimit.start\_link()

user\_id \= 42
key \= "upload\_video:#{user\_id}"
scale \= :timer.minutes(1)
limit \= 3

case MyApp.RateLimit.hit(key, scale, limit) do
  {:allow, \_count} \->
    \# upload the video
    :ok

  {:deny, retry\_after} \->
    \# deny the request
    {:error, :rate\_limit, \_message \= "try again in #{retry\_after}ms"}
end

Available Backends
------------------

-   Hammer.ETS (default, can be distributed)
-   Hammer.Redis
-   Hammer.Mnesia

Acknowledgements
----------------

Hammer was originally inspired by the ExRated library, by grempe.

License
-------

Copyright (c) 2023 June Kelly

This library is MIT licensed. See the LICENSE for details.
