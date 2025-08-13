---
project: Fast-Docker
stars: 639
description: This repo covers containerization and Docker Environment: Docker File, Image, Container, Commands, Volumes, Networks, Swarm, Stack, Service, possible scenarios.
url: https://github.com/omerbsezer/Fast-Docker
---

Fast-Docker
===========

This repo aims to cover Docker details (Dockerfile, Image, Container, Commands, Volumes, Docker-Compose, Networks, Swarm, Stack) quickly, and possible example usage scenarios (HowTo: LABs) in a nutshell. Possible usage scenarios are aimed to update over time.

**Keywords:** Docker-Image, Dockerfile, Containerization, Docker-Compose, Docker-Volume, Docker-Network, Docker-Swarm, Service, Cheatsheet.

Quick Look (HowTo: LABs)
========================

-   LAB-01: Creating First Docker Image and Container using Docker File
-   LAB-02: Binding Volume to the Different Containers
    -   LAB-02.1: Binding Mount to the Container
-   LAB-03: Docker-Compose File - Creating 2 Different Containers: WordPress Container depends on MySql Container
-   LAB-04: Creating Docker Swarm Cluster With 5 PCs using PlayWithDocker : 3 x WordPress Containers and 1 x MySql Container using Docker-Compose File
-   LAB-05: Running Docker Free Local Registry, Tagging Image, Pushing Image to the Local Registry, Pulling Image From Local Registry and Deleting Images from Local Registry
-   LAB-06: Transferring Content between Host PC and Docker Container
-   LAB-07: Creating Docker Container using Dockerfile to Build C++ on Ubuntu18.04
-   LAB-08: Creating Docker Container using Dockerfile to Build C++ on Windows
-   LAB-09: Docker Configuration (Proxy, Registry)
-   Docker Commands Cheatsheet

Table of Contents
=================

-   Motivation
    -   Needs
    -   Benefits
    -   Problems Docker does not solve
-   What is Docker?
    -   Architecture
    -   Installation
    -   Docker Engine (Deamon, REST API, CLI)
    -   Docker Registry and Docker Hub
    -   Docker Command Structure
    -   Docker Container
    -   Docker Volumes/Bind Mounts
    -   Docker Network
    -   Docker Log
    -   Docker Stats/Memory-CPU Limitations
    -   Docker Environment Variables
    -   Docker File
    -   Docker Image
    -   Docker Compose
    -   Docker Swarm
    -   Docker Stack / Docker Service
-   Play With Docker
-   Docker Commands Cheatsheet
-   Other Useful Resources Related Docker
-   References

Motivation
----------

Why should we use Docker? "Docker changed the way applications used to build and ship. It has completely revolutionized the containerization world." (Ref:ItNext)

### Needs

-   Installing all dependencies, setting up a new environment for SW (time-consuming every time to install environment for testing )
-   We want to run our apps on different platforms (Ubuntu, Windows, Raspberry Pi).
    -   Question in our mind: What if, it does not run on a different OS?
-   CI/CD Integration Testing: We can handle unit testing, component testing with Jenkins. What if integration testing?
    -   Extending Chain: Jenkins- Docker Image - Docker Container - Automatic testing
-   Are our SW products portable to carry on different PC easily? (especially in the development & testing phase)
-   Developing, testing, maintenance of code as one Monolithic App could be problematic when the app needs more features/services. It is required to convert one big monolithic app into microservices.

### Benefits

-   NOT needed to install dependencies/SWs again & again
-   Enables to run on different OS, different platforms
-   Enables a consistent environment
-   Enables more efficient use of system resources
-   Easy to use and maintain
-   Efficient use of the system resources
-   Isolate SW components
-   Enables faster software delivery cycles
-   Containers give us instant application portability.
-   Enables developers to easily pack, ship, and run any application as a lightweight, portable, self-sufficient container
-   Microservice Architecture (Monolithic Apps to MicroService Architecture, e.g. Cloud Native App)

(Ref: Infoworld)

### Problems Docker does not solve

-   Docker does NOT fix your security issues
-   Docker does NOT turn applications magically into microservices
-   Docker isn’t a substitute for virtual machines

(Ref: Infoworld)

What is Docker?
---------------

-   Docker is a tool that reduces the gap between the Development/Deployment phase of a software development cycle.
-   Docker is like a VM but it has more features than VMs (no kernel, only small app and file systems, portable)
    -   On Linux Kernel (2000s) two features are added (these features support Docker):
        -   Namespaces: Isolate process.
        -   Control Groups: Resource usage (CPU, Memory) isolation and limitation for each process.
-   Without Docker, each VM consumes 30% of resources (Memory, CPU)

(Ref: Docker.com)

### Architecture

(Ref: docs.docker.com)

### Installation

-   Linux: Docker Engine
    -   https://docs.docker.com/engine/install/ubuntu/
-   Windows: Docker Desktop for Windows
    -   WSL: Windows Subsystem for Linux,
    -   WSL2: virtualization through a highly optimized subset of Hyper-V to run the kernel and distributions, better than WLS.
        -   https://docs.docker.com/docker-for-windows/install/
-   Mac-OS: Docker Desktop for Mac
    -   https://docs.docker.com/docker-for-mac/install/

### Docker Engine (Deamon, REST API, CLI)

-   There are mainly 3 components in the Docker Engine:
    -   Server is the docker daemon named docker daemon. Creates and manages docker images, containers, networks, etc.
    -   Rest API instructs docker daemon what to do.
    -   Command Line Interface (CLI) is the client used to enter docker commands.

(Ref: Docker.com)

### Docker Registry and Docker Hub

-   https://hub.docker.com/

App: Running Docker Free Local Registry, Tagging Container, Pushing to Local Registry, Pulling From Local Registry and Deleting Images from Local Registry

### Docker Command Structure

-   docker \[ManagementCommand\] \[Command\]

```
docker container ls -a
docker image ls
docker volume ls
docker network ls
docker container rm -f [containerName or containerID]
```

### Docker Container

(Ref: docker-handbook-borosan)

-   When we create the container from the image, in every container, there is an application that is set to run by default app.
    -   When this app runs, the container runs.
    -   When this default app finishes/stops, the container stops.
-   There could be more than one app in docker image (such as: sh, ls, basic commands)
-   When the Docker container is started, it is allowed that a single application is configured to run automatically.

```
docker container run --name mywebserver -d -p 80:80 -v test:/usr/share/nginx/html nginx
docker container ls -a
docker image pull alpine
docker image push alpine
docker image build -t hello . (run this command where “Dockerfile” is)
(PS: image file name MUST be “Dockerfile”, no extension)
docker save -o hello.tar test/hello
docker load -i <path to docker image tar file>
docker load -i .\hello.tar
```

Goto: App: Creating First Docker Image and Container using Docker File

#### Docker Container: Life Cycle

(Ref: life-cycle-medium)

```
e.g. [imageName]=alpine, busybox, nginx, ubuntu, etc.
docker image pull [imageName]
docker container run [imageName]
docker container start [containerId or containerName]
docker container stop [containerId or containerName]
docker container pause [containerId or containerName]
docker container unpause [containerId or containerName]
```

#### Docker Container: Union File System

-   Images are read only (R/O).
-   When containers are created, new read-write (R/W) thin layer is created.

(Ref: docs.docker.com)

### Docker Volumes: Why Volumes needed?

-   Containers do not save the changes/logs when erased if there is not any binding to volume/mount.
-   For persistence, volumes/mounts MUST be used.
-   e.g. Creating a log file in the container. When the container is deleted, the log file also deleted with the container. So volumes/binding mounts MUST be used to provide persistence!

(Ref: udemy-course:adan-zye-docker)

### Docker Volumes/Bind Mounts

-   Volumes and binding mounts must be used for saving logs, output files, and input files.
-   When volumes bind to the directory in the container, this directory and volume are synchronized.

```
docker volume create [volumeName]
docker volume create test
docker container run --name [containerName] -v [volumeName]:[pathInContainer] [imageName]
docker container run --name c1 -v test:/app alpine
```

Goto: App: Binding Volume to the Different Containers

#### Bind Mount

```
docker container run --name [containerName] -v [pathInHost]:[pathInContainer] [imageName]
docker container run --name c1 -v C:\test:/app alpine
```

(Ref: Docker.com)

Goto: App: Binding Mount to Container Goto: App: Transferring Content between Host PC and Docker Container

### Docker Network

-   Docker containers work like VMs.
-   Every Docker container has network connections
-   Docker Network Drivers:
    -   None
    -   Bridge
    -   Host
    -   Macvlan
    -   Overlay

#### Docker Network: Bridge

-   Default Network Driver: Bridge (--net bridge)

```
docker network create [networkName]
docker network create bridge1
docker container run --name [containerName] --net [networkName] [imageName] 
docker container run --name c1 --net bridge1 alpine sh
docker network inspect bridge1
docker container run --name c2 --net bridge1 alpine sh
docker network connect bridge1 c2
docker network inspect bridge1
docker network disconnect bridge1 c2
```

-   Creating a new network using customized network parameters:

```
docker network create --driver=bridge --subnet=10.10.0.0/16 --ip-range=10.10.10.0/24 --gateway=10.10.10.10 newbridge
```

(Ref: Docker.com)

#### Docker Network: Host

-   Containers reach host network interfaces (--net host)

```
docker container run --name [containerName] --net [networkName] [imageName] 
docker container run --name c1 --net host alpine sh
```

(Ref: Docker.com)

#### Docker Network: MacVlan

-   Each Container has its own MAC interface (--net macvlan)

(Ref: Docker.com)

#### Docker Network: Overlay

-   Containers that work on different PCs/hosts can work as the same network (--net overlay)

(Ref: Docker.com)

#### Port Mapping/Publish:

-   Mapping Host PC's port to container port:

```
-p [hostPort]:[containerPort], --publish [hostPort]:[containerPort] e.g. -p 8080:80, -p 80:80
docker container run --name mywebserver -d -p 80:80 nginx
```

### Docker Log

-   Docker Logs show /dev/stdout, /dev/stderror

```
docker logs --details [containerName]
```

### Docker Stats/Memory-CPU Limitations

### Docker Environment Variables

### Docker File

Goto: App: Creating Docker Container using Dockerfile to Build C++ on Ubuntu18.04

Goto: App: Creating Docker Container using Dockerfile to Build C++ on Windows

#### Sample Docker Files

```
FROM python:alpine3.7
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
EXPOSE 5000
CMD python ./index.py
```

```
FROM ubuntu:18.04
RUN apt-get update -y
RUN apt-get install default-jre -y
WORKDIR /myapp
COPY /myapp .
CMD ["java","hello"]
```

-   Multistage Docker File (Creating temporary container):
    -   In the example, JDK (Java Development Kit) based temporary image (~440MB) container is created for compilation.
    -   Compiled files are copied into JRE (Java Runtime Environment) based image (~145MB). Finally, we have only JRE based image.

```
COPY --from=<stage 1> stage1/src stage2/destination
```

-   In the example below, 'compiler' is 'stage1'.

```
FROM mcr.microsoft.com/java/jdk:8-zulu-alpine AS compiler
COPY /myapp /usr/src/myapp
WORKDIR /usr/src/myapp
RUN javac hello.java

FROM mcr.microsoft.com/java/jre:8-zulu-alpine 
WORKDIR /myapp
COPY --from=compiler /usr/src/myapp .
CMD ["java", "hello"]
```

### Docker Image

-   Create Image using Dockerfile

```
docker image build -t hello . (run this command where “Dockerfile” is)
(PS: image file name MUST be “Dockerfile”, no extension)
docker image pull [imageName]
docker image push [imageName]
docker image tag [imageOldName] [imageNewName]
(PS: If you want to push DockerHub, [imageNewName]=[username]/[imageName]:[version])
docker save -o hello.tar test/hello
docker load -i <path to docker image tar file>
docker load -i .\hello.tar
```

Goto: App: Creating First Docker Image and Container using Docker File

### Docker Compose

-   Define and run multi-container applications with Docker.
-   Easy to create Docker components using one file: Docker-Compose file
-   It is a YAML file that defines components:
    -   Services,
    -   Volumes,
    -   Networks,
    -   Secrets
-   Sample "docker-compose.yml" file:

```
version: "3.8"

services:
  mydatabase:
    image: mysql:5.7
    restart: always
    volumes: 
      - mydata:/var/lib/mysql
    environment: 
      MYSQL_ROOT_PASSWORD: somewordpress
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    networks:
      - mynet
  mywordpress:
    image: wordpress:latest
    depends_on: 
      - mydatabase
    restart: always
    ports:
      - "80:80"
      - "443:443"
    environment: 
      WORDPRESS_DB_HOST: mydatabase:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    networks:
      - mynet
volumes:
  mydata: {}
networks:
  mynet:
    driver: bridge
```

-   After saving the file as "docker-compose.yml", run the following commands where the docker-compose file is, to create containers, volumes, networks:

```
docker-compose up -d
docker-compose down
```

Goto: App: Docker-Compose File - Creating 2 Different Containers: WordPress Container depends on MySql Container

### Docker Swarm

One of the Container Orchestration tool:

-   Automating and scheduling the
    -   deployment,
    -   management,
    -   scaling, and
    -   networking of containers
-   Container Orchestration tools:
    -   Docker Swarm,
    -   Kubernetes,
    -   Mesos

(Ref: udemy-course:adan-zye-docker)

### Docker Stack / Docker Service

-   With Docker Stack, multiple services can be created with one file.
-   It is like a Docker-Compose file but it has more features than a Docker-compose file: update\_config, replicas.
-   But it is running on when Docker Swarm mode is activated.
-   Network must be 'overlay'.

#### Creating, Listing, Inspecting

```
docker service create --name testservice --replicas=5 -p 8080:80 nginx
docker service ps testservice (listing running containers on which nodes)
docker service inspect testservice
```

#### Scaling

```
docker service scale testservice=10 (scaling up the containers to 10 replicas)
```

#### Updating

```
docker service update --detach --update-delay 5s --update-parallelism 2 --image nginx:v2 testservice (previous state: testservice created, now updating)
docker service update --help (to see the parameters of update)
```

#### Rollbacking

```
docker service rollback --detach testservice (rollbacking to previous state)
```

Goto: App: Creating Docker Swarm Cluster With 5 PCs using PlayWithDocker : 3 x WordPress Containers and 1 x MySql Container using Docker-Compose File

Play With Docker
----------------

-   https://labs.play-with-docker.com/

Docker Commands Cheatsheet
--------------------------

Goto: Docker Commands Cheatsheet

Other Useful Resources Related Docker
-------------------------------------

-   Original Docker Document: https://docs.docker.com/get-started/
-   Cheatsheet: https://github.com/wsargent/docker-cheat-sheet
-   Workshop: https://dockerlabs.collabnix.com/workshop/docker/
-   All-in-one Docker Image for Deep Learning: https://github.com/floydhub/dl-docker
-   Various Dockerfiles for Different Purposes: https://github.com/jessfraz/dockerfiles
-   Docker Tutorial for Beginners \[FULL COURSE in 3 Hours\]- Youtube: https://www.youtube.com/watch?v=3c-iBn73dDE&t=6831s
-   Docker and Kubernetes Tutorial | Full Course \[2021\] - Youtube: https://www.youtube.com/watch?v=bhBSlnQcq2k&t=3088s

References
----------

-   Docker.com
-   docs.docker.com
-   docker-handbook-borosan
-   life-cycle-medium
-   Infoworld
-   ItNext
-   udemy-course:adan-zye-docker
