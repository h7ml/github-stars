---
project: openebs
stars: 9069
description: Most popular & widely deployed Open Source Container Native Storage platform for Stateful Persistent Applications on Kubernetes.
url: https://github.com/openebs/openebs
---

OpenEBS - Cloud Native Storage
------------------------------

Project Purpose
---------------

OpenEBS is an open-source storage service for Kubernetes applications. OpenEBS manages the block storage and file systems based on the block storage for containers running in Kubernetes. Use OpenEBS for creating fast and resilient storage; with options for single-node, and replicated multi-node storage.  

**Try our Slack channel**  
If you have questions about using OpenEBS, please use the CNCF Kubernetes **OpenEBS slack channel**, it is open for anyone to ask a question  

  

Monthly Community Meetings
--------------------------

OpenEBS holds a monthly community meeting via Zoom on the last Thursday of the month, at 14:00 UTC.  
The next meeting is on: `Thursday 31 October, at 14:00 UTC`  
Meeting Link: https://us05web.zoom.us/j/87535654586?pwd=CigbXigJPn38USc6Vuzt7qSVFoO79X.1  
Starting in August 2024, the meetings will be recorded and posted on YouTube. Check here  

Why OpenEBS?
------------

OpenEBS provides enterprise-grade data management for Kubernetes clusters, with five storage engines (four single-node and one replicated) that meet a range of use cases for Kubernetes users. The five engines are summarized in the table below:  

Important

The OpenEBS platform, provides 2 types of K8s Storage Services. `Replicated PV` and `Local PV`.

  

Engine

Local PV HostPath

Local PV ZFS

Local PV LVM

Local PV Rawfile

Replicated PV Mayastor

Type

Single-node

Single-node

Single-node

Single-node

Multi-node

What is it for?

Replacement for in-Tree Kubernetes CSI HostPath

Storage engine for ZFS managed backend storage

Storage engine for LVM2 managed backend storage

Experimental engine for using an extent file as block storage

General purpose replicated enterprise storage

Designed for

Developers or DevOps

ZFS users and production deployments

LVM2 users and production deployments

Developers

Enterprises and production deployments

Features

Everything in Kubernetes HostPath, plus: - Dynamic provisioning, Zero configuration, No CSI driver

Provision ZFS datasets, Provision ZFS volumes, Dynamic provisioning, ZFS resilience, ZFS RAID protection, CSI driver

Provision LVM2 volumes, Dynamic provisioning, LVM2 RAID protection, CSI driver

Provision file system from local files as persistent volumes, CSI driver

Replicated storage NVMe / RDMA, Snapshots, Clones, High availability, CSI driver

Status

Stable, deployable in PROD

Stable, deployable in PROD

Stable, deployable in PROD

Beta, undergoing evaluation & integration

Stable, deployable in PROD

Current Version

`release: v0.70`

  

Important

**OpenEBS provides**...  

-   Stateful persistent Dynamically provisioned storage volumes for Kubernetes
-   High-performance NVMe-oF & NVMe/RDMA storage transport optimized for All-Flash Solid State storage media
-   Block devices, LVM, ZFS, ext2/ext3/ext4, XFS, BTRFS...and more
-   100% Cloud-Native K8s declarative storage platform
-   A cluster-wide vSAN block-mode fabric that provides containers/Pods with HA-resilient access to storage across the entire cluster.
-   Node local K8s PVs and n-way Replicated K8s PVs
-   Deployable On-premise & in-cloud: (AWS EC2/EKS, Google GCP/GKE, Azure VM/AKS, Oracle OCI, IBM/RedHat OpenShift, Civo Cloud, Hetzner Cloud... and more)
-   Enterprise Grade data management capabilities such as **snapshots, clones, replicated volumes, DiskGroups, Volume Groups, Aggregates, RAID**  
    

  

> ☑️   It uses the High performance SPDK storage stack - (SPDK is an open-source NVMe project initiated by INTEL)  
> ☑️   The hyper-modern IO\_Uring Linux Kernel Async polling-mode I/O Interface - (fastest kernel I/O mode possible)  
> ☑️   Native abilities for RDMA and Zero-Copy I/O  
> ☑️   NVMe-oF TCP Block storage Hyper-converged data fabric  
> ☑️   Block layer volume replication  
> ☑️   Logical volumes and Diskpool based data management  
> ☑️   a Native high performance Blobstore  
> ☑️   Native Block layer Thin provisioning  
> ☑️   Native Block layer Snapshots and Clones  

* * *

Activity dashboard
------------------

Current status
--------------

Release

Support

Twitter/X

Contrib

License status

CI Status

* * *

**Read this in** 🇩🇪 🇷🇺 🇹🇷 🇺🇦 🇨🇳 🇫🇷 🇧🇷 🇪🇸 🇵🇱 🇰🇷 **other languages.**

Deployment
----------

-   In-cloud: (AWS EC2/EKS, Google GCP/GKE, Azure VM/AKS, Oracle OCI, IBM/RedHat OpenShift, Civo Cloud, Hetzner Cloud... and more)
-   On-Premise: Bare Metal, Virtualized Hypervisor infra using VMWare ESXi, KVM/QEMU (K8s KubeVirt), Proxmox
-   Deployed as native K8s resources: `Deployments`, `Containers`, `Services`, `Stateful sets`, `CRD's`, `Sidecars`, `Jobs` and `Binaries` all on K8s worker nodes.
-   Runs 100% in K8s userspace. So it's highly portable and runs across many OSs & platforms.

Roadmap (as of June 2024)
-------------------------

-   OpenEBS Roadmap

* * *

QUICKSTART : Installation  

----------------------------

`NOTE:` Depending on which of the 5 storage engines you choose to deploy, pre-requisites must be met. See detailed quickstart docs...  

  

> 1.  **Setup helm repository.**

# helm repo add openebs https://openebs.github.io/openebs
# helm repo update

> 2a. **Install the Full OpenEBS helm chart with default values.**  
> 
> -   This installs **ALL OpenEBS Storage Engines**\* in the openebs namespace and chart name as openebs:  
>     `Local PV Hostpath`, `Local PV LVM`, `Local PV ZFS`, `Replicated PV Mayastor`

# helm install openebs --namespace openebs openebs/openebs --create-namespace

> 2b. **To Install just the OpenEBS `Local PV` Storage Engines, use the following command**:

# helm install openebs --namespace openebs openebs/openebs --set engines.replicated.mayastor.enabled=false --create-namespace

> 1.  **To view the chart**

# helm ls -n openebs

Output:
NAME     NAMESPACE   REVISION  UPDATED                                   STATUS     CHART           APP VERSION
openebs  openebs     1         2024-06-25 09:13:00.903321318 +0000 UTC   deployed   openebs-4.1.0   4.1.0

> 1.  **Verify installation**
>     -   List the pods in namespace
>     -   Verify StorageClasses

# kubectl get pods -n openebs

Example Ouput:
NAME                                              READY   STATUS    RESTARTS   AGE
openebs-agent-core-674f784df5-7szbm               2/2     Running   0          11m
openebs-agent-ha-node-nnkmv                       1/1     Running   0          11m
openebs-agent-ha-node-pvcrr                       1/1     Running   0          11m
openebs-agent-ha-node-rqkkk                       1/1     Running   0          11m
openebs-api-rest-79556897c8-b824j                 1/1     Running   0          11m
openebs-csi-controller-b5c47d49-5t5zd             6/6     Running   0          11m
openebs-csi-node-flq49                            2/2     Running   0          11m
openebs-csi-node-k8d7h                            2/2     Running   0          11m
openebs-csi-node-v7jfh                            2/2     Running   0          11m
openebs-etcd-0                                    1/1     Running   0          11m
openebs-etcd-1                                    1/1     Running   0          11m
openebs-etcd-2                                    1/1     Running   0          11m
...

# kubectl get sc

Example Output:
NAME                                              READY   STATUS    RESTARTS   AGE
openebs-localpv-provisioner-6ddf7c7978-jsstg      1/1     Running   0          3m9s
openebs-lvm-localpv-controller-7b6d6b4665-wfw64   5/5     Running   0          3m9s
openebs-lvm-localpv-node-62lnq                    2/2     Running   0          3m9s
openebs-lvm-localpv-node-lhndx                    2/2     Running   0          3m9s
openebs-lvm-localpv-node-tlcqv                    2/2     Running   0          3m9s
openebs-zfs-localpv-controller-f78f7467c-k7ldb    5/5     Running   0          3m9s
...

For more details, please refer to OpenEBS Documentation.

OpenEBS is a CNCF project and DataCore, Inc. is a CNCF Silver member. DataCore supports CNCF extensively and has funded OpenEBS participating in every KubeCon event since 2020. Our project team is managed under the CNCF Storage Landscape and we contribute to the CNCF CSI and TAG Storage project initiatives. We proudly support CNCF Cloud Native Community Groups initiatives.  

> Project updates, subscribe to OpenEBS Announcements  
> Interacting with other OpenEBS users, subscribe to OpenEBS Users

  

   

Commercial Offerings
--------------------

Commercially supported deployments of OpenEBS are available via the companies below. (Some provide services, funding, technology, infra, and resources to the OpenEBS project).  

-   DataCore Software, Inc.
-   Clouds Sky GmbH
-   CodeWave
-   Gridworkz Cloud Services

(OpenEBS OSS is a CNCF project. CNCF does not endorse any specific company).

License Compliance
------------------
