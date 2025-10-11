---
project: incubator-seata
stars: 25844
description: :fire: Seata is an easy-to-use, high-performance, open source distributed transaction solution.
url: https://github.com/apache/incubator-seata
---

Seata: Simple Extensible Autonomous Transaction Architecture
============================================================

What is Seata?
--------------

A **distributed transaction solution** with high performance and ease of use for **microservices** architecture.

### Distributed Transaction Problem in Microservices

Let's imagine a traditional monolithic application. Its business is built up with 3 modules. They use a single local data source.

Naturally, data consistency will be guaranteed by the local transaction.

Things have changed in a microservices architecture. The 3 modules mentioned above are designed to be 3 services on top of 3 different data sources (Pattern: Database per service). Data consistency within every single service is naturally guaranteed by the local transaction.

**But how about the whole business logic scope?**

### How Seata do?

Seata is just a solution to the problem mentioned above.

Firstly, how to define a **Distributed Transaction**?

We say, a **Distributed Transaction** is a **Global Transaction** which is made up with a batch of **Branch Transaction**, and normally **Branch Transaction** is just **Local Transaction**.

There are three roles in Seata Framework:

-   **Transaction Coordinator(TC):** Maintain status of global and branch transactions, drive the global commit or rollback.
-   **Transaction Manager(TM):** Define the scope of global transaction: begin a global transaction, commit or rollback a global transaction.
-   **Resource Manager(RM):** Manage resources that branch transactions working on, talk to TC for registering branch transactions and reporting status of branch transactions, and drive the branch transaction commit or rollback.

A typical lifecycle of Seata managed distributed transaction:

1.  TM asks TC to begin a new global transaction. TC generates an XID representing the global transaction.
2.  XID is propagated through microservices' invoke chain.
3.  RM registers local transaction as a branch of the corresponding global transaction of XID to TC.
4.  TM asks TC for committing or rollbacking the corresponding global transaction of XID.
5.  TC drives all branch transactions under the corresponding global transaction of XID to finish branch committing or rollbacking.

For more details about principle and design, please go to Seata wiki page.

### History

##### Alibaba

-   **TXC**: Taobao Transaction Constructor. Alibaba middleware team started this project since 2014 to meet the distributed transaction problems caused by application architecture change from monolithic to microservices.
-   **GTS**: Global Transaction Service. TXC as an Aliyun middleware product with new name GTS was published since 2016.
-   **Fescar**: we started the open source project Fescar based on TXC/GTS since 2019 to work closely with the community in the future.

##### Ant Financial

-   **XTS**: Extended Transaction Service. Ant Financial middleware team developed the distributed transaction middleware since 2007, which is widely used in Ant Financial and solves the problems of data consistency across databases and services.
    
-   **DTX**: Distributed Transaction Extended. Since 2013, XTS has been published on the Ant Financial Cloud, with the name of DTX .
    

##### Seata Community

-   **Seata** :Simple Extensible Autonomous Transaction Architecture. Ant Financial joins Fescar, which make it to be a more neutral and open community for distributed transaction, and Fescar be renamed to Seata.

Maven dependency
----------------

Depending on the scenario, choose one of the two dependencies: `org.apache.seata:seata-all` or `org.apache.seata:seata-spring-boot-starter`.

<properties\>
  <seata.version>2.5.0</seata.version>
</properties\>

<dependencies\>
<!--dependencies for non-SpringBoot application framework\-->
  <dependency\>
    <groupId\>org.apache.seata</groupId\>
    <artifactId\>seata-all</artifactId\>
    <version\>${seata.version}</version\>
  </dependency\>

<!--If your project base on \`Spring Boot\`, you can directly use the following dependencies\-->
<!--Notice: \`seata-spring-boot-starter\` has already included \`seata-all\` dependency\-->
  <dependency\>
    <groupId\>org.apache.seata</groupId\>
    <artifactId\>seata-spring-boot-starter</artifactId\>
    <version\>${seata.version}</version\>
  </dependency\>
</dependencies\>

Quick Start
-----------

Quick Start

Documentation
-------------

You can view the full documentation from Seata Official Website: Seata Website page.

Reporting bugs
--------------

Please follow the template for reporting any issues.

Security
--------

Please do not use our public issue tracker but refer to our security policy

Contributing
------------

Contributors are welcomed to join the Seata project. Please check CONTRIBUTING and CONTRIBUTING-CN about how to contribute to this project.

Contact
-------

-   Mailing list:
    -   dev@seata.apache.org , for dev/user discussion. subscribe, unsubscribe, archive
-   Online chat:

Dingtalk group

Wechat official account

QQ group

Wechat assistant

Seata ecosystem
---------------

-   Seata Website - Seata official website
-   Seata GoLang - Seata GoLang client
-   Seata Samples - Samples for Seata Java
-   Seata GoLang Samples - Samples for Seata GoLang
-   Seata K8s - Seata integration with Kubernetes
-   Seata CLI - CLI tool for Seata operations

Contributors
------------

This project exists thanks to all the people who contribute. \[Contributors\].

License
-------

Seata is under the Apache 2.0 license. See the LICENSE file for details.

Who is using
------------

These are only part of the companies using Seata, for reference only. If you are using Seata, please add your company here to tell us your scenario to make Seata better.
