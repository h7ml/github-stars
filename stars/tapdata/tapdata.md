---
project: tapdata
stars: 599
description: Tapdata Live Data Platform Project
url: https://github.com/tapdata/tapdata
---

  
  

* * *

What is Tapdata ?
-----------------

Tapdata is a Change Data Capture(CDC) based, Real-Time data integration platform that enables data to be synchronized in real-time among various systems such as databases, SaaS services, applications, and files. The synchronization tasks can be easily built through drag-and-drop operations, from table creation to full and incremental synchronization, all processes are fully automated.

1.  Supported Connectors
2.  FAQ

For more details, please read docs

Based on different distribution strategies and functionalities, Tapdata has three distribution versions: Community Edition, Cloud Service, and Enterprise Edition. All content under this open-source project corresponds to the Community Edition.

For the differences between the three versions, you can refer to: https://tapdata.io/

Table of contents
-----------------

1\. **Key Features**  
2\. **Use Cases**  
3\. **Quick Start**  
4\. **Examples**  
5\. **License**  
6\. **Contact Us**  
7\. **Build From Source**  
8\. **Contributing**  

Key Features
------------

### End-To-End Visual UI

**Full Process Automation**  
Automatic table creation, and Automatic switching between Full and Incremental synchronization.  
  
**Drag-And-Drop**  
Operate through a visual interface, Easy to use  
  
**Monitor**  
sync performance, task progress, key events, and logs.

  

### Lightweight ETL Solution

**Table Filter and Mapping**  
Rich visual processors that allow table selection, renaming, adding or deleting fields, and renaming.  
  
**Record Transformation**  
Easily use JS/Python code to do transformation  
  
**Union**  
Union multi tables to one target.

  

### Build materialized views in MongoDB

**Document-style view**  
Support Embedded documents and arrays, deeply integrated with MongoDB.  
  
**Multi-table association**  
hierarchical nesting, and convenient construction of 1:1 and 1:N models.  
  
**Multi-table stream merging**  
Unified batch and stream processing, multi-table updates in any order.

  

Primary Use Cases
-----------------

1.  Synchronize data from traditional RDBMS to modern databases such as MongoDB, Elasticsearch (ES), or Redis to support new business uses.
2.  Consolidate data from various databases into a unified data warehouse.
3.  Stream database changes to Kafka.
4.  Perform data synchronization between heterogeneous databases.
5.  Use MongoDB to build your unified data hub.

Quick Start
-----------

### Start with docker

To run the complete service, the basic resource requirements are:

1.  At least 5GB of available memory
2.  At least 20GB of available disk space
3.  At least 1 free CPU core

RUN `docker run -d -p 3030:3030 ghcr.io/tapdata/tapdata:latest`, wait for 3 minutes, then you can get it from http://localhost:3030/, if everything is ok, you can see login page like this: default username is: admin@admin.com, default password is admin

### Start with cloud service

Tapdata service is available in cloud service, you can use fully-managed service, or deploy engine to your private network

Try on https://cloud.tapdata.io/, support google and github account login, free trial, NO credit card needed, start your real-time data journey immediately.

Examples
--------

#### 🗂️ Create Datasource and Test it

1.  Login tapdata platform
    
2.  In the left navigation panel, click Connections
    
3.  On the right side of the page, click Create
    
4.  In the pop-up dialog, search and select MySQL
    
5.  On the page that you are redirected to, follow the instructions below to fill in the connection information for MySQL
    

1.  Click Test, make sure all test pass, then click Save

#### 🗂️ Sync Data From MySQL To MongoDB

1.  Create MySQL and MongoDB data source
    
2.  In the left navigation panel, click Data Pipelines -> Data Replications
    
3.  On the right side of the page, click Create
    
4.  Drag and drop MySQL and MongoDB data sources onto the canvas
    
5.  Drag a line from the MySQL data source to MongoDB
    
6.  Configure the MySQL data source and select the data tables you want to synchronize
    

1.  Click the Save button in the upper right corner, then click the Start button
    
2.  Observe the indicators and events on the task page until data is in sync
    

#### 🗂️ MySQL To PostgreSQL with Simple ETL

1.  Create MySQL and PostgreSQL data source
    
2.  In the left navigation panel, click Data Pipelines -> Data Transformation
    
3.  On the right side of the page, click Create
    
4.  Drag and drop MySQL and PostgreSQL data sources onto the canvas
    
5.  Drag a line from the MySQL data source to PostgreSQL
    
6.  Click the plus sign on the connection line and select Field Rename
    

1.  Click Field Rename node, change i\_price to price, i\_data to data in config form

1.  Click the Save button in the upper right corner, then click the Start button
    
2.  Observe the indicators and events on the task page until data is in sync
    

#### 🗂️ Making materialized views in MongoDB

Materialized view is a special feature of tapdata, You can give full play to the characteristics of MongoDB document database and create the data model you need, try enjoy it !

In this example, I will make a view using 2 tables in MySQL: order and product, make product as a embedded document of order, here is the step:

1.  Create MySQL and MongoDB data source
    
2.  In the left navigation panel, click Data Pipelines -> Data Transformation
    
3.  On the right side of the page, click Create
    
4.  Click mysql data source in left up side, then drag and drop order table and product table onto the canvas
    
5.  Drag and drop "Master-slave merge" node in left bottom side onto the canvas
    
6.  Drag a line from the order table to Master-slave merge
    
7.  Drag a line from the product table to Master-slave merge
    
8.  Drag and drop MongoDB data source onto the canvas, and drag a line from the "Master-slave merge" node to MongoDB node
    

1.  Click "Master-slave merge" node, then drag product table into order table in the right side in "Table Name"

1.  Click "Master-slave merge" node, then click product table, config Data write model to "Match and Merge", Field write path to "product", Association Conditions to "order\_id" => "order\_id", then you can see Schema in bottom changed
    
2.  Click MongoDB node, and config target table name as order\_with\_product, update condition field config as "order\_id"
    

1.  Click the Save button in the upper right corner, then click the Start button
    
2.  Observe the indicators and events on the task page until data is in sync
    
3.  Check collection order\_with\_product in MongoDB, and you will see the data model
    

#### 🗂️ Data consistency check

Using the data verification feature, you can quickly check whether the synchronized data is consistent and accurate

1.  In the left navigation panel, click Data Pipelines -> Data Validation
    
2.  On the right side of the page, click Task Consistency Validation
    
3.  Choose 1 task, and valid type choose "All Fields Validation", it means system will check all fields for all record
    

1.  Click Save, then click Execute in the task list
    
2.  Wait validation task finished, click Result in the task list, and check the validation result
    

Architecture
------------

License
-------

Tapdata Community is under the Apache 2.0 license. See the LICENSE file for details.

Contact Us
----------

-   Send Email
-   Slack channel
