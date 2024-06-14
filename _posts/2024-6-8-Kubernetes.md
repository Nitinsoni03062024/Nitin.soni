---
layout: post
title: Kubernetes for DevOps
---

# What is kubernetes

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

# How install kubernetes in ubuntu- 20.04 version , (Install kubernete-Master Server)

> Note **3 Server required for kubernetes server and master, 1st for kubernetes master and 2ad and 3ad kubernetes-node server **

> **This is for kubernetes server**

{% highlight ruby %}
    1  hostname
    2  sudo apt-get update
    3  sudo apt-get install -y apt-transport-https ca-certificates curl gpg
    4  curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
    5  echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
    6  sudo apt-get update
    7  apt install containerd
    8  sudo apt-get install -y kubelet kubeadm kubectl
    9  kubeadm init
   10  kubeadm init --ignore-preflight-errors=all
   11  kubectl get nodes
   12  cd /etc/console-setup/
   13  cd
   14  mkdir .kube/config
   15  mkdir .kube
   16  cd .kube/
   17  touch config
   18  ls
   19  cdd
   20  cd
   21  cp /etc/kubernetes/admin.conf .kube/config
   22  kubectl get nodes
  23 curl https://raw.githubusercontent.com/projectcalico/calico/v3.28.0/manifests/calico.yaml -O
   38  kubectl create -f calico.yaml
   39  curl https://raw.githubusercontent.com/projectcalico/calico/v3.28.0/manifests/calico.yaml -O (Download the Calico networking manifest for the Kubernetes API datastore)
   40 apt install calico -y
   41  kubeadm token create --print-join-command (to create token for join kubernetes nod)


{% endhighlight %}

> **This is fro kubernetes-node server**
>
{% highlight ruby%}
 sudo apt-get update
    1  sudo apt-get install -y apt-transport-https ca-certificates curl gpg
    2  curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
    3  echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
    4  sudo apt-get update
    5  apt install containerd
    6 sudo apt-get update
    7 sudo apt-get install -y kubelet kubeadm kubectl
    8 sudo apt-mark hold kubelet kubeadm kubectl
    9 kubeadm join 172.31.40.85:6443 --token 6jxmip.jcbwjv50beo7a4v4 --discovery-token-ca-cert-hash sha256:eae5c3eccedd332263cc7a8c76a9960b3d9a02108fcefdf44c37b72c57bdfa9a --ignore-preflight-errors=all (For join worker node)


{% endhighlight%}

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

First you can go to docker website, (Install ubuntu-20.04)

# How to install kubernetes in ubuntu machine

> **for setup kubernetes atleast required 3 machine,**
- 1:- Master node (ubuntu)
- 2:- Worker node (ubuntu)
- 3:- Workder node (ubuntu)
> Master Ubuntu (ubuntu)


- sudo apt-get update
- sudo apt-get install ca-certificates curl
- sudo install -m 0755 -d /etc/apt/keyringspackages.cloud.google.com/apt/doc/apt-key.gpg
- sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
- sudo chmod a+r /etc/apt/keyrings/docker.asc
- echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
- sudo apt-get update
- sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
- sudo apt-get update
- sudo apt-get install -y apt-transport-https ca-certificates curl gpg
- curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
- echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
- sudo apt-get update
- sudo apt-get install -y kubelet kubeadm kubectl

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
  

> **Note**
- /etc/container (we can deleteing one file)
- mkdir .kube
- cp /etc/kubernetes/admin.conf .kube/config



> **What is kubernetes namespace(Project)**

Kubernetes namespace means that according to which user is working in which namespace, every user has a particular area which the user can do only by logging in with his user, multipule team can work easily and also we can seprate workload team wise based on the project we can provide priviliges for users and we can provide CPU/Memory/storage use for team ,

To easiy explain, namespace and project in simple language, if we open any account of our AWS or cloud, not everyone can see our dashboard, all user has their own account which one user can see his dashboard. Other users cannot see


> - kubectl get ns (show all namespaces in kuberneres)

# How to create Pod in kubernetes

> **There are 2 types of pod**
 
- 1:- Pod Creation (Simple/Orphan pod)
- 2:- Controlller pod
  
# How to create simple/orphan pod by command line in kubernetes.

{% highlight ruby%}
> - kubectl get ns 
> - kubectl run test --image=docker.io/nginx 
> - kubectl get pod
> - kubectl get pod -o wide 
> - kubectl exec -it test bash 
> - exit 
> - kubectl get event
> - kubectl delete pod podname 
> - kubectl get pod
> - kubectl create ns nitin
> - kubectl run demo1 --image=docekr.io/nginx -n nitin 
> - kubectl run dem2 --image=docker.io nginx
{% endhighlight %}

> **How to create pod by using file method (yaml) kubernetes.**
> 
{% highlight ruby %}

> - kubectl run core1 --image=nginx --dry-run -o yaml (show with yaml file)
> - kubectl run core1 --image=nginx --dry-run -o yaml > pod.yaml (save file in pod.yaml)
> - kubectl create -f pod.yaml (create pod from pod.yaml file)

{% endhighlight %}

![This is yaml bases file for refrence](../images/yml.png)

> **In yaml file most important the resources**

>> **Note**

{% highlight end%}

**all parametter already defined for yaml file,
and we can see all formates from these commands**
  
> - kubectl api-resources (Show all resources)
> - vim rc.yml  (telling that How we can careate yml file for creating yml file.)
> - kubectl describe pod nitin-7sp6k | grep -i controller 
> - kubectl scale --replicas=4 rc nitin (we can reduse and Extand replica of pod)
> - kubectl delete rc nitin (delete rc)
>- kubectl get rc



{% endhighlight %}

# How to create pod using API Controller.

> Purpise of API Controller pod.

   -  Maintain pod stat   (Hight availability)
   -  scalability.
              1. Manual (Horizontal)

1. **RC (Replication Controller) :-**

it's privide high availability and scalability for pod, if pod is crased and failed to automatic pod is create in horizonatal form.

We can't create RC method by command line, onyl we can create file method.
that the reasion we are going to kubernetes offial page, and in search option we can search , **Replication Controller**, after you can see RC based yaml file.

{% highlight ruby%}

> RC Yaml file, we can edit according to the need and company

> - kubectl delete pod --all (delete all pod)
> - vim rc.yml (all parametter is available in this file)
**For Example**
 ![This is example for RC file](../images/RC.png)
> - kubectl create -f rc.yml (Create RC file from this command)
> - kubectl get rc (Display RC)

{% endhighlight %}

> - 






