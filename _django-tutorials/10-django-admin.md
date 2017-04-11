---
layout: single
title: 10 Explaining the Django Admin
category: tutorials
video: https://www.youtube.com/embed/wxXVK_-GJl4?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---

Django has a very powerful management interface built right in to Django. This means that you can create, read, update and delete (CRUD) anything you may need to on your live site without even having to use the Django shell.

By default if you created your project with the `startproject` command, you will be able to go straight to the Django login page at [localhost:8000/admin](http://localhost:8000).

You can login using any Django user account credentials, although it is best to login as a superuser (create one as necessary by doing `python manage.py createsuperuser`) first.

When you are logged in, you should see `Groups` and `Users` underneath the heading `Authentication and Authorization`. `Groups` and `Users` are visual representations of two rather handy models that also come built in to Django for you to be able to manage those things as well as the permissions for those things as you see fit.

Let's click on `Users`. Now it shows you the `User` instances that you have created in your database. There is only one in my case - the superuser account called `max`, so let's click on that.

Now you can see the power of the Django admin. There is an extensive form that allows us to update and configure _everything_ on the `User` model for the selected instance. We can of course also change any of these things programmatically.
