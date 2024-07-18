---
layout: post
title: RHCE-Ansible (Redhat Certified Engineer)
---

# What is Ansible ?

Ansible is an open source, command-line IT automation software application written in Python. It can configure systems, deploy software, and orchestrate advanced workflows to support application deployment, system updates, and more. Ansible's main strengths are simplicity and ease of use,
We can automate any task with the help of Ansible with out of any agent of ansible.

- Developer: Red Hat Software
- Initial release: February 20, 2012; 12 years ago
- License: GNU General Public License version 3
- Operating system: Linux, Unix-like, MacOS, Windows
- Written in: Python, PowerShell, Shell

# How to install Ansbile server in ubuntu 22.04

- (EPEL) Extra Packages for Enterprise Linux.

{% highlight ruby %}

    -  sudo apt-get update -y && sudo apt-get upgrade -y
    -  sudo apt install alien -y
    -  sudo add-apt-repository "deb [arch= amd64] http://download.webmin.com/download/repository sarge contrib"
    -  sudo add-apt-repository ppa:ansible/ansible
    -  apt install ansible -y
    -  ansible --version

{% endhighlight %}

> **Configuration**

1. Shell Scritping
2. Configuration tool (RHCE-Ansible)

> # Ansible**

It's a opensource IT configureation tool management tool, we can automate IT infra.

      - Server (Linux/Window)
      - Device (Router/Switch/firewall)
      - Virtulizztion (EXSI/KVM)
      - Storage Service (SAN/NAS)
    
> # Ansible Arch**

1. Working Sytle (it's an agent less configuration tool)
2. Controll Node (we can install ansible in linux Server, bottom of Linux OS)
3. Manage Node (the server deivces, /devices/firewall/switch/router/virtulization)
4. Connection Plugin (ansible by default runing i SSH service)
5. Inventory Files (the file which contians about your manage node)
6. Modules (module is write in python)
7. Ad Hoc (command line)
8. Playbook (fule method)
9. Yaml file (we will write yaml playbook file)

> # What is Inventory files and How to create incentory files, ( we can manage controll node and we can contins data of node)

By default ansible 2 places read the inventory file,

1. /etc/ansible/hosts
2. /etc/ansible/ansible.cfg

{% highlight ruby %}

1. mkdir inventory (create direcotry)
2. cd inventory
3. vim test (add controller nodes in this file, thi is a costom invenytory file)


              - [web] # This is grouping, if we want to add multule node from ansible server side, then we grouping for identificatio
              - 192.168.10.1
              - 192.168.10.1
              - 192.168.10.1

              - [Database Server]
              - system1@example.com
              - system2@example.com

              - [Dev]
              - exmapple1@nitin.com
              - example2@nitin.com
              
              - [nitinsoni:children] ( we can add group of subgrup, we can run both group at a time)
              - web
              - prod


4. ls -l /etc/ansible/hosts (This is by default inventory of ansible)
5. ansible web:dev --list-hosts -i inventory/test (this command is show how many entrys is there in /hosts file)
6. ansible all --list-hosts -i inventory/
7. ansible web --list-hosts -i inventory/test (showing only web group node)
 
{% endhighlight %}

- ansibe --vesion  (show by default inventory file)
- vim /etc/ansible/ansible.cf (this is by default inventory file, we can modifie according to the need)
- export ANSIBLE_CONFIG=/etc/ansible/ansible.cfg (We are exporting varialble of anible cfg file, we can fire command for ansible from any location, but this is a temprory)
- vim .bashrc 

       - export ANSIBLE_CONFIG=/etc/ansible/ansible.cfg (this is permant )

> # How to set password less authentication in server machine, (how many types of server authentication)

1. Password authentication
2. Password less authenticaion
3. file based authentication
4. SSH based authentication

> **Password less authenticaion**

- ssh-keygen (server side)
- ls .ssh/ (create private and pulic key in this file)
- sh-copy-id -i id_rsa.pub ubuntu@13.202.94.27 (copy public file in another server)


> # Connection Estabilished with manage node

Authentication:- 

 1. key based authentication
 2. Password Based authenticaion (-k, password authentication with manage node)
 3. inventory file based authentication 


> **inventory file based authentication**

          - [web]
          - 52.66.88.107    ansible_ssh_user=ubuntu ansible_ssh_pass=Nitin@003

          - [dev]
          - 43.204.230.252  ansible_ssh_user=ubuntu ansible_ssh_pass=Nitin@003

          ansible all -m ping (when we are putting the password in this file /etc/ansible/hosts, then then don't have any -u option)

> # How to push configuration

    - Ad Hoc (Command line)
    - playbook (Write a file and Excute)

           - Be sure that, controlle node will communicate with worker node or not

- ansible targate(where you wnat to push configuration) -m module -a (arguments) 'key=value'

# Example Number-1

> **How to copy file contolle node to manage node**

{% highlight ruby %}

- ansible all -m ping (this command will sure that, from the contolle node will communicate with worker node or not)
- ansible all -m ping -k (if your private key is deleted, then we can access with -k opetion with password)
- ansible all -m ping -u ubuntu -k (ansible is login from all worker node in ubuntu user, and push tasks)
- ansible-doc -l (showing all modules in ansible)
- ansible-doc -l | grep -i win (showing all window modules)
- ansible-doc -l | grep -i user (showing user relted module)
- ansible-doc -l copy
- ansible web -m copy -a 'src=test dest=/tmp/' (copy test file in tmp folder)
- ansible wall -m copy -a 'src=test dest=/tmp/'
- ansible dev -m command -a 'id' ( this command excute from worker node and showing owner details)
- 

{% endhighlight %}


# Ad Hoc Exmaples

{% highlight ruby %}

1. command module (for OS related)
- ansible all -m command -a 'uname -r'

2. Raw module (run two command in at a time)
- ansible all -m raw -a 'uname -m ; uptime'

3. Copy Module (for copy)
- ansible web -m copy -a 'src=test dest=/tmp/

4. fatch module (for revers, to fatch data from worker node to controller node)
- ansible all -m fetch -a 'src=/etc/fstab dest=/tmp/backup'

5. synchrone (between the worker node we can copy the file and data)

6. Lineinlife (we can add one line,)

7. Replace 

8. File 
{% endhighlight %}

# Basic Ansible,

> Name ( should be must that, we are taking the file extenstion .yml OR .yaml file)
> Path ( anywhere we can write a path)

**What is yml OR Yaml**

> Yaml (ain't another markup language) :- When we are creating any file in linux then we can take the file name extensiton, yml OR yaml formate for example :- "nitin.yml OR nitin.yaml" this is file extension 

- address : c32 ( key: value ) (String type value)

- address:  (List Type Arrey, When the same key has multiple values, there are - )
        - c1
        - c2
        - c3
        - c3

- Nitin :       ( mapping type arrey, must be take space )
        skills: 
            - Python
            - java
        number: 3443
        address: Noida

**Now we are write fist playbook of ansible**

- Task: folder /tmp/cloud
- Task: /etc/fstab into /tmp/cloud
- Task: crond restart


**This is basic file for anisble**

 {% highlight ruby %}

- hosts:
    - web
    - prod
  tasks:
    - file:
       path: /tmp/cloud
       state: directory
    - copy:
       src: /etc/fstab
       dest: /tmp/cloud
    - service:
       name: cron.service
       state: restarted

 {% endhighlight %}

1. ansible-playbook p1.yml --syntax-check (from this command we are cheking that my file synctax is correct or not)
2. ansible-playbook p1.yml --check ( we can run or excute yml file, this method we can say dry run)
3. ansible-playbook p1.yml --C (2 And 3 both command are same)
4. ansible-playbook p1.yml --step ( task will perform step by step )


# How to write multi play in single playbook 

> **we can add multipule host in a single yml file**

{% highlight ruby %}

- hosts: web
  tasks:
    - file:
       path: /tmp/cloud
       state: directory
    - copy:
       src: /etc/fstab
       dest: /tmp/cloud
    - service:
       name: cron.service
       state: restarted


- hosts: prod
  tasks:
    - name: Install the package
      apt:
        name: ftp
        state: present              

{% endhighlight %}


> **We can write the file in these formate**

1. Single Line Formate
2. Multi Line Formate
3. Dictionary Formate

> **Billow example of 3 formate**

{% highlight ruby %}

- hosts: web
  tasks:
    - name: This is exmaple of dictionary formate
    - file:
       path: /tmp/cloud
       state: directory

    - name: This is exmaple of single line formate
      file: path=/tmp/cloud state=directory mode=0777 owner-wheel


    - name: This is exmaple of multilne formate
      file: path=/tmp/cloud
            state=directory
            mode=0777
            owner=root
            group=root           

{% endhighlight %}


# We are leaning Variable in ansible

**What is variable** :- Ansible support variable that can be used to store  values that can then ne resued thoughout file in an ansible project, This can simplify the creation and maintain of a project and reduse the number of errors.

< **This is Example of valid and Invailed ansible variable in ansible**


          **In valid variable names**                  **Valid variable names**
              - web server                                 - web_server
              - renote.file                                - remote_file
              - 1st file                                   - 1st_file
              - remotesever$1                              - remote_server_$_1

  
> **How many places for placing the varianble values in ansible**

1. Playbook lavel variable 
2. Command lavel variable
3. Inventory File lavel variable

# Inventory Lavel Variable Example,

**host invenory file is not allow to write ansible playbook**

{% highlight ruby }

[web]
13.202.149.170	web_root=/var/www/www1

[prod]
13.202.95.120	web_root=/var/www/www2


{% endhighlight }



# keep Learnining.......

