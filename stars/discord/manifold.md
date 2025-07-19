---
project: manifold
stars: 1805
description: Fast batch message passing between nodes for Erlang/Elixir.
url: https://github.com/discord/manifold
---

Manifold
========

Erlang and Elixir make it very easy to send messages between processes even across the network, but there are a few pitfalls.

-   Sending a message to many PIDs across the network also copies the message across the network that many times.
-   Send calls cost about 70 µs/op so doing them in a loop eventually gets too expensive.

Discord runs a single `GenServer` per Discord server and some of these ~100,000 PIDs connected to them from many different Erlang nodes. Increasingly we noticed some of them getting behind on processing their message queues and the culprit was the cost of 70 µs per `send/2` call multiplied by connected sessions. How could we solve this?

Inspired by a blog post about boosting performance of message passing between nodes, Manifold was born. Manifold distributes the work of sending messages to the remote nodes of the PIDs, which guarantees that the sending processes at most only calls `send/2` equal to the number of involved remote nodes. Manifold does this by first grouping PIDs by their remote node and then sending to `Manifold.Partitioner` on each of those nodes. The partitioner then consistently hashes the PIDs using `:erlang.phash2/2`, groups them by number of cores, sends to child workers, and finally those workers send to the actual PIDs. This ensures the partitioner does not get overloaded and still provides the linearizability guaranteed by `send/2`.

The results were great! We observed packets/sec drop by half immediately after deploying. The Discord servers in question also were finally able to keep up with their message queues.

Usage
-----

Add it to `mix.exs`

defp deps do
  \[{:manifold, "~> 1.0"}\]
end

Then just use it like the normal `send/2` except it can also take a list of PIDs.

Manifold.send(self(), :hello)
Manifold.send(\[self(), self()\], :hello)

### Options

When using Manifold there are two performance options you can choose to enable.

#### pack\_mode

By default Manifold will send the message using vanilla External Term Format. If `pack_mode` is not specified or is set to `nil` or `:etf` then this mode will be used.

When messages are very large `pack_mode` can be set to `:binary` and this will cause Manifold to ensure that the term is only converted into External Term Format once. The encoding will happen in the sending process (either the calling process or a `Manifold.Sender`, see `send_mode` for additional details) and will

The `:binary` optimization works best with large and deeply nested messages that are being sent to PIDs across multiple nodes. Without the optimization, a message sent to N nodes will have to be translated into External Term Format N times. With large data structures, this operation can be expensive. With the optimization enabled, the encoding into binary happens once and then over distribution each sending process only needs to transmit the binary.

To send using the binary pack mode, just add the `pack_mode` argument

Manifold.send(self(), :hello, pack\_mode: :binary)

#### send\_mode

By default Manifold will send the message over the network from the caller process. If `send_mode` is not specified then the default behavior of sending from the caller process will be used.

When messages are very large, `send_mode` can be set to `:offload` which offloads the send from the calling process to a pool of `Manifold.Sender` processes. To maintain the linearizability guaranteed by `send/2`, the same calling process always offloads the work to the same `Manifold.Sender` process. The size of the `Manifold.Sender` pool is configurable.

This send mode is optional because its benefits are workload dependent. The optimization works best when the cost of sending a message to a local process < the cost of sending a message over distribution. This is most common for messages that are very large in size. For some workloads, it might degrade overall performance. Use with caution.

Caution: To maintain the linearizability guaranteed by `send/2`, do not mix calls to Manifold with and without offloading. Mixed use of the two different send modes to the same set of receiving nodes would break the linearizability guarantee.

To use the `:offload` send mode, make sure the `Manifold.Sender` pool size is appropriate for the workload:

config :manifold, senders: <size\>

Then:

Manifold.send(self(), :hello, send\_mode: :offload)

### Configuration

Manifold takes a single configuration option, which sets the module it dispatches to actually call send. The default is GenServer. To set this variable, add the following to your `config.exs`:

config :manifold, gen\_module: MyGenModule

In the above instance, `MyGenModule` must define a `cast/2` function that matches the types of `GenServer.cast`.

License
-------

Manifold is released under the MIT License. Check LICENSE file for more information.
