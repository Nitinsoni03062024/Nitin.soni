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

2. **Custom Image:-**

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
  
> **Basics command about the Images/containers**

1. systemctl is-acitve docker (docker runing or not)
2. docker info (all deatils is show of docker)
3. ls /var/lin/docker (all folder are available for docker)
4. docker images (show all images)
5. docker pull images (httpd) (pull images from docker resitory)
6. docker search (we can search image, in docker machine)
7. docker system df (how many space consume from docker machine)
8. docker rmi httpd:2.2 (remove images, untaga)
9. docker tag 356125da0595 httpd:latest (Tag images from docker)
10. docker pull ubuntu (You can pull raw images)

> **Two Types of images are available in docker**

1. Service image (mysql,nginx,httpd,apaceh, etc)

2. Raw images (minor footprint, Packed same services, In a raw images same normal command are avalable, like:- ls, mkdir,touch etc.), Raw images when we want to create costom images then we need raw images, with help of raw images we can create images, we can't create any images with raw image.

> **How to create container images in docker**

1. docker ps (how many container runiung)
2. docker images
3. docker run -d(deamon) --name=con1 nginx (Create container con1 from nginx images)
4.  ls /var/lib/docker/containers/ (Container data is available in this diretory)
5.  docker exec -it con1 bash (we can log in container)
6.  exit
7.  docker rm container-name (delete container name)
8.  docker rm -f image id (delete image)
   
- docker run  -d   (Daemon Container)
- docker run -it   (Raw Image deploy container)

- docker exec 
              1. Login
              2. any command you can run inside the container from docker host

- docker attach con1  
(also provide login in container but only  raw containers.
attach existing  bash process. i dont start  new  bash process .)

9. docker stop CON1 (stop and kill process container)
10. docker ps -a (show all container)
11. docker start CON1 (start container)
12. ps -ef (how many process is runing in system)
13. dockr inspect CON1 (all information about the container)
14. docker stats CON1 (information about memory and network)
15. docker top CON1 (how many process is runing in container)
16. docker logs CON1 (log how about container)
17. docker pull ubuntu (pull raw image)
18. docker run -d --name=demo ubuntu bash (log and create container)

> **How to insatll database in docker, mysql,nariadb**

19. docker pull mysql
20. docker logs containername (you can find logs)
21. 

# Note :-

1. docker run -d --name=rawcon (if we are using this commnd, after run this command your process by defautl killed itself just because RAW container does not have its own processing)

2. docker run -d it --name=rawcon (if we are runing this command then conatienr is runing and login because we can fire command with -d option -d mean that direct login contaienr and create container deamon mode)



# Keep Learning......









