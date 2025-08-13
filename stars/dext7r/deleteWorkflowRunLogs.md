---
project: deleteWorkflowRunLogs
stars: 1
description: A GitHub Action to delete logs of a workflow run | 用于删除工作流运行日志的 GitHub action
url: https://github.com/dext7r/deleteWorkflowRunLogs
---

deleteWorkflowRunLogs
=====================

deleteWorkflowRunLogs
=====================

deleteWorkflowRunLogs 是基于@octokit/rest 封装的github action版本。也可使用 @dext7r/delete-workflow-run-logs,在node环境下使用

action
------

### 新建一个workflow文件

name: Push Notifications

on:
push:
  branches:
    - main

jobs:
delete-workflow-run-logs:
  runs-on: ubuntu-latest

  steps:
  - name: Run Push Notifications action
    uses: dext7r/delete-workflow-run-logs@main
    with:
      token: ${{ secrets.GITHUB\_TOKEN }}
      per\_page: 100
      expire\_time: 7d
      status: completed
      repo: ${{ github.repository.repo }}
      owner: ${{ github.repository.owner }}

参数
--

变量名

描述

可选值

默认值

必填

token

GitHub token

是

per\_page

每页展示的数量

100

否

expire\_time

过期时间

d/h/m/y

7d

否

status

工作流运行状态

completed/cancelled/skipped

completed

否

repo

仓库名称

是

owner

仓库所有者

是
