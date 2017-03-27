---
layout: single
title: 1 Introduction to the Django Web Framework for Python
category: tutorials
video: 'https://www.youtube.com/embed/Fc2O3_2kax8'
tags:
- introduction
---

_So you want to learn Django?_

In whichever folder you want to store your project, create a folder called `Django` and change in to it:
``` shell
mkdir Django
cd Django
```
Now, if you know what a virtual environment is then I would highly recommend that you [use one](http://docs.python-guide.org/en/latest/dev/virtualenvs/) so that you can isolate your Python dependencies. If you use one, just drop the prepended `sudo` from the start of any applicable command. However, this tutorial assumes that you either don't or have chosen not to. In that case, do:
``` shell
sudo pip install Django
```
This will install the latest version of Python globally on your computer.

Now that we're all set up, we're ready to create a Django project called `tutorial`:
``` shell
python manage.py startproject tutorial
```
This creates a good starter template for your new website that has the following structure:
``` shell
├── manage.py
└── tutorial
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```
At this point, our new Django project is ready and working. To preview, type `python manage.py runserver` and go to [http://localhost:8000](http://localhost:8000) to see the default Django starter project home page.

You can also access the default Django administration page by going to [http://localhost:8000/admin](http://localhost:8000/admin).
