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
`
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

# keep Learnining.......
