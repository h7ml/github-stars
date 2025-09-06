---
project: oceanbase
stars: 9455
description: The Fastest Distributed Database for Transactional, Analytical, and  AI Workloads. Welcome to our community: https://discord.gg/74cF8vbNEs
url: https://github.com/oceanbase/oceanbase
---

English | 中文版 | 日本語版

**OceanBase Database** is a distributed relational database. It is developed entirely by Ant Group. The OceanBase Database is built on a common server cluster. Based on the Paxos protocol and its distributed structure, the OceanBase Database provides high availability and linear scalability. The OceanBase Database is not dependent on specific hardware architectures. It also supports vector database functionality, enabling efficient vector search for AI and large-scale retrieval scenarios.

Key features
============

-   **Vector Search**: Supports vector indexing and efficient queries, making it ideal for AI applications, recommendation systems, and semantic search, providing high throughput and low-latency vector search capabilities.
-   **Transparent Scalability**: 1,500 nodes, PB data and a trillion rows of records in one cluster.
-   **Ultra-fast Performance**: TPC-C 707 million tmpC and TPC-H 15.26 million QphH @30000GB.
-   **Cost Efficiency**: saves 70%–90% of storage costs.
-   **Real-time Analytics**: supports HTAP without additional cost.
-   **Continuous Availability**: RPO = 0(zero data loss) and RTO < 8s(recovery time)
-   **MySQL Compatible**: easily migrated from MySQL database.

See also key features for more details.

Quick start
===========

See also Quick experience or Quick Start (Simplified Chinese) for more details.

🔥 Start with all-in-one
------------------------

You can quickly deploy a stand-alone OceanBase Database to experience with the following commands:

**Note**: Linux Only

# download and install all-in-one package (internet connection is required)
bash -c "$(curl -s https://obbusiness-private.oss-cn-shanghai.aliyuncs.com/download-center/opensource/oceanbase-all-in-one/installer.sh)"
source ~/.oceanbase-all-in-one/bin/env.sh

# quickly deploy OceanBase database
obd demo

🐳 Start with docker
--------------------

**Note**: We provide images on dockerhub, quay.io and ghcr.io. If you have problems pulling images from dockerhub, please try the other two registries.

1.  Start an OceanBase Database instance:
    
    # Deploy a mini standalone instance.
    docker run -p 2881:2881 --name oceanbase-ce -e MODE=mini -d oceanbase/oceanbase-ce
    
    # Deploy a mini standalone instance using image from quay.io.
    # docker run -p 2881:2881 --name oceanbase-ce -e MODE=mini -d quay.io/oceanbase/oceanbase-ce
    
    # Deploy a mini standalone instance using image from ghcr.io.
    # docker run -p 2881:2881 --name oceanbase-ce -e MODE=mini -d ghcr.io/oceanbase/oceanbase-ce
    
2.  Connect to the OceanBase Database instance:
    
    docker exec -it oceanbase-ce obclient -h127.0.0.1 -P2881 -uroot # Connect to the root user of the sys tenant.
    

See also Docker Readme for more details.

☸️ Start with Kubernetes
------------------------

You can deploy and manage OceanBase Database instance in kubernetes cluster with ob-operator quickly. Refer to the document Quick Start for ob-operator to see details.

👨‍💻 Start developing
----------------------

See OceanBase Developer Document to learn how to compile and deploy a manually compiled observer.

Roadmap
=======

For future plans, see Product Iteration Progress. See also OceanBase Roadmap for more details.

Case study
==========

OceanBase has been serving more than 2000 customers and upgraded their database from different industries, including Financial Services, Telecom, Retail, Internet, and more.

See also success stories and Who is using OceanBase for more details.

System architecture
===================

Introduction to system architecture

Contributing
============

Contributions are highly appreciated. Read the development guide to get started.

License
=======

OceanBase Database is licensed under the Mulan Public License, Version 2. See the LICENSE file for more info.

Community
=========

Join the OceanBase community via:

-   Discord: Best for: asking questions, sharing feedback, getting the latest news, and connecting with other OceanBase users.
-   GitHub Issues: Best for: addressing bugs encountered while using OceanBase, as well as submitting feature proposals.
-   Chinese User Forum: Only for Chinese users, best for: asking questions, sharing feedback, getting the latest news, and connecting with other OceanBase users.
-   WeChat Group (Add the assistant with WeChat ID: OBCE666): Only for Chinese users, best for: getting the latest news and connecting with other OceanBase users.
