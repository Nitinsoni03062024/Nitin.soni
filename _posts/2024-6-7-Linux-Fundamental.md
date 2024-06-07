---
layout: post
title: Linux fundamental (07/06/2024)
---
> **This is Image of Linux Logo**

![Logo Of Linux](../images/linuxlogo.png)
 
> **About Linux**

- Developer: Linus Torvalds
- Initial release date: 17 September 1991
- Programming languages: C, Assembly language

> ***We are coverd findamental linux**

 Linux is Operating system (OS) for open surce and command line interface, Just like Windows, iOS, and Mac OS one of the most popular platforms on the planet An operating system is software that manages all of the hardware resources associated with your desktop or laptop. To put it simply, the operating system manages the communication between your software and your hardware. Without the operating system (OS), the software wouldn’t function and linux os monolithic kernal.

 > **Why use Linux?**

Linux is a totly open source Oprating system and commnad line interface, we can modify kernal and configuration file accoring to the company and me and linux is very secur operaing system which is user to SHA algoritham in linux That’s right, zero cost of entry… as in free. You can install Linux on as many computers as you like without paying a cent for software or server licensing.

> **Open source**

> Linux is also distributed under an open source license:- 

- The freedom to run the program, for any purpose.
- The freedom to study how the program works, and change it to make it do what you wish.
- The freedom to redistribute copies so you can help your neighbor.
- The freedom to distribute copies of your modified versions to others.
  
> **In the market multpule distribustion are avauilebl in the market**

- LINUX MINT
- KALI LINUX
- CENTOS
- DEBIAN
- UBUNTU
- FEDORA
- OPENSUSE

> This is most oprating system uses in company's,

- Ubuntu
- CentOS 
- Opensuse
- RHEL


> **Now we are insatlling Linux**

- 1. Decide which Linux distribution you want to use. (Later we will give a table of common choices and useful links
for downloading install media, and helpful tutorials on procedure.)

- 2. Download the install image, which will be either a local or network install image or a Live image (which can also
be used for install.)

- 3. Decide if you want to do a:

- Native Installation: To do this you will need a machine with enough useable disk space or will have to
repartition to make space available.
- Virtual Machine Installation: To do this you’ll have to first install a hypervisor program as described later.
- Live CD/DVB/USB method: To do this no install is needed, but performance will be weaker.

- 4. Do the install following distribution-supplied directions.


> **Installtion mathod**

All Linux distributions provide downloadable installation media in the form of optical media images (CD and/
or DVD) which can be easily burned to a physical disk, or USB stick images, together with instructions on how to 
produce a USB drive that can be booted from for installation. 

These images vary in type of machine (e.g., 64-bit or 32-bit; we recommend doing only 64-bit installs on modern 
hardware that supports it) or small or large (e.g., minimal or full desktop or server system).
Alternatively, one can do a much smaller download and get a network install image which has just a few files; then 
the installation procedure goes out on the Internet to get whatever else is needed. Such a network install has only 
a short initial download, but the install process itself can take a long time based on your network download speed. 
A full install image may also support going out to the Internet during installation, like a network install, but only to 
retrieve software with a newer version available than was included in the full install image. 

> **Using Live Media Instead of a Full Install **

Many popular distributions provide Live CD, DVD, or USB media which can be used to run Linux without actually 
installing it on your disk drives. As you can imagine, this is the safest method of experimenting with Linux if you 
already have a computer running another operating system. 

There are disadvantages however:

- • Slow startup: every time you boot up the hardware has to be examined and the operating system set up as if
you were doing a fresh install.
- • Performance can be poor, so more memory and CPU power may be required to make things run acceptably.
- • It can be awkward to save any work or other material either on the normal hard disk or to external media etc,
although it can be done. In particular, any changes in setup or any other software that is installed may be lost
each time one boots up.

Please note that the Live media image and the Install image is the same for many modern user-friendly distributions! 
One simply boots off the Live image and then clicks on Install once the system starts. One very nice aspect of this 
dual-use media is that before you even attempt an install, you know whether or not the Linux-based operating system 
can recognize and work with all of your hardware and peripherals, such as your network card, sound system, webcam etc

> **Installing a Hypervisor and a Virtual Machine**

Everyone has probably heard the phrase Virtual Machine. This is a full guest operating system (which may or may not be
Linux) which runs on top of a Hypervisor program on a host machine, which can be running any operating system with an 
available hypervisor, including all flavors of Windows, Linux and Mac OS. 
An advantage of using the virtual machine images is that you can’t fundamentally destroy your host system while
running them, and they run as an unprivileged application, which may be more compatible with company IT policies, if
applicable. A further advantage, especially with on-line classes, is that a system failure does not take you off-line.
The disadvantages have mostly to do with performance and requiring somewhat more memory and CPU power.
However, in many circumstances this will not be a disqualifying aspect.
You will have to install a hypervisor program if you don’t already have one. Here are two easily obtainable low- or nocost solutions:

- • Oracle Virtual Box
Can be downloaded from https://www.virtualbox.org
Exists for Windows, Linux, Mac OS and Solaris operating systems.

- • VMware
Exists in full-featured products such as VMware Workstation but also in a freely downloadable version, VMware
Player which can be reached at http://www.vmware.com/try-vmware.html. While VMware Player is free of charge
only for Windows and Linux host operating systems, VMware Fusion is a low cost program for the Mac OS.
Once you have installed the hypervisor, installing a guest operating system is pretty easy. You don’t even have to burn 
the install image to a CD or DVD; you can just point the hypervisor to the .iso image on your computer. In some cases 
(such as for Virtual Box) you can even perform an automatic installation which doesn’t even ask you questions when 
you install.

The rest of the discussion on installation for the most part applies here, except you won’t have to worry about the 
difficult things like partitioning; you can just take the default choices. However, make sure you assign enough disk space 
(say at least 20 GB to be safe, although you’ll probably need quite a bit less).

> ***Now We are learing Booting process **

- 1:- Power on machine
- 2:- After power on machine SMPS (Switch on power supply), Will supply the power to all the conctvity devices and motherboard
- 3:- Basically it provide the current from AC (Alternative current) to DC (Direct Current)
- 4:- This supply is provide to proper amount of voltage
- 5 :- **BIOS INITIALIZATION** ==> BIOS to firmware used to perform haedware inistiozation durring the booting process (POST)
- 6 :- **What is BIOS**
- **First** :- BIOS is the first think loads when you start your computer, it initilization hardware befour booting an OS from your hard dirve or another device
- **Second** :- BIOS second for , Basic input/Output System and all the types of firmware storage on a chip on your motherboard, when you start you computer, the computer boot the BIOS, Which configure your hardware befoure handling off to a boot device 

- 7:- The BIOS perform POST Operation (Power on self test), to detect and initialization system hardware component.
- 8:- If all device is OK, then Boop sound,
- 9:- Then MBR in the hard disk it refer to the location of the boot loader using DISK priority 
- 10:- BIOS load and exciutes the MBR boot laoder and give control to MBR

**This is a Imges of Booting Process you can understand**

![This is images if Linux Booting process, for better understranding](../images/Booting.png)

> **What is apache web server and HTTPD Server**

- Apache web server or Apache http server is one of the most widely used on 
the Internet It is developed and maintained by Apache Software Foundation, Apache is 
an open source software available for free A web server generally hosts the web content, and responds to requests for 
this content from web browsers such as Internet explorer, Google chrome 
and Firefox And httpd is the same as apache2. It depends on the OS you use. For example in 
RHEL 6.2 it is called httpd and in Ubuntu it is called apache2. 

> **How many web Servers we have in market ?**

- 1- apache web server, 
- 2- IIS web server 
- 3- Nginx webserver and litespeed web server. 
  
- Beside Apache, IIS and Nginx also among the most common web servers in 
use today As reported (July 18, 2016) the web server statistics shows that from the 
entire internet web, there are 46% web server running in Apache, 29% in 
Microsoft IIS and 19% in Nginx,

-  The http protocol is sent over the wire in clear text, using port 80/TCP by 
default (though other ports can be used). 
 There is also a TLS/SSL encrypted version of the protocol called https that 
uses port 443/TCP by default.

> **Types of website in markets ?**

- 1:- Name based hosting 
- 2:- IP Based Hosting 

- Package name: httpd (Apache2)
- Daemon: httpd (Apache2)
- Port number: 80 { http } and 443 { https } 
- File : /etc/httpd/conf/httpd.conf OR (etc/apache2/apache2.conf)
- Log: /var/log/httpd/access.log 
- /var/log/httpd/error.log 
- Document root place: /var/www/html 

> **What is HTTPS ?**

- HTTPS stands for Hyper Text Transfer Protocol Secure, It is a protocol for securing the communication between two systems e.g. the 
browser and the web server, t is the protocol where encrypted HTTP data is transferred over a secure 
connection. By using secure connection such as Transport Layer Security or 
Secure Sockets Layer The principal motivations for HTTPS are authentication of the accessed website, 
and protection of the privacy and integrity of the exchanged data while in transit It uses the port no. 443 for Data Communication. It allows the secure transactions
by encrypting the entire communication with SSL.

> **How to install webserver in Ubuntu ?**

- sudo apt update
- sudo apt install apache2
- sudo systemctl status apache2
- sudo systemctl stop apache2
- sudo systemctl staret apach2
- Now you can hit in broser "localhost" Output open samething open,

![Go to any browser and hit "localhost"](../images/localhost.png)

> **Linux File System**

- We can read and write the data from file system, a Linux file system is a structured collection of files on a disk drive or a partition. A partition is a segment of memory and contains some specific data. In our machine, there can be various partitions of the memory. Generally, every partition contains a file system.

The general-purpose computer system needs to store data systematically so that we can easily access the files in less time. It stores the data on hard disks (HDD) or some equivalent storage type. There may be below reasons for maintaining the file system.

> **What is the Linux File System?**

Linux file system is generally a built-in layer of a Linux operating system used to handle the data management of the storage. It helps to arrange the file on the disk storage. It manages the file name, file size, creation date, and much more information about a file.

> **Types of Linux File System**

When we install the Linux operating system, Linux offers many file systems such as Ext, Ext2, Ext3, Ext4, JFS, ReiserFS, XFS, btrfs, and swap.

![We can understand from this image for Linux file system](../images/linuxfile.png)

- Ext :- The file system Ext stands for Extended File System. It was primarily developed for MINIX OS. The Ext file system is an older version, and is no longer used due to some limitations.
  
- Ext2 :- Ext2 is the first Linux file system that allows managing two terabytes of data, Individual File Size 16GB-2TB
  
- Ext3 :- Ext3 is developed through Ext2; it is an upgraded version of Ext2 and contains backward compatibility Individual File Size 16GB-2TB
  
- Ext4 :- Ext4 file system is the faster file system among all the Ext file systems. It is a very compatible option for the SSD (solid-state drive) disks, and it is the default file system in Linux distribution, Individual File Size 16GB-16TB
  
- XFS :- XFS is a highly scalable, high-performance file system and size is manage up to 16 exabytes
  
- Swap :- Swap memory it a virtual memory in linux, Swap space in Linux is used when the amount of physical memory (RAM) is full. If the system needs more memory resources and the RAM is full And accepts its space from SDD or HDD, according to the need we can extand and reduse swap file system.

> **How to extant swap memory in linux**

- sudo swapon --show
- free -h
- df -h
- sudo fallocate -l 1G /swapfile
- ls -lh /swapfile
- sudo chmod 600 /swapfile
- ls -lh /swapfile
- sudo mkswap /swapfile
- sudo swapon /swapfile

> **What is partistion in linux**

- it is a method by which we can break a disk into small small parts, These partition can be use to store OS files and personal data files.

> **In windows:-**

Disk 
partition  ==>   C:\    D:\    E:\   F:\  .....so on 
C:\   ==> mandatory Disk and remainigs are optional.

C:\  ==> use to store os file and we can also use it for the data. 
D:\  E:  F:\ ==> recommened drive to store data .

> **In linux:-**

there is no concept of  C:\  D:\  E:\   F:\  Drive.
Whole OS will represent by  / 
 [ root filesystem or root partition or parent directory ]

> **Disk Name in Linux**

1- PATA OR IDE  ===> hda ==> hda1  hda2 hda3   hdb ==> hdb1 hdb2 hdb3 ..etc
2- SATA         ===> sda ==> sda1  sda2  sda3....etc 
3- Virtual Disk ===> vda ==> vda1  vda2 

fdisk -l  ==> to find out the details about your disk
   OR
lsblk  

Disk  ==> 30 GB ==> During the Installation 

1- Automatic Partition   ==> machine will automatically used this space but we can not mentioned size manually
2- Custom Partition      ==> we can plan these partition as per needs

> **Types of Partition Creation technology ?**

- Standard Method OR Standard Volume ==> fixed size partition concept 
- LVM Method [ logical volume manager]     ==> Recomended,
we can extend or reduce this volume size in future

> **How many partitions requried to install linux OS ?**

1-    /              ==> OS Files + Data files    
2-    swap partition ==> Virtual memory ==> twice of main memory

> **About linux Partistion**

- Every hard drive always manage by MBR or GPT [GUID partition Table ] technology ?
- In first sector we have already installed MBR [master boot record ] technology.
- MBR Basically Bydefault  allow maximum four partition into any disk.
- MBR basically allow two types of partition .

- Primary partition  <== can be use to store os data and personal data.
- Extended partition <== 3- Logical partition

> **Primary Limits**

1- Min ==> 1 
2- MAX ==> 4 

> **Extended Limits  [can be optional ]**

> **What is the Filesystem Hierarchy Standard**

Filesystem hierarchy standard describes directory structure and its content,

- 1:- / (Root)
- 2:- /bin 
- 3:- /boot 
- 4:- /dev 
- 5:- /etc
- 6:- /home
- 7:- /lib
- 8:- /media
- 9:- /mnt
- 10: /opt
- 11:- /sbin
- 13:- /tmp
- 14:- /usr
- 15:- /proc

![This is a linux file system Hierarchy](../images/linuxfilesystemhierarchy.png)

1- Min  ==> 0 
2- Max  ==> 1

> **Switching Users in Ubuntu**

- sudo su (We can switch from another user)
- poweroff (power off the system with this command)
- init 0 (reboot the system), and init 1 (power off the system)

> **Recovering Deleted Files**

- Create a new text file on the desktop named coredge.txt, using the graphical file manager
- Delete the file by sending it to Trash.
- Verify the file is now in ~/.local/share/Trash, or a subdirectory thereof. NOTE: You will have to get your file browser to show      hidden files and directories, those that start with a .)
- Recover the file and make sure it is in its original location.
  
  


# Keep Learning......



