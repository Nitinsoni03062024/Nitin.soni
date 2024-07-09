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
    -  alien -V
    -  wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
    -  sudo alien -i google-chrome-stable_current_x86_64.rpm
    -  sudo alien -i google-chrome-stable_current_x86_64.rpm 
    -  sudo alien -i google-chrome-stable_current_x86_64.rpm --no-force-overwrite
    -  wget https://rpmfind.net/linux/openmandriva/cooker/repository/x86_64/main/release/firefox-114.0.2-3-omv2390.x86_64.rpm
    - wget -qO- https://download.webmin.com/jcameron-key.asc | sudo tee -a /etc/apt/trusted.gpg.d/jcameron-key.asc
    -  ll
    -  sudo add-apt-repository "deb [arch=amd64] http://download.webmin.com/download/repository sarge contrib"
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

{% highlight ruby %}

1. mkdir inventory (create direcotry)
2. cd inventory
3. vim test (add controller nodes in this file)
4. ls -l /etc/ansible/hosts (This is by default inventory of ansible)
5. ansible web --list-hosts -i inventory/test (this command is show how many entrys is there in /hosts file)
6. ansible all --list-hosts -i inventory/

{% endhighlight %}

- ansibe --vesion  (show by default inventory file)
- vim /etc/ansible/ansible.cf (thi is by default inventory file, we can modifie according to the need)
- export ANSIBLE_CONFIG=/etc/ansible/ansible.cfg (We are exporting varialble of anible cfg file, we can fire command for ansible from any location, but this is a temprory)
- vim .bashrc 

       - export ANSIBLE_CONFIG=/etc/ansible/ansible.cfg (this is permant )


# keep Learnining.......
