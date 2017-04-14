---
layout: single
title: 1 How to Put Source Code on GitHub
category: tutorials
video: https://www.youtube.com/embed/M0yPNIjJ_yY?list=PLw02n0FEB3E1Sgm0vPnXEvBcRWAXncCLO
tags:
- introduction
- git
---
Git is the software itself (written in the C programming language) that is commonly used to manage source code. Companies like GitHub allow you to put your Git repository online somewhere so that it is easier to review and collaborate with others, amongst other things.

# Put It on GitHub
Open a new terminal window and make sure you are in the root folder for the project that you want to store on GitHub. For this example, I am going to use the source code from my Django project. To see the contents of that folder:
``` shell
ls -a
```
This will show you all the files and folders in the current directory. Let's assume you don't have `.git`  folder already. This folder will store important information about your source code to be able to manage it in its entirety using Git. The good news is, all you have to do to create one is:
``` shell
git init
```
Now your project is using a Git repository. To see what state your Git repository is in currently:
``` shell
git status
```
This will show you all the untracked files and folders. Untracked means quite simply that Git is not recording any changes that you make at the moment. _But it can._

The next step would be to "add" the files (we'll add them all in this case), so that they are ready to be commited:
``` shell
git add -A
```
Then we can commit the files and folders. Think of a commit as the changes you made to your project at a particular point in time. To see what we're about to commit, you can go `git status` again. Only the one in green will be committed. Because we used the `-A` flag, they should all be green and therefore a part of the following commit.
``` shell
git commit -m "Initial commit"
```
Unless you're doing what's called a merge commit, the `-m` flag followed by some sort of commit message is required in order to make a successful commit.

To see a history of recent commits:
``` shell
git log
```
Doing the with our new repository should show only one commit - the one that we just made.

The final step is to put this repository on GitHub. This assumes you have a GitHub account. On the website, you need to create a `New Repository` from the dropdown in the top right. Give it a name (mine is called `Django Tutorials`). GitHub will automatically turn spaces in to dashes because you can't have a space in a URL unless it has been percent-encoded.

Once that's done, follow the instructions on GitHub or do:
``` shell
git remote origin add https://github.com/maxg203/Django-Tutorials.git
git push origin master
```
