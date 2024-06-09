---
layout: post
title: Kubernetes for DevOps, 08/06/2024
---

> **What is kubernetes.**

Kubernetes it's a orchestration tool, With the help of Kubernetes we can manage multiple containers at a time If one of our containers failed for same reaion, then we can automatically create another container with the same configuration, Kubernetes provide me same featuer like and Kubernetes is a system for application deployment that enables efficient use of the containerized infrastructure that powers modern applications, You can also run Kubernetes on-premises or within the public cloud. AWS, Azure and Google Cloud Platform (GCP) offer managed Kubernetes solutions to help you start quickly and efficiently operating K8s apps. Kubernetes also makes apps much more portable, so IT can move them more easily between different clouds and internal environments Kubernetes is the most popular open-source project from the Cloud Native Computing Foundation (CNCF), with active engagement and contribution from many enterprises, large and small we can login multuile node from a one place.

> **These are most popular feature of kubernetes**

> - 1:- Centralized managment for conatiner host :- We are able to all conatainer mahcine/  Container host from the single host
> - 2:- Cluster Failer :- Kubernetes also provide cluster failer feature container can migrate one machine to another machine
> - 3:- Scalability :- We can add contianer for exisring runing applications
                   - A:- Vertical Scalling
                   - B :- Horizontal Scalling

> A:- Vertical Scalling:- We can describes adding additional resources to a system increase or decrease the power of a system to handle increased or reduced workload Add or reduce the CPU or memory capacity of the existing VM

> This is a vertical iamge, You can undersatnd from this iamge.

![This is a vertial scalling images you can understand from this images](../images/vertical.webp)

> B :- Horizontal Scalling :- Horizontal scaling is the ability for an application to automatically scale by adding/reducing computing nodes as the workload increases/decreases. This is in contrast to vertical scaling, which means that you scale by adding more power (CPU, RAM) to an existing machine.

> This is Horizontal Image, you can undersatand from this image.


![This is a Horizontal Image, you can understrand from this image](../images/horizontal.webp)

- 4:- Multi-cloud flexibility
- 5:- Effective migration to the cloud
  
> - 4:- ROllout and Rollback :- We can rollout and rollback of conatiner application with out downtime, kubernetes it'saying that we can distroy and deploy new containter in zero downtime, we can upgrade you application in new conatiner, and there is same issue in new conatainer then rollback to previous version conatiner.

> **How does work kubernetes**

This is a Images,

![How does work kubernetes master images](../images/K8.png)

> **There are 4 services is always runing in kubernetes master node**

- 1:- Kube-API (Application programming interface)
- 2:- Kube-Etcs
- 3:- Kube-Sheduler
- 4:- Kuber-Controller

> What is Kuber-API :- Any command (Delete/create/scale) which extand by administrator it goes  to API Fist and it does validation (Authentiction and authorization) for any instructor.

> What is Kube-Etcd :- It contain complete kubernetes cluster information and store API related information and alos store the data key and valume formate.

> Kube-Sheduller :- it help to find the worker nodes for your application pod(container)

> Kube-controller (Port of Kubelet , 10250) :- it maintain comminicate with worker node and provide instructor to worker nodes.

> **These are same service is runing in Node side**

- CRI/containerd/dockerd :- it's a sercvices for runing worker node/conatainer We need a socket to run a container and CRI socket do not understand directly kubernetes language
  
- kubelet :- If we have to manage any container or node through kubernetes then we have to install kubectl agent with Cri socket on the front node side of kubernetes, it is kubernetes agent which take command from kube-controller

> **What Runing from worker node side**

1:- Container run time :- 

A :- Dockerd
B :- Contianerd
C :- Cri (Redhat/Ibm)

> This is a images of working process to kubernetes maste node to worker node

![This is a images](../images/Kubernetes-Work.png)

> **How to install kubernetes in ubuntu machine**

> Master Ubuntu
- apt-get update
- apt-get install -y apt-transport-https ca-certificates curl
- curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
- echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
- apt install containerd
- apt-get install -y kubelet kubeadm kubectl
- kubeadm init
- kubeadm init --ignore-preflight-errors=all
- cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
- mkdir .kube
- cp /etc/kubernetes/admin.conf .kube/config
- kubectl get pod -A
- curl https://raw.githubusercontent.com/projectcalico/calico/v3.24.0/manifests/calico.yaml -O
- kubectl create -f calico.yaml
- kubectl get nodes
- kubeadm  token create --print-join-command
- kubectl get nodes
  
> Worker Node

- apt-get update
- apt-get install -y apt-transport-https ca-certificates curl
-  curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
-  echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
-   apt install containerd
-   apt-get install -y kubelet kubeadm kubectl
-    apt-mark hold kubelet kubeadm kubectl
-    kubeadm join 172.31.32.151:6443 --token twvupt.c9h12ojc6lywt7km --discovery-token-ca-cert-hash sha256:c63ff01bbf7fcf968d31e85d51a91a9e89724d7766504cc8b45a8ba383ca68b0
-    kubeadm join 172.31.32.151:6443 --token twvupt.c9h12ojc6lywt7km --discovery-token-ca-cert-hash sha256:c63ff01bbf7fcf968d31e85d51a91a9e89724d7766504cc8b45a8ba383ca68b0 --ignore-preflight-errors=all
    
 - Kubelet :- Agent
 - kubeadm :- Installtion Utility
 - kubectl :- API command interface

> **What is kubernetes namespace(Project)**

Kubernetes namespace means that according to which user is working in which namespace, every user has a particular area which the user can do only by logging in with his user, multipule team can work easily and also we can seprate workload team wise based on the project we can provide priviliges for users and we can provide CPU/Memory/storage use for team.

> - kubectl get ns (show all namespaces in kuberneres)

> How to pod create in kubernetes. 







