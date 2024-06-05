---
layout: DevOps Learning
title: coredge.io india pvt ltd, DevOps Engineer. 
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

> **About of Git ?**

Original author:- Linus Torvalds
Operating system:- POSIX (Linux, macOS, Solaris Windows)
Initial release:- 7 April 2005; 19 years ago
Programming languages:- Python, C, C++, Perl, Shell script, Tcl

Mr Linus Torvalds is devoped Linux OS and Git.

> **What is Git ?**

Git is a version control system and 2 trype version control are available in the market, and we easy push and upload the code in the git server and any timne we can chenge and commit the code, If anyone changes the code then one of its created commit i'd, through which we come to know which user has changed what in the code.

1:- centralized version control system (CVCS)
2:- distributed version control system (DVCS).

> **centralized version control system (CVCS),**

with the help of Centralized version control system we can push and commit the code on git repository server, But reasion same drobacks of centralized version control system we are not use this.

> **Drobacks of centralized version control system CVCS:-**

- We needed internet to access the code, so if the internet was slow then the repository server would become slow which would cause problems in reducing it.
- If the repository server crashed for any reason, there was no backup of the server.

> **Distributed version control system (DVCS):-**

In Distributed version control system 2 copy are available of code, If our repository server fails or crashes we have another copy availebl in system and for access the code no need to access to internet, that the reasion Distributed version control system is a very popular version control system.

> **Advantage of Distributed version control system (DVCS)**

- We do not need any internet sleep to access the code
- second copy of code available in local machine and repository server.

> **Stages of Git ?**

We are available 3 Stages of git, 
After run this commmand (git init) git init in git CMD, from the name .git directory has been created and direcory and folder are created repository also 3 stages is created 
- 1:- Working Space OR Working Directory 
- 2:- Staging Aria 
- 3:- Local repo (Commit). 

> **1:- Working Space OR Working Directory :-**

Working Space and Working direcoty mean that, Working directory is the area where our code is available, where we can change, modify and commit the code, that is called Working Sapce OR Working direcotry. 

> **2:- Staging Aria:-**

When we are any changes in a code, then adding the code in staging aria with this cmmand (git add .) 

> **3:- Local Repo :-**

Local repositoy mean that code are availe in local system, or local disk space.

> **These are same command available, for push the code in github repository, and Add repository,**

- git init ( This command is activate and initialize of git)
- git remote add origin master "github url"
- git pull origin master (We are pull code from github server to local system)
- git status ( Showing status of git)
- git log ( Showing logs of git)
- git add . ( This command, your code to add in staging aria )
- git commit -m "Nitin Soni" ( This command is indicate to commit and commit user name)
- git push origin master ( Push the code in github server repo).

> **What is Branch in git ?**

Each task has one saprate branch, we can create multipule branches for coding of users and after done the code we can marge the code from master branch and this is a perallel branch, we can ceate any no of branches 

- git branch ( we can see all branches)
- git log --oneline ( we can see all commited code in a one line)
- git branch nitin ( we can create a branch from nitin name)
- git checkout nitin ( we can going to another branches)
- git branch -d "branch nname" ( With the hekp this command we can delete branch)

> **Marge branch and files in git ?**

We can't marge brachges of diffrence repository, and we can marg branch to another branch for copy the code, if any emplooye saying that, i want to wright the code in saprate, then i am creating saprate branch for user,

> **Note**

we can merge data to difrent branches and files, data can conflict.   

- git merge <branch name> ( from this command we can merge brach to another branch)
- git log ( we can verify git log)
- git merge branch1 ( we can marge branch for copy the codegit )
- git branch

> **What is Stack ?**

Stack is a linear data structure. The elements are inserted or removed from the same end. Queue is also a linear data structure. The elements are inserted or removed from two different ends, that is called (FIFO,First in first out And LIFO, Last in first out). In one stack we can uplaod and remove data from the stack.

 Push :- We can upload the data in stack
 pop :- We can remove the data from stack 

 > **Example of Stack**

 ![Book Logo](img src="https://cdn1.byjus.com/wp-content/uploads/2022/01/last-in-first-out-in-stack.png)

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

