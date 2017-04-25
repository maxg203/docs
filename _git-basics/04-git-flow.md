---
layout: single
title: 4 How to Use the Master and Develop Branches
category: tutorials
video: https://www.youtube.com/embed/KScwEeYwJJk?list=PLw02n0FEB3E1Sgm0vPnXEvBcRWAXncCLO
tags:
- git
---
Git Flow is the name of a branching methodology that can be used to enable developers to manage their source code more effectively together and on their own. It also allows for a much more convenient code review process.

At the moment, there is only one branch called `master`. Let's create another branch for the most active development called `dev`:
``` shell
git checkout -b dev
```
You can do `git branch to double check that we've now been switched to the newly created `dev` branch. I'm going to add (stage) some files so that they are ready to be committed. For me, that is:
``` shell
git add tutorial/requirements/*
```
You can do `git status` to make sure that the file(s) you want to include in the commit that follows are in fact ready to be committed. When that is as you want it, make a commit:
``` shell
git commit -m "Added requirements files"
```
Now you're ready to push that entire new branch (along with the newest commit) up to the remote repository:
``` shell
git push origin dev
```
If you want to double check where you are pushing to, check the remote by doing:
``` shell
git remote -v
```
You can then go to the link shown to see your updated code now in your remote repository on a new branch.
