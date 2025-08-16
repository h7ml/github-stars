---
project: emqx
stars: 15123
description: The most scalable and reliable MQTT broker for AI, IoT, IIoT and connected vehicles
url: https://github.com/emqx/emqx
---

EMQX
====

EMQX is the world's most scalable and reliable MQTT platform, designed for high-performance, reliable, and secure IoT data infrastructure. It supports MQTT 5.0, 3.1.1, and 3.1, as well as other protocols like MQTT-SN, CoAP, LwM2M, and MQTT over QUIC. EMQX enables you to connect millions of IoT devices, process and route messages in real time, and integrate with a wide range of backend data systems. It's ideal for applications in AI, IoT, Industrial IoT (IIoT), connected vehicles, smart cities, and beyond.

**Starting from v5.9.0, EMQX has unified all features from the previous Open Source and Enterprise editions into a single, powerful offering with the Business Source License (BSL) 1.1.**

If you want to understand why we made the change, please read this blog post.

Please go to the License section for more details about BSL 1.1.

Key Features
------------

EMQX delivers a powerful set of capabilities for modern connected systems:

### Comprehensive Protocol Support

-   Full MQTT v5.0, v3.1.1, and v3.1 support.
-   MQTT over QUIC: Leverage the benefits of QUIC for faster connection establishment, reduced head-of-line blocking, and seamless connection migration.
-   Support for other IoT protocols like LwM2M, CoAP, MQTT-SN, and more through gateways.

### Massive Scalability & High Availability

-   Connect 100M+ of concurrent MQTT clients with a single cluster.
-   Process millions of messages per second with sub-millisecond latency.
-   Masterless clustering for high availability and fault tolerance.
-   Seamless global communication with EMQX Cluster Linking.

### Powerful Rule Engine & Data Integration

-   SQL-based Rule Engine to process, transform, enrich, and filter in-flight data.
-   Seamless data bridging and integration with 50+ cloud services and enterprise systems, including:
    -   **Message Queues**: Kafka, RabbitMQ, Pulsar, RocketMQ, etc.
    -   **Databases**: PostgreSQL, MySQL, MongoDB, Redis, ClickHouse, InfluxDB, etc.
    -   **Cloud Services**: AWS Kinesis, GCP Pub/Sub, Azure Event, Confluent Cloud, and more.
-   Webhook support for easy integration with custom services.

### Flow Designer

-   Drag‑and‑drop canvas to orchestrate real‑time data pipelines with zero code, using nodes for rules, integrations, and AI tasks.

### Smart Data Hub

-   Schema Registry: Define, store, and manage data schemas to ensure consistency.
-   Schema Validation: Validate incoming data against registered schemas to maintain data integrity.
-   Message Transformation: Convert data between different formats and structures to facilitate seamless integration.

### AI Processing & Integration:

-   Native AI processing capabilities for IoT data streams.
-   Integration with popular AI services.
-   Support for AI-driven decision making at the edge or in the cloud.

### Robust Security

-   Secure connections with TLS/SSL and WSS.
-   Flexible authentication mechanisms: username/password, JWT, PSK, X.509 certificates, etc.
-   Granular access control with ACLs.
-   Integration with external authentication databases (LDAP, SQL, Redis).

### Advanced Observability & Management:

-   Comprehensive monitoring with Prometheus, Grafana, Datadog, and OpenTelemetry.
-   Detailed logging and tracing capabilities.
-   User-friendly Dashboard for cluster overview and management.
-   Rich HTTP API for automation and third-party integration.

### Extensibility

-   Plugin architecture for extending functionality.
-   Hooks for customizing behavior at various points in the message lifecycle.

### Unified Experience:

-   With the BSL 1.1 license (from v5.9.0), all features, including those previously exclusive to the enterprise edition, are available to all developers.

Quick Start
-----------

### Try EMQX Cloud

The simplest way to set up EMQX is to create a managed deployment with EMQX Cloud. You can try EMQX Cloud for free.

-   EMQX Serverless
-   EMQX Dedicated
-   EMQX BYOC

### Run a single node using Docker

```
docker run -d --name emqx \
  -p 1883:1883 -p 8083:8083 -p 8084:8084 \
  -p 8883:8883 -p 18083:18083 \
  emqx/emqx-enterprise:latest
```

Next, please follow the Install EMQX Using Docker guide for further instructions.

### Run EMQX cluster on Kubernetes

Please refer to the official EMQX Operator documentation for details.

### Download EMQX

If you prefer to install and manage EMQX yourself, you can download the latest version from the official site.

For more installation options, see the EMQX installation documentation

Documentation
-------------

-   EMQX self-hosted: docs.emqx.com/en/emqx/latest.
-   EMQX Cloud: docs.emqx.com/en/cloud/latest.

Contributing
------------

Please see our contributing guide.

For more organised improvement proposals, you can send pull requests to EIP.

Community
---------

-   Follow us on: X, YouTube.
-   Ask Questions: GitHub Discussions or EMQX Community Slack.
-   Report Bugs: GitHub Issues.
-   Discord: EMQX Discord Server.

Resources
---------

-   EMQX Website: emqx.com
-   EMQX Blog: emqx.com/en/blog
-   MQTT Client Programming: Tutorials
-   MQTT SDKs: Popular SDKs
-   MQTT Tool: MQTTX

Build From Source
-----------------

The master branch tracks the latest version 5.

-   EMQX 5.4 and newer can be built with OTP 25 or 26
-   EMQX 5.9+ can be built with OTP 27

git clone https://github.com/emqx/emqx.git
cd emqx
make
\_build/emqx-enterprise/rel/emqx/bin/emqx console

For 4.2 or earlier versions, release has to be built from another repo.

git clone https://github.com/emqx/emqx-rel.git
cd emqx-rel
make
\_build/emqx/rel/emqx/bin/emqx console

Rolling Upgrade Paths Since 5.0
-------------------------------

Below is the matrix supported rolling upgrade paths since 5.0.

-   Version numbers end with `?` e.g. `6.0?` are future releases.
-   ✅: Supported, or planed to support.
-   ⚠️: May experience issues, require manual resolution.
-   ❌: Not supported.
-   🔄: Tentative support for future versions.

See release notes for detailed information.

From\\To

5.1

5.2

5.3

5.4

5.5

5.6

5.7

5.8

5.9

5.10?

6.0?

5.0

✅

✅

✅

✅

✅

✅

✅

✅

⚠️\[1\]

❌\[2\]

❌\[2\]

5.1

✅

✅

✅

✅

✅

✅

✅

✅

✅

❌\[2\]

❌\[2\]

5.2

✅

✅

✅

✅

✅

✅

✅

✅

❌\[2\]

❌\[2\]

5.3

✅

✅

✅

✅

✅

✅

✅

❌\[2\]

❌\[2\]

5.4

✅

✅

⚠️

✅

✅

✅

✅

🔄

5.5

✅

⚠️

✅

✅

✅

✅

🔄

5.6

✅

✅

✅

✅

✅

🔄

5.7

✅

✅

✅

✅

🔄

5.8

✅

✅

✅

🔄

5.9

✅

✅

✅

5.10?

✅

✅

6.0?

✅

-   \[1\] Old limiter configs should be deleted from the config files (`etc/emqx.conf` and `data/configs/cluster-override.conf`) before upgrade.
-   \[2\] Pre-5.4 routing table will be deleted. Upgrade to 5.9 first, then perform a full-cluster restart (not rolling) before upgrade to 5.10 or later.

License
-------

### Important License Update

Effective from version **5.9.0**, EMQX has transitioned from Apache 2.0 to the Business Source License (BSL) 1.1.

### License Requirement for Clustering (v5.9.0+)

Starting with EMQX v5.9.0, due to the license change and the unification of all features, deploying an EMQX cluster (more than 1 node) requires a license file to be loaded.

Please refer to the following resources for details on license acquisition, application, and the specifics of the BSL 1.1.

-   **News**: EMQX Adopts Business Source License
-   **Blog**: Adopting Business Source License to Accelerate MQTT and AI Innovation
-   **FAQ**: EMQX License FAQ
