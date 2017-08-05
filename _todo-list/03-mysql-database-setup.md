
---
layout: single
title: 3 How To Set Up Django with a MySQL Database Backend
category: tutorials
video: https://www.youtube.com/embed/s16p32pndK0?list=PLw02n0FEB3E0smsGO7EcnSqR-PCAWruJC
tags:
- django
- mysql
---
Before we configure Django to use MySQL as the database backend for the project, I will assume that you already have MySQL installed on your computer.

To check, you can type `mysql -u root` which should drop you in to the standard MySQL command line interface. I am using MySQL version 5.7.18, though that shouldn't matter too much.

To get started, we need to update the `DATABASES` setting in the Django settings file. Mine looks like this:
``` python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'todo',
        'USER': 'root',
        'PASSWORD': ''
    }
}
```
Now we need to install the Python package that allows Django to talk to MySQL more easily. I'm using Python 3, but if you're still using Python 2 you need to `pip install mysql-python`.
``` shell
pip3 install mysqlclient
```
Now, as one final step before Django can leverage the MySQL database backend, we need to manually create an empty database with the name that we specified earlier in the database settings. Jump in to MySQL by doing `mysql -u root` and create the `todo` database with `CREATE DATABASE todo;`.

You should now be able to access the MySQL prompt through the Django management command `django-admin dbshell`.
