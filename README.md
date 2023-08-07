# GIT AND GITHUB

## 1. Basic git command

repo -> repository

**git clone** -> bring a repo down from the internet (remote repository like Github) to your local machine

**git add** -> track your files and changes with Git

**git commit** -> save your changes into Git

**git push** -> push your changes to your remote repo on Github.

**git pull** -> to fetch and download content from a remote repository and immediately update the local repository to match that content.

**git status** -> check to see which files are being tracked or need to be commited

**git init** -> use this command inside of your project to turn it into a Git repository and start using Git with that codebase

git remote add origin <HTTPS of repo>

error: remote origin already exists.

Solution: git remote set-url origin <HTTP of repo>

## 2. More command

git clone <ssh key> : to clone repository from your github account

ls -la : shows file  present in the folder along with hidden one

git status : shows all files that have been added, updated or deleted(modified) but haven't committed yet

**untracked file** : git doesn't know about this file yet

**NOTE** : to commit file on git first we have to add the file

git add . : to update/track all the changes made in all file, what will be committed

git add <file_name>: to update/track only specified file, what will be committed

git commit -m "title" -m "Description" : title is mandatory field ex. Added index.html but description is optional. it gives information about what changes have been made git commit command saves our code locally

git push : to make changes live on github

git branch -M main : helps to rename our local branch as "main" which will match to our remote repo default branch name i.e "main"

**NOTE** : we put <name>.pub i.e public key on github, when we want to get data from our github account we have to give private key through which github will know that i had generated that public key and I am the owner.

cat <file_name> : gives content of the file

cd~ : (the character known as the tilde) to return to their home directory at any time.

clip < ~/.ssh/id_ed25519.pub : copy the content of the file

git restore <file> : to discard changes in working directory

git remote : gives all existing remotes for the current repository

git remote -v : (verbose) this will return not only the names of each remote but also its URLs:
origin  git@github.com:Prince0Pandey/gitlocal.git (fetch)
origin  git@github.com:Prince0Pandey/gitlocal.git (push)

## 3. how to initialize git repository locally and push it to github

1. create folder in your local machine

2. on bash cmd inside that directory run the below command for making it git repository and it contains a hidden folder with .git name
    git init

3.  write your code then check status using git status it will give "untracked file"
     git add .
     git commit -m "description"

4. git remote add origin <HTTPS>

5. git push -u origin main

now it will be pushed on github and when next time we have to push we use git push

-u is same as --set-upstream

## 4. Git Branching

**Main Branch** : Default branch of a repo 

**Feature Branch** : by default code in feature branch is same as main branch but if we make changes in feature branch those changes(commit) can be seen only from feature branch.
it is used to commit some functionality of the project but not sure if there is any bug in it so we put it in a feature branch if any error occur in code we can either solve it or delete it.
it does not effect our main branch

**Hotfix Branch** : when we have error on main branch we solve it in new branch.

**NOTE** : no branch will be able to know what changes(commit) had made to other branch

git branch : will list all the branches present in that repo.

git branch -d <name of branch> : will delete the branch.

**NOTE** : star at the start of branch means current branch on which we are right now

git diff : will give show all the changes we made since last commit

git diff <name of branch> : It will give difference b/w both branch code

**NOTE** : if the code is not present in current branch but present in <given name of branch> then it will be in minus(-) in red

 if the code is present in current branch but does not present in <given name of branch> then it will be in plus(+) in green

git checkout <name of branch> : will switch to given branch

git checkout -b <name for branch> : will create new branch

git commit -am "Description" : it can be used when we modify a file not create a file. Here we don't have to perform git add <name of file> command

git merge main :  : will add current branch changes to main branch

git reset or git reset <name of file>: will undo the last staging(whatever we added using git add <file name>) will be undone then it will show modified Readme.md file if we run git status cmd

git reset HEAD : HEAD means pointer to the last commit(so it will undo or reset the last commit) and git reset HEAD~1 HEAD~1 means one step further then last commit

git reset <hash of commit> : will reset/undo the commit but file will be modified

git reset --hard <hash of commit> : will remove the commit along with the modification

git log : show history of all commits

NOTE : enter only half name of branch then enter TAB will fill whole name
