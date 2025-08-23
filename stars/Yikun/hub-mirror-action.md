---
project: hub-mirror-action
stars: 672
description: 一个Github Action，用于在Github, Gitee, GitLab和GitCode之间同步代码。Action for mirroring repos between Hubs (like Github, Gitee, GitLab and GitCode).
url: https://github.com/Yikun/hub-mirror-action
---

Hub Mirror Action
=================

简体中文 | English

一个用于在hub间（例如Github，Gitee, Gitlab 和 Gitcode）账户代码仓库同步的action

用法
--

### 同步GitHub到Gitee

steps:
- name: Mirror the Github organization repos to Gitee.
  uses: Yikun/hub-mirror-action@master
  with:
    # 支持Gitee, Github, Gitlab and Gitcode
    src: github/kunpengcompute
    # 支持Gitee, Github, Gitlab and Gitcode
    dst: gitee/kunpengcompute
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    # 支持Github/Gitee/Gitcode的用户、组织以及Gitlab的组
    account\_type: org
    # 支持分别设置源和目的端的类型
    # src\_account\_type: org
    # dst\_account\_type: org

上面的配置完成了kunpencompute组织从github到gitee的同步，你可以在测试和demo找到完整用法。

有疑问、想法、问题、建议，可以通过找到我们。

谁在使用？
-----

超过100+组织，4000+使用者正在使用，50+来自使用者的使用教程：

参数详解
----

#### 必选参数

-   `src` 需要被同步的源端账户名，如github/kunpengcompute，表示Github的kunpengcompute账户。
-   `dst` 需要同步到的目的端账户名，如gitee/kunpengcompute，表示Gitee的kunpengcompute账户。
-   `dst_key` 用于在目的端上传代码的私钥(默认可以从~/.ssh/id\_rsa获取），可参考生成/添加SSH公钥或generating SSH keys生成，并确认对应公钥已经被正确配置在目的端。对应公钥，Github可以在这里配置，Gitee可以这里配置，Gitlab可以在这里配置。
-   `dst_token` 创建仓库的API tokens， 用于自动创建不存在的仓库，Github可以在这里找到，Gitee可以在这里找到，Gitlab可以在这里找到（Required scopes: api, read\_api, read\_repository, write\_repository）。

#### 可选参数

-   `account_type` 默认为user，源和目的的账户类型，可以设置为org（组织）、user（用户）或者group（组），该参数支持**同类型账户**（即组织到组织，或用户到用户，或组到组）的同步。如果源目的仓库是不同类型，请单独使用`src_account_type`和`dst_account_type`配置。
-   `src_account_type` 默认为`account_type`，源账户类型，可以设置为org（组织）、user（用户）或者group（组）。
-   `dst_account_type` 默认为`account_type`，目的账户类型，可以设置为org（组织）、user（用户）或者group（组）。
-   `clone_style` 默认为https，可以设置为ssh或者https。当设置为ssh时，你需要将`dst_key`所对应的公钥同时配置到源端和目的端。
-   `cache_path` 默认为'', 将代码缓存在指定目录，用于与actions/cache配合以加速镜像过程。
-   `black_list` 默认为'', 配置后，黑名单中的repos将不会被同步，如“repo1,repo2,repo3”。
-   `white_list` 默认为'', 配置后，仅同步白名单中的repos，如“repo1,repo2,repo3”。
-   `static_list` 默认为'', 配置后，仅同步静态列表，不会再动态获取需同步列表（黑白名单机制依旧生效），如“repo1,repo2,repo3”。
-   `force_update` 默认为false, 配置后，启用git push -f强制同步，**注意：开启后，会强制覆盖目的端仓库**。
-   `debug` 默认为false, 配置后，启用debug开关，会显示所有执行命令。
-   `timeout` 默认为'30m', 用于设置每个git命令的超时时间，'600'=>600s, '30m'=>30 mins, '1h'=>1 hours
-   `mappings` 源仓库映射规则，比如'A=>B, C=>CC', A会被映射为B，C会映射为CC，映射不具有传递性。主要用于源和目的仓库名不同的镜像。
-   `lfs` 提供git lfs支持, 默认为false, 配置为true后，调用`git lfs fetch --all`和`git lfs push --all`进行同步。
-   `api_timeout`（可选）默认值为 `60`，用于设置 API 请求的超时时间（单位：秒）。 例如：`api_timeout: '90'`

举些例子
----

#### 组织同步

同步Github的kunpengcompute组织到Gitee

\- name: Organization mirror
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/kunpengcompute
    dst: gitee/kunpengcompute
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    account\_type: org

#### 黑/白名单

动态获取源端github/Yikun的repos，但仅同步名为hub-mirror-action，不同步hashes这个repo到Gitee

\- name: Single repo mirror
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    white\_list: "hub-mirror-action"
    black\_list: "hashes"

#### 静态名单（可用于单一仓库同步）

不会动态获取源端github/Yikun的repos，仅同步hub-mirror-action这个repo

\- name: Black list
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    static\_list: "hub-mirror-action"

#### clone方式

使用ssh方式进行clone

说明：请把`dst_key`所的公钥配置到源端（在这里为github）及目的端（在这里为gitee）

\- name: ssh clone style
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    clone\_style: "ssh"

#### 指定目录cache

\- name: Mirror with specific cache
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    cache\_path: /github/workspace/hub-mirror-cache

#### 强制更新，并打开debug日志开关

\- name: Mirror with force push (git push -f)
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    force\_update: true
    debug: true

#### 设置命令行超时时间为1小时

\- name: Mirror with force push (git push -f)
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    force\_update: true
    timeout: '1h'

#### 仓库名不同时同步（github/yikun/yikun.github.com to gitee/yikunkero/blog）

\- name: mirror with mappings
  uses: Yikun/hub-mirror-action@mappings
  with:
    src: github/yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    mappings: "yikun.github.com=>blog"
    static\_list: "yikun.github.com"

#### 仅同步非fork且非private的仓库

\- name: Get repository list exclude private and fork
  id: repo
  uses: yi-Xu-0100/repo-list-generator@v1.0.1
- name: Mirror repository list exclude private and fork
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    static\_list: ${{ steps.repo.outputs.repoList }}

#### 支持LFS同步

\- name: Mirror with lfs (git lfs fetch/push --all)
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/Yikun
    dst: gitee/yikunkero
    dst\_key: ${{ secrets.GITEE\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITEE\_TOKEN }}
    lfs: true

#### 同步GitHub到Gitlab

\- name: GitLab group mirror
  uses: Yikun/hub-mirror-action@master
  with:
    src: github/organization-name
    dst: gitlab/group-name
    dst\_key: ${{ secrets.GITLAB\_PRIVATE\_KEY }}
    dst\_token: ${{ secrets.GITLAB\_TOKEN }}
    account\_type: group
    src\_account\_type: org
    dst\_account\_type: group

FAQ
---

-   如何在secrets添加dst\_token和dst\_key？ 下面是添加secrets的方法，也可以参考secrets官方文档了解更多：
    
    1.  **获取Token和Key**，例如
    
    -   Github: 配置并保存ssh key和token
    -   Gitee: 配置并保存ssh key和token
    -   Gitlab: 配置并保存ssh key和token
    -   Gitcode: 配置并保存ssh key和token
    
    1.  **增加Secrets配置**，在配置仓库的Setting-Secrets中新增Secrets，例如`GITEE_PRIVATE_KEY`\`GITLAB\_PRIVATE\_KEY`\`GITCODE\_PRIVATE\_KEY`、`GITEE\_TOKEN`\`GITLAB\_TOKEN`\`GITCODE\_TOKEN\`。
    2.  **在Workflow中引用**， 可以用过类似`${{ secrets.GITEE_PRIVATE_KEY }}`来访问。

参考
--

-   Hub mirror template: 一个用于展示如何使用这个action的模板仓库. from @yi-Xu-0100
-   自动镜像 GitHub 仓库到 Gitee: 一个关于如何使用这个action的介绍. from @ShixiangWang
-   巧用Github Action同步代码到Gitee: Github Action第一篇软文

最后
--

如果觉得不错，**来个star**支持下作者吧！你的Star是我更新代码的动力！：）

想任何想吐槽或者建议的都可以直接飞个issue.
