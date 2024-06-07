---
layout: post
title: Linux fundamental (07/06/2024)
---
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



![This is images if Linux Booting process, for better understranding](../images/Booting.png)



