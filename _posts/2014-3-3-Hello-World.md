---
layout: DevOps Learning
title: Coredge.io india pvt ltd, DevOps Engineer. 
---
# (03/06/2024) Monday
---

> What is Shell ?
---
To write a script in any OS a language is needed, which we call shell in Linux OR When we give any input into the system and after interpreting the same input into a shell, we give the output in the machine language, which is called shell, and shell is a intface between user and kernal, that shell is called Bash.
shell and kernel are reposable in the backend of whatever Linux is running.

> **Types Of Shell ?**

  Bourn Shell (sh) /bin/sh Bourn again shell (bash) /bin/bash Kourn shell (ksh) /bin/ksh C shell (Csh) /bin/csh
  echo $SHELL (With the help this command we can check shell in current Linux machine machine) and shell is located in /bin/sh location.
  when we are ceating shell scripting, so sript is devide in 2 parts, 1 :- sebang and header 2:- commented line 3 :- program body #!/bin/bash OR #!/bin/sh and This 
  is indicate to not commented) /bin/sh and /bin/bash ( This is indicate to shell location) you can fire this command in linux , echo $ECHO*

---
# (04/06/2024 and 05/06/2024)
---

> **What is shell scripting ?**

  Shell scripting is a set of command, with the help of shell scripting we can automante any task shell scripting, when we are input - any command from the keyboad   or mounse After interpreting the input, it converts our input into 0 and 1 and gives us output.
  When we are creating shell scripting so fist going to the anyh editor, for example (vim,nano,vi) these are 3 editors for linux OS.

> **3 Parameter are available in shell scripting.**

- 1:- shebang OR header section
- 2:- comment section
- 3:- Program body secotion

> **This is a basic shell scripting,** 

- vim coredge.sh (#This is coredege file for creating shell scripting, after enter we are gose to the editor)
- #!/bin/bash (#!, we can say not commaneted and /bin/bash, It means, this is location shell location and The interpreter takes our input and converts it into the - form of 0 and 1 and gives us output.)
- #!/bin/bash
 mkdir coredge
 touch coredge.io
 apt install apache2
 systemctl restart apache2
 echo "Hello Everyone"
 (This is normal basic shell scripting)
  And if we are run shell scripting file. and We should always know that when we create a shell scripting file, the file must have excution permissions to - - run it. we can run with help of .coredge OR sh .coredge
 these are tools are available in the market for automate the task
 Shell/Bash Scripting and Ansible for automate task

> **What is VIM Editor ?**

  VIM Editor it's test editor file, we can edit and modify any existing file and we can create new file accoring to the need.
  For Example :- If we want to create a new file, vim coredge, vim core, we can take any name

> **Types of Editor in Linux OS,**

- VIM,VI,NANO
  In VIM Editor, we can use these commands for save,quit,set number etc,
  1:- Esc+wq! = Enter (file save and quit from the file)
  2:- Esc+q!
  3:- I ( press i for eiditing in file)
  4:- / (we can search any work in file)
  5:- :set number ( With this coommand can set numnber of test lines), and these are same command we can use it.

> **What is Data Wrangling ?**

Data Wrangling it is kind to transforming or orgnaize you raw data into the same another formate, and wrangling data easy to undersatnd, according to the data wranging we can take a decision on data wranging, RAW data it's a critical data we can't ready and not understable data.

> **Data Wrangling gives us some features**

- Easy to understable
- transform/orgnize
- data accessing
- Analisys and process
- Improved Communication and Decision-Making

> **About Alterys Tools ( This is data analytics and visualization tool)**

Alteryx processes values based on the data type. Alteryx supports string, numeric, date-time, and boolean data types, as well as, spatial objects and Alteryx is used to automate data processes more quickly and efficiently
- CEO of Alterys :-  Mark Anderson
- Date founded:- 1997
- Founder: Dean Stoecker.

 > **What is Command-line Environment ?**

With the command line interface we can run any command and services, in server and systems all operation system are provide commaand line interface (CLI) Window,Mac,Linux, and CLI it's a faster interection interface.

These are CLI available inm the market for OS,
Window OS = CMD and and power shell
Linux OS = Linux itself CLI cammnd line 
Mac OS = Mac-CLI

We can oprate OS from the CLI method (Window,Mac,Linux).


> **What is Stack ?**

Stack is a linear data structure. The elements are inserted or removed from the same end. Queue is also a linear data structure. The elements are inserted or removed from two different ends, that is called (FIFO,First in first out And LIFO, Last in first out). In one stack we can uplaod and remove data from the stack.

 Push :- We can upload the data in stack
 pop :- We can remove the data from stack 

 > **Private Cloud**

Private cloud is not availale to each persion and private cloud are desined only instities or only orgnizations, private closud provide to security and costly, best example of open stack for private cloud, private cloud mostly use IAAS Service (Insfrasture As A Service). and more then costmized.

Private Cloud :- OpenStack 

> **About of openstack ?**

Written in:- Python
Initial release:- 21 October 2010, 14 years ago
Type of OpneStack :- Cloud
Developer: Rackspace Technology

> **Monolithic Kernal ?**

All OS related component stuffed as a single module of a kernal, all services are runing in a single kernal, If any service failed or crashes in Karnal then it becomes difficult to find the field service, these kernal are diffecult to debug.

Monolithic Kernal :- Linux,Unix,Dos

> **What is SSID :-**

SSID (Service set identifier), When we install Wi-Fi at home, and after installing Wi-Fi, we receive a name which is called SSID when we login to the wifi by entering the password.

