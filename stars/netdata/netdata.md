---
project: netdata
stars: 74306
description: X-Ray Vision for your infrastructure!
url: https://github.com/netdata/netdata
---

### X-Ray Vision for your infrastructure!

#### Every Metric, Every Second. No BS.

  

  
  
  

**Visit the Project's Home Page**

* * *

MENU: **GETTING STARTED** | **HOW IT WORKS** | **FAQ** | **DOCS** | **COMMUNITY** | **CONTRIBUTE** | **LICENSE**

> **Important** 💡  
> People get addicted to Netdata. Once you use it on your systems, **there's no going back!**  

**TL;DR**

Netdata is an open-source, real-time infrastructure monitoring platform designed for instant visibility and proactive troubleshooting across your entire IT environment. It captures every metric, every second, providing detailed insights into systems, containers, applications, and logs without compromising performance or requiring complex setup.

Key Advantages:

-   **Instant Insights**  
    Real-time, per-second metrics and visualizations for rapid problem detection.
-   **Automated and Zero-Configuration**  
    Easy deployment with immediate monitoring—no complex setup needed.
-   **ML-Driven Intelligence**  
    Built-in machine learning detects anomalies, predicts issues, and assists in root-cause analysis automatically.
-   **Highly Efficient**  
    Proven minimal resource usage, exceptional scalability, and best-in-class energy efficiency validated by independent research.
-   **Distributed & Secure**  
    Data stays securely within your infrastructure; no centralization required.

Netdata complements or replaces traditional monitoring tools, offering significant performance and usability advantages over Prometheus, Datadog, Dynatrace, and similar products, while remaining fully compatible and integration-friendly.

Designed for organizations seeking simplified operations, reduced overhead, and cost-effective monitoring solutions, Netdata provides a comprehensive, scalable, and user-friendly approach to observability.

**✨ Key Features**:

-   **Real-Time**
    
    Per-second data collection and real-time processing provides immediate visibility into your infrastructure's behavior.
    
    _**Unique**: Netdata works in a beat and everything happens at this pace. You hit enter on a terminal and a second later you see the result on the dashboard._
    
-   **Zero-Configuration**
    
    Start monitoring in minutes with automatic detection and discovery, fully automated dashboards, and hundreds of pre-configured alerts.
    
    _**Unique**: Netdata auto-discovers everything on the nodes it runs. All kernel technologies, all processes, all applications, all containers, all hardware components. And with its dynamic configuration, any changes can be done via the dashboard._
    
-   **ML-Powered**
    
    Unsupervised anomaly detection and pattern recognition for all metrics, providing advanced correlations and instant root cause analysis.
    
    _**Unique**: Netdata trains multiple true ML models per metric, at the edge, for all metrics!_  
    _**Unique**: A scoring engine identifies correlations across metrics, applications, nodes, services, even cloud providers and data centers!_
    
-   **Long-Term Retention**
    
    High-performance and efficient tiered storage for years of retention and fast query responses.
    
    _**Unique**: Netdata needs ~0.5 per sample on disk, offering superb compression for high-resolution data!_  
    _**Unique**: A tiered storage engine automatically downsamples old data for archiving, long term retention and capacity planning._
    
-   **Advanced Visualization**
    
    Rich, interactive low-latency dashboards for deep system and applications insights and rapid troubleshooting.
    
    _**Unique**: Netdata dashboards allow you to slice and dice any dataset, without learning a query language._  
    _**Unique**: A multi-faceted query engine, analyzes all aspects of your data in one go, and the dashboard provides interactive analysis for all them (NIDL framework)._
    
-   **Extreme Scalability**
    
    Native horizontal scalability, while maintaining performance and ease of use.
    
    _**Unique**: Simple Parent-Child centralization and native horizontal scalability._  
    _**Unique**: Each Netdata can scale to multi-million samples/s with best in-class resources utilization._
    
-   **Complete End-to-End Visibility**
    
    From infrastructure to applications, logs to metrics, hardware to databases, all in one solution.
    
    _**Unique**: Netdata is built to simplify your operations, empower your team, provide clarity and eliminate silos._
    
-   **Edge-Based**
    
    All processing and storage of your data, at your premises, as close to the edge as possible.
    
    _**Unique**: Instead of centralizing observability data, Netdata distributes the code. This provides higher processing capacity by utilizing resources that are usually available and spare, while eliminating most of the cost involved for metrics and logs management._
    

* * *

### The Netdata Ecosystem

> **Note**: This repository contains the Netdata Agent, the open-source core of the Netdata ecosystem. For information about other components, see below.

This three-part architecture enables Netdata to scale seamlessly from single-node deployments to complex multi-cloud environments with thousands of nodes, supporting long-term data retention without compromising performance.

Component

Description

License

Netdata Agent

• The heart of Netdata's monitoring capabilities  
• Handles data collection, storage, querying, ML analysis, exports, and alerts  
• Runs on physical/virtual servers, cloud, Kubernetes, and IoT devices  
• Optimized for zero production impact  
• Core of all observability features

GPL v3+

Netdata Cloud

• Adds enterprise-grade features  
 (user management and RBAC, horizontal scalability,  
  centralized alert management, access from anywhere)  
• Available as SaaS or on-premises  
• Includes free community tier  
• Does not centralize metric storage

Netdata UI

• Powers all dashboards and visualizations  
• Free to use with both Agent and Cloud  
• Included in standard Netdata packages  
• Latest version available via CDN

NCUL1

### Key capabilities of the Netdata Agent

With these capabilities, Netdata Agent provides a powerful, automated monitoring solution that works right out-of-the-box while remaining highly customizable for specific needs.

Capability

Description

Comprehensive Data Collection

• 800+ integrations out of the box  
• Collects metrics from systems, containers, VMs, hardware sensors  
• Supports OpenMetrics exporters, StatsD, and logs  
• OpenTelemetry support coming soon

Performance & Precision

• Per-second data collection  
• Real-time visualization with 1-second latency  
• High-resolution metrics for precise monitoring

Edge-Based ML

• Trains ML models directly at the edge  
• Automatic anomaly detection per metric  
• Pattern recognition based on historical behavior

Advanced Log Management

• Direct systemd-journald and Windows Event Log integrations  
• Tools for log conversion (log2journal, systemd-cat-native)  
• Process logs at the edge - no centralization needed  
• Rich log visualization dashboards

Observability Pipeline

• Build Parent-Child relationships between Agents  
• Create flexible centralization points  
• Control data replication and retention at multiple levels

Automated Visualization

• NIDL (Nodes, Instances, Dimensions & Labels) data model  
• Auto-generated, correlated dashboards  
• Filter and analyze data without query language  
• Free to use, powered by Netdata UI

Smart Alerting

• Hundreds of pre-configured alerts  
• Detect common issues automatically  
• Multiple notification methods  
• Proactive problem detection

Low Maintenance

• Auto-detection of metrics  
• Zero-touch machine learning  
• Easy scalability  
• CI/CD friendly deployment

Open & Extensible

• Modular architecture  
• Easy to extend and customize  
• Integrates with existing monitoring tools  
• Active community ecosystem

### What can be monitored with the Netdata Agent

Netdata monitors all the following:

Component

Linux

FreeBSD

macOS

Windows

**System Resources**  
CPU, Memory and system shared resources

Full

Yes

Yes

Yes

**Storage**  
Disks, Mount points, Filesystems, RAID arrays

Full

Yes

Yes

Yes

**Network**  
Network Interfaces, Protocols, Firewall, etc

Full

Yes

Yes

Yes

**Hardware & Sensors**  
Fans, Temperatures, Controllers, GPUs, etc

Full

Some

Some

Some

**O/S Services**  
Resources, Performance and Status

Yes  
`systemd`

\-

\-

\-

**Processes**  
Resources, Performance, OOM, and more

Yes

Yes

Yes

Yes

System and Application **Logs**

Yes  
`systemd`\-journal

\-

\-

Yes  
`Windows Event Log`, and  
`Event Tracing for Windows`

**Network Connections**  
Live TCP and UDP sockets per PID

Yes

\-

\-

\-

**Containers**  
Docker/containerd, LXC/LXD, Kubernetes, etc

Yes

\-

\-

\-

**VMs** (from the host)  
KVM, qemu, libvirt, Proxmox, etc

Yes  
`cgroups`

\-

\-

Yes  
`Hyper-V`

**Synthetic Checks**  
Test APIs, TCP ports, Ping, Certificates, etc

Yes

Yes

Yes

Yes

**Packaged Applications**  
nginx, apache, postgres, redis, mongodb,  
and hundreds more

Yes

Yes

Yes

Yes

**Cloud Provider Infrastructure**  
AWS, GCP, Azure, and more

Yes

Yes

Yes

Yes

**Custom Applications**  
OpenMetrics, StatsD and soon OpenTelemetry

Yes

Yes

Yes

Yes

When operating on Linux, the Netdata Agent continuously monitors every available kernel feature and all hardware sensors for errors. This covers Intel, AMD, and Nvidia GPUs, PCI Advanced Error Reporting (PCI AER), RAM Error Detection and Correction (RAM EDAC), Intelligent Platform Management Interface (IPMI), S.M.A.R.T. for disks, Intel Running Average Power Limit (Intel RAPL), NVMe disks, as well as fans, power supplies, voltage readings, and more.

* * *

### ⭐ Netdata is the most energy-efficient monitoring tool ⭐

Dec 11, 2023: University of Amsterdam published a study related to the impact of monitoring tools for Docker based systems, aiming to answer 2 questions:

1.  **The impact of monitoring on the energy efficiency of Docker-based systems**
2.  **The impact of monitoring on Docker-based systems?**

-   🚀 Netdata excels in energy efficiency: **"... Netdata is the most energy-efficient tool ..."**, as the study says.
-   🚀 Netdata excels in CPU Usage, RAM Usage and Execution Time, and has a similar impact on Network Traffic as Prometheus.

The study didn’t normalize the results based on the number of metrics collected. Given that Netdata usually collects significantly more metrics than the other tools, Netdata managed to outperform the other tools, while ingesting a much higher number of metrics. Read the full study here.

* * *

### Netdata vs Prometheus 2025 Review

NEW! On the same workload, Netdata uses **1/3rd less CPU**, consumes **1/8th of the RAM**, performes **31 times less disk I/O** and stores **40 times more data** while being up to **22 times faster** in query responses! Read the full 2025 review in our blog.

* * *

   

  
Netdata actively supports and is a member of the Cloud Native Computing Foundation (CNCF)  
   
...and due to your love ❤️, it is one of the most ⭐'d projects in the CNCF landscape!

   

* * *

**You can see Netdata live!**  
**FRANKFURT** | **NEWYORK** | **ATLANTA** | **SANFRANCISCO** | **TORONTO** | **SINGAPORE** | **BANGALORE**  
_We've set up multiple demo clusters around the world, each running with the default configuration and showing real monitoring data._  
_Choose the instance closest to you for the best experience._

* * *

Getting Started
---------------

  

### 1\. **Install Netdata everywhere** ✌️

Netdata can be installed on all Linux, macOS, FreeBSD and Windows systems. We provide binary packages for the most popular operating systems and package managers.

-   Install on Ubuntu, Debian CentOS, Fedora, Suse, Red Hat, Arch, Alpine, Gentoo, even BusyBox.
-   Install with Docker.  
    Netdata is a Verified Publisher on DockerHub and our users enjoy free unlimited DockerHub pulls 😍.
-   Install on macOS 🤘.
-   Install on FreeBSD and pfSense.
-   Install on Windows.
-   Install from source
-   For Kubernetes deployments check here.

Check also the Netdata Deployment Guides to decide how to deploy it in your infrastructure.

By default, you will have immediately available a local dashboard. Netdata starts a web server for its dashboard at port `19999`. Open up your web browser of choice and navigate to `http://NODE:19999`, replacing `NODE` with the IP address or hostname of your Agent. If installed on localhost, you can access it through `http://localhost:19999`.

_Note: the binary packages we provide, install Netdata UI automatically. Netdata UI is closed-source, but free to use with Netdata Agents and Netdata Cloud._

### 2\. **Configure Collectors** 💥

Netdata auto-detects and auto-discovers most operating system data sources and applications. However, many data sources require some manual configuration, usually to allow Netdata to get access to the metrics.

-   For a detailed list of the 800+ collectors available, check this guide.
-   To monitor SNMP devices, check this guide.

### 3\. **Configure Alert Notifications** 🔔

Netdata comes with hundreds of pre-configured alerts that automatically check your metrics immediately after they start getting collected.

Netdata can dispatch alert notifications to multiple third party systems, including: `email`, `Alerta`, `AWS SNS`, `Discord`, `Dynatrace`, `flock`, `gotify`, `IRC`, `Matrix`, `MessageBird`, `Microsoft Teams`, `ntfy`, `OPSgenie`, `PagerDuty`, `Prowl`, `PushBullet`, `PushOver`, `RocketChat`, `Slack`, `SMS tools`, `Syslog`, `Telegram`, `Twilio`.

By default, Netdata will send e-mail notifications if there is a configured MTA on the system.

### 4\. **Configure Netdata Parents** 👪

Optionally, configure one or more Netdata Parents. A Netdata Parent is a Netdata Agent that has been configured to accept streaming connections from other Netdata Agents.

Netdata Parents provide:

-   **Infrastructure level dashboards, at `http://parent.server.ip:19999/`.**  
    
    Each Netdata Agent has an API listening at the TCP port 19999 of each server. When you hit that port with a web browser (e.g. `http://server.ip:19999/`), the Netdata Agent UI is presented. When the Netdata Agent is also a Parent, the UI of the Parent includes data for all nodes that stream metrics to that Parent.
    
-   **Increased retention for all metrics of all your nodes.**  
    
    Each Netdata Agent maintains each own database of metrics. But Parents can be given additional resources to maintain a much longer database than individual Netdata Agents.
    
-   **Central configuration of alerts and dispatch of notifications.**  
    
    Using Netdata Parents, all the alert notifications integrations can be configured only once at the Parent and they can be disabled at the Netdata Agents.
    

You can also use Netdata Parents to:

-   Offload your production systems (the parents run ML, alerts, queries, etc. for all their children)
-   Secure your production systems (the parents accept user connections for all their children)

### 5\. **Connect to Netdata Cloud** ☁️

Sign-in to Netdata Cloud and connect your Netdata Agents and Parents. If you connect your Netdata Parents, there is no need to connect your Netdata Agents. They will be connected via the Parents.

When your Netdata nodes are connected to Netdata Cloud, you can (on top of the above):

-   Access your Netdata Agents from anywhere
-   Access sensitive Netdata Agent features (like "Netdata Functions": processes, systemd-journal)
-   Organize your infra in spaces and Rooms
-   Create, manage, and share **custom dashboards**
-   Invite your team and assign roles to them (Role-Based Access Control)
-   Get infinite horizontal scalability (multiple independent Netdata Agents are viewed as one infra)
-   Configure alerts from the UI
-   Configure data collection from the UI
-   Netdata Mobile App notifications

🤟 Netdata Cloud doesn’t prevent you from using your Netdata Agents and Parents directly, and vice versa.  

👌 Your metrics are still stored in your network when you connect your Netdata Agents and Parents to Netdata Cloud.

* * *

How it works
------------

Netdata is built around a **modular metrics processing pipeline**.

Click to see more details about this pipeline...    

Each Netdata Agent can perform the following functions:

1.  **`COLLECT` metrics from their sources**  
    Uses internal and external plugins to collect data from their sources.
    
    Netdata auto-detects and collects almost everything from the operating system: including CPU, Interrupts, Memory, Disks, Mount Points, Filesystems, Network Stack, Network Interfaces, Containers, VMs, Processes, `systemd` units, Linux Performance Metrics, Linux eBPF, Hardware Sensors, IPMI, and more.
    
    It collects application metrics from applications: PostgreSQL, MySQL/MariaDB, Redis, MongoDB, Nginx, Apache, and hundreds more.
    
    Netdata also collects your custom application metrics by scraping OpenMetrics exporters, or via StatsD.
    
    It can convert web server log files to metrics and apply ML and alerts to them in real-time.
    
    And it also supports synthetic tests / white box tests, so you can ping servers, check API responses, or even check filesystem files and directories to generate metrics, train ML and run alerts and notifications on their status.
    
2.  **`STORE` metrics to a database**  
    Uses database engine plugins to store the collected data, either in memory and/or on disk. We have developed our own `dbengine` for storing the data in a very efficient manner, allowing Netdata to have less than one byte per sample on disk and amazingly fast queries.
    
3.  **`LEARN` the behavior of metrics** (ML)  
    Trains multiple Machine-Learning (ML) models per metric to learn the behavior of each metric individually. Netdata uses the `kmeans` algorithm and creates by default a model per metric per hour, based on the values collected for that metric over the last 6 hours. The trained models are persisted to disk.
    
4.  **`DETECT` anomalies in metrics** (ML)  
    Uses the trained machine learning (ML) models to detect outliers and mark collected samples as **anomalies**. Netdata stores anomaly information together with each sample and also streams it to Netdata Parents so that the anomaly is also available at query time for the whole retention of each metric.
    
5.  **`CHECK` metrics and trigger alert notifications**  
    Uses its configured alerts (you can configure your own) to check the metrics for common issues and uses notification plugins to send alert notifications.
    
6.  **`STREAM` metrics to other Netdata Agents**  
    Push metrics in real-time to Netdata Parents.
    
7.  **`ARCHIVE` metrics to third party databases**  
    Export metrics to industry standard time-series databases, like `Prometheus`, `InfluxDB`, `OpenTSDB`, `Graphite`, etc.
    
8.  **`QUERY` metrics and present dashboards**  
    Provide an API to query the data and present interactive dashboards to users.
    
9.  **`SCORE` metrics to reveal similarities and patterns**  
    Score the metrics according to the given criteria, to find the needle in the haystack.
    

When using Netdata Parents, all the functions of a Netdata Agent (except data collection) can be delegated to Parents to offload production systems.

The core of Netdata is developed in C. We have our own `libnetdata`, that provides:

-   **`DICTIONARY`**  
    A high-performance algorithm to maintain both indexed and ordered pools of structures Netdata needs. It uses JudyHS arrays for indexing, although it is modular: any hashtable or tree can be integrated into it. Despite being in C, dictionaries follow object-oriented programming principles, so there are constructors, destructors, automatic memory management, garbage collection, and more. For more, see here.
    
-   **`ARAL`**  
    ARray ALlocator (ARAL) is used to minimize the system allocations made by Netdata. ARAL is optimized for maximum multithreaded performance. It also allows all structures that use it to be allocated in memory-mapped files (shared memory) instead of RAM. For more, see here.
    
-   **`PROCFILE`**  
    A high-performance `/proc` (but also any) file parser and text tokenizer. It achieves its performance by keeping files open and adjusting its buffers to read the entire file in one call (which is also required by the Linux kernel). For more, see here.
    
-   **`STRING`**  
    A string internet mechanism, for string deduplication and indexing (using JudyHS arrays), optimized for multithreaded usage. For more, see here.
    
-   **`ARL`**  
    Adaptive Resortable List (ARL) is a very fast list iterator, that keeps the expected items on the list in the same order they are found in an input list. So, the first iteration is somewhat slower, but all the following iterations are perfectly aligned for the best performance. For more, see here.
    
-   **`BUFFER`**  
    A flexible text buffer management system that allows Netdata to automatically handle dynamically sized text buffer allocations. The same mechanism is used for generating consistent JSON output by the Netdata APIs. For more, see here.
    
-   **`SPINLOCK`**  
    Like POSIX `MUTEX` and `RWLOCK` but a lot faster, based on atomic operations, with significantly smaller memory impact, while being portable.
    
-   **`PGC`**  
    A caching layer that can be used to cache any kind of time-related data, with automatic indexing (based on a tree of JudyL arrays), memory management, evictions, flushing, pressure management. This is extensively used in `dbengine`. For more, see here.
    

The above, and many more, allow Netdata developers to work on the application fast and with confidence. Most of the business logic in Netdata is a work of mixing the above.

Netdata data collection plugins can be developed in any language. Most of our application collectors though are developed in Go.

FAQ
---

### 🛡️ Is Netdata secure?

Of course, it is! We do our best to ensure it is!

Click to see detailed answer ...    
   

We understand that Netdata is a software piece installed on millions of production systems across the world. So, it is important for us, Netdata to be as secure as possible:

-   We follow the Open Source Security Foundation best practices.
-   We have given great attention to detail when it comes to security design. Check out our security design.
-   Netdata is a popular open-source project and is frequently tested by many security analysts.
-   Check also our security policies and advisories published so far.  

### 🌀 Will Netdata consume significant resources on my servers?

No, it will not! We promise this will be fast!

Click to see detailed answer ...    
   

Although each Netdata Agent is a complete monitoring solution packed into a single application, and despite the fact that Netdata collects **every metric every single second** and trains **multiple ML models** per metric, you will find that Netdata has amazing performance! In many cases, it outperforms other monitoring solutions that have significantly fewer features or far smaller data collection rates.

This is what you should expect:

-   For production systems, each Netdata Agent with default settings (everything enabled, ML, Health, DB) should consume about 5% CPU utilization of one core and about 150 MiB or RAM.
    
    By using a Netdata parent and streaming all metrics to that parent, you can disable ML & health and use an ephemeral DB (like `alloc`) on the children, leading to utilization of about 1% CPU of a single core and 100 MiB of RAM. Of course, these depend on how many metrics are collected.
    
-   For Netdata Parents, for about 1 to 2 million metrics, all collected every second, we suggest a server with 16 cores and 32GB RAM. Less than half of it will be used for data collection and ML. The rest will be available for queries.
    

Netdata has extensive internal instrumentation to help us reveal how the resources consumed are used. All these are available in the "Netdata Monitoring" section of the dashboard. Depending on your use case, there are many options to optimize resource consumption.

Even if you need to run Netdata on extremely weak embedded or IoT systems, you will find that Netdata can be tuned to be very performant.  

### 📜 How much retention can I have?

As much as you need!

Click to see detailed answer ...    
   

Netdata supports **tiering**, to downsample past data and save disk space. With default settings, it has three tiers:

1.  `tier 0`, with high resolution, per-second, data.
2.  `tier 1`, mid-resolution, per minute, data.
3.  `tier 2`, low-resolution, per hour, data.

All tiers are updated in parallel during data collection. Increase the disk space you give to Netdata to get a longer history for your metrics. Tiers are automatically chosen at query time depending on the time frame and the resolution requested.  

### 🚀 Does it scale? I really have a lot of servers!

Netdata is designed to scale and can handle large volumes of data.

Click to see detailed answer ...    
   
Netdata is a distributed monitoring solution. You can scale it to infinity by spreading Netdata Agents across your infrastructure.

With the streaming feature of the Agent, we can support monitoring ephemeral servers but also allow the creation of "monitoring islands" where metrics are aggregated to a few servers (Netdata Parents) for increased retention, or for offloading production systems.

-   ✈️ Netdata Parents provide great vertical scalability, so you can have as big parents as the CPU, RAM and Disk resources you can dedicate to them. In our lab, we constantly stress test Netdata Parents with several million metrics collected per second, to ensure it is reliable, stable, and robust at scale.
    
-   🚀 In addition, Netdata Cloud provides virtually unlimited horizontal scalability. It "merges" all the Netdata parents you have into one unified infrastructure at query time. Netdata Cloud itself is probably the biggest single installation monitoring platform ever created, currently monitoring about 100k online servers with about 10k servers changing state (added/removed) per day!
    

Example: the following chart comes from a single Netdata Parent. As you can see on it, 244 nodes stream to it metrics of about 20k running containers. On this specific chart, there are three dimensions per container, so a total of about 60k time-series queries are executed to present it.  

### 💾 My production servers are very sensitive in disk I/O. Can I use Netdata?

Yes, you can!

Click to see detailed answer ...    
   

The Netdata Agent has been designed to spread disk writes across time. Each metric is flushed to disk every 17 minutes (1000 seconds), but metrics are flushed evenly across time, at an almost constant rate. Also, metrics are packed into bigger blocks we call `extents` and are compressed with ZSTD before saving them, to minimize the number of I/O operations made.

The Netdata Agent also employs direct I/O for all its database operations. By managing its own caches, Netdata avoids overburdening system caches, facilitating a harmonious coexistence with other applications.

Single node Agents (not Parents), should have a constant write rate of about 50 KiB/s or less, with some spikes above that every minute (flushing of tier 1) and higher spikes every hour (flushing of tier 2).

Health Alerts and Machine-Learning run queries to evaluate their expressions and learn from the metrics' patterns. These are also spread over time, so there should be an almost constant read rate too.

To make Netdata not use the disks at all, we suggest the following:

1.  Use database mode `alloc` or `ram` to disable writing metric data to disk.
2.  Configure streaming to push in real-time all metrics to a Netdata Parent. The Netdata Parent will maintain metrics on disk for this node.
3.  Disable ML and health on this node. The Netdata Parent will do them for this node.
4.  Use the Netdata Parent to access the dashboard.

Using the above, the Netdata Agent on your production system will not use a disk.  

### 🤨 How is Netdata different from a Prometheus and Grafana setup?

Netdata is a "ready to use" monitoring solution. Prometheus and Grafana are tools to build your own monitoring solution.

Netdata is also a lot faster, requires significantly fewer resources and puts almost no stress on the server it runs. For a performance comparison check this blog.

Click to see detailed answer ...    
   

First, we have to say that Prometheus as a time-series database and Grafana as a visualizer are excellent tools for what they do.

However, we believe that such a setup is missing a key element: A Prometheus and Grafana setup assumes that you know everything about the metrics you collect, and you understand deeply how they’re structured, they should be queried and visualized.

In reality, this setup has a lot of problems. The vast number of technologies, operating systems, and applications we use in our modern stacks makes it impossible for any single person to know and understand everything about anything. We get testimonials regularly from Netdata users across the biggest enterprises, that Netdata manages to reveal issues, anomalies and problems they weren’t aware of, and they didn't even have the means to find or troubleshoot.

So, the biggest difference of Netdata to Prometheus, and Grafana, is that we decided that the tool needs to have a much better understanding of the components, the applications, and the metrics it monitors.

-   When compared to Prometheus, Netdata needs for each metric much more than just a name, some labels, and a value over time. A metric in Netdata is a structured entity that correlates with other metrics in a certain way and has specific attributes that depict how it should be organized, treated, queried, and visualized. We call this the NIDL (Nodes, Instances, Dimensions, Labels) framework.
    
    Maintaining such an index is a challenge: first, because the raw metrics collected do not provide this information, so we have to add it, and second because we need to maintain this index for the lifetime of each metric, which with our current database retention, it is usually more than a year.
    
    At the same time, Netdata provides better retention than Prometheus due to database tiering, scales easier than Prometheus due to streaming, supports anomaly detection, and it has a metrics scoring engine to find the needle in the haystack when needed.
    
-   When compared to Grafana, Netdata is fully automated. Grafana has more customization capabilities than Netdata, but Netdata presents fully functional dashboards by itself, and most importantly, it gives you the means to understand, analyze, filter, slice and dice the data without the need for you to edit queries or be aware of any peculiarities the underlying metrics may have.
    
    Furthermore, to help you when you need to find the needle in the haystack, Netdata has advanced troubleshooting tools provided by the Netdata metrics scoring engine, that allows it to score metrics based on their anomaly rate, their differences or similarities for any given time frame.
    

Still, if you’re already familiar with Prometheus and Grafana, Netdata integrates nicely with them, and we have reports from users who use Netdata with Prometheus and Grafana in production.  

### 🤨 How is Netdata different from DataDog, New Relic, Dynatrace, X SaaS Provider?

With Netdata your data are always on-prem and your metrics are always high-resolution.

Click to see detailed answer ...    
   

Most commercial monitoring providers face a significant challenge: they centralize all metrics to their infrastructure, and this is, inevitably, expensive. It leads them to one or more of the following:

1.  be unrealistically expensive
2.  limit the number of metrics they collect
3.  limit the resolution of the metrics they collect

As a result, they try to find a balance: collect the least possible data, but collect enough to have something useful out of it.

We, at Netdata, see monitoring in a completely different way: **monitoring systems should be built bottom-up and be rich in insights**, so we focus on each component individually to collect, store, check and visualize everything related to each of them, and we make sure that all components are monitored. Each metric is important.

This is why Netdata trains multiple machine-learning models per metric, based exclusively on their own past (no sampling of data, no sharing of trained models) to detect anomalies based on the specific use case and workload each component is used.

This is also why Netdata alerts are attached to components (instances) and are configured with dynamic thresholds and rolling windows, instead of static values.

The distributed nature of Netdata helps scale this approach: your data is spread inside your infrastructure, as close to the edge as possible. Netdata is not one data lane. Each Netdata Agent is a data lane, and all of them together build a massive distributed metrics processing pipeline that ensures all your infrastructure components and applications are monitored and operating as they should.  

### 🤨 How is Netdata different from Nagios, Icinga, Zabbix, etc.?

Netdata offers real-time, comprehensive monitoring and the ability to monitor everything without any custom configuration required.

Click to see detailed answer ...    
   

While Nagios, Icinga, Zabbix, and other similar tools are powerful and highly customizable, they can be complex to set up and manage. Their flexibility often comes at the cost of ease-of-use, especially for users who aren’t systems administrators or don’t have extensive experience with these tools. Additionally, these tools generally require you to know what you want to monitor in advance and configure it explicitly.

Netdata, on the other hand, takes a different approach. It provides a "ready to use" monitoring solution with a focus on simplicity and comprehensiveness. It automatically detects and starts monitoring many different system metrics and applications out-of-the-box, without any need for custom configuration.

In comparison to these traditional monitoring tools, Netdata:

-   Provides real-time, high-resolution metrics, as opposed to the often minute-level granularity that tools like Nagios, Icinga, and Zabbix provide.
    
-   Automatically generates meaningful, organized, and interactive visualizations of the collected data. Unlike other tools, where you have to manually create and organize graphs and dashboards, Netdata takes care of this for you.
    
-   Applies machine learning to each individual metric to detect anomalies, providing more insightful and relevant alerts than static thresholds.
    
-   Designed to be distributed, so your data is spread inside your infrastructure, as close to the edge as possible. This approach is more scalable and avoids the potential bottleneck of a single centralized server.
    
-   Has a more modern and user-friendly interface, allowing anyone, not just experienced administrators, to easily assess the health and performance of their systems.
    

Even if you're already using Nagios, Icinga, Zabbix, or similar tools, you can use Netdata alongside them to augment your existing monitoring capabilities with real-time insights and user-friendly dashboards.  

### 😳 I feel overwhelmed by the amount of information in Netdata. What should I do?

Netdata is designed to provide comprehensive insights, but we understand that the richness of information might sometimes feel overwhelming. Here are some tips on how to navigate and use Netdata effectively...

Click to see detailed answer ...    
   

Netdata is indeed a very comprehensive monitoring tool. It's designed to provide you with as much information as possible about your system and applications, so that you can understand and address any issues that arise. However, we understand that the sheer amount of data can sometimes be overwhelming.

Here are some suggestions on how to manage and navigate this wealth of information:

1.  **Start with the Metrics Dashboard**  
    Netdata's Metrics Dashboard provides a high-level summary of your system's status. We have added summary tiles on almost every section, you reveal the information that is more important. This is a great place to start, as it can help you identify any major issues or trends at a glance.
    
2.  **Use the Search Feature**  
    If you're looking for specific information, you can use the search feature to find the relevant metrics or charts. This can help you avoid scrolling through all the data.
    
3.  **Customize your Dashboards**  
    Netdata allows you to create custom dashboards, which can help you focus on the metrics that are most important to you. Sign-in to Netdata and there you can have your custom dashboards. (coming soon to the Agent dashboard too)
    
4.  **Leverage Netdata's Anomaly Detection**  
    Netdata uses machine learning to detect anomalies in your metrics. This can help you identify potential issues before they become major problems. We have added an `AR` button above the dashboard table of contents to reveal the anomaly rate per section so that you can spot what could need your attention.
    
5.  **Take Advantage of Netdata's Documentation and Blogs**  
    Netdata has extensive documentation that can help you understand the different metrics and how to interpret them. You can also find tutorials, guides, and best practices there.
    

Remember, it's not necessary to understand every single metric or chart right away. Netdata is a powerful tool, and it can take some time to fully explore and understand all of its features. Start with the basics and gradually delve into more complex metrics as you become more comfortable with the tool.  

### ☁️ Do I have to subscribe to Netdata Cloud?

Netdata Cloud delivers the full suite of features and functionality that Netdata offers, including a free community tier.

While our default onboarding process encourages users to take advantage of Netdata Cloud, including a complimentary one-month trial of our full business product, it is not mandatory. Users can bypass this process entirely and still use the Netdata Agents along with the Netdata UI, without the need to sign up for Netdata Cloud.

Click to see detailed answer ...    
   

The Netdata Agent dashboard and the Netdata Cloud dashboard are the same. Still, Netdata Cloud provides additional features that the Netdata Agent is not capable of. These include:

1.  Access your infrastructure from anywhere.
2.  Have SSO to protect sensitive features.
3.  Customizable (custom dashboards and other settings are persisted when you’re signed in to Netdata Cloud)
4.  Configuration of Alerts and Data Collection from the UI
5.  Security (Role-Based Access Control).
6.  Horizontal Scalability ("blend" multiple independent parents in one uniform infrastructure)
7.  Central Dispatch of Alert Notifications (even when multiple independent parents are involved)
8.  Mobile App for Alert Notifications

We encourage you to support Netdata by buying a Netdata Cloud subscription. A successful Netdata is a Netdata that evolves and gets improved to provide simpler, faster and easier monitoring for all of us.

For organizations that need a fully on-prem solution, we provide Netdata Cloud for on-prem installation. Contact us for more information.  

### 🔎 What does the anonymous telemetry collected by Netdata entail?

Your privacy is our utmost priority. As part of our commitment to improving Netdata, we rely on anonymous telemetry data from our users who choose to leave it enabled. This data greatly informs our decision-making processes and contributes to the future evolution of Netdata.

Should you wish to disable telemetry, instructions for doing so are provided in our installation guides.

Click to see detailed answer ...    
   

Netdata is in a constant state of growth and evolution. The decisions that guide this development are ideally rooted in data. By analyzing anonymous telemetry data, we can answer questions such as "What features are being used frequently?", "How do we prioritize between potential new features?" and "What elements of Netdata are most important to our users?"

By leaving anonymous telemetry enabled, users indirectly contribute to shaping Netdata's roadmap, providing invaluable information that helps us prioritize our efforts for the project and the community.

We are aware that for privacy or regulatory reasons, not all environments can allow telemetry. To cater to this, we’ve simplified the process of disabling telemetry:

-   During installation, you can append `--disable-telemetry` to our `kickstart.sh` script, or
-   Create the file `/etc/netdata/.opt-out-from-anonymous-statistics` and then restart Netdata.

These steps will disable the anonymous telemetry for your Netdata installation.

Please note, even with telemetry disabled, Netdata still requires a Netdata Registry for alert notifications' Call To Action (CTA) functionality. When you click an alert notification, it redirects you to the Netdata Registry, which then directs your web browser to the specific Netdata Agent that issued the alert for further troubleshooting. The Netdata Registry learns the URLs of your Agents when you visit their dashboards.

Any Netdata Agent can act as a Netdata Registry. Designate one Netdata Agent as your Registry, read more here.  

### 😏 Who uses Netdata?

Netdata is a widely adopted project...

Click to see detailed answer ...    
   

Browse the Netdata stargazers on GitHub to discover users from renowned companies and enterprises, such as ABN AMRO Bank, AMD, Amazon, Baidu, Booking.com, Cisco, Delta, Facebook, Google, IBM, Intel, Logitech, Netflix, Nokia, Qualcomm, Realtek Semiconductor Corp, Redhat, Riot Games, SAP, Samsung, Unity, Valve, and many others.

Netdata also enjoys significant usage in academia, with notable institutions including New York University, Columbia University, New Jersey University, Seoul National University, University College London, among several others.

And, Netdata is also used by many governmental organizations worldwide.

In a nutshell, Netdata proves invaluable for:

-   **Infrastructure intensive organizations**  
    Such as hosting/cloud providers and companies with hundreds or thousands of nodes, who require a high-resolution, real-time monitoring solution for a comprehensive view of all their components and applications.
    
-   **Technology operators**  
    Those in need of a standardized, comprehensive solution for round-the-clock operations. Netdata not only facilitates operational automation and provides controlled access for their operations engineers, but also enhances skill development over time.
    
-   **Technology startups**  
    Who seek a feature-rich monitoring solution from the get-go.
    
-   **Freelancers**  
    Who seek a simple, efficient and straightforward solution without sacrificing performance and outcomes.
    
-   **Professional SysAdmins and DevOps**  
    Who appreciate the fine details and understand the value of holistic monitoring from the ground up.
    
-   **Everyone else**  
    All of us, who are tired of the inefficiency in the monitoring industry and would love a refreshing change and a breath of fresh air. 🙂  

### 🌐 Is Netdata open-source?

The **Netdata Agent** is open-source, but the **overall Netdata ecosystem** is a hybrid solution, combining open-source and closed-source components.

Click to see detailed answer ...    
   

Open-source is about sharing intellectual property with the world, and at Netdata, we embrace this philosophy wholeheartedly.

The **Netdata Agent**, the core of our ecosystem and the engine behind all our observability features, is fully open-source. Licensed under GPLv3+, the Netdata Agent represents our commitment to open-sourcing innovation in a wide array of observability technologies, including data collection, database design, query engines, observability data modeling, machine learning and unsupervised anomaly detection, high-performance edge computing, real-time monitoring, and more.

**The Netdata Agent is our gift to the world**, ensuring that the cutting-edge advancements we've developed are freely accessible to everyone.

However, as a privately funded company, we also need to monetize our open-source software to demonstrate product-market fit and sustain our growth.

Traditionally, open-source projects have often used the open-core model, where a basic version of the software is open-source, and additional features are reserved for a commercial, closed-source version. This approach can limit access to advanced innovations, as most of these remain closed-source.

At Netdata, we take a slightly different path. We don't create a separate enterprise version of our product. Instead, all users - both commercial and non-commercial - use the same Netdata Agent, ensuring that all of our observability innovations are always open source.

To experience the full capabilities of the Netdata ecosystem, users need to combine the open-source components with our closed-source offerings. The complete product still remains free to use.

The closed-source components include:

-   **Netdata UI**: This is closed-source but free to use with the Netdata Agents and Netdata Cloud. It’s also publicly available via a CDN.
-   **Netdata Cloud**: A commercial product available both as an on-premises installation and as a SaaS solution, with a free community tier.

By balancing open-source and closed-source components, we ensure that all users have access to our innovations while sustaining our ability to grow and innovate as a company.  

### 💰 What is your monetization strategy?

Netdata generates revenue through subscriptions to advanced features of Netdata Cloud and sales of on-premise and private versions of Netdata Cloud.

Click to see detailed answer ...    
   

Netdata generates revenue from these activities:

1.  **Netdata Cloud Subscriptions**  
    Direct funding for our project's vision comes from users subscribing to Netdata Cloud's advanced features.
    
2.  **Netdata Cloud On-Prem or Private**  
    Purchasing the on-premises or private versions of Netdata Cloud supports our financial growth.
    

Our Open-Source Community and the free access to Netdata Cloud, contribute to Netdata in the following ways:

-   **Netdata Cloud Community Use**  
    The free usage of Netdata Cloud demonstrates its market relevance. While this doesn't generate revenue, it reinforces trust among new users and aids in securing appropriate project funding.
    
-   **User Feedback**  
    Feedback, especially issues and bug reports, is invaluable. It steers us towards a more resilient and efficient product. This, too, isn't a revenue source but is pivotal for our project's evolution.
    
-   **Anonymous Telemetry Insights**  
    Users who keep anonymous telemetry enabled, help us make data informed decisions on refining and enhancing Netdata. This isn't a revenue stream, but knowing which features are used and how, contributes in building a better product for everyone.
    

We don't monetize, directly or indirectly, users' or "device heuristics" data. Any data collected from community members is exclusively used for the purposes stated above.

Netdata grows financially when technology intensive organizations and operators need - due to regulatory or business requirements - the entire Netdata suite on-prem or private, bundled with top-tier support. It is a win-win case for all parties involved: these companies get a battle tested, robust and reliable solution, while the broader community that helps us build this product enjoys it at no cost.  

📖 Documentation
----------------

Netdata's documentation is available at **Netdata Learn**.

This site also hosts a number of guides to help newer users better understand how to collect metrics, troubleshoot via charts, export to external databases, and more.

🎉 Community
------------

Netdata is an inclusive open-source project and community. Please read our Code of Conduct.

Join the Netdata community:

-   Chat with us and other community members on Discord.
-   Start a discussion on GitHub discussions.
-   Open a topic to our community forums.

> **Meet Up** 🧑‍🤝‍🧑🧑‍🤝‍🧑🧑‍🤝‍🧑  
> The Netdata team and community members have regular online meetups.  
> **You are welcome to join us!** Click here for the schedule.

You can also find Netdata on:  
Twitter | YouTube | Reddit | LinkedIn | StackShare | Product Hunt | Repology | Facebook

🙏 Contribute
-------------

Contributions are essential to the success of open-source projects. In other words, we need your help to keep Netdata great!

What is a contribution? All the following are highly valuable to Netdata:

1.  **Let us know of the best practices you believe should be standardized**  
    Netdata should out-of-the-box detect as many infrastructure issues as possible. By sharing your knowledge and experiences, you help us build a monitoring solution that has baked into it all the best-practices about infrastructure monitoring.
    
2.  **Let us know if Netdata is not perfect for your use case**  
    We aim to support as many use cases as possible and your feedback can be invaluable. Open a GitHub issue, or start a GitHub discussion about it, to discuss how you want to use Netdata and what you need.
    
    Although we can't implement everything imaginable, we try to prioritize development on use-cases that are common to our community, are in the same direction we want Netdata to evolve and are aligned with our roadmap.
    
3.  **Support other community members**  
    Join our community on GitHub, Discord, and Reddit. Generally, Netdata is relatively easy to set up and configure, but still people may need a little push in the right direction to use it effectively. Supporting other members is a great contribution by itself!
    
4.  **Add or improve integrations you need**  
    Integrations tend to be easier and simpler to develop. If you would like to contribute your code to Netdata, we suggest that you start with the integrations you need, which Netdata doesn’t currently support.
    

General information about contributions:

-   Check our Security Policy.
-   Found a bug? Open a GitHub issue.
-   Read our Contributing Guide, which contains all the information you need to contribute to Netdata, such as improving our documentation, engaging in the community, and developing new features. We've made it as frictionless as possible, but if you need help, just ping us on our community forums!

Package maintainers should read the guide on building Netdata from source for instructions on building each Netdata component from the source and preparing a package.

License
-------

The Netdata ecosystem consists of three key parts:

-   **Netdata Agent**: The heart of the Netdata ecosystem, the Netdata Agent is an open-source tool that must be installed on all systems monitored by Netdata. It offers a wide range of essential features, including data collection via various plugins, an embedded high-performance time-series database (dbengine), unsupervised anomaly detection powered by edge-trained machine learning, alerting and notifications, as well as query and scoring engines with associated APIs. Additionally, it supports exporting data to third-party monitoring systems, among other capabilities.
    
    The Netdata Agent is released under the GPLv3+ license and redistributes several other open-source tools and libraries, which are listed in the Netdata Agent third-party licenses.
    
-   **Netdata Cloud**: A commercial, closed-source component, Netdata Cloud enhances the capabilities of the open-source Netdata Agent by providing horizontal scalability, centralized alert notification dispatch (including a mobile app), user management, role-based access control, and other enterprise-grade features. It is available both as a SaaS solution and for on-premises deployment, with a free-to-use community tier also offered.
    
-   **Netdata UI**: The Netdata UI is closed-source, and handles all visualization and dashboard functionalities related to metrics, logs and other collected data, as well as the central configuration and management of the Netdata ecosystem. It serves both the Netdata Agent and Netdata Cloud. The Netdata UI is distributed in binary form with the Netdata Agent and is publicly accessible via a CDN, licensed under the Netdata Cloud UI License 1 (NCUL1). It integrates third-party open-source components, detailed in the Netdata UI third-party licenses.
    

The binary installation packages provided by Netdata include the Netdata Agent and the Netdata UI. Since the Netdata Agent is open-source, it is frequently packaged by third parties (e.g., Linux Distributions) excluding the closed-source components (Netdata UI is not included). While their packages can still be useful in providing the necessary back-ends and the APIs of a fully functional monitoring solution, we recommend using the installation packages we provide to experience the full feature set of Netdata.
