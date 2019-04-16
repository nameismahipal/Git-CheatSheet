Practicing Git.

https://guides.github.com/features/mastering-markdown/

https://github.com/joshnh/Git-Commands

# Git Tips

## Log

1. git log  

> logs all the commits

2. git diff <commit#1> <commit#2>

> shows diff b/n 2 commits. first 4 digits are okay.

3. git log --stat

> logs all commits,but also shows which files are changed.
> q to quit log.

4. git log --graph --oneline <#branch-name> <#branch-name>
 
5. git log --graph --oneline 

6. git log -n1
> shows only 1 commit

7. Filter by Author
	- git log --author=Mahi
	- git log --author=“Mahipal Reddy” (for spacing)

8. git shortly 
> gives details of each contributor with no. of commits he/she did, and commit messages

9. git shortlog -s -n
> displays only the total no. of commits from each user. (-n) is to sort numerically

10. Filter by commit id (first 4 digits)
	- git show <# commit-id>

11. Filter by commit message
	- git log --grep="unit tests" (for spacing)
	- git log --grep=bug **(or)** git log --grep bug
> then Git will display only the commits that have the character b followed by the character u followed by g. 
		
## Remote 

1. git remote -v
> shows remote origin/upstream

2. git remote add origin <#url>
> adds remote origin to git repo

3. git remote add upstream <#original repository link from where we forked>

4. git remote rename <“new-name”> origin
5. git remote rename <“new-name”> upstream
 
## Git Push/Pull

1. git push origin <#branch-name>

2. git pull origin master <#branch-name-of-remote-Origin>

## Colored Output

1. git config --global color.uri auto

## Checkout

1. git checkout <checkout#>

> If the checkout # is a old version, then you are in detached Head state. Any changes made in detached head state, things get complicated.

## Staging Area

1. git add <#filename> or git add . (to add all files)
 
2. git reset <#file name>
> to remove file from Staging area
  
3. git status
> gives status about staging area

4. git commit -m "<#comment>"  or git commit => opens editor to add comment
  
## Branch

1. git branch
> shows all the existing branches

2. git branch <#name>
> creates a new branch with <name>
 
3. git checkout <#branch-name>
> changes will happen on this branch
 
4. git checkout -b <#new-branch-name>
> it creates new branch & checkouts that branch


## Different Directories

| Working Directory | Staging Area  | Repository Commit  |
| ----------------- |:-------------:| ------------------:|
| File 1      | File 1 | commit[File1, File2] |
| File 2*     | File 2 |                      |
   
  
   git diff
   > gives diff b/n *Working Directory* and *Staging Area*
   
   git diff --staged
   > gives diff b/n *Staging Area* and *Repository Area*
   
## Merge

1. git merge branch1 branch2 
> (same as git merge branch2 if you are in branch1)

2. *If you are in branch3,* 

   git merge branch1 branch2
> Here, branch1, branch2 get merged to branch3.

After Merge, git log shows commits of both branches lined based on timestamp.

3. git show <#commit>
> to see changes from its actual parent
 
## Merge Conflict

1. git merge --abort
> Restore files to their state before you Started the merge.
 
## Amend

git commit --amend
> to undo the most recent commit or to change the wording of commit message.

## Delete

1. git branch -d <#branch-name>
> this will delete only label name, but not commits, so commits accessable by commit id.
 
## Garbage Collector

git gc

# DANGER

git reset --hard
> Removes changes in both Working directory and Staging directory

***

## When Clone

|  Local copy |                          
| ----------------- |                        
| eb2 v1      |                            
| -> Master     |                     
| -> origin/master(last known pos) |  
 


| Github Repository (Origin) |
| ---------- |    
| eb2 v1 (last known pos) |
| -> Master |   

>When clone, 
> you get local copy of remote branch. Here it is Origin/Master ( you can have more than one remote)
> you get local branch, same as in Origin. Here it is Master

## When Commit Locally

|  Local copy |                          
| ----------------- |                        
| eb2 v1 - origin/master(pos of remote) |
|^|
| f34 v1 v1  (master)    |
 


| Github Repository (Origin) |
| ---------- |    
| eb2 v1 (Master) |   

## When Push

|  Local copy |                          
| ----------------- |                        
| eb2 v1 |
|^|
| f34 v1 v1  |
| -> master branch |
| -> origin/master of remote |
 

Local -> PUSH master -> Repo


| Github Repository (Origin) |
| ---------- |    
| eb2 v1 |
|^|
| f34 v1 v1  |
| -> master branch |

## Different Changes on Local and Github

|  Local copy |                          
| ----------------- |                        
| eb2 v1 |
|^|
| f34 v1 v1  |
|^|
| a72 v2 v1  (master branch) |
 

| Github Repository (Origin)|
| ---------- |    
| eb2 v1 |
|^|
| f34 v1 v1  |
|^|
| 5b3 v2 v1 (master branch) |

You can update, Only the Local copy by Fetching

#### git fetch Origin

|  Local copy |     |                     
| ----------------- |---|                        
| eb2 v1 ||
|^||
| f34 v1 v1   | --> 5b3 v2 v1 (origin/master) |
|^| |
| a72 v2 v1 (master)  | |

 
FETCH Operaion

| Github Repository|
| ---------- |    
| eb2 v1 |
|^|
| f34 v1 v1  |
|^|
| 5b3 v2 v1  (master branch) |

Local copy can be merged by, 

git merge master origin/master

This is same as, 
git pull origin master

== git fetch origin
   git merge master origin/master
