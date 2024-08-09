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


# Inventory Lavel Variable Example

**host invenory file is not allow to write ansible playbook**

{% highlight ruby %}

[web]
13.202.149.170	web_root=/var/www/www1

[prod]
13.202.95.120	web_root=/var/www/www2


{% endhighlight %}


{% highlight ruby %}

[web]
13.202.149.170	web_root=/var/www/www1

[prod]
13.202.95.120	web_root=/var/www/www2


{% endhighlight %}


---
> **Playbook lavel variable** 

{% highlight ruby %}

- name: Example of playbook lavel variable
  hosts: web
  vars_files:
          - /home/ubuntu/uint04/mycostum.yml # agar hamare play book me multipule variable aate hai to ham variables ki 
                                              new file bana ke use file yaha par call kar sakte hai.
  tasks:
    - name: Install the packages
      apt:
        name: "{{web}}" # We are calling variable value of web
        state: installed


    - name: Start "{{web}}" service
      service:
        name: "{{web}}"
        state: started
        enabled: true

    - name: Create Directory "{{webroot}}"
      file:
          path: "{{webroot}}"
          state: directory

{% endhighlight %}


{% highlight ruby %}

- name: Example of playbook lavel variable
  hosts: web
  vars:
    web: httpd
    web_pkg:
        - httpd
        - vsftpd
        - wget
    myuser:
        - name: ram
          phone: 344354353
        - name: nitin
          phone: 2344543

  tasks:
    - name: add user # We are calling variable of user add
      user:
         name:  "{{myuser.name}}"
    - name: Install the packages
      apt:
        name: "{{web}}" # We are calling variable value of web
        state: installed


    - name: Start "{{web_pkg}}" service 
      service:
        name: "{{web}}"
        state: started
        enabled: true

    - name: Create Directory "{{webroot}}" 
      file: 
          path: "{{webroot}}"
          state: directory

   

{% endhighlight %}



> **Command lavel variable**


{% highlight ruby %}

- name: add user and apply password
  hosts: web
  vars_prompt:         # This is prompt variable
    - name: "myname"
      prompt: "What is your name"
    - name: "mypassword"
      prompt: "What is your password"
      private: yes
  tasks:
    - name: create user and apply password
      user:
        name: "{{myname}}"
        password: "{{mypass}}"

{% endhighlight %}



{% highlight ruby %}

- hosts: all
  become: true
  tasks:
      - name: create directory
        file:
            path: "{{web_root}}"
            state: directory


      - debug:
          msg: "{{web_root}}"

{% endhighlight %}

**For inventory level variable example, this is allow in indrastry**

1. mkdir goup_vars
2. mkdir hosts_vars

sudo vim group_vars/web

{% highlight ruby %}

web_root: /var/www/www1  

{% endhighlight %}

---

{% highlight ruby %}

webpkg: apache2   

{% endhighlight %}

# Ansible Fact ?

 
> **setup** :- Setup it's a module, to geathraing system all information from the manage node.

1. ansible web -m setup 

>***Example Number one**

{% highlight ruby %}

- name: Example of fact use case in playbook
  hosts: all
  become: true
  tasks:

{% endhighlight %}

1.  ansible-playbook p5.yml 
2. ansible all -m setup -a 'filter=*fqdn*' (We can filer from the manage node fully quali fied domain)

{% highlight ruby %}

- name: Example of fact use case in playbook
  hosts: all
  become: true
  tasks:
    - name: Store Kernal Information
      copy:
        content: "This is your kernal versio {{ ansible_kernel }}"
        dest: /etc/motd

{% endhighlight %}


# Register Variable

With the help of register variable, we can store the output in ansible playbook and use the task with variable,

{% highlight ruby %}

- hosts: all
  become: true
  tasks:
      - name: Please check H/W mode
        command: uname -m
        register: xyz


      - debug:
          var: xyz.stdout

      - name: Store over the all machine
        copy:
          content: "hello everyone my name is nitin soni{{ xyz.stdout }}"
          dest: /etc/motd

{% endhighlight %}


# Ansible Vault


**With the ansible vault we can encript, ansible playbook**

> This is a example of vault 

{% hightlight ruby %}

- hosts: all
  become: true
  vars:
    mypass: redhat
  task:
    - name: Create user name and pasword
      user:
        name: nitin
        password: "{{ mypass}}"
     
{% endhightlight %}

after write the playbook then we will fire this cammand,

1. ansible-vault encrypt p1.yml
2. and give the passowrd of file (form this command your play  book is encrypt and without your, anyone can't anythink to do your file)
3. ansible-vault edit p1.yml (with this command we can eidt file)
4. ansible-vault view p1.yml ( we can read the file only owner not another user)
5. ansible-playbook p1.yml --ask-vault-pass ( we can push the file with vault password)
6. ansible-vault decrypt p1.yml ( we can decrypt the file with paswword)
 

# Costum fact


We are engecting the variable in csotum fact, and for run the task then we are creating file firt, and should the extension file, nitin.fact and we can perform same task in repeted 

/etc/ansible/facts.d

> # Ansible Loop ?

When a key has multiple values ​​then we call it loop concept.

> **This is exmaple of without loop yml file**

{% highlight ruby %}

- name: Example of without loop
  hosts: all
  tasks:
    - name: add ravi
      user:
          name: ravi
          state: present
            
    - name: add nitin
      user:
          name: nitin
          state: present


            
    - name: add nitin1
      user:
          name: nitin
          state: present
     

{% endhighlight %}

> **Ansible is provide 3 type loop concept**

1. **Simple/Standard loop (Same FOR Loop in python)**
2. **List of hash Loop (1st list value is runing with 2ad value, then we can use List type Loop)** 
3. **Nested Loop (when 1st loop is runing with 2ad list loop continous then  runing nested loop)**



> **This is Example of Simple/Standard loop (Same FOR Loop in python)**

{% highlight ruby %}

- name: Example of simple loop
  hosts: all
  tasks:
    - name: add users ravi manish syam
      user:
           name: "{{item}}" # This is predefine value (itme)
           state: present
           group: wheel
      with_items:            # And item value is point to with_item, with item hold your values
            - ravi
            - manish
            - saym
            - neha
            - nitin
            - soni
            - gagan
            - anshu
            - nikhil


    - name: add group tcs kr nitin abc stop guest
      group:
          name: "{{item}}"
          state: present
      loop:
          - tcs
          - nitin
          - kr
          - stop
          - guest

{% endhighlight %}


# keep Learnining.......

