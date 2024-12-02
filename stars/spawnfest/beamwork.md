---
project: beamwork
stars: 28
description: SpawnFest 2020 - Your description here..!
url: https://github.com/spawnfest/beamwork
---

Phoenix Response Time Graphs
============================

✔️ Very very low overhead (powered by DogSketch)

✔️ Cluster-wide performance charts (not just a single node!)

✔️ No external dependencies (runs 100% in-BEAM)

✔️ Accurate p50, p90, p99 and throughput

✔️ Linear and Log scale

Linear Scale
------------

Log Scale
---------

Caveat
======

To our knowledge nobody is running this in production yet. BUT, in theory, it should be able to track an obscene number of requests without slowing down your system. I suspect it will handle at least 100k requests per second per node with ease. Give it a try and let us know!

Installation
============

1.  Add `spotlight` to your list of dependencies
2.  Configure LiveView (if you haven't already)
3.  Add spotlight to your Phoenix router

1\. Add `spotlight` to your list of dependencies
------------------------------------------------

Add to `mix.exs`:

def deps do
  \[
    {:spotlight, "~> 0.1.0"}
  \]
end

Then run `mix deps.get`.

2\. Configure LiveView (if you haven't already)
-----------------------------------------------

3\. Add `spotlight` to your Phoenix router
------------------------------------------

\# lib/my\_app\_web/router.ex
use MyAppWeb, :router
import SpotlightWeb.Router

...

scope "/" do
  pipe\_through :browser
  spotlight("/spotlight")
end

We heavily recommend that you put Spotlight behind some kind of authentication before adding it to your production servers.
