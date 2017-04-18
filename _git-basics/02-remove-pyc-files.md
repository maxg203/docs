---
layout: single
title: 2 How to Remove Unwanted Files from a Remote Repository
category: tutorials
video: https://www.youtube.com/embed/ZVlrqdTBtWU?list=PLw02n0FEB3E1Sgm0vPnXEvBcRWAXncCLO
tags:
- git
---
To remove the `.pyc` files (or any other file type for that matter) from a repository, first remove them locally:
``` shell
find . -name "*.pyc" -delete
```
Then commit that change:
``` shell
git add -A
git commit -m "Removed .pyc files"
```
See that commit that you just made locally by doing:
``` shell
git log
```
Finally, just send that change to the remote repository:
``` shell
git push origin master
```
