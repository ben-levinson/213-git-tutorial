## What is git?
Git is a form of version control. This allows you to more efficiently manage and keep track of changes to documents like source code. For projects that take a lot of time and/or many people you will definately want to have a cleaner way to share and track    -changes than zipping files up and emailing them out to everyone. There are other types of version control, but git is the most popular.

### Some terminology
There's a fair bit of terminology in git. Here are the basics:

* Repo - Short for repository. This is essentially a project folder where your code goes.
* Commit - Command to save changes to watched files in your repo
* Clone - Make a copy of a repo
* Branch - The data structure of commits often resembles a tree, changes can diverge from a given node
* Master - The default / production branch
* fork - Create a new branch. Often 3rd parties in open source projects
* Push - Upload a commit
* Pull - Download the most recent changes
* Merge - Combine two branches into 1
* Conflict - Occurs when merging, two or more people have changed the same lines
* Stage - What files are tracked to go into the next commit
* gitignore - File that specifies what files 


### Suggestions for Using Git
There are a lot of online clients that make using git easy. Sooner or later (now) you'll probably hear about GitHub. There are other services, but GitHub is the largest. Using your u.northwestern.edu account, you can sign up for a GitHub student account [here](https://education.github.com/pack). That gives you a lot of stuff you may not ever use, but one thing you should use for classwork is the unlimited free repositories. Using GitHub to collaborate with your group is great, but make it easy for other groups now or in the future to plagiarize your work.

## The easy way: GitHub Desktop
Git uses the command line, but GitHub does have a GUI client lets you do most of what you would need to do. Its good to learn the command line too, but if you're not doing anything too complex the GUI should work just fine. You can download it [here](https://desktop.github.com). More on this later, but even if you plan mostly plan on using the command line I would still suggest downloading it and logging into your github account with it. It should get everything setup easily for you to use your private repos. 

## The command line
There's only a handful of commands you need to go going:

* git init - create a new (local) repo
* git clone - Clone an existing repo
* git add - Addgit file(s) to be watched by the repo
* git commit - Create a commit. Always give a message with -m
* git push - Push your commit
* git pull - Get new changes
* git status - Show the current status of the repo
* git log - Show the commit log 
* git checkout branch_name - Switch to a different branch
* git merge commit_number - merge two branches

## Your first repo
There's a couple of ways to go about it. You can either first create a repo online, clone it to your local machine and then add files, or you could create a local repo first and then push it to GitHub. I personally think the first way is a little easier with private repos but either is fine. 

1. Go to your github home page. Click new repository
2. Type in a name
3. Choose public or private repo
4. Create repository 

This will take you to the repository screen. If you need to give access to someone else, go to the navigation bar at the top and hit settings. Go to collaborators and type in the other person's user name. 

To get started with your repo locally on the command line, click clone or download and then use HTTPS. Copy this link.

### On the terminal
#### Setup
1. Navigate to the directory where you want your local repo
2. Type git clone and paste the information here

#### Every time
3. Create/modify your files
4. Typing git status will show you it detects modified files
5. Type git add for each file you want added or use git add -a. This stages the files for the commit.
6. Type git commit -m "Your message here". The hello world equivalent is initial commit. The current state of these files are now saved, but they haven't been uploaded yet.
7. Type git push to upload modified files to your online repo
8. Type git pull to update your local files after someone else pushes.

### In GitHub Desktop
#### Setup
1.  Go to file, clone repository. A menu will appear with repositories on your account.
2. Choose a local path for the repo and hit clone. 

#### Every time
3. Create/modify your files
4. Go back to Github desktop. In the changes menu on the left side, make sure the files you want to commit are checked. The changes will be visible in the righthand pane. 
5. Type a commit message and commit to master or your branch
6. Click the push button in the top middle. 
7. Click it again to refresh, and it will change to pull if there is a commit to pull.

## Branches
### How to create a branch
On the command line git checkout -b branch_name will create and switch to a new branch.

On the GUI the button to the left of push/fetch/pull says current branch. Clicking it will open a dropdown that has a button saying create branch. Type a name in the text box to its left and click the button.

### How to change branches
On the command line, to change branches, type git checkout branch_name. It will download the version of files present at that branch. Commits will now occur on this branch.

On the GUI, the button to the left of push/fetch/pull indicates the branch. Clicking it will open a dropdown giving you the same effect as on the command line.  

## Merge Conflicts
#### How to initiate a merge
1. Checkout the target branch
2. Type git merge commit_number
 
Multiple people working on the same file or merging branches together may create merge conflicts. Merge conflicts most commonly occur when someone makes changes to code that is no longer the most up to date. Git is saying it doesn't know how to handle these very different pieces of code. 

Pulling frequently will largely prevent this from happening but if it does, your push will fail and affected sections of code will be surrounded in sections marked like this snippet:
![alt text](https://info201.github.io/img/git-branches/merge-conflict.png)

Once you clean this up, you have resolved a merge conflict and can commit again. 

### Reverting
One of the main advantages to using git with your projects is the ability to undo changes if things get seriously broken. To do this on the command line type:
git checkout commit_number file_name 

One the GUI, change to the history tab, and right click on the commit you wish to revert to. Click revert to this commit. 

## That's more or less it
There's a lot of other things in git. But that is really about all you need for most projects, but a couple last tips.
1. Make your commit messages meaningful. If you need to revert, the last thing you want to do is spend time looking through the change logs because all you said was "idk maybe it'll work."
2. Remember to actually push your commits. Others won't see your changes if you don't.
3. When you're working with other people, remember to pull before you start working. It'll keep your code updated and you won't need to deal with nearly as many merge conflicts.
4. For malloc lab in particular, you may want to leave your currently (mostly) functioning code alone. Create a new branch to work on major overhauls/changes to your code. That way you at least have a functioning version to hand in without having to undo a bunch of code that doesn't work. 
