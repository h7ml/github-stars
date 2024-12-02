---
project: schism
stars: 72
description: Partition testing tool for elixir
url: https://github.com/elixir-toniq/schism
---

Schism
======

Schism provides a simple api for testing partitions between BEAM nodes.

Documentation: https://hexdocs.pm/schism.

Installation
------------

If available in Hex, the package can be installed by adding `schism` to your list of dependencies in `mix.exs`:

def deps do
  \[
    {:schism, "~> 1.0", only: \[:dev, :test\]}
  \]
end

Usage
-----

Let's say that we have 5 nodes and we want to test what happens when they disconnect from each other. We can use schism like so:

test "netsplits" do
  \[n1, n2, n3, n4, n5\] \= nodes

  \# Partition our nodes
  Schism.partition(\[n1, n3\])
  Schism.partition(\[n4\])
  Schism.partition(\[n2, n5\])

  \# Test some stuff...

  \# Heal our partitions
  Schism.heal(\[n1, n3\])
  Schism.heal(\[n2, n4, n5\])
end

This api is useful for testing and development in conjunction with tools like local cluster and propcheck.

It is not recommended that you use this in production.

Things Schism doesn't do
------------------------

Schism's reason for existing is to quickly and easily test netsplits between BEAMS and it uses a rudimentary trick with cookies to achieve this goal. This is great for quickly testing your system against faults.

But because of Schism's simple nature it should not be considered a replacement for a more robust suite of tests. It _does not_ test failed TCP connections, interleaving of messages, race-conditions, clock skew, corruption, or any of the other issues you will see in a distributed system.
