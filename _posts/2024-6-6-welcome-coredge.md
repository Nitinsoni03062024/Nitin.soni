---
Layout: post
Titile: This is Basic About Git/GitHub (04/06/2024).
---


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

Each task has one saprate branch, we can create multipule branches for coding of users and after done the code we can marge the code from master branch and this is a perallel branch, we can ceate any no of branches, and when we are ceating any branch and in a branch write any changes and after addd and commit, so data is not repflect in master branch, only showing in saprate branch.and for exmaple we have create one branch and inside the branch, create one file and if not commit and not push so file is showing in all branches.

- git branch ( we can see all branches)
- git log --oneline ( we can see all commited code in a one line)
- git branch nitin ( we can create a branch from nitin name)
- git checkout nitin ( we can going to another branches)
- git branch -d "branch nname" ( With the hekp this command we can delete branch)

> **Marge branch and files in git ?**

We can marge brachges of diffrence repository, and we can marg branch to another branch for copy the code, if any emplooye saying that, i want to wright the code in saprate space, then i am creating saprate branch for user, after merge the data, data is available in both side. and data will merge in central repository, 
When same name file having diffrent contect in a diffrent branches, if you do merge data is conflict

> **we can merge data to difrent branches and files, data can conflict.**   

- git merge <branch name> ( from this command we can merge brach to another branch)
- git log ( we can verify git log)
- git merge branch1 ( we can marge branch for copy the codegit )
- git branch

> **What is Git Stashing**

Stashing is temporary storage for kept a data or code,
If you have written code in your project and now the customer gives any work on urgent basis then you have to work for the customer instead of working on your code and have to stop your code for a few hours. and we keep the code in stashing.

> **These are same command for stashing the code**

- git stash (we can stashing the code)
- git stash list ( we can see all shashing list)
- git stash apply stash@{0,1} ( we can find particuler stash)
- git stash clear ( to clear all stash)

> **Git Reset ? **

Git reset is a very poer full command, that is use to undo local changes to the state of a git repo, git reset basicly remove OR delete the changes from stagging area, befoure commit the code we can remove and delete the code fom stagging aria and local/working aria.

These are same command we can manage reset code from stagging aria.

- git reset filename (to reset the file from stagging aria)
- git reset . ( to reset all code from stagging aria)
- git reset hard ( Code is deleted from stagging aria and working space both)

> **What is Git revert ?**

The reset command helps you undo an exciting commit. after commit your code is public any one can access and see you file from central repository, it does not delete any data in this process insrtend rathere git created a new commit with the includes files reverted to their previous stat, so your version control history movies forword while the state of your file moves backword.

> **These are same commnd for revert your code,**

- git revert <commit i'd> ( Revet the command from this command)

> **How to remove untrack files**

- git clean -n (during the deleting file, this commnad ask that you are really you want to delete this file or not)
- git clean -f  (force fully can delete untrack file).
