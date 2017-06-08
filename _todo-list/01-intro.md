---
layout: single
title: 1 How to Build a To Do List
category: tutorials
video: https://www.youtube.com/embed/sVF5mzhlV-4?list=PLw02n0FEB3E0smsGO7EcnSqR-PCAWruJC
tags:
- introduction
- angular-1
- django-rest-framework
---
This is a brand new series on how to build a JSON API using Angular 1 and the Django Rest Framework. I will be using Python 3 for this project.

To get set up, make sure you have a virtual environment and install Django by doing ``pip install django==1.11.2`` with the virtual environment activated.

Now we can create the beginnings of our Django project by doing ``django-admin startproject todo``.

Let's go inside that folder and save the requirements to a file called ``base.txt``:
``` shell
cd todo
mkdir requirements
pip freeze > requirements/base.txt
```
Now we need to make sure our ``DJANGO_SETTINGS_MODULE`` environment variable is set correctly as below. I like to stick this in the virtual environment's ``postactivate`` script so that it will always be set correctly assuming the virtual environment is activated.
``` shell
export DJANGO_SETTINGS_MODULE=todo.settings
```
Your project should now run successfully with ``django-admin runserver``. In the next one, we'll look at organising a template or two.
