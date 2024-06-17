---
layout: post
title: Kubernetes for DevOps
---
---
# What is kubernetes
---

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

---
# How to install kubernetes in ubuntu machine
---

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

> **In yaml file most important the resources and how to create pod by using file method**

>> **Note**

{% highlight end%}

**all parametter already defined for yaml file,
and we can see all formates from these commands**
  
> - kubectl api-resources (Show all resources)
> - kubectl explain pod  (telling that How we can careate yml file for creating yml file.)
> - kubectl explain pod.metadata (telling that How we can careate yml file for creating yml file.)
> - vim rc.yml (yml file)
> - kubctl create -f rc.yml (create RC pod)
> - kubectl get rc  (see RC in kubernetes)
> - kubectl get pod (we can see pod)
> - kubectl get pod -o wide (show all detail for pod)
> - kubectl describe pod nitin-c65ws | grep -i controller (who is controller of this pod or not)
> - kubectl delete pod coredge-hzgq5 (if you are delete RC pod then by automatic one RC pod will create, maintain desiered state of pod)
> 


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

> **RC Yaml file, we can edit according to the need and company**

> - kubectl delete pod --all (delete all pod)
> - vim rc.yml (all parametter is available in this file)
**For Example**
 ![This is example for RC file](../images/RC.png)
> - kubectl create -f rc.yml (Create RC file from this command)
> - kubectl get rc (Display RC)
> - kubectl scale --replicas=7 rc coredge (we can extand and reduse rc pod by using this command)
> - kubectl delete rc core (delete rc pod)
**Note**

> after create rc pod, and now you want to extand rc pod from insdie the rc file, we can extand rc pod number and run billow command for apply,

> - vim rc.yml
> - kubectl apply -f rc-yml (after update in rc file, we requried this command, and from this command rc pod is extand, without this command pod is not extand)
> - kubectl get rc
> - kubectl describe rc coredge | grep -i image (we can check, which from image pod is created)
> - kubectl describe rc coredge | grep -i image (show version of rc pod, if are we wnat to change veriosn of application from yml file but because of same resion veriosn is not reflact)
> - kubectl describe rc coredge | grep -i image (hare is showing version,)
> - kubectl delete pod --all (delete pod for reflect verion of applciation)
> - kuebctl get pod (how we can check appliction version)
> - kubectl describe pod coredge-9pwcz | grep -i image (how version will show)

{% endhighlight %}

# What is Label and Selector in kubernetes Resources.
> **In case pod only**

for example you have to a multipule pod with labels, and you you find pod from label level, the we need to label

{% highlight ruby %}

> - vim nitin.yml
> - kubectl create -f nitin.yml
> - kubectl get pod
> - kubectl get pod --show-labels (show label of pod)
> - kubectl get pod -l env-qa (show pod from envirement level)
> - kubectl delete -l tier=nitin (delete pod, which name of this teri)
> - kubectl get pod --show-labels (show all labels of pod)
> - kubectl label pod coredge-9pwcz type=B (we can define label in rungin pod)

{% endhighlight %}

> **Now, we are set lable in RC pod file**

In RC work on equality base, and if value is machted during the creating 2 container then you one pod will not ceate during the valume match from label and selector.  

> **Note**

Label and sector are at 2 places in the RC pod file, 1st **top of spac** section and 2ad **billow of the spec**

{% highlight ruby %}
> - vim rc.yml
> - kubectl get rc --show-labels (show label with rc file)
> - kubectl get rc (show all rc file) 
> - kubectl delete rc -l tier=web (delete rc with define label)

{% endhighlight %}

**This is a example of top label in file**

![This is a file](../images/lable-topof%20spec.png)

# Replica Set.

In replica set, work on set bases, 

**thi is image of relica set**

![This is image of replica set](../images/replica-set.png)

# Application And Rollback

> **Deplyment Provided feature**

  1. Desired State maintain
  2. Scalalibilty
  3. Rollout And Rollback 
   
> **3 types methood available for Application Deployment stretagy**

1. Blue And Gree Stretagy (by default), Save yor downtime
2. Recreate Stretagy
3. Canary Deployment.
   
> Deployment pod by command line.

**Blue And Gree Stretagy**

{% highlight ruby %}

1. kubectl create deploy nitin --image=nginx --replicas=2 (create two pod)
2. kubectl get deploy (show pod)
3. kubectl delete pod nitin-75f6b7bf46-k6dz7 (if same reasion you one pod is delted, then by default one pod will create)
4. kubectl get pod
5.kubectl scale --replicas=4 deploy nitin (exatant pod with this command)
1. kubectl get pod
2. kubectl delete deploy nitin (delete deplo, witj app pods)
3. kubectl get pod

**Fiel Method**

vim deploy.yml

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80

9. kubectl create -f deployment.yml
10. kubectl get pod --show-labels
   
{% endhighlight %}

> **Now Will cover Rolllout First**

In Deployment stretagy follow to blue green stretagy,  when we are upgarde appllication version to old version to new version with downtime.

> Old version :- Blue Deployment Stretagyy
> New Version :- Green Deployment stretagy

> **Nte**

Deployment Stretgy follow to Blue,Green formolla rule, first available 25% and unable 25%, but it's default rule, we can chenge this rule for deployment stretagy.

. Unavailable (delete)
. available (creation)

**You can understand from this image for deployment stretagy**

![This is a image of, how to work Blue,Green stretagy](../images/Deployment.png)

{% highlight ruby %}

1. kubectl create deploy nitin --image=nginx:1.14 --replicas=10 (create deployment pod by command line)
2. watch kubectl get pod (we can watch process of upgradtion stretagy)
3. kubectl describe deploy nitin | grep -i max (we can see stretagy)
4. kubectl edit deploy nitin (going to yml file of deployment,and we can modify this file according to the need)
5. kubectl describe pod nitin-86d775cc94-kckbh | grep -i image (we can applicaiton version from this command)
6. kubectl rollout history deploy nitin (we can check rollout histoy)
7. kubectl rollout history deploy nitin --revision=2 (check details of application)
8. kubectl rollout undo deploy nitin --to-revision=2 (we can move back in previous verison application from this commnad)
9. kubectl describe deploy nitin | grep -i image (we can applcaition versio)

{% endhighlight %}

**Recreate stretagy**

In This stretagy old veriso directoly is deleted and then new version is created,

1. vim deploy.yml
2. kubectl create -f deploy.yml

**Canary Deployment**

It's a teknic for both application is runing, When both the applications were run, we could see a difference in both version application.

# Pod Shedulling.

1. Node Name based shedulling 
2. Node label and selector based schedulling
3. tait and toleration based schedulling
4. Affinity And Anti-Affinity based schedulling.

> **Node Name based shedulling**

We tell the node that this deployment should run on that node. (worker-node1 , worker-node-2) ,

.But there is also a dropback, once we give the name of the node, the deployment will run on that node, and if no resources in node then pod will crashed and not create pod in kubernetes,

{% highlight ruby %}

1. kubectl create deploy nitin --image=nginx --dry-run -o yaml > deploy.yml (create one deployment)
2. kubectl get node (show node in kubernetes)
3. vim deploy.yml (open deploy file)

{% endhighlight %}

We will change in **spac section** for node base shedulling and menstion node name, for exmaple, bollow this image.

 We can understand this image,
   ![This is node based schedulling](../images/nodebaseschedulling.png)

4. kubectl create -f deploy.yml (create pod)
5. kubectl get pod
6. kubectl get pod -o wide

> **Node label and selector based schedulling**

We can decide which role to run in which node, according to the need, if one node is down due to some reasion, then going itself to another node. 

**We can understand this imgages** 

![This is a image of lablel and selector based schedulling](../images/labelandselectorbnasescheddulling.png)

**How we can in command line**

{% highlight ruby %}

1. kubectl label node kube-clien-1 nitin=nitinsoni gagan=gaggi buti=lallu (we can define label in node)
2. kubectl label node kube-client-2 roll=rool1 abc=web --overwrite (If we accidentally assign a roll to the wrong node then we can overwrite it. )
3. kubectl get node --show-labels (show label in node)
4. kubectl get node -l roll=rool1 (we can check role of node)

{% endhighlight %}

**This is image of, how to create label bases schedulling**

![This is a image](../images/node.png)

5. kubectl get node -l role=web (check role)
6. kubectl create -f deploy.yml
7. kubectl get pod -o wide

> Selector:-
     1. Deployment (deploment file only)
     2. Namespaces (Deplyment on namesapce levelfrom node)
   
**cd /etc/kubernetes/manifests/ (control 4 servics)**

{% highlight ruby%}

1. etcd.yaml  
2. kube-apiserver.yaml  
3. kube-controller-manager.yaml  
4. kube-scheduler.yaml
5. kubectl get ns
6. kubectl create ns nitin
7. kubectl edit ns nitin

(going to this file and edit this varialble **we need the add same value**) 

Billow of metadata:-

 -     annotations:
 -        scheduler.alpha.kubernetes.io/node-selector: env=nitin

8. kubectl label node kube-clien-1 env=nitin (given lable of node)
9.  kubectl create deploy home --image=nginx -n nitin (deployment with niitn name namesapce)
10. kubectl create ns nitin
11. kubectl create deploy web --image=nginx -n nitin (create deploy from web name in nitin namespace)
12. kubectl get pod -o wide -n nitin (check details of nitin node)
13. kubectl get pod -o wide -n nitin (who pods in nitin namespace)

{% endhighlight %}

**this image refrensh of namespace edit**

![This is iamge of add valumes in namespcace](../images/namescpaceedit.png)


> **Tait and toleration Based Schedulling**

Test and Tolerance is used only for deidcated hardware requirement for pode, So that no pod can come to that node.

> - Taint :- Node Side
> - Toleration :- Deployment Side

{% highlight ruby %}

1. kubectl taint node kube-clien-1 monitoringpurpoise:NoSchedule (node is taint from this command)
2. kubectl create deploy nitinsoniji --image=nginx --replicas=10 (create 10 pod, after taint any node then when we have create any pode, so pod is not going to taint node. )
3. kubectl describe node kube-clien-1 | grep -i taint (we can find tiant node)
4. kubectl run dge --image=nginx --dry-run -o yaml > pod.yml
5. vim pod.yml
6. kubectl taint node kube-clien-1 monitoringpurpoise- (untant node)

6. kubectl create -f pod.yml 
7. kubectl get pod -o wide

- We can pass vule for toleration,

{% endhighlight %}

![This is image of toleration](../images/taint.png)


> **Type of taint Effect**

1. NoSchedule :- it does not delete (evict), existing pod even the don't have toleration (if any pod is created already, and after pod creation, we have assign tolaretion so dones not effect exiting pod, and upcoming pod does not creaete tolaretion node)

{% highlight ruby %}   

    - kubectl create deploy tent --image=nginx --replicas=2
    - kubectl get pod
    - kubectl get pod -o wide
    - kubectl get node
    - kubectl taint node kube-clien-1 tes:NoSchedule
    - kubectl get pod -o wide
    - kubectl delete pod tent-5644c9c7bc-l6z8s
    - kubectl get pod
   
{% endhighlight %}

2. NoExcute :- it evict (delete) all pod they don't have toleration
   

    - kubectl taint node kube-client-2 DB:NoExecute
    - kubectl get pod -o wide  

> **Type of toleration Effect**

**Operator**
 1. Exist :- It only match single string
    
    - kubectl taint node kube-clien-1 role=DB:NoExecute ( we can define role of pod)
   - vim pod.yml
    **how to add parametter in Exist**
    ![This is image we can take the refrensh](../images/qual.png)


 2. Qual :- Key and value both matched.
   
  - kubectl taint node kube-clien-1 role=DB:NoExecute (we can pass valume during the taint node)
  - kubectl create -f pod.yml
  - kuebctl get pod

---
# Wait

> **Afinity And Anti-Afinity**

- 2 Types of Afinity And Anti-Afinity available,
  
  1. Node Level
          - Afinity
          - Anti-Afinity
  2. Pod lavel
          -  Afinity
          - Anti-Afinity
  
> **How to apply node lavel Afinity And Anti-Afinity**

1. Node Lavel, 
2. Afinity And Anti-Afinity,
  
**Example of Affinity** = disk=sd

---
> **Compute And Resource Quota**
---

We can manage how many pods will be created on which node or how many resources it will have, You can limit the total sum of compute resources that can be requested in a given namespace. Across all pods in a non-terminal state, the sum of CPU limits cannot exceed this value. Across all pods in a non-terminal state, the sum of memory limits cannot exceed this value

2 Types Quota are availebl,

1. Compute Quota (CPU,MEMORY)
2. Resource Quota (Objective, In kubernets language, pod,rs,rs,deployment, contollers etc.)
  
**Compute Quota**

    - Deployment Level,
              - Soft Quota (Requrest Quota)
              - Hard Quota (Limit Quota)
    - Project Level (NameSpace),
              - For limitrand for pod, if any pod is comming in namepsce.
  
**How to create Deployment Node Quota**

{% highlight ruby %}

  1. vim deploy.yml
  2. kubectl create -f deploy.yml
  3. kubectl get pod -o wide
  4. kubectl describe node kube-clien-1 | grep -iA5 allocated (check allocated space of node)

{% endhighlight %}

**we can add valumes in deploy file**

> (Agar ham kise deployment me ja kar CPU ya memory ko chagne karte hai ya fir cpu memory badhate hai and ek hi pod ke duplicate replica banate hai ise ko ham Horizontal scalling bolate hai,)

![This is a image of compute quota](../images/computequota.png)   

> **How to create Project Level (NameSpace)**

If we fix any limit in the namespace, then we can create as many pods in that namespace as we have given the limit in the namespace.

{% highlight ruby %}

1. kubectl create ns qa
2. kubectl create quota cka --hard=cpu=400m,memory=400mi -n qa (we have allocated fix space for namespace)
3. kubectl get quota -n qa
4. kubectl describe quota -n qa (show name space limits)

{% endhighlight %}

> **Limit Rang**

1. We can define default value for CPU/Memory, 
2. Max/Min value for cpu/memory. 
   
**This is available only yml file not command line**

When we define the limitrange at the namespace level, the pod created after that by default gets the CPU and memory that we have given at the namespace level.

{% highlight ruby %}

Going to kubernete site and copy the sentax for limite rang,

1. vim limit.yml (we can take any name)
2. kubectl create ns nit (create one namespace)
3. kubectl create -f limit.yml -n nit (this is creted limitrang, I have attched image for your referensh)
4. kubectl run test --image=nginx -n nit (create orphan pod)
5. kubectl describe quota test -n example 
6. kubectl describe pod test -n nit | less
7. kubectl get limitrange -n nit (we can check limitrang of namespace)
8. kubectl delete limitrang xyz -n nit (remove limitrang)


{% endhighlight %}

**This is exmaple of limitrang of namepsace level**

![This is image of limitrang difine example](../images/limit1.png)


# > Voulme

> 2 Types valume are availanle,
1. Static Volume
2. Dynamic Volume


1. Local Volume
2. Network Based Volume
             > - NAS Based
             > - SAN Based


> **Static Volume provisoing using NAS (NAF)Server**

          - PV [Persitent Volume] (Object, Commnd line is not availabnle only we can create yml file method)
  
          - PVC (Object, Commnd line is not availabnle only we can create yml file method)
  
**For PV and PVS creation we requrid yml file from kubernetes officel site**
  
>  For this prectical perform, we will setup nfs server first,

1. sudo apt update
2. sudo apt install nfs-kernel-server
3. sudo mkdir -p /var/nfs/general
4. sudo chown nobody:nogroup /var/nfs/general
5. vim /etc/exports
6. /var/nfs/general    client_ip(rw,sync,no_subtree_check) 
7. sudo exportfs -a
8. sudo systemctl start nfs-kernel-server
9. sudo systemctl enable nfs-kernel-server

> Now we will configure PV yml file

1. vim pv.yml

**This is exmapl of PV** 

{% highlight ruby %}

apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv0003 ==> This is PV name we can take any name, PV should be uniqe
spec:
  capacity:
    storage: 5Gi
  volumeMode: Filesystem
  accessModes:   ==> 3 Type AccessModes available, PV mode means how many worker nodes a node can access at a time.

                               -  **ReadyWritemany** ==> (A PV whose mode is ReadWriteMany can be accessed at a time on multiple worker nodes.)
                               -  **ReadOnlyMany** 
                               -  **ReadWriteOnce** 
                               -  **ReadWriteOncePod** (Only one pod read and write,)
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Recycle
 
 ---                 
 **This is Work only static provisiong**

                                **3 Type Policy available of persistentVolumeReclaimPolicy,**
                               - 1. Recycle, (if PVC deleted, Application changes lost but PV will available in cluster so it can be use for another namespca and other deployment)
                               - 2. Retain, (If PV + Data both available)
---
**This is Work only dynaic provisning**
                               - 3. Deleted, (PV +Data Lost )
  
  storageClassName: slow
  mountOptions:
    - hard
    - nfsvers=4.1
  nfs:
    path: /tmp
    server: 172.17.0.2

{% endhighlight %}
  
2.