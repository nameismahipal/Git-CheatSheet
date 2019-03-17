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

## Remote 

1. git remote -v
> shows remote origin/upstream

2. git remote add origin <#url>
> adds remote origin to git repo
 
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
 
 
## Delete

1. git branch -d <#branch-name>
> this will delete only label name, but not commits, so commits accessable by commit id.
 
## Garbage Collector

git gc

# DANGER

git reset --hard
> Removes changes in both Working directory and Staging directory
