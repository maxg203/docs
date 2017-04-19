---
layout: single
title: 3 How to Create and Use a .gitignore File
category: tutorials
video: https://www.youtube.com/embed/f3yQu7YepuE?list=PLw02n0FEB3E1Sgm0vPnXEvBcRWAXncCLO
tags:
- git
---
Any files and folders that you choose can be hidden from Git and not tracked at all. The contents of the `.gitignore` file is what dictates what is tracked by Git and what is not. To hide the `.pyc` files from Git, create a file called `.gitignore` in the project root and add `*.pyc` in one line by doing:
``` shell
echo "*.pyc" > .gitignore
```
This will put anything inside the double quotes in a new file called (in this case) `.gitignore`.

The database file could also be added to the `.gitignore` file but for this there is an extra step because the file has already been committed in to the remote repository. To stop a file like this from being tracked by Git:
``` shell
git rm --cached db.sqlite3
```
This will make Git ignore this file now but it will _not_ remove it from the computer!

Now just make a commit and push to update the remote branch with those changes:
``` shell
git status
git add -A
git commit -m "Added .gitignore file, removed database"
git push origin master
```
