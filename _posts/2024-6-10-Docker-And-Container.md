---
layout: post
title: Docker And Container for DevOps, 08/06/2024
---
# About Docker?

- Programming language: Go
- Initial release: March 20, 2013; 11 years ago
- Developer: Docker, Inc.
- Operating system: Linux, Windows, macOS
  
# What is Docker? 

Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. The service has both free and premium tiers docker is an open platform for developing, shipping, and running applications, Docker enables you to separate your applications from your infrastructure so you can deliver software quickly And Docker provides the ability to package and run an application in a loosely isolated environment called a container The isolation and security lets you run many containers simultaneously on a given host. Containers are lightweight and contain everything needed to run the application.

> **What is provisoning**

It’s a method to providing VMs with some application installation.

> **Provisioning Method**

- 1) VM/Instance Based: This is example of hardware virtualization.
- 2) Container Based: This is example of OS base virtualization.
  
  Docker: Docker is a community and It is Open source container technology

> **Virtualization**

1. H/w Based Virtualization (Hypervisor)
2. OS Virtulization 

Virtualization is a technology by which we can run multiple machines on a 
hardware simultaneously. 

> You can understand from this image,

![Thi is images](../images/Hypervisor.png)

> **OS Virtualization**

1. Docker Host/Engine: A machine/OS that will run multiple container machines

**Two release available in market**

Docker ce: Community Edition
Docker ee: Enterprise Edition (One month subscription is free with your ID)

> **What is docker client**

Client machine from where we can provision containers. This is just like your client workstation and 
generally its not recommended to take docker client.

> **What is docker images**

Its light weight image for particular application. To spin the container you should have at least 
available. It has minimal configuration to deploy any container.

**Two types of images available in market**

1. Community based :- There have some communities available in market and they are providing free of cost images.
   
For example: docker hub
Free available: CE
Red hat also provide their docker images.
but need subscription: registry.access.redhat.com

2. Custom Image:- 

We can configure our offline Docker registry and we can import some ready to use images.

> **Docker Registry**

From where we can pull the container images

> **Docker Container**

It’s a micro machine running over the docker host  And its have own process/storage/IP/NIC.

Note: We can deploy multiple container using same docker image.

> **How to Install Docker community addition**

> **: Create one centos machine in AWS Cloud**

-  yum install -y yum-utils
- yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
- ls -lrt /etc/yum.repos.d/
- yum install docker-ce -y [docker-ce will install docker client/command also ]
- docker version 
- systemctl start docker [to show docker server version]
- systemctl enable docker
- docker version
  
> **Docker Image command**

- docker images
- docker ps
- docker search mysql
- docker pull mysql:latest
- docker pull mysql:5.6
- docker images
- docker pull nginx:latest
- ls -ld /var/lib/docker
- docker pull centos:7
- docker images
- docker history b5b4d78bc90c [to check the history of docker image]
  
> **Create first container by using centos image**

- hostnamectl set-hostname docker-host
- bash
- docker run -it --name=test centos:7
- /]# touch abc
- /]# exit
- docker ps [you will not see any container listed here]
- docker ps -a [to list all containers]








