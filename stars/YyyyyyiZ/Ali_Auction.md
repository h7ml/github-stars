---
project: Ali_Auction
stars: 2
description: Crawl data from https://sf.taobao.com/ and clean data
url: https://github.com/YyyyyyiZ/Ali_Auction
---

Ali\_Auction
============

Publication
-----------

SIGHCI 2023 Proceedings: When Online Auction Meets Virtual Reality: An Empirical Investigation estigation

Data
----

### source

Ali auction website historical auction records of houses

### Details

Collection requirements:

-   Type of subject matter: residential houses
-   Location of the subject matter: Suzhou, Wuxi, Hangzhou, Wenzhou, Hefei, Chengdu
-   Type of asset: unlimited
-   Auction status: terminated (main), suspended, withdrawn
-   date: January 1, 2020 to June 30, 2022

Crawling
--------

### Workflow

#### Crawling the listpage and detail page

> crawler\_alfp.py

Crawl the specific content (including listpage and corresponding detail page) of the subject matter. First, modify line 347 of crawler\_alfp\_city.py to set crawler\_list = True to collect listpage (need to slice), then set crawler\_list = False for detail page collection. The second process takes a long time.

This part gets the listpage.csv, source.csv and html local files.

#### Parsing data

> parse\_source.py

Run the parsing code to clean the fields based on source.csv and then get the parsed data. After all the pages are collected, modify the last line of the parse\_source.py to change the parameter of run to the path of the existing source.csv, for parsing and normalization.

This part gets the std\_city\_final.csv file.

#### Downloading attachments

> get\_file.py

After all the fields are parsed and standardized, run get\_file.py to download attachments to local.
