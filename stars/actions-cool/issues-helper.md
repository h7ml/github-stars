---
project: issues-helper
stars: 398
description: 🤖 A GitHub Action easily helps you automatically manage issues. Welcome to try.
url: https://github.com/actions-cool/issues-helper
---

🤖 Issues Helper
================

A GitHub Action that easily helps you automatically manage issues

English | 简体中文

🔗 Link
-------

-   Online documentation
-   Online v2 documentation
-   Changelog

😎 Why use GitHub Action?
-------------------------

1.  Complete free
2.  Fully automatic
3.  Hosted on the GitHub server, as long as GitHub is not down, it is not affected

> Private projects have a limit of 2000 times per month. Specific view. Public are unlimited.

Who is using?
-------------

Please leave a message at **here**.

ant-design

ant-design-blazor

ant-design-mobile

ant-design-vue

bootstrap

dumi

electron

element-plus

formily

jsx-next

material-ui

nutui

prettier

react-component

react-music-player

S2

swiper

umi

vite

vitest

vue-request

vuepress-next

zoo

Badge
-----

If you think `actions-cool` can help you, please copy it to the README to support promotion and bring convenience to more repositories:. More color see.

```
[![actions-cool](https://img.shields.io/badge/using-actions--cool-blue?style=flat-square)](https://github.com/actions-cool)
```

⚡ Feedback
----------

You are very welcome to try it out and put forward your comments. You can use the following methods:

-   Report bugs or consult with Issue
-   Discuss via Discussions
-   Submit Pull Request to improve the code of `issues-helper`

List
----

When the following list does not have the features you want, you can submit it in issues.

-   ⭐ Base
    -   `add-assignees`
    -   `add-labels`
    -   `close-issue`
    -   `create-comment`
    -   `create-issue`
    -   `create-label`
    -   `delete-comment`
    -   `get-issue`
    -   `lock-issue`
    -   `open-issue`
    -   `remove-assignees`
    -   `remove-labels`
    -   `set-labels`
    -   `unlock-issue`
    -   `update-comment`
    -   `update-issue`
-   🌟 Advanced
    -   `check-inactive`
    -   `check-issue`
    -   `close-issues`
    -   `find-comments`
    -   `find-issues`
    -   `lock-issues`
    -   `mark-assignees`
    -   `mark-duplicate`
    -   `toggle-labels`
    -   `welcome`

🚀 Usage
--------

### ⭐ Base

In order to better display the function, the following is an example of the actual scene, please refer to it flexibly.

#### `add-assignees`

When an issue is added or modified, assign this issue to one or more people.

name: Add Assigness

on:
  issues:
    types: \[opened, edited\]

jobs:
  add-assigness:
    runs-on: ubuntu-latest
    steps:
      - name: Add assigness
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'add-assignees'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}
          assignees: 'xxx' or 'xx1,xx2'
          random-to: 1

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

assignees

Designated person. No operation when no input or empty character

string

✖

random-to

When set, it will be randomly selected in assignees

number

✖

-   `actions` support multiple and separated by comma. Like: `add-assignees,add-labels`
-   The `name` can be modified according to the actual situation
-   Reference to on
-   `${{ github.event.issue.number }}` is the current issue. More references
-   `assignees` support multiple and separated by comma
-   You can assign up to 10 people to each issue

⏫ Back to list

#### `add-labels`

When the content of a new issue does not contain the specified format, add labels for the issue.

name: Add Labels

on:
  issues:
    types: \[opened\]

jobs:
  add-labels:
    runs-on: ubuntu-latest
    if: contains(github.event.issue.body, 'xxx') == false
    steps:
      - name: Add labels
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'add-labels'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}
          labels: 'bug' or 'xx1,xx2'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

labels

New labels. When it is not filled in or is empty character, do not add

string

✖

-   `labels` support multiple and separated by comma

⏫ Back to list

#### `close-issue`

Close the specified issue.

\- name: Close issue
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'close-issue'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: xxx

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

close-reason

Reason for closing. Default `not_planned`, another `completed`

string

✖

⏫ Back to list

#### `create-comment`

When a designated label is added, comment on the issue.

name: Create Comment

on:
  issues:
    types: \[labeled\]

jobs:
  create-comment:
    runs-on: ubuntu-latest
    if: github.event.label.name == 'xxx'
    steps:
      - name: Create comment
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'create-comment'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}
          body: |
            Hello @${{ github.event.issue.user.login }}. Add some comments.
            你好 @${{ github.event.issue.user.login }}。巴拉巴拉。
          emoji: '+1' or '+1,heart'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

body

Add comment content

string

✔

emoji

Add emoji

string

✖

-   No action when `body` is empty
-   Return `comment-id`, which can be used for subsequent operations. Usage reference
-   `${{ github.event.issue.user.login }}` indicates the creator of the issue
-   `emoji` support multiple and separated by comma

⏫ Back to list

#### `create-issue`

Here is an example, add an issue at UTC 00:00 on the 1st of every month.

name: Create Issue

on:
  schedule:
    - cron: "0 0 1 \* \*"

jobs:
  create-issue:
    runs-on: ubuntu-latest
    steps:
      - name: Create issue
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'create-issue'
          token: ${{ secrets.GITHUB\_TOKEN }}
          title: 'xxxx'
          body: 'xxxx'
          labels: 'xx'
          assignees: 'xxx'
          emoji: '+1'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

title

The title of the new issue

string

✔

body

The body of the new issue

string

✖

labels

The labels for the new issue

string

✖

assignees

The assignees for the new issue

string

✖

random-to

When set, it will be randomly selected in assignees

number

✖

emoji

Add emoji

string

✖

-   No action when `title` is empty
-   Return `issue-number`. Usage reference

⏫ Back to list

#### `create-label`

Create label. If you want to maintain labels in batches, see.

\- name: Create label
  uses: actions-cool/issues-helper@v3
  with:
    actions: 'create-label'
    token: ${{ secrets.GITHUB\_TOKEN }}
    label-name: 'xx'
    label-color: '0095b3'
    label-desc: 'xx'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

label-name

Label name, emoji support

string

✔

label-color

Label color, the format is hexadecimal color code, without `#`

string

✖

label-desc

Label description

string

✖

-   `label-name`: If it already exists, no operation
-   `label-color`: Default is `ededed`

⏫ Back to list

#### `delete-comment`

According to `comment-id` delete the specified comment.

\- name: Delete comment
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'delete-comment'
      token: ${{ secrets.GITHUB\_TOKEN }}
      comment-id: xxx

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

comment-id

The comment ID

number

✔

⏫ Back to list

#### `get-issue`

Query issue information.

\- name: Get Issue
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'get-issue'
      token: ${{ secrets.GITHUB\_TOKEN }}

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

-   Return `issue-number` `issue-title` `issue-body` `issue-labels` `issue-assignees` `issue-state`. Usage reference

⏫ Back to list

#### `lock-issue`

When the `invalid` label is added, the issue is locked.

name: Lock Issue

on:
  issues:
    types: \[labeled\]

jobs:
  lock-issue:
    runs-on: ubuntu-latest
    if: github.event.label.name == 'invalid'
    steps:
      - name: Lock issue
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'lock-issue'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

lock-reason

Reason for locking issue

string

✖

-   `lock-reason`: Optional values are `off-topic` `too heated` `resolved` `spam`

⏫ Back to list

#### `open-issue`

Open the specified issue.

\- name: Open issue
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'open-issue'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: xxx

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

⏫ Back to list

#### `remove-assignees`

Remove the person designated by issue.

\- name: Remove assignees
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'remove-assignees'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: ${{ github.event.issue.number }}
      assignees: 'xx'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

assignees

Designated person removed. When it is an empty character, do not remove

string

✔

⏫ Back to list

#### `remove-labels`

Remove the specified labels.

\- name: Remove labels
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'remove-labels'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: ${{ github.event.issue.number }}
      labels: 'xx'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

labels

The removed labels. When it is a blank character, do not remove

string

✔

-   `labels` supports multiple, such as `x1,x2,x3`, only the labels added by the issue will be removed

⏫ Back to list

#### `set-labels`

Replace the labels of issue.

\- name: Set labels
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'set-labels'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: ${{ github.event.issue.number }}
      labels: 'xx'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

labels

labels set. When empty characters, will remove all

string

✔

⏫ Back to list

#### `unlock-issue`

Unlock the specified issue.

\- name: Unlock issue
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'unlock-issue'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: ${{ github.event.issue.number }}

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

⏫ Back to list

#### `update-comment`

Update the specified comment according to `comment-id`.

The following example shows that 👀 is added for each new comment.

name: Add eyes to each comment

on:
  issue\_comment:
    types: \[created\]

jobs:
  update-comment:
    runs-on: ubuntu-latest
    steps:
      - name: Update comment
          uses: actions-cool/issues-helper@v3
          with:
            actions: 'update-comment'
            token: ${{ secrets.GITHUB\_TOKEN }}
            comment-id: ${{ github.event.comment.id }}
            emoji: 'eyes'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

comment-id

The comment ID

number

✔

out-comments

The output of `find-comments`, if you find multiple, operate multiple

string

✖

body

Update the content of comment

string

✖

update-mode

Update mode. Default `replace`, another `append`

string

✖

emoji

Add reaction

string

✖

-   When `body` is not entered, it will remain as it is
-   When `update-mode` is `append`, additional operations will be performed. Anything other than `append` will be replaced. Only effective for `body`

⏫ Back to list

#### `update-issue`

Update the specified issue according to the `issue-number`.

\- name: Update issue
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'update-issue'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: ${{ github.event.issue.number }}
      state: 'open'
      title: 'xxx'
      body: 'xxxx'
      update-mode: 'replace'
      labels: 'xx'
      assignees: 'xxx'
      emoji: '+1'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

state

Modify the status of issue, optional value `open` `closed`

string

✖

title

Modify the title of the issue

string

✖

body

Modify the content of issue

string

✖

update-mode

Update mode. Default `replace`, another `append`

string

✖

labels

Replace the labels of issue

string

✖

assignees

Replace the assignees of issue

string

✖

emoji

Add reaction

string

✖

-   `state` defaults to `open`
-   When the option is not filled, it will keep the original

⏫ Back to list

### 🌟 Advanced

Advanced usage is not recommended to use multiple actions at the same time.

#### `check-inactive`

At UTC 0 on the 1st of each month, add the `inactive` tag to all issues that have not been active for more than 30 days.

name: Check inactive

on:
  schedule:
    - cron: "0 0 1 \* \*"

jobs:
  check-inactive:
    runs-on: ubuntu-latest
    steps:
      - name: check-inactive
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'check-inactive'
          token: ${{ secrets.GITHUB\_TOKEN }}
          inactive-day: 30

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

body

When operating an issue, you can comment. Do not comment when not typing

string

✖

emoji

Add reaction for this comment

string

✖

labels

Labels filtering

string

✖

issue-state

State filtering

string

✖

issue-assignee

Assignee filtering

string

✖

issue-creator

Creator filtering

string

✖

issue-mentioned

Mentioned filtering

string

✖

body-includes

Body filtering

string

✖

title-includes

Title filtering

string

✖

inactive-day

Inactive days filtering

number

✖

inactive-mode

Detect inactive mode, default `issue`

string

✖

inactive-label

The label name adding

string

✖

exclude-labels

Exclude labels filtering

string

✖

exclude-issue-numbers

Exclude the specified issues

string

✖

-   `labels`: When there are multiple, the query will have multiple at the same time. If not entered, all
-   `issue-state`: The default is `all`. Optional value `open` `closed`, when these 2 items are not, both are `all`
-   `issue-assignee`: Multiplayer is not supported. If you do not enter or enter \*, all will be searched. Entering `none` will query issues for which the specified person is not added
-   `inactive-day`: When entering, it will filter the issue update time earlier than the current time minus the number of inactive days. If not entered, all
-   `inactive-label`: The default is `inactive`, others can be customized. When the project does not contain the label, it will be created automatically
-   `exclude-labels`: When set to include `$exclude-empty`, no label issue can be excluded
-   `inactive-mode`:
    -   Default `issue`: the issue updated time
    -   Optional `comment`: the last comment update time
    -   Optional `issue-created`: the issue created time
    -   Optional `comment-created`: the comment creation time
    -   You can also set multiple such as: `comment, issue-created`
        -   It will be detected with priority, the update time of the last comment will be detected first, if there is no comment, the creation time of the issue will be used

⏫ Back to list

#### `check-issue`

Check whether the issue meets the conditions according to the passed parameters and `issue-number`, and return a boolean value.

The effect of the following example is: when an issue is newly opened, verify whether the current issue designator contains `x1` or `x2`.

If one designated person is satisfied, the verification will pass, and at the same time, verify whether the title meets the conditions. Check rules

name: Check Issue

on:
  issues:
    types: \[edited\]

jobs:
  check-issue:
    runs-on: ubuntu-latest
    steps:
      - name: check-issue
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'check-issue'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}
          assignee-includes: 'x1,x2'
          title-includes: 'x1,x2/y1,y2'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

assignee-includes

Assignees contains check

string

✖

title-includes

Title contains check

string

✖

title-excludes

Check whether the title is empty after removing the default title

string

✖

body-includes

Body contains check

string

✖

-   `title-includes` `body-includes` supports the format `x1,x2` or `x1,x2/y1,y2`. Only supports two levels
-   Return `check-result`, due to yml reasons, the judgment condition is `if: steps.xxid.outputs.check-result =='true'`

⏫ Back to list

#### `close-issues`

Every 7 days at UTC 0, close the issues that have been filled with the `need info` label and have not been active for more than 7 days.

name: Check need info

on:
  schedule:
    - cron: "0 0 \*/7 \* \*"

jobs:
  check-need-info:
    runs-on: ubuntu-latest
    steps:
      - name: close-issues
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'close-issues'
          token: ${{ secrets.GITHUB\_TOKEN }}
          labels: 'need info'
          inactive-day: 7

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

body

When operating an issue, you can comment. Do not comment when not typing

string

✖

emoji

Add reaction for this comment

string

✖

labels

Labels filtering

string

✖

issue-assignee

Assignee filtering

string

✖

issue-creator

Creator filtering

string

✖

issue-mentioned

Mentioned filtering

string

✖

body-includes

Body filtering

string

✖

title-includes

Title filtering

string

✖

inactive-day

Inactive days filtering

number

✖

exclude-labels

Exclude labels filtering

string

✖

close-reason

Reason for closing. Default `not_planned`, another `completed`

string

✖

-   `labels`: When there are multiple, the query will have multiple at the same time. If not entered, all
-   `issue-assignee`: Multiplayer is not supported. If you do not enter or enter \*, all will be searched. Entering `none` will query issues for which the specified person is not added
-   `inactive-day`: When entering, it will filter the issue update time earlier than the current time minus the number of inactive days. If not entered, all
-   `exclude-labels`: When set to include `$exclude-empty`, no label issue can be excluded

⏫ Back to list

#### `find-comments`

Find the current warehouse issue No. 1, the creator is k and the content contains the comment list of `this`.

\- name: Find comments
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'find-comments'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-number: 1
      comment-auth: 'k'
      body-includes: 'this'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

comment-auth

Comment creator, all will be queried if not filled

string

✖

body-includes

Comment content includes filtering, no verification if not filled

string

✖

direction

Return `comments` sort

string

✖

-   Return `comments` in the following format:

\[
  {id: 1, auth: 'x', body: 'xxx', created: '', updated: ''},
  {id: 2, auth: 'x', body: 'xxx', created: '', updated: ''},
\]

-   `direction` defaults to ascending order, only when `desc` is set, descending order will be returned
-   The `created` `updated` in the returned array, determined by the environment, will be UTC +0

⏫ Back to list

#### `find-issues`

Find the current repository, the creator is k , the title contains `this` , the body contains `that`, and the list of issues in the open state.

\- name: Find issues
    uses: actions-cool/issues-helper@v3
    with:
      actions: 'find-issues'
      token: ${{ secrets.GITHUB\_TOKEN }}
      issue-creator: 'k'
      issue-state: 'open'
      title-includes: 'this'
      body-includes: 'that'
      labels: 'documentation'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-state

State filtering

string

✖

issue-creator

Creator filtering

string

✖

title-includes

Title filtering

string

✖

body-includes

Body filtering

string

✖

labels

Labels filtering

string

✖

exclude-labels

Exclude labels filtering

string

✖

inactive-day

Inactive days filtering

number

✖

direction

Return sort

string

✖

create-issue-if-not-exist

Create a new issue if not exist

boolean

✖

-   Returns `issues` in the following format:

\[
  {number: 1, auth: 'x', body: 'xxx', body: 'xxx', state: 'open', assignees: \['x1', 'x2'\], created: '', updated: ''},
  {number: 2, auth: 'x', body: 'xxx', body: 'xxx', state: 'closed', assignees: \['x1', 'x2'\], created: '', updated: ''},
\]

-   `issue-state`: The default is `open`. Other values are: `closed`, `all`
-   `direction` defaults to ascending order, only when `desc` is set, descending order will be returned
-   The `created` `updated` in the returned array, determined by the environment, will be UTC +0
-   `exclude-labels`: When set to include `$exclude-empty`, no label issue can be excluded

⏫ Back to list

#### `lock-issues`

Every 3 months at UTC 0 on the 1st, lock all issues that have been filled with the `inactive` label and have not been active for more than 128 days.

name: Lock inactive issues

on:
  schedule:
    - cron: "0 0 1 \*/3 \*"

jobs:
  lock-issues:
    runs-on: ubuntu-latest
    steps:
      - name: lock-issues
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'lock-issues'
          token: ${{ secrets.GITHUB\_TOKEN }}
          labels: 'inactive'
          inactive-day: 128

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

body

When operating an issue, you can comment. Do not comment when not typing

string

✖

emoji

Add reaction for this comment

string

✖

labels

Labels filtering

string

✖

issue-state

State filtering

string

✖

issue-assignee

Assignee filtering

string

✖

issue-creator

Creator filtering

string

✖

issue-mentioned

Mentioned filtering

string

✖

body-includes

Body filtering

string

✖

title-includes

Title filtering

string

✖

inactive-day

Inactive days filtering

number

✖

lock-reason

Reason for locking issue

string

✖

exclude-labels

Exclude labels filtering

string

✖

-   `labels`: When there are multiple, the query will have multiple at the same time. If not entered, all
-   `issue-state`: The default is `all`. Optional value `open` `closed`, when these 2 items are not, both are `all`
-   `issue-assignee`: Multiplayer is not supported. If you do not enter or enter \*, all will be searched. Entering `none` will query issues for which the specified person is not added
-   `inactive-day`: When entering, it will filter the issue update time earlier than the current time minus the number of inactive days. If not entered, all
-   `exclude-labels`: When set to include `$exclude-empty`, no label issue can be excluded

⏫ Back to list

#### `mark-assignees`

Quickly assign person, only for the issue to add editor comments.

name: Issue Mark Assignees

on:
  issue\_comment:
    types: \[created, edited\]

jobs:
  mark-assignees:
    runs-on: ubuntu-latest
    steps:
      - name: mark-assignees
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'mark-assignees'
          token: ${{ secrets.GITHUB\_TOKEN }}

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

assign-command

Simple commands can be set, such as: `/a`

string

✖

require-permission

Permission required, default is `write`

string

✖

-   `assign-command`: default `/assign`
-   `require-permission`: Optional values are `admin`, `write`, `read`, `none`
    -   If the team member sets the `read` permission, it is `read`
    -   If the external Collaborator is set to `read` permission, it is `read`
    -   Ordinary users have `read` permission
    -   When set `write`, `admin` and `write` meet the conditions

⏫ Back to list

#### `mark-duplicate`

Quickly mark duplicate questions, only for issue new comments or edit comments.

name: Issue Mark Duplicate

on:
  issue\_comment:
    types: \[created, edited\]

jobs:
  mark-duplicate:
    runs-on: ubuntu-latest
    steps:
      - name: mark-duplicate
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'mark-duplicate'
          token: ${{ secrets.GITHUB\_TOKEN }}

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

duplicate-command

Simple commands can be set, such as: `/d`

string

✖

duplicate-labels

Add additional labels to this issue

string

✖

remove-labels

Set removable labels

string

✖

labels

Replace the labels of the issue

string

✖

emoji

Add reaction for this comment

string

✖

close-issue

Whether to close the issue at the same time

string

✖

require-permission

Permission required, default is `write`

string

✖

close-reason

Reason for closing. Default `not_planned`, another `completed`

string

✖

-   `duplicate-command`: When setting concise commands, while still supporting the original `Duplicate of`. Block content contains `?`
-   `labels`: Highest priority
-   `close-issue`: Both `true` or `'true'` can take effect
-   `require-permission`: Optional values are `admin`, `write`, `read`, `none`
    -   If the team member sets the `read` permission, it is `read`
    -   If the external Collaborator is set to `read` permission, it is `read`
    -   Ordinary users have `read` permission
    -   When set `write`, `admin` and `write` meet the conditions

⏫ Back to list

#### `toggle-labels`

When an issue is reopened, the set labels are removed if they already exist, otherwise they are added.

name: Toggle Labels

on:
  issues:
    types: \[reopened\]

jobs:
  toggle-labels:
    runs-on: ubuntu-latest
    steps:
      - name: Toggle labels
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'toggle-labels'
          token: ${{ secrets.GITHUB\_TOKEN }}
          issue-number: ${{ github.event.issue.number }}
          labels: 'unread,outdated'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

issue-number

The number of issue. When not input, it will be obtained from the trigger event

number

✖

labels

The toggle labels. Delete if the label already exists, add if it does not exist

string

✖

⏫ Back to list

#### `welcome`

When an issue is created, the user who created the issue for the first time is welcome.

If the user is not creating for the first time, there is no operation.

name: Issue Welcome

on:
  issues:
    types: \[opened\]

jobs:
  issue-welcome:
    runs-on: ubuntu-latest
    steps:
      - name: welcome
        uses: actions-cool/issues-helper@v3
        with:
          actions: 'welcome'
          token: ${{ secrets.GITHUB\_TOKEN }}
          body: hi @${{ github.event.issue.user.login }}, welcome!
          labels: 'welcome1, welcome2'
          assignees: 'xx1'
          issue-emoji: '+1, -1, eyes'

Param

Desc

Type

Required

actions

Action type

string

✔

token

Token explain

string

✖

body

Comment on the welcome content, no comment if you leave it blank

string

✖

labels

Add labels to this issue

string

✖

assignees

Add assignees to this issue

string

✖

issue-emoji

Add reaction to this issue

string

✖

-   If these 4 options are not filled, no operation

⏫ Back to list

🎁 Reference
------------

### token

Need to have the person token with push permission.

-   Personal token application
    -   Need to check `Full control of private repositories`
-   Project add secrets
    -   Select settings, select secrets, select `New repository secret`
    -   `Name` is the same as in actions
    -   `Value` fill in the token just applied by the individual

When the token is not filled in actions or input `${{ secrets.GITHUB_TOKEN }}`, it will default to `github-actions-bot`. More.

⏫ Back to list

### GitHub Docs

-   Workflow syntax for GitHub Actions
-   Events that trigger workflows

⏫ Back to list

### `outputs` use

\- name: Create issue
  uses: actions-cool/issues-helper@v3
  id: createissue
  with:
    actions: 'create-issue'
    token: ${{ secrets.GITHUB\_TOKEN }}
- name: Check outputs
  run: echo "Outputs issue\_number is ${{ steps.createissue.outputs.issue-number }}"

More:

1.  https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/metadata-syntax-for-github-actions#outputs
2.  https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob\_idoutputs

⏫ Back to list

### Check rules

"title-includes": 'x1,x2'

x1
x2

"x1y3y2"  true
"y2 x1"   true
"x2"      true
"x3"      false

"title-includes": 'x1,x2/y1,y2'

x1 + y1
x2 + y1
x1 + y2
x2 + y2

"x1y3y2"  true
"y2 x1"   true
"1x2y"    false
"x1"      false

⏫ Back to list

### Emoji types

content

emoji

`+1`

👍

`-1`

👎

`laugh`

😄

`confused`

😕

`heart`

❤️

`hooray`

🎉

`rocket`

🚀

`eyes`

👀

⏫ Back to list

### `comment-id`

Click the `···` icon in the upper right corner of a comment, select `Copy link`, and the number at the end of the url is `comment_id`.

⏫ Back to list

Actions Template
----------------

-   You can directly use this GitHub Actions workflow template repositorie template
-   Personal exercises and tests Actions repository
-   Can also refer to the warehouse of online users

LICENSE
-------

MIT
