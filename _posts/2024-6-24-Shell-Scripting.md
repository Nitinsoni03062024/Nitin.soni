---
layout: post
title: Shell Scripting ? 
---

# What is Shell ?

To write a script in any OS a language is needed, which we call shell in Linux OR When we give any input into the system and after interpreting the same input into a shell, we give the output in the machine language, which is called shell, and shell is a intface between user and kernal, that shell is called Bash. shell and kernel are reposable in the backend of whatever Linux is running.

> **Types Of Shell ?**

1. Bourn Shell (sh) /bin/sh 
2. Bourn again shell (bash) /bin/bash 
3. Kourn shell (ksh) /bin/ksh 
4. C shell (Csh) /bin/csh 
   
echo $SHELL (With the help this command we can check shell in current Linux machine machine) and shell is located in /bin/sh location. when we are ceating shell scripting, so sript is devide in 2 parts,

- 1:- sebang and header 
- 2:- commented line 
- 3:- program body 
- #!/bin/bash OR #!/bin/sh, (This is indicate to not commented)
- /bin/sh and /bin/bash (This is indicate to shell location) you can fire this command in linux , echo $ECHO*
  

> **What is shell scripting ?**

Shell scripting is a set of command, with the help of shell scripting we can automante any task shell scripting, when we are input - any command from the keyboad or mounse After interpreting the input, it converts our input into 0 and 1 and gives us output. When we are creating shell scripting so fist going to the anyh editor, for example (vim,nano,vi) these are 3 editors for linux OS.

> **3 Parameter are available in shell scripting.**

    1. shebang OR header section
    2. comment section
    3. Program body secotion

    This is a basic shell scripting,

    vim coredge.sh (#This is coredege file for creating shell scripting, after enter we are gose to the editor)

- #!/bin/bash (#!, we can say not commaneted and /bin/bash, It means, this is location shell location and The interpreter takes our input and converts it into the - form of 0 and 1 and gives us output.)
  
  {% highlight ruby %}

  #!/bin/bash 
  mkdir coredge 
  touch coredge.io 
  apt install apache2 
  systemctl restart apache2 
  echo “Hello Everyone” (This is normal basic shell scripting) 

  {% endhighlight %}

And if we are run shell scripting file. and We should always know that when we create a shell scripting file, the file must have excution permissions to - - run it. we can run with help of .coredge OR sh .coredge these are tools are available in the market for automate the task Shell/Bash Scripting and Ansible for automate task.

- This # is indiacte commment line
- << comment  (This is indicate multuiline comment)
  and close line after comment 

> **What is variable**

It is use to store or define any value into any name, that name or variable name can be call anywhere into the program 

- Santax,
- variable=value (we can't use the space between variable and value)
-  $ (Doller symbol is use to call any variable value OR  symbol is use to  print value of any variable)

  {% highlight ruby%}

!#/bin/bash (This is a Sebang section)

clear (this is commnad)
echo "Hello Every One How are You"

<<nitin (multi line commment)

My name is nitin soni and i am learning basic
shell scripting

nitin (pass the comment from starting commnet)

  {% endhighlight %}

> **Types of Quotes**

1. Single Quota ( '' )
2. Doublle Quota ( "" )
3. Back Quota ( `` )
4. echo $? (what is last status of command)
5. sh -x nitin.sh (we can check step by step command performed)
  
6. **Single Quota ( '' )** 
  
Print as it is 

2. **Doublle Quota ( "" )**
  
We can print message with variable and values as well

3. **Back Quota ( `` )**
   
It is use to pirnt output of any command ony, in back quotes we can not pirnt any message otr any value of any varialble
For Exmaple,
 ` Command ` OR $(Command)

{% highlight ruby %}


date +%A
date +%H:%M

date --help

{% endhighlight %}


> **This is basic Script for practice**


{% highlight ruby %}

!#/bin/bash

clear
echo "Hello EveryOne How are You"
date +%A
cal
date +%H:%M
echo "My machine name is $`hostname`" # OR $(hosname) both commmand are same
echo "Hello everyone my name is nitin soni I am working coredge.io india private limited company as a DevOps Engineer Trenee"
echo "What is my current path $(pwd)"
mkdir /home/nitinsoni-$(date +%H:%M)
cal
expr 10 + 10
expr 10 - 4
expr 10 / 5
expr 10 \* 2

#date --help

echo ""
echo ""

a=10
b=10
expr $a + $b
<<nitin

My name is nitin soni and i am learning basic
shell scripting

nitin


{% endhighlight %}

# Keep Learning.......