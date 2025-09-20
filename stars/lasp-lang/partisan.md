---
project: partisan
stars: 986
description: High-performance, high-scalability distributed computing for the BEAM.
url: https://github.com/lasp-lang/partisan
---

  

Partisan
========

Partisan is a scalable and flexible, TCP-based membership system and distribution layer for the BEAM. It bypasses the use of Distributed Erlang for manual connection management via TCP, and has several pluggable backends for different deployment scenarios.

Partisan is a runtime system that enables greater scalability and reduced latency for distributed actor applications.

-   Partisan improves scalability by allowing the application developer to specialize the overlay network to the application’s communication patterns.
-   Partisan achieves lower latency by leveraging several predominately automatic optimizations that result in the efficient scheduling of messages.
-   Bring Your Own Overlay - Partisan exposes an API for users to implement their own overlays; application developers must simply implement the `membership_strategy` interface for handling messages. Partisan automatically uses this membership strategy for processing incoming and outgoing messages to the system – the application developer only needs to handle internal state transitions and supplying the system with an updated list of members. Partisan automatically sets up required connections, serializes and deserializes messages, performs failure detection, and message forwarding. This makes it possible to implement protocols with very little code; our implementation of the full-mesh membership protocol is 152 LOC.
-   Partisan is the first distributed actor system to expose this level of control to the application developer, improving the performance of existing actor application and enabling new types of actor applications.

Getting started
---------------

See the documentation for Partisan at hex.pm.

Alternatively you can build the documentation yourself locally using `make docs`. The resulting documentation will be found in the `docs` directory, just open the `index.html` file with your preferred web browser.

Why do we need Partisan?
------------------------

Erlang/OTP, specifically distributed erlang (a.k.a. `disterl`), uses a full-mesh overlay network. This means that in the worst case scenario all nodes are connected-to and communicate-with all other nodes in the system.

**Failure detector**. These nodes send periodic heartbeat messages to their connected nodes and deem a node "failed" or "unreachable" when it misses a certain number of heartbeat messages i.e. the `net_tick_time` setting in `disterl`.

Due to this heartbeating and other issues in the way Erlang handles certain internal data structures, Erlang systems present a limit to the number of connected nodes that depending on the application goes between 60 and 200 nodes.

Also, Erlang conflates control plane messages with application messages on the same TCP/IP connection and uses a single TCP/IP connection between two nodes, making it liable to the Head-of-line blocking issue. This also leads to congestion and contention that further affects latency.

This model might scale well for datacenter deployments, where low latency can be assumed, but not for geo-distributed deployments, where latency is non-uniform and can show wide variance.

Partisan was also designed to handle failures:

-   Message omission
-   Message reordering, this can happen in Erlang during reconnections
-   State loss
-   Bit flips
-   Message corruption
-   Faulty failure detectors
-   Etc.

Partisan features
-----------------

Partisan was designed to increase scalability, reduce latency and improve failure detection for Erlang/BEAM distributed applications.

-   Scalability
    -   Provides several overlays that are configurable at runtime
        -   `partisan_pluggable_peer_service_manager`: full mesh with TCP-based failure detection. All nodes maintain active connections to all other nodes in the system using one or more TCP connections.
        -   `partisan_hyparview_peer_service_manager.`: modified implementation of the HyParView protocol, peer-to-peer, designed for high scale, high churn environments. A hybrid partial view membership protocol, with TCP-based failure detection.
        -   `partisan_client_server_peer_service_manager.`: star topology, where clients communicate with servers, and servers communicate with other servers.
        -   `partisan_static_peer_service_manager`: static membership, where connections are explicitly made between nodes
    -   Specialised to particular application communication patterns
    -   Doesn't alter application behaviour
-   Reduce latency
    -   Increasing parallelism - by configuring the number of TCP/IP connections between nodes (named channels).
    -   Pushing background and maintenance traffic to other communication channels - to avoid the Head-of-line blocking due to background activity
    -   Leveraging monotonicity - so that you can do load shedding more possible.
        -   Monotonic channels drop messages when state is increasing on the channel to reduce load and transmission of redundation information. Ideal for growing monotonic hash rings, objects designated with vector clock, CRDTs, etc.
-   Failure detection
    -   Performed using TCP/IP
    -   Connections are verified at each gossip round
    -   Reliable delivery and stronger ordering
    -   Fault-injection
-   Erlang-like API and OTP compliance
    -   Partisan offers re-implementations of `gen_server` and `gen_statem`.
    -   Monitoring: Partisan offers an API similar to the modules `erlang` and `net_kernel` for monitoring nodes and remote processes. Notice this currently only works for `partisan_pluggable_peer_service_manager` backend.
-   Other
    -   On join, gossip is performed immediately, instead of having to wait for the next gossip round.
    -   Single node testing, facilitated by a `disterl` control channel for figuring out which ports the peer service is operating at.

Requirements
------------

-   Erlang/OTP 24+

Who is using Partisan
---------------------

### Projects

-   Bondy
-   Erleans
-   PlumDB

### Organizations and People

-   Christopher Meiklejohn's Blog
-   Leapsight

Reference
---------

### Academic Papers

-   Partisan: Enabling Real-World Protocol Evaluation - ApPLIED '18: Proceedings of the 2018 Workshop on Advanced Tools, Programming Languages, and PLatforms for Implementing and Evaluating Algorithms for Distributed systems, Christopher Meiklejohn
-   Partisan: Enabling Cloud-Scale Erlang Applications, Christopher Meiklejohn, Heather Miller
-   Partisan: Scaling the Distributed Actor Runtime - 2019 USENIX Annual Technical Conference, Christopher S. Meiklejohn and Heather Miller, Carnegie Mellon University; Peter Alvaro, UC Santa Cruz
-   HyParView: a membership protocol for reliable gossip-based broadcast, João Leitão, José Pereira, Luís Rodrigues
-   X-BOT: A Protocol for Resilient Optimization of Unstructured Overlay Networks, João Leitão, João Pedro Marques, José Pereira, Luís Rodrigues

### Presentations

-   Rethinking the Language Runtime for Scale - Erlang User Conference 2016, Christopher S. Meiklejohn
-   Partisan: Scaling the Distributed Actor Runtime - 2019 USENIX Annual Technical Conference, Christopher S. Meiklejohn
-   Partisan: testable, high performance, large scale distributed Erlang - Code BEAM SF 2019, Christopher S. Meiklejohn
-   Distributed Erlang: From Datacenter Applications to Planetary Scale Applications, Christopher Meiklejohn.
