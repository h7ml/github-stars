---
project: Thanks-Mirror
stars: 2989
description: 整理记录各个包管理器，系统镜像，以及常用软件的好用镜像，Thanks Mirror。     走过路过，如觉不错，麻烦点个赞👆🌟
url: https://github.com/opsre/Thanks-Mirror
---

Thanks Mirror
=============

整理记录各个包管理器，系统镜像，以及常用软件的好用镜像

  

本项目灵感来自：package-manager-proxy-settings，该项目分享的是包管理器配置代理的方法，这里分享的是包管理器直接可用，质量好，速度快的镜像，以及一些其他常用软件，系统镜像的国内镜像。

在此，对那些提供公共仓库镜像的企业或组织，致以感谢 🫡！

Gitee：https://gitee.com/eryajf/Thanks-Mirror

GitHub：https://github.com/eryajf/Thanks-Mirror

每天自动运行一次链接检查，以保证项目中提供的链接都还正常可用，检查详情查看。

📢 注意：之前有朋友在issue中提过是否可以做一个工具来管理这些源，现在，有一个很不错的，适用于多平台的换源工具：https://github.com/RubyMetric/chsrc

**🥳 欢迎关注我的其他项目：**

> -   Go-Ldap-Admin：🌉 基于 Go+Vue 实现的 openLDAP 后台管理项目。
> -   learning-weekly：📝 周刊内容以运维技术和 Go 语言周边为主，辅以 GitHub 上优秀项目或他人优秀经验。
> -   HowToStartOpenSource：🌈 GitHub 开源项目维护协同指南。
> -   magic-of-sysuse-scripts：🪄 运维外挂小工具。
> -   care-screenshot：给我一个 URL，我能将你关心的元素截图发给机器人 🤖
> -   read-list：📖 优质内容订阅，阅读方为根本
> -   awesome-github-profile-readme-chinese：🦩 优秀的中文区个人主页搜集

**赞助商**

> 302.AI 是一个按需付费的一站式企业级AI应用平台，开放平台，开源生态。
> 
> -   点击注册: 立即获得 1PTC(1PTC=1 美金，约为 7 人民币)代币。
> -   集合了最新最全的AI模型和品牌，包括但不限于语言模型、图像模型、声音模型、视频模型。
> -   在基础模型上进行深度应用开发，做到让小白用户都可以零门槛上手使用，无需学习成本。
> -   零月费，所有功能按需付费，全面开放，做到真正的门槛低，上限高。
> -   创新的使用模式，管理和使用分离，面向团队和中小企业，一人管理，多人使用。
> -   所有AI能力均提供API接入，所有应用开源支持自行定制（进行中）。
> -   强大的开发团队，每周推出2-3个新应用，平台功能每日更新。

**目录**

-   Package-Mirror
    -   Go
    -   Npm
    -   Pip
    -   Composer
    -   Rubygems
    -   Maven
    -   Yum
    -   Remi
    -   Epel
    -   Homebrew
    -   cargo
-   Software-Mirror
    -   JDK
    -   Docker
    -   Kubernetes
    -   K3s
    -   Minikube
    -   Helm
    -   Harbor
    -   Jenkins
    -   GitLab-ce
    -   GitLab-runner
    -   ElasticSearch
    -   Logstash
    -   Kibana
    -   Filebeat
    -   MySQL
    -   MariaDB
    -   Percona
    -   MongoDB
    -   Redis
    -   PostgreSQL
    -   Golang
    -   Node
    -   Yarn
    -   Python
    -   Rust
    -   Maven
    -   Zabbix
    -   Prometheus
    -   Grafana
    -   Pinpoint
    -   Apache
    -   Nginx
    -   OpenResty
    -   Keepalived
    -   Ceph
    -   Influxdata
    -   ClickHouse
    -   Rabbitmq
    -   ETCD
    -   WireShark
    -   Virtualbox
    -   iina
    -   chromium
-   System-Mirror
    -   CentOS
    -   CentOS-altarch
    -   Ubuntu
    -   Debian
    -   Deepin
    -   Fedora
    -   Alpine
    -   Void
    -   Gentoo
    -   kali
    -   Opensuse
    -   FreeBSD
    -   GNU
-   Other-Mirror
    -   Docker-hub
    -   GitHub
    -   Google
    -   Nix
-   如何贡献
-   贡献者

Package-Mirror
--------------

以往工作中经历过建设企业内部私服的经历，私服的建设离不开国内一些优秀的镜像代理，这里记录下来，以供大家参考。

`注意：`假如所有的镜像都已经被本地 nexus 私服代理，那么对应的地址为`nexus.eryajf.net/repository/***/`。(这只是个域名示例，不代表实际可用！)

### Go

#### Configuration

如果 go 版本用的`go1.11`或者`go1.12`，需进行如下配置：

export GO111MODULE=on
export GOPROXY="http://nexus.eryajf.net/repository/go/"

如果使用 `go1.13`以上的版本则可以用如下配置：

export GOPROXY="http://nexus.eryajf.net/repository/go/"
GONOPROXY="gitlab.eryajf.net"
GONOSUMDB="gitlab.eryajf.net"
GOPRIVATE="gitlab.eryajf.net"
GOSUMDB="sum.golang.google.cn"

关于如上两个版本配置差异，以及配置参数详解可参考：https://wiki.eryajf.net/pages/4941.html

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/goproxy/
-   Proxy-cn
    -   https://goproxy.cn
-   Proxy-io
    -   https://goproxy.io
-   Baidu
    -   http://goproxy.baidu.com/
-   Tencent
    -   https://mirrors.cloud.tencent.com/go/
-   HUAWEI
    -   https://repo.huaweicloud.com/repository/goproxy/

其中`GOSUMDB`在国内可用的两个镜像分别如下：

-   Google
    -   https://sum.golang.google.cn/

🔝回到顶部

### Npm

#### Configuration

配置`npm`代理，需进行如下配置：

```
# npm配置
$ echo 'registry=http://nexus.eryajf.net/repository/npm' > ~/.npmrc
# 查看
$ npm config get registry
http://nexus.eryajf.net/repository/npm

# yarn配置
$ echo 'registry "http://nexus.eryajf.net/repository/npm"' > ~/.yarnrc
# 查看
$ yarn config get registry
http://nexus.eryajf.net/repository/npm
```

#### Mirrors

-   Taobao
    -   https://npmmirror.com/
-   HUAWEI
    -   https://mirrors.huaweicloud.com/repository/npm/
-   Tencent
    -   http://mirrors.cloud.tencent.com/npm/
-   npmjs
    -   https://registry.npmjs.org

🔝回到顶部

### Pip

#### Configuration

配置`Python`代理，需进行如下配置：

$ mkdir ~/.pip

$ cat \> ~/.pip/pip.conf << EOF
\[global\]
timeout = 60
trusted-host =  nexus.eryajf.net
index-url = http://nexus.eryajf.net/repository/pypi/simple
EOF

`注意：`通常在配置文件后边，我们会添加一个`simple`。

# 简洁配置方式 1
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
# 简洁配置方式 2
pip3 install --upgrade -i https://pypi.tuna.tsinghua.edu.cn/simple yt-dlp

#### Mirrors

目前代理外部私仓有：

-   Aliyun
    -   http://mirrors.aliyun.com/pypi/
-   清华
    -   https://pypi.tuna.tsinghua.edu.cn/
-   HUAWEI
    -   https://repo.huaweicloud.com/repository/pypi/simple
-   Tencent
    -   https://mirrors.cloud.tencent.com/pypi/
-   火山引擎
    -   https://mirrors.volces.com/pypi/
-   北大
    -   https://mirrors.pku.edu.cn/pypi/
-   南阳理工
    -   https://mirror.nyist.edu.cn/pypi/
-   大连东软
    -   http://mirrors.neusoft.edu.cn/pypi/web/
-   上海交通大学
    -   https://mirror.sjtu.edu.cn/pypi/web/simple/

🔝回到顶部

### Composer

_Composer_ 是 PHP 的一个依赖管理工具，需要 PHP 5.3.2 以上才能运行。

#### Configuration

配置`PHP`代理，需进行如下配置：

-   全局配置（推荐）
    -   所有项目都会使用该镜像地址：
        
        ```
        composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
        ```
        
    -   取消配置：
        
        ```
        composer config -g --unset repos.packagist
        ```
        
-   项目配置
    -   仅修改当前工程配置，仅当前工程可使用该镜像地址：
        
        ```
        composer config repo.packagist composer https://mirrors.aliyun.com/composer/
        ```
        
    -   取消配置：
        
        ```
        composer config --unset repos.packagist
        ```
        

参考：https://developer.aliyun.com/composer

#### Mirrors

目前代理外部私仓有：

-   Aliyun
    -   https://mirrors.aliyun.com/composer/
-   Tencent
    -   https://mirrors.cloud.tencent.com/composer/
-   Packagist
    -   https://packagist.phpcomposer.com
-   上海交通
    -   https://packagist.mirrors.sjtug.sjtu.edu.cn

🔝回到顶部

### Rubygems

_RubyGems_ 是 Ruby 的一个包管理器，它提供一个分发 Ruby 程序和库的标准格式，还提供一个管理程序包安装的工具。

#### Configuration

配置`Ruby`代理，需进行如下配置：

# 首先，查看当前源：
$ gem sources -l
\*\*\* CURRENT SOURCES \*\*\*
https://rubygems.org/

# 接着，移除 https://rubygems.org/ ，并添加国内下载源 https://gems.ruby-china.com/ 。
$ gem sources --remove https://rubygems.org/
$ gem sources -a https://gems.ruby-china.com/
$ gem sources -l
\*\*\* CURRENT SOURCES \*\*\*

https://gems.ruby-china.com/

# 请确保只有 gems.ruby-china.com
$ gem install rails

参考：https://www.runoob.com/ruby/ruby-rubygems.html

#### Mirrors

目前代理外部私仓有：

-   Aliyun
    -   https://mirrors.aliyun.com/rubygems/
-   Tencent
    -   https://mirrors.cloud.tencent.com/rubygems/
-   HUAWEI
    -   https://repo.huaweicloud.com/repository/rubygems/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/rubygems/
-   中科大
    -   https://mirrors.ustc.edu.cn/rubygems/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/rubygems/
-   南京大学
    -   https://mirror.nju.edu.cn/rubygems/

🔝回到顶部

### Maven

#### Configuration

Java 系的工具版本规范如下：

-   `JDK：`1.8.0\_292
-   `MVN：`3.3.9

配置 Maven 代理，参考配置文件： settings.xml

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/repository/maven/
-   Maven Central Repository
    -   https://repo1.maven.org/maven2/
-   Aliyun
    -   http://maven.aliyun.com/nexus/content/groups/public/
-   Tencent
    -   https://mirrors.cloud.tencent.com/maven/
-   Apache Maven
    -   https://repo.maven.apache.org/maven2
    -   https://repository.apache.org/content/groups/snapshots
    -   https://repository.apache.org/content/groups/staging/
    -   https://repository.apache.org/content/groups/public/
-   confluent
    -   http://packages.confluent.io/maven/
-   jboss
    -   https://repository.jboss.org/nexus/content/groups/public
-   Lss233's.Mirror（供 Minecraft 开发使用）
    -   http://lss233.littleservice.cn/repositories/minecraft

🔝回到顶部

### Yum

#### Configuration

如果`CentOS`服务器要接入私服`yum`源，则清空本地 `/etc/yum.repos.d`的内容，添加如下内容：

$ cat \>> /etc/yum.repos.d/nexus.repo << 'EOF'
\[nexus\]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/yum/$releasever/os/$basearch/
enabled=1
gpgcheck=0
\[nexus-local\]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/eryajf-yum-local/
enabled=1
gpgcheck=0
EOF

然后执行如下命令：

yum clean all
yum makecache

#### Mirrors

目前代理外部源：

-   Aliyun
    -   https://mirrors.aliyun.com/centos/
-   HUAWEI
    -   https://repo.huaweicloud.com/centos/
-   Tencent
    -   https://mirrors.cloud.tencent.com/centos/
-   兰州大学
    -   https://mirror.lzu.edu.cn/centos/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/centos/
-   华中科技大学
    -   https://mirrors.ustc.edu.cn/centos/
-   浙江大学
    -   http://mirrors.zju.edu.cn/centos/
-   souhu
    -   http://mirrors.sohu.com/centos/
-   163：
    -   http://mirrors.163.com/centos/

🔝回到顶部

### Remi

Remi repository 是包含最新版本 PHP 和 MySQL 包的 Linux 源，由 Remi 提供维护。

官方地址：https://rpms.remirepo.net/

#### Configuration

详情参考：https://wiki.eryajf.net/pages/f35986

yum install -y epel-release
yum install -y https://mirrors.tuna.tsinghua.edu.cn/remi/enterprise/remi-release-7.rpm

#### Mirrors

目前代理外部源：

-   Aliyun
    -   https://mirrors.aliyun.com/remi/
-   HUAWEI
    -   https://repo.huaweicloud.com/remi/
-   火山引擎
    -   https://mirrors.volces.com/remi/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/remi/
-   中科大
    -   https://mirrors.ustc.edu.cn/remi/
-   上海交通
    -   http://ftp.sjtu.edu.cn/remi/
-   首都在线
    -   http://mirrors.yun-idc.com/remi/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/remi/
-   南京大学
    -   https://mirror.nju.edu.cn/remi/

🔝回到顶部

### Epel

EPEL 的全称叫 Extra Packages for Enterprise Linux。EPEL 是由 Fedora 社区打造，为 RHEL 及衍生发行版如 CentOS、Scientific Linux 等提供高质量软件包的项目。

官方地址：https://docs.fedoraproject.org/en-US/epel/

#### Configuration

# 备份
mv /etc/yum.repos.d/epel.repo /etc/yum.repos.d/epel.repo.backup
mv /etc/yum.repos.d/epel-testing.repo /etc/yum.repos.d/epel-testing.repo.backup

# 下载
wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo

#### Mirrors

目前代理外部源：

-   Aliyun
    -   https://mirrors.aliyun.com/epel/
-   Tencent
    -   https://mirrors.cloud.tencent.com/epel/
-   HUAWEI
    -   https://repo.huaweicloud.com/epel/
-   火山引擎
    -   https://mirrors.volces.com/epel/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/epel/
-   中科大
    -   https://mirrors.ustc.edu.cn/epel/
-   浙江大学
    -   http://mirrors.zju.edu.cn/epel/
-   兰州大学
    -   https://mirror.lzu.edu.cn/epel/
-   上海交通
    -   http://ftp.sjtu.edu.cn/epel/
-   首都在线
    -   http://mirrors.yun-idc.com/epel/
-   大连东软
    -   http://mirrors.neusoft.edu.cn/epel/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/epel/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/epel/
-   公云
    -   https://mirrors.pubyun.com/epel/

🔝回到顶部

### Homebrew

#### Configuration

如果你使用了 zsh，那么配置方式如下：

echo 'export HOMEBREW\_BREW\_GIT\_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' \>> ~/.zshrc
echo 'export HOMEBREW\_CORE\_GIT\_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"' \>> ~/.zshrc
echo 'export HOMEBREW\_BOTTLE\_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"' \>> ~/.zshrc

source ~/.zshrc
brew update

参考：Homebrew 替换国内镜像源

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/homebrew/
-   Tencent
    -   https://mirrors.cloud.tencent.com/homebrew/
-   清华：
    -   https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/homebrew/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/help/homebrew/

🔝回到顶部

### cargo

rust 包管理镜像源

#### Configuration

修改文件`~/.cargo/config`(没有则新建)

```
[source.crates-io]
replace-with = 'rsproxy'

[source.rsproxy]
registry = "https://rsproxy.cn/crates.io-index"

[registries.rsproxy]
index = "https://rsproxy.cn/crates.io-index"

[net]
git-fetch-with-cli = true
```

#### Mirrors

-   字节
    -   https://rsproxy.cn
-   中国科学技术大学
    -   https://mirrors.ustc.edu.cn/help/crates.io-index.html
-   清华：
    -   https://mirrors.tuna.tsinghua.edu.cn/help/crates.io-index.git/
-   上海交通大学
    -   https://mirrors.sjtug.sjtu.edu.cn/docs/git/crates.io-index
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/help/crates.io-index.git/

🔝回到顶部

Software-Mirror
---------------

还有一些软件，直接通过官方下载比较困难，也整理出方便下载的国内优质镜像。

### JDK

#### Official

-   https://openjdk.org/

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/java/jdk/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/Adoptium/
-   编程宝库
    -   http://www.codebaoku.com/jdk/jdk-index.html
-   injdk
    -   https://www.injdk.cn/

🔝回到顶部

### Docker

#### Official

-   https://docs.docker.com/engine/install/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/docker-ce
-   Tencent
    -   https://mirrors.cloud.tencent.com/docker-ce/
-   HUAWEI
    -   https://repo.huaweicloud.com/docker-ce/
-   火山引擎
    -   https://mirrors.volces.com/docker/
-   北大
    -   https://mirrors.pku.edu.cn/docker-ce/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/docker-ce/
-   中科大
    -   https://mirrors.ustc.edu.cn/docker-ce/
-   浙江大学
    -   http://mirrors.zju.edu.cn/docker-ce/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/docker-ce/
-   上海交通
    -   https://mirror.sjtu.edu.cn/docker-ce/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/docker-ce/
-   南京大学
    -   https://mirror.nju.edu.cn/docker-ce/

🔝回到顶部

### Kubernetes

#### Official

-   https://kubernetes.io/releases/download/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/kubernetes
-   Tencent
    -   https://mirrors.cloud.tencent.com/kubernetes/
-   HUAWEI
    -   https://repo.huaweicloud.com/kubernetes/
-   火山引擎
    -   https://mirrors.volces.com/kubernetes/
-   北大
    -   https://mirrors.pku.edu.cn/kubernetes/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/kubernetes/
-   中科大
    -   https://mirrors.ustc.edu.cn/kubernetes/

🔝回到顶部

### K3s

#### Official

-   https://github.com/k3s-io/k3s/releases/

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/github-release/k3s-io/k3s/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/github-release/k3s-io/k3s/
-   南京大学
    -   https://mirror.nju.edu.cn/github-release/k3s-io/k3s/

🔝回到顶部

### Minikube

#### Official

-   https://github.com/kubernetes/minikube/releases

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/github-release/kubernetes/minikube/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/github-release/kubernetes/minikube/
-   南京大学
    -   https://mirror.nju.edu.cn/github-release/kubernetes/minikube/

🔝回到顶部

### Helm

#### Official

-   https://helm.sh/docs/intro/install/

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/helm/

🔝回到顶部

### Harbor

#### Official

-   https://github.com/goharbor/harbor/releases

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/github-release/goharbor/harbor/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/github-release/goharbor/harbor/
-   南京大学
    -   https://mirror.nju.edu.cn/github-release/goharbor/harbor/

🔝回到顶部

### Jenkins

#### Official

-   安装包-稳定版：https://get.jenkins.io/war-stable/
-   安装包-开发版：https://get.jenkins.io/war/
-   插件：https://plugins.jenkins.io/

#### Mirrors

-   Aliyun
    -   安装包-稳定版：https://mirrors.aliyun.com/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.aliyun.com/jenkins/war/
    -   插件：https://mirrors.aliyun.com/jenkins/plugins/
-   Tencent
    -   安装包-稳定版：https://mirrors.cloud.tencent.com/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.cloud.tencent.com/jenkins/war/
    -   插件：https://mirrors.cloud.tencent.com/jenkins/plugins/
-   HUAWEI
    -   安装包-稳定版：https://repo.huaweicloud.com/jenkins/war-stable/
    -   安装包-开发版：https://repo.huaweicloud.com/jenkins/war/
    -   插件：https://repo.huaweicloud.com/jenkins/plugins/
-   火山引擎
    -   安装包-稳定版：https://mirrors.volces.com/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.volces.com/jenkins/war/
    -   插件：https://mirrors.volces.com/jenkins/plugins/
-   中科大
    -   安装包-稳定版：https://mirrors.ustc.edu.cn/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.ustc.edu.cn/jenkins/war/
    -   插件：https://mirrors.ustc.edu.cn/jenkins/plugins/
-   清华
    -   安装包-稳定版：https://mirrors.tuna.tsinghua.edu.cn/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.tuna.tsinghua.edu.cn/jenkins/war/
    -   插件：https://mirrors.tuna.tsinghua.edu.cn/jenkins/plugins/
-   北京外国语大学
    -   安装包-稳定版：https://mirrors.bfsu.edu.cn/jenkins/war-stable/
    -   安装包-开发版：https://mirrors.bfsu.edu.cn/jenkins/war/
    -   插件：https://mirrors.bfsu.edu.cn/jenkins/plugins/
-   南京大学
    -   安装包-稳定版：https://mirror.nju.edu.cn/jenkins/war-stable
    -   安装包-开发版：https://mirror.nju.edu.cn/jenkins/war
    -   插件：https://mirror.nju.edu.cn/jenkins/plugins

🔝回到顶部

### GitLab-ce

#### Official

-   https://packages.gitlab.com/gitlab/gitlab-ce

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/gitlab-ce/
-   Tencent
    -   https://mirrors.cloud.tencent.com/gitlab-ce/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/
-   南京大学
    -   https://mirror.nju.edu.cn/gitlab-ce/

🔝回到顶部

### GitLab-runner

#### Official

-   https://docs.gitlab.com/runner/install/

#### Mirrors

-   Tencent
    -   https://mirrors.cloud.tencent.com/gitlab-runner/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/gitlab-runner/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/gitlab-runner/
-   南京大学
    -   https://mirror.nju.edu.cn/gitlab-runner/

🔝回到顶部

### ElasticSearch

#### Official

-   https://www.elastic.co/cn/downloads/elasticsearch

#### Mirrors

-   elastic 中文社区
    -   https://elasticsearch.cn/download/
-   Aliyun
    -   https://mirrors.aliyun.com/elasticstack/
-   HUAWEI
    -   https://repo.huaweicloud.com/elasticsearch/
-   Tencent
    -   https://mirrors.cloud.tencent.com/elasticstack/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/elasticstack/

🔝回到顶部

### Logstash

#### Official

-   https://www.elastic.co/cn/downloads/logstash

#### Mirrors

-   elastic 中文社区
    -   https://elasticsearch.cn/download/
-   HUAWEI
    -   https://repo.huaweicloud.com/logstash/

🔝回到顶部

### Kibana

#### Official

-   https://www.elastic.co/cn/downloads/kibana

#### Mirrors

-   elastic 中文社区
    -   https://elasticsearch.cn/download/
-   HUAWEI
    -   https://repo.huaweicloud.com/kibana/

🔝回到顶部

### Filebeat

#### Official

-   https://www.elastic.co/cn/downloads/beats/filebeat

#### Mirrors

-   elastic 中文社区
    -   https://elasticsearch.cn/download/
-   HUAWEI
    -   https://repo.huaweicloud.com/filebeat/

🔝回到顶部

### MySQL

#### Official

-   https://dev.mysql.com/downloads/repo/yum/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/mysql
-   HUAWEI
    -   https://repo.huaweicloud.com/mysql/Downloads/
-   Tencent
    -   https://mirrors.cloud.tencent.com/mysql/
-   Souhu
    -   http://mirrors.sohu.com/mysql/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/mysql/
-   中科大
    -   https://mirrors.ustc.edu.cn/mysql-ftp/Downloads/
-   南阳理工
    -   https://mirror.nyist.edu.cn/mysql/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/mysql/
-   南京大学
    -   https://mirror.nju.edu.cn/mysql/

🔝回到顶部

### MariaDB

#### Official

-   https://mariadb.org/download/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/mariadb
-   Tencent
    -   https://mirrors.cloud.tencent.com/mariadb/
-   HUAWEI
    -   https://repo.huaweicloud.com/mariadb/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/mariadb/
-   中科大
    -   https://mirrors.ustc.edu.cn/mariadb/

🔝回到顶部

### Percona

#### Official

-   https://www.percona.com/downloads/

#### Mirrors

-   Tencent
    -   https://mirrors.cloud.tencent.com/percona/
-   火山引擎
    -   https://mirrors.volces.com/percona/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/percona/
-   中科大
    -   https://mirrors.ustc.edu.cn/percona/

🔝回到顶部

### MongoDB

#### Official

-   https://www.mongodb.com/try/download/community

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/mongodb
-   Tencent
    -   https://mirrors.cloud.tencent.com/mongodb/
-   火山引擎
    -   https://mirrors.volces.com/mongodb/
-   163
    -   http://mirrors.163.com/mongodb/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/mongodb/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/mongodb/
-   南京大学
    -   https://mirror.nju.edu.cn/mongodb/

🔝回到顶部

### Redis

#### Official

-   https://redis.io/download/

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/redis/

🔝回到顶部

### PostgreSQL

#### Official

-   https://www.postgresql.org/download/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/postgresql/
-   Tencen
    -   https://mirrors.cloud.tencent.com/postgresql/
-   HUAWEI
    -   https://repo.huaweicloud.com/postgresql/
-   火山引擎
    -   https://mirrors.volces.com/postgresql/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/postgresql/
-   中科大
    -   https://mirrors.ustc.edu.cn/postgresql/
-   浙江大学
    -   http://mirrors.zju.edu.cn/postgresql/
-   南阳理工
    -   https://mirror.nyist.edu.cn/postgresql/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/postgresql/
-   南京大学
    -   https://mirror.nju.edu.cn/postgresql/

🔝回到顶部

### Golang

#### Official

-   https://go.dev/dl/

#### Mirrors

-   Go 语言中文网
    -   https://studygolang.com/dl
-   Aliyun
    -   https://mirrors.aliyun.com/golang/
-   中科大
    -   https://mirrors.ustc.edu.cn/golang/
-   南京大学
    -   https://mirror.nju.edu.cn/golang/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/golang/

🔝回到顶部

### Node

#### Official

-   https://nodejs.org/en/download/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/nodejs-release/
-   HUAWEI
    -   https://repo.huaweicloud.com/nodejs/
-   Tencent
    -   https://mirrors.cloud.tencent.com/nodejs-release/
-   火山引擎
    -   https://mirrors.volces.com/nodejs-release/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/nodejs-release/
-   中科大
    -   https://mirrors.ustc.edu.cn/node/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/nodejs-release/

🔝回到顶部

### Yarn

#### Official

-   https://github.com/yarnpkg/yarn/releases

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/yarn/

🔝回到顶部

### Python

#### Official

-   https://www.python.org/downloads/

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/python/
-   北京交通
    -   https://mirror.bjtu.edu.cn/python/
-   淘宝 NPM
    -   https://registry.npmmirror.com/binary.html?path=python

🔝回到顶部

### Rust

#### Official

-   https://forge.rust-lang.org/infra/other-installation-methods.html

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/rustup/
-   上海交通大学
    -   https://mirror.sjtu.edu.cn/rust-static/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/rustup/

🔝回到顶部

### Maven

#### Official

-   https://maven.apache.org/download.cgi

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/apache/maven/maven-3/

🔝回到顶部

### Zabbix

#### Official

-   https://www.zabbix.com/cn/download

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/zabbix
-   HUAWEI
    -   https://repo.huaweicloud.com/zabbix/
-   Tencent
    -   https://mirrors.cloud.tencent.com/zabbix/
-   火山引擎
    -   https://mirrors.volces.com/zabbix/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/zabbix/
-   南阳理工
    -   https://mirror.nyist.edu.cn/zabbix/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/zabbix/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/zabbix/

🔝回到顶部

### Prometheus

#### Official

-   https://prometheus.io/download/

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/github-release/prometheus/prometheus/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/github-release/prometheus/prometheus/
-   南京大学
    -   https://mirror.nju.edu.cn/github-release/prometheus/
-   上海交通大学
    -   https://mirror.sjtu.edu.cn/github-release/prometheus/?mirror\_intel\_list 此地址下包含了 prometheus 应用体系的大部分软件，包含：
        -   alertmanager
        -   blackbox\_exporter
        -   consul\_exporter
        -   graphite\_exporter
        -   haproxy\_exporter
        -   memcached\_exporter
        -   mysqld\_exporter
        -   node\_exporter
        -   prometheus
        -   pushgateway
        -   statsd\_exporter

🔝回到顶部

### Grafana

#### Official

-   https://grafana.com/grafana/download

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/grafana
-   HUAWEI
    -   https://repo.huaweicloud.com/grafana/
-   Tencent
    -   https://mirrors.cloud.tencent.com/grafana/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/grafana/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/grafana/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/grafana/
-   南京大学
    -   https://mirror.nju.edu.cn/grafana/

🔝回到顶部

### Pinpoint

#### Official

-   https://github.com/pinpoint-apm/pinpoint/releases

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/pinpoint/

🔝回到顶部

### Apache

#### Official

-   https://httpd.apache.org/download.cgi

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/apache
-   HUAWEI
    -   https://repo.huaweicloud.com/apache/
-   Tencent
    -   https://mirrors.cloud.tencent.com/apache/
-   Souhu
    -   http://mirrors.sohu.com/apache/
-   北大
    -   https://mirrors.pku.edu.cn/apache/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/apache/
-   中科大
    -   https://mirrors.ustc.edu.cn/apache/
-   北京交通
    -   https://mirror.bjtu.edu.cn/apache/
-   南京大学
    -   https://mirror.nju.edu.cn/apache/

🔝回到顶部

### Nginx

#### Official

-   http://nginx.org/en/download.html

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/nginx/
-   Souhu
    -   http://mirrors.sohu.com/nginx/
-   中科大
    -   https://mirrors.ustc.edu.cn/nginx/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/nginx/
-   南京大学
    -   https://mirror.nju.edu.cn/nginx/

🔝回到顶部

### OpenResty

#### Official

-   https://openresty.org/cn/download.html

#### Mirrors

-   Tencent
    -   https://mirrors.cloud.tencent.com/openresty/
-   HUAWEI
    -   https://repo.huaweicloud.com/openresty/
-   中科大
    -   https://mirrors.ustc.edu.cn/openresty/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/openresty/
-   南京大学
    -   https://mirror.nju.edu.cn/openresty/

🔝回到顶部

### Keepalived

#### Official

-   https://www.keepalived.org/download.html

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/keepalived/

🔝回到顶部

### Ceph

#### Official

-   https://docs.ceph.com/en/quincy/install/get-packages/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/ceph
-   Tencent
    -   https://mirrors.cloud.tencent.com/ceph/
-   HUAWEI
    -   https://repo.huaweicloud.com/ceph/
-   163
    -   http://mirrors.163.com/ceph/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/ceph/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/ceph/
-   中科大
    -   https://mirrors.ustc.edu.cn/ceph/
-   南京大学
    -   https://mirror.nju.edu.cn/ceph/

🔝回到顶部

### Influxdata

#### Official

-   https://portal.influxdata.com/downloads/

#### Mirrors

-   Tencent
    -   https://mirrors.cloud.tencent.com/influxdata/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/influxdata/
-   中科大
    -   https://mirrors.ustc.edu.cn/influxdata/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/influxdata/
-   南京大学
    -   https://mirror.nju.edu.cn/influxdata/

🔝回到顶部

### ClickHouse

#### Official

-   https://clickhouse.com/#quick-start

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/clickhouse/
-   火山引擎
    -   https://mirrors.volces.com/clickhouse/

🔝回到顶部

### Rabbitmq

#### Official

-   https://www.rabbitmq.com/download.html

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/rabbitmq-server/

🔝回到顶部

### ETCD

#### Official

-   https://github.com/etcd-io/etcd/releases

#### Mirrors

-   HUAWEI
    -   https://repo.huaweicloud.com/etcd/

🔝回到顶部

### WireShark

#### Official

-   https://www.wireshark.org/

#### Mirrors

-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/wireshark/
-   上海交通大学
    -   https://mirror.sjtu.edu.cn/wireshark/

🔝回到顶部

### Virtualbox

#### Official

-   https://www.virtualbox.org/wiki/Downloads

#### Mirrors

-   Tencent
    -   https://mirrors.cloud.tencent.com/virtualbox/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/virtualbox/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/virtualbox/

🔝回到顶部

### iina

#### Official

-   https://github.com/iina/iina/releases/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/iina/
-   Tencent
    -   https://mirrors.cloud.tencent.com/iina/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/iina/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/iina/
-   南京大学
    -   https://mirror.nju.edu.cn/iina/

🔝回到顶部

### chromium

#### Official

-   https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html

#### Mirrors

-   Aliyun
    -   https://registry.npmmirror.com/binary.html?path=chromium-browser-snapshots/
-   huaweicloud
    -   https://repo.huaweicloud.com/chromium-browser-snapshots/
-   ungoogled-software.github.io(ungoogle chromium)
    -   https://ungoogled-software.github.io/ungoogled-chromium-binaries/releases/

🔝回到顶部

System-Mirror
-------------

系统镜像，又大又远，更需要找到好用优秀的国内镜像。

### CentOS

尽管 CentOS 不再更新了，但它仍旧并且还将持续是国内企业系统主力军。

可能官方考虑到下载困难的问题，官方也列出了距离使用者更近的镜像列表，可谓贴心。

#### Official

-   https://www.centos.org/download/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/centos/
-   Tencent
    -   https://mirrors.cloud.tencent.com/centos/
-   HUAWEI
    -   https://repo.huaweicloud.com/centos/
-   火山引擎
    -   https://mirrors.volces.com/centos/
-   163
    -   http://mirrors.163.com/centos/
-   Souhu
    -   http://mirrors.sohu.com/centos/
-   北大
    -   https://mirrors.pku.edu.cn/centos/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/centos/
-   中科大
    -   https://mirrors.ustc.edu.cn/centos/
-   浙江大学
    -   http://mirrors.zju.edu.cn/centos/
-   兰州大学
    -   https://mirror.lzu.edu.cn/centos/
-   上海交通
    -   http://ftp.sjtu.edu.cn/centos/
-   首都在线
    -   http://mirrors.yun-idc.com/centos/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/centos/
-   公云
    -   https://mirrors.pubyun.com/centos/
-   北京交通
    -   https://mirror.bjtu.edu.cn/centos/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/centos/
-   南京大学
    -   https://mirror.nju.edu.cn/centos/

🔝回到顶部

### CentOS-altarch

ARM 架构下的 CentOS 镜像。

#### Official

-   https://www.centos.org/download/

#### Mirrors

-   Aliyun
    -   https://developer.aliyun.com/mirror/centos-altarch
-   Tencent
    -   https://mirrors.cloud.tencent.com/centos-altarch/
-   HUAWEI
    -   https://repo.huaweicloud.com/centos-altarch/
-   火山引擎
    -   https://mirrors.volces.com/centos-altarch/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/centos-altarch/
-   中科大
    -   https://mirrors.ustc.edu.cn/centos-altarch/
-   兰州大学
    -   https://mirror.lzu.edu.cn/centos-altarch/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/centos-altarch/
-   南京大学
    -   https://mirror.nju.edu.cn/centos-altarch/

🔝回到顶部

### Ubuntu

#### Official

-   官方镜像：https://ubuntu.com/download

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/ubuntu/
-   Tencent
    -   https://mirrors.cloud.tencent.com/ubuntu/
-   HUAWEI
    -   https://repo.huaweicloud.com/ubuntu/
-   火山引擎
    -   https://mirrors.volces.com/ubuntu/
-   163
    -   http://mirrors.163.com/ubuntu/
-   Souhu
    -   http://mirrors.sohu.com/ubuntu/
-   北大
    -   https://mirrors.pku.edu.cn/ubuntu/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/ubuntu/
-   中科大
    -   https://mirrors.ustc.edu.cn/ubuntu/
-   浙江大学
    -   http://mirrors.zju.edu.cn/ubuntu/
-   兰州大学
    -   https://mirror.lzu.edu.cn/ubuntu/
-   大连东软
    -   http://mirrors.neusoft.edu.cn/ubuntu/
-   上海交通
    -   http://ftp.sjtu.edu.cn/ubuntu/
-   首都在线
    -   http://mirrors.yun-idc.com/ubuntu/
-   南阳理工
    -   https://mirror.nyist.edu.cn/ubuntu/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/ubuntu/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/ubuntu/
-   北京交通
    -   https://mirror.bjtu.edu.cn/ubuntu/
-   南京大学
    -   https://mirror.nju.edu.cn/ubuntu/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/ubuntu/

🔝回到顶部

### Debian

#### Official

-   官方镜像：https://www.debian.org/mirror/
-   全球镜像：https://www.debian.org/mirror/list

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/debian/
-   Tencent
    -   https://mirrors.cloud.tencent.com/debian/
-   HUAWEI
    -   https://repo.huaweicloud.com/debian/
-   火山引擎
    -   https://mirrors.volces.com/debian/
-   163
    -   http://mirrors.163.com/debian/
-   Souhu
    -   http://mirrors.sohu.com/debian/
-   北大
    -   https://mirrors.pku.edu.cn/debian/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/debian/
-   中科大
    -   https://mirrors.ustc.edu.cn/debian/
-   浙江大学
    -   http://mirrors.zju.edu.cn/debian/
-   兰州大学
    -   https://mirror.lzu.edu.cn/debian/
-   大连东软
    -   http://mirrors.neusoft.edu.cn/debian/
-   上海交通
    -   http://ftp.sjtu.edu.cn/debian/
-   首都在线
    -   http://mirrors.yun-idc.com/debian/
-   南阳理工
    -   https://mirror.nyist.edu.cn/debian/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/debian/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/debian/
-   公云
    -   https://mirrors.pubyun.com/debian/
-   北京交通
    -   https://mirror.bjtu.edu.cn/debian/
-   南京大学
    -   https://mirror.nju.edu.cn/debian/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/debian/

🔝回到顶部

### Deepin

#### Official

-   官方镜像：https://www.deepin.org/zh/download/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/deepin/
-   HUAWEI
    -   https://repo.huaweicloud.com/deepin/
-   163
    -   http://mirrors.163.com/deepin/
-   Souhu
    -   http://mirrors.sohu.com/deepin/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/deepin/
-   中科大
    -   https://mirrors.ustc.edu.cn/deepin/
-   浙江大学
    -   http://mirrors.zju.edu.cn/deepin/
-   兰州大学
    -   https://mirror.lzu.edu.cn/deepin/
-   上海交通
    -   http://ftp.sjtu.edu.cn/deepin/
-   南阳理工
    -   https://mirror.nyist.edu.cn/deepin/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/deepin/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/deepin/
-   南京大学
    -   https://mirror.nju.edu.cn/deepin/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/deepin/

🔝回到顶部

### Fedora

#### Official

-   官方镜像：https://getfedora.org/en/server/download/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/fedora/
-   Tencent
    -   https://mirrors.cloud.tencent.com/fedora/
-   HUAWEI
    -   https://repo.huaweicloud.com/fedora/
-   火山引擎
    -   https://mirrors.volces.com/fedora/
-   163
    -   http://mirrors.163.com/fedora/
-   Souhu
    -   http://mirrors.sohu.com/fedora/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/fedora/
-   中科大
    -   https://mirrors.ustc.edu.cn/fedora/
-   浙江大学
    -   http://mirrors.zju.edu.cn/fedora/
-   兰州大学
    -   https://mirror.lzu.edu.cn/fedora/
-   上海交通
    -   http://ftp.sjtu.edu.cn/fedora/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/fedora/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/fedora/
-   南京大学
    -   https://mirror.nju.edu.cn/fedora/

🔝回到顶部

### Alpine

#### Official

-   官方镜像：https://dl-cdn.alpinelinux.org/alpine/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/alpine/
-   Tencent
    -   https://mirrors.cloud.tencent.com/alpine/
-   HUAWEI
    -   https://repo.huaweicloud.com/alpine/
-   火山引擎
    -   https://mirrors.volces.com/alpine/
-   中科大
    -   https://mirrors.ustc.edu.cn/alpine/
-   兰州大学
    -   https://mirror.lzu.edu.cn/alpine/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/alpine/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/alpine/
-   清华大学
    -   https://mirrors.tuna.tsinghua.edu.cn/alpine/
-   上海交大
    -   https://mirrors.sjtug.sjtu.edu.cn/alpine/
-   南方科技大学
    -   https://mirrors.sustech.edu.cn/alpine/
-   北京交通
    -   https://mirror.bjtu.edu.cn/alpine/
-   南京大学
    -   https://mirror.nju.edu.cn/alpine/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/alpine/

🔝回到顶部

### Void

#### Official

-   官方镜像：https://voidlinux.org/

#### Mirrors

-   清华大学
    -   https://mirrors.tuna.tsinghua.edu.cn/voidlinux/
-   上海交大
    -   https://mirror.sjtu.edu.cn/voidlinux/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/voidlinux/
-   南京大学
    -   https://mirror.nju.edu.cn/voidlinux/

🔝回到顶部

### Gentoo

#### Official

-   官方镜像：https://www.gentoo.org/downloads/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/gentoo/
-   Tencent
    -   https://mirrors.cloud.tencent.com/gentoo/
-   HUAWEI
    -   https://repo.huaweicloud.com/gentoo/
-   163
    -   http://mirrors.163.com/gentoo/
-   Souhu
    -   http://mirrors.sohu.com/gentoo/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/gentoo/
-   中科大
    -   https://mirrors.ustc.edu.cn/gentoo/
-   浙江大学
    -   http://mirrors.zju.edu.cn/gentoo/
-   兰州大学
    -   https://mirror.lzu.edu.cn/gentoo/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/gentoo/
-   上海交通
    -   https://mirrors.sjtug.sjtu.edu.cn/gentoo/
-   南京大学
    -   https://mirror.nju.edu.cn/gentoo/

🔝回到顶部

### kali

#### Official

-   https://www.kali.org/get-kali/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/kali/
-   Tencent
    -   https://mirrors.cloud.tencent.com/kali/
-   HUAWEI
    -   https://repo.huaweicloud.com/kali/
-   火山引擎
    -   https://mirrors.volces.com/kali/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/kali/
-   中科大
    -   https://mirrors.ustc.edu.cn/kali/
-   浙江大学
    -   http://mirrors.zju.edu.cn/kali/
-   南阳理工
    -   https://mirror.nyist.edu.cn/kali/
-   大连东软
    -   http://mirrors.neusoft.edu.cn/kali/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/kali-images/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/kali/
-   上海交通大学
    -   https://mirrors.sjtug.sjtu.edu.cn/kali/
-   北京交通
    -   https://mirror.bjtu.edu.cn/kali/
-   西北农林科技大学
    -   https://mirrors.nwsuaf.edu.cn/kali/
-   南京大学
    -   https://mirror.nju.edu.cn/kali/
-   华中科技大学
    -   https://mirrors.hust.edu.cn/kali/

🔝回到顶部

### Opensuse

#### Official

-   https://get.opensuse.org/zh\_CN/

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/opensuse/
-   Tencent
    -   https://mirrors.cloud.tencent.com/opensuse/
-   HUAWEI
    -   https://repo.huaweicloud.com/opensuse/
-   火山引擎
    -   https://mirrors.volces.com/opensuse/
-   Souhu
    -   http://mirrors.sohu.com/opensuse/
-   北大
    -   https://mirrors.pku.edu.cn/opensuse/
-   中科大
    -   https://mirrors.ustc.edu.cn/opensuse/
-   兰州大学
    -   https://mirror.lzu.edu.cn/opensuse/
-   上海交通
    -   http://ftp.sjtu.edu.cn/opensuse/
-   首都在线
    -   http://mirrors.yun-idc.com/opensuse/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/opensuse/
-   重庆大学
    -   https://mirrors.cqu.edu.cn/opensuse/
-   南方科技大学
    -   https://mirrors.sustech.edu.cn/opensuse/
-   北京外国语大学
    -   https://mirrors.bfsu.edu.cn/opensuse/
-   北京交通
    -   https://mirror.bjtu.edu.cn/opensuse/
-   南京大学
    -   http://mirror.nju.edu.cn/opensuse/

🔝回到顶部

### FreeBSD

#### Official

-   https://download.FreeBSD.org/

#### Mirrors

注意：FreeBSD 有四类源：pkg、ports、portsnap、update。不是所有镜像站都同时支持上述四类源。目前在大陆境内没有官方镜像站，以下均为非官方镜像站。

##### pkg 源：pkg 源提供二进制安装包

pkg 的下载路径是 `/var/cache/pkg/`

FreeBSD 中 pkg 源分为系统级和用户级两个配置文件。不建议直接修改 `/etc/pkg/FreeBSD.conf` ,因为该文件会随着基本系统的更新而发生改变。

创建用户级源目录:

```
# mkdir -p /usr/local/etc/pkg/repos
```

###### 网易开源镜像站

创建用户级源文件:

```
# ee /usr/local/etc/pkg/repos/163.conf
```

写入以下内容:

```
163: {
url: "pkg+http://mirrors.163.com/freebsd-pkg/${ABI}/quarterly",
mirror_type: "srv",
signature_type: "none",
fingerprints: "/usr/share/keys/pkg",
enabled: yes
}
FreeBSD: { enabled: no }
```

> 故障排除
> 
> **若要获取滚动更新的包，请将 `quarterly` 修改为 `latest`。二者区别见 FreeBSD 手册。请注意, `CURRENT` 版本只有 `latest`：**
> 
> ```
> # sed -i '' 's/quarterly/latest/g' /etc/pkg/FreeBSD.conf
> ```

> 若要使用 https，请先安装 `security/ca_root_nss`，并将 `http` 修改为 `https`，最后使用命令 `# pkg update -f` 刷新缓存即可。

###### 中国科学技术大学开源软件镜像站

创建用户级源文件:

```
# ee /usr/local/etc/pkg/repos/ustc.conf
```

写入以下内容:

```
ustc: {
url: "pkg+http://mirrors.ustc.edu.cn/freebsd-pkg/${ABI}/quarterly",
mirror_type: "srv",
signature_type: "none",
fingerprints: "/usr/share/keys/pkg",
enabled: yes
}
FreeBSD: { enabled: no }
```

###### 南京大学开源镜像站

```
# ee /usr/local/etc/pkg/repos/nju.conf
```

写入以下内容:

```
nju: {
url: "pkg+http://mirrors.nju.edu.cn/freebsd-pkg/${ABI}/quarterly",
mirror_type: "srv",
signature_type: "none",
fingerprints: "/usr/share/keys/pkg",
enabled: yes
}
FreeBSD: { enabled: no }
```

###### FreeBSD.cn

```
# ee /usr/local/etc/pkg/repos/freebsdcn.conf
```

写入以下内容:

```
freebsdcn: {
url: "pkg+http://pkg.freebsd.cn/${ABI}/quarterly",
mirror_type: "srv",
signature_type: "none",
fingerprints: "/usr/share/keys/pkg",
enabled: yes
}
FreeBSD: { enabled: no }
```

##### ports 源：以源代码方式安装软件的包管理器

> ports 下载路径是 `/usr/ports/distfiles`。
> 
> **警告**
> 
> 只有 freebsd.cn 镜像站的 ports 镜像是完整的，其余的大概只镜像了不到十分之一。请优先考虑使用 FreeBSD.cn。见 ustclug/discussions#408。

###### FreeBSD.cn（推荐）

创建或修改文件 `# ee /etc/make.conf`:

写入以下内容（注意结尾的 / 是必须的！下同）:

`MASTER_SITE_OVERRIDE?=http://ports.freebsd.cn/ports-distfiles/${DIST_SUBDIR}/`

###### 网易开源镜像站（该镜像不完整）

创建或修改文件 `# ee /etc/make.conf`:

写入以下内容:

`MASTER_SITE_OVERRIDE?=http://mirrors.163.com/freebsd-ports/distfiles/${DIST_SUBDIR}/`

###### 中国科学技术大学开源软件镜像站（该镜像不完整）

创建或修改文件 `# ee /etc/make.conf`:

写入以下内容:

`MASTER_SITE_OVERRIDE?=http://mirrors.ustc.edu.cn/freebsd-ports/distfiles/${DIST_SUBDIR}/`

##### portsnap 源：打包的 ports 文件

###### FreeBSD.cn

编辑 portsnap 配置文件 `# ee /etc/portsnap.conf` :

将 `SERVERNAME=portsnap.FreeBSD.org` 修改为 `SERVERNAME=portsnap.FreeBSD.cn`

##### freebsd-update 源：提供基本系统更新

> 注意：只有一级架构的 release 版本才提供该源。也就是说 current 和 stable 是没有 freebsd-update 源的。 关于架构的支持等级说明请看：
> 
> https://www.freebsd.org/platforms

###### FreeBSD.cn

编辑 `# ee /etc/freebsd-update.conf` 文件:

将 `ServerName update.FreeBSD.org` 修改为 `ServerName update.FreeBSD.cn`

🔝回到顶部

### GNU

#### Official

-   https://www.gnu.org/software/octave/download

#### Mirrors

-   Aliyun
    -   https://mirrors.aliyun.com/gnu/
-   Tencent
    -   https://mirrors.cloud.tencent.com/gnu/
-   HUAWEI
    -   https://repo.huaweicloud.com/gnu/
-   火山引擎
    -   https://mirrors.volces.com/gnu/
-   清华
    -   https://mirrors.tuna.tsinghua.edu.cn/gnu/
-   中科大
    -   https://mirrors.ustc.edu.cn/gnu/
-   兰州大学
    -   https://mirror.lzu.edu.cn/gnu/
-   北京交通
    -   https://mirror.bjtu.edu.cn/gnu/
-   南京大学
    -   https://mirror.nju.edu.cn/gnu/

🔝回到顶部

Other-Mirror
------------

### Docker-hub

没有整理 Docker-hub 的镜像的原因是，鉴于这种仓库的特殊性，国内也确实没有一家将之全站镜像的，果真如此，倒也并不科学了。

不过关于 Docker-hub 以及 GitHub 的使用，又的确会经常遇到网络方面的问题，因此也一直在留心这方面的解决方案，目前大多是提供加速的方案，算是镜像方案之下的一个折中策略。

#### Official

-   https://hub.docker.com/

其他的镜像仓库不再单独列出。

#### Mirrors

**方案一：**

`使用方式：`

使用方式都是替换原来镜像的前缀域名即可实现加速效果，比如：

```
原来地址： eryajf/centos:7.4  # 这个是官方镜像，省略了前边的域名
替换地址： docker.mirrors.sjtug.sjtu.edu.cn/eryajf/centos:7.4
```

另外，加速通常只是针对某个源站进行的加速，国外对公开放的 docker 仓库并非官方一家，因此这里就以源站的维度进行区分，整理出经过测试可用的加速站。

-   Docker-hub
    -   上海交通大学
        -   docker.mirrors.sjtug.sjtu.edu.cn
    -   中科大
        -   docker.mirrors.ustc.edu.cn
    -   docker proxy
        -   dockerproxy.com
-   gcr.io
    -   南京大学
        -   gcr.nju.edu.cn
    -   docker proxy
        -   gcr.dockerproxy.com
    -   lank8s：后期可能会转成付费
        -   gcr.lank8s.cn
-   k8s.gcr.io
    -   上海交通大学
        -   k8s-gcr-io.mirrors.sjtug.sjtu.edu.cn
    -   南京大学
        -   gcr.nju.edu.cn/google-containers
    -   docker proxy
        -   k8s.dockerproxy.com
    -   lank8s
        -   lank8s.cn
-   ghcr.io
    -   docker proxy
        -   ghcr.dockerproxy.com
    -   南京大学
        -   ghcr.nju.edu.cn
-   quay.io
    -   中科大
        -   quay.mirrors.ustc.edu.cn
    -   南京大学
        -   quay.nju.edu.cn
-   nvcr.io
    -   南京大学
        -   ngc.nju.edu.cn
-   其他
    -   https://github.com/DaoCloud/public-image-mirror

**方案二：**

还有一种方案是通过将加速地址写入到 docker 配置文件当中实现加速。

在 `/etc/docker/daemon.json` 中写入如下内容（如果文件不存在请新建该文件）：

{
  "registry-mirrors": \[
    "https://hub-mirror.c.163.com"
  \]
}

注意，一定要保证该文件符合 json 规范，否则 Docker 将不能启动。

之后重新启动服务。

$ sudo systemctl daemon-reload
$ sudo systemctl restart docker

目前可用的加速地址有：

-   网易
    -   http://hub-mirror.c.163.com
-   ustc
    -   https://docker.mirrors.ustc.edu.cn
-   百度云
    -   https://mirror.baidubce.com/

🔝回到顶部

### GitHub

#### Official

-   https://github.com

#### Mirrors

GitHub 相关的国内镜像，有不同的使用方式，这里仅列出目前可用的国内镜像，具体用法请查阅镜像的官方说明。

-   https://gitclone.com/
    
    提供了 GitHub 全面的加速，详见官方文档。
    
-   https://mirror.ghproxy.com/
    
    GitHub 文件 , Releases , archive , gist , raw.githubusercontent.com 文件代理加速下载服务，使用细则参见官方。
    
-   https://toolwa.com/github/
    
-   https://gh.con.sh/
    
    与油猴脚本效果一致，只是通过插件的形式安装配置。
    

🔝回到顶部

### Google

#### Official

-   https://www.google.cn/
-   https://www.google.com/
-   https://www.google.com.hk/

#### Mirrors

目前所能使用到的，基本上都是一些加速方案，而且并不十分稳定。

-   目前来看还不错的

暂无

🔝回到顶部

### Nix

#### Official

-   nixos.org

#### Mirrors

-   清华
    -   https://mirror.tuna.tsinghua.edu.cn/help/nix
-   中国科学技术大学
    -   https://mirrors.ustc.edu.cn/nix-channels
-   ISCAS
    -   https://mirror.iscas.ac.cn/nix/
-   校园网联合镜像站
    -   https://mirrors.cernet.edu.cn/list/nix

🔝回到顶部

如何贡献
----

欢迎大家补充优秀的镜像，让我们一起建设好这个仓库！

贡献内容只需要注意目录的层级与原有内容格式对齐，术业有专攻，大家提交的镜像，最好都是有经过测试验证的！

贡献者
---

  
**二丫讲梵**

  
**Ykla**

  
**Sunrise**

  
**Poplar At Twilight**

  
**Colinxu2020**

  
**淡白**

  
**咕咕乔**

  
**好吧，你想说啥**

  
**菠萝包趣多多**

🔝回到顶部
