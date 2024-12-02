---
project: local-cluster
stars: 226
description: Easy local cluster creation for Elixir to aid in unit testing
url: https://github.com/whitfin/local-cluster
---

LocalCluster
============

This library is designed to assist in testing distributed states in Elixir which require a number of local nodes.

The aim is to provide a small set of functions which hide the complexity of spawning local nodes, as well as providing the ease of cleaning up the started nodes. The entire library is simple shimming around the Erlang APIs for dealing with distributed nodes, As some of it is non-obvious, and as I need this code for several projects, I span it out as a smaller project.

Installation
------------

To install it for your project, you can pull it directly from Hex. Rather than use the version shown below, you can use the the latest version from Hex (shown at the top of this README).

def deps do
  \[{:local\_cluster, "~> 2.0", only: \[:test\]}\]
end

Documentation and examples can be found on Hexdocs as they're updated automatically alongside each release. Note that you should only use the `:test` flag in your dependency if you're not using it for other environments.

Setup
-----

To configure your test suites for cluster testing, you need to run through a one-time setup to change some stuff in your `test_helper.exs`. This is required to avoid some potential issues with your node name changing after your application tree has already stated. This also reduces some bloat due to having `LocalCluster.start/0` in most test cases. The snippet below can be used as a sample helper file. Make sure to change the application name to match your application name.

\# start the current node as a manager
:ok \= LocalCluster.start()

\# start your application tree manually
Application.ensure\_all\_started(:my\_app)

\# run all tests!
ExUnit.start()

You will also need to pass the `--no-start` flag to `mix test`. Fortunately this is easy enough, as you can add an alias in your `mix.exs` to do this automatically:

def project do
  \[
    \# ...
    aliases: \[
      test: "test --no-start"
    \]
    \# ...
  \]
end

This library itself uses this setup, so you can copy/paste as needed or use as an example when integrating into your own codebase. Note that you must have ensured that `epmd` has been started before using this lib; typically with `epmd -daemon`.

Usage
-----

As mentioned above, the API is deliberately _tiny_ to make it easier to use this library when testing. Below is an example of using this library to spawn a set of child nodes for testing:

defmodule MyTest do
  use ExUnit.Case

  test "creates and stops child nodes" do
    \# create a new cluster of 3 nodes
    {:ok, cluster} \= LocalCluster.start\_link(3)

    \# fetch the list of nodes contained in the cluster
    {:ok, \[node1, node2, node3\]} \= LocalCluster.nodes(cluster)

    \# check that all nodes respond
    assert Node.ping(node1) \== :pong
    assert Node.ping(node2) \== :pong
    assert Node.ping(node3) \== :pong

    \# stop a single node in our cluster
    :ok \= LocalCluster.stop(cluster, node1)

    \# check that node does not respond
    assert Node.ping(node1) \== :pang
    assert Node.ping(node2) \== :pong
    assert Node.ping(node3) \== :pong

    \# stop the entire cluster
    :ok \= LocalCluster.stop(cluster)

    \# check that no nodes respond
    assert Node.ping(node1) \== :pang
    assert Node.ping(node2) \== :pang
    assert Node.ping(node3) \== :pang
  end
end

After calling `start_link/2` you will receive a process identifier which can be used to fetch a list of spawned nodes to communicate with via RPC (or whatever you like). Although these nodes are automatically cleaned up when the calling process dies, you can manually stop nodes to test disconnection within a test.

Options
-------

There are various options supported when creating a cluster, here are most of them with a few notes about what they're for and what they do:

LocalCluster.start\_link(3, \[
  \# Allows the caller to determine startup order of bundled applications,
  \# and allows you to exclude applications from the startup sequence. If
  \# this option is not provided, the default behaviour will be to match
  \# the startup sequence of the local node. Each of these applications
  \# will be loaded with all dependencies via \`Application.ensure\_all\_started/2\`.
  applications: \[
    :start\_this\_application,
    :and\_then\_this\_one
  \],

  \# Similar to the above; if you need to override the application environment
  \# inherited by your cluster nodes, you can use the \`:environment\` option to
  \# merge values \_over\_ the environment inside the started nodes.
  environment: \[
    my\_app: \[
      port: 9999
    \]
  \],

  \# Enables loading any additional files onto the remote notes, by providing
  \# an absolute file path to compile inside the cluster. This is necessary if
  \# you wish to spawn tasks onto the cluster from inside your test code, as
  \# test code is not loaded automatically.
  files: \[
    \_\_ENV\_\_.file
  \],

  \# Enables naming and registration of the cluster PID. If this value is
  \# not provided the cluster is reachable only by PID.
  name: :my\_cluster,

  \# Enables a custom node name prefix for members of the cluster. If this
  \# is not provided it will default to the value of \`:name\`. If that flag
  \# is also not provided, a random string will be generated.
  prefix: ""
\])

Migration to v2
---------------

If you previously used this module on the v1.x line, a few things have changed within the API to make it more consistent and Elixir-y (hopefully). The following examples should show how you can map over to the new API easily:

\# starting a cluster in v1.x
nodes \= LocalCluster.start\_nodes("my-cluster", 3, \[
  \# options...
\])

\# stopping a cluster in v1.x
LocalCluster.stop\_nodes(nodes)

\# starting a cluster in v2.x
{:ok, cluster} \= LocalCluster.start\_link(3, \[
  prefix: "my\_cluster"
\])
{:ok, nodes} \= LocalCluster.nodes(cluster)

\# stopping a cluster in v2.x
LocalCluster.stop(cluster)

Hopefully even though this is a major bump it's not very disruptive. Unfortunately there was no reliable way to keep the old API, as frequent use in `ExUnit` meant that we can't use the process dictionary to store the cluster name.
