---
project: lima
stars: 18309
description: Linux virtual machines, with a focus on running containers
url: https://github.com/lima-vm/lima
---

\[🌎**Web site**\] \[📖**Documentation**\] \[👤**Slack (`#lima`)**\]

Lima: Linux Machines
====================

Lima launches Linux virtual machines with automatic file sharing and port forwarding (similar to WSL2).

The original goal of Lima was to promote containerd including nerdctl (contaiNERD ctl) to Mac users, but Lima can be used for non-container applications as well.

Lima also supports other container engines (Docker, Podman, Kubernetes, etc.) and non-macOS hosts (Linux, NetBSD, etc.).

Getting started
---------------

Set up (Homebrew):

brew install lima
limactl start

To run Linux commands:

lima uname -a

To run containers with containerd:

lima nerdctl run --rm hello-world

To run containers with Docker:

limactl start template://docker
export DOCKER\_HOST=$(limactl list docker --format 'unix://{{.Dir}}/sock/docker.sock')
docker run --rm hello-world

To run containers with Kubernetes:

limactl start template://k8s
export KUBECONFIG=$(limactl list k8s --format 'unix://{{.Dir}}/copied-from-guest/kubeconfig.yaml')
kubectl apply -f ...

See https://lima-vm.io/docs/ for the further information.

Contributing
------------

We welcome contributions! Please see our Contributing Guide for details on:

-   **Developer Certificate of Origin (DCO)**: All commits must be signed off with `git commit -s`
-   Code licensing and pull request guidelines
-   Testing requirements

Community
---------

### Adopters

Container environments:

-   Rancher Desktop: Kubernetes and container management to the desktop
-   Colima: Docker (and Kubernetes) on macOS with minimal setup
-   Finch: Finch is a command line client for local container development
-   Podman Desktop: Podman Desktop GUI has a plug-in for Lima virtual machines

GUI:

-   Lima xbar plugin: xbar plugin to start/stop VMs from the menu bar and see their running status.
-   lima-gui: Qt GUI for Lima

### Communication channels

-   GitHub Discussions
-   `#lima` channel in the CNCF Slack
    -   New account: https://slack.cncf.io/
    -   Login: https://cloud-native.slack.com/
-   Zoom meetings (tentatively monthly)
    -   Meeting notes & agenda proposals: https://github.com/lima-vm/lima/discussions/categories/meetings
    -   Calendar: https://zoom-lfx.platform.linuxfoundation.org/meetings/lima

### Code of Conduct

Lima follows the CNCF Code of Conduct.

* * *

**We are a Cloud Native Computing Foundation incubating project.**

The Linux Foundation® (TLF) has registered trademarks and uses trademarks. For a list of TLF trademarks, see Trademark Usage.
