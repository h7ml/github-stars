---
project: taos-connector-node
stars: 13
description: TDengine connector for Node.js.
url: https://github.com/taosdata/taos-connector-node
---

TDengine Node.js Connector
==========================

  

English | 简体中文

Table of Contents
-----------------

-   1\. Introduction
-   2\. Documentation
-   3\. Prerequisites
-   4\. Build
-   5\. Testing
    -   5.1 Test Execution
    -   5.2 Test Case Addition
    -   5.3 Performance Testing
-   6\. CI/CD
-   7\. Submitting Issues
-   8\. Submitting PRs
-   9\. References
-   10\. License

1\. Introduction
----------------

@tdengine/websocket is an efficient connector specially designed by TDengine for Node.js developers. It uses the WebSocket API provided by the taosAdapter component to establish a connection with TDengine, eliminating the dependence on TDengine client drivers and opening up a convenient development path for developers. With this powerful tool, developers can easily build applications for TDengine clusters. Whether it is performing complex SQL write and query tasks, implementing flexible schemaless write operations, or achieving highly real-time subscription functionality, this connector can easily and perfectly meet diverse data interaction needs in all aspects.

2\. Documentation
-----------------

-   To use Node.js connector, please refer to the Developer Guide, which includes instructions on how to integrate `@tdengine/websocket` into an application, along with examples of data writing, querying, schemaless writing, parameter binding, and data subscription.
-   For other reference information, please check Reference Manual, which includes version history, data types, example programs, API descriptions, and FAQs.
-   This quick guide is primarily for developers who wish to contribute, build, and test the Node.js connector on their own. To learn about TDengine, you can visit the official documentation.

3\. Prerequisites
-----------------

-   Install the Node.js development environment, using version 14 or above. Download link: https://nodejs.org/en/download/
-   Install the Node.js connector dependencies using npm, execute the 'npm install' command in the `nodejs` directory of the project for installation.
-   Install TypeScript 5.3.3 and above using npm.
-   TDengine has been deployed locally. For specific steps, please refer to Deploy TDengine. Please make sure `taosd` and `taosAdapter` have been started.

4\. Build
---------

Execute `tsc` to build the project in the 'nodejs' directory.

5\. Testing
-----------

### 5.1 Test Execution

Execute `npm run test` in the project directory to run the tests. The test cases will connect to the local TDengine server and taosAdapter for testing. After running the tests, the result similar to the following will be printed eventually. If all test cases pass, without any failures or errors.

```
Test Suites: 8 passed, 8 total
Tests:       1 skipped, 44 passed, 45 total
Snapshots:   0 total
Time:        20.373 s
Ran all test suites.
```

### 5.2 Test Case Addition

All tests are located in the `nodejs/test/bulkPulling` directory of the project. You can add new test files or add test cases in existing test files. The test cases use the jest framework. Generally, a connection is established and a database is created in the `beforeAll` method, and the database is droped and the connection is released in the `afterAll` method.

### 5.3 Performance Testing

Performance testing is in progress.

6\. CI/CD
---------

-   Build Workflow
-   Code Coverage

7\. Submitting Issues
---------------------

We welcome the submission of GitHub Issue. When submitting, please provide the following information:

-   Problem description, is it necessary to present it.
-   Nodejs version.
-   @tdengine/websocket version.
-   Connection parameters (no username or password required).
-   TDengine Server Version.

8\. Submitting PRs
------------------

We welcome developers to contribute to this project. When submitting PRs, please follow these steps:

1.  Fork this project, refer to (how to fork a repo).
2.  Create a new branch from the main branch with a meaningful branch name (`git checkout -b my_branch`). Do not modify the main branch directly.
3.  Modify the code, ensure all unit tests pass, and add new unit tests to verify the changes.
4.  Push the changes to the remote branch (`git push origin my_branch`).
5.  Create a Pull Request on GitHub (how to create a pull request).
6.  After submitting the PR, you can find your PR through the Pull Request. Click on the corresponding link to see if the CI for your PR has passed. If it has passed, it will display "All checks have passed". Regardless of whether the CI passes or not, you can click "Show all checks" -> "Details" to view the detailed test case logs.
7.  After submitting the PR, if CI passes, you can find your PR on the codecov page to check the test coverage.

9\. References
--------------

-   TDengine Official Website
-   TDengine GitHub

10\. License
------------

MIT License
