---
layout: single
title: 9 How to Use Django Database Backend and Migrations
category: tutorials
video: https://www.youtube.com/embed/W16yjTa7cTw?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
At the moment, when we run the development server using `python manage.py runserver` there is a red message that says that (in my case) there are 13 unapplied migrations. This means that the database currently configured by your Django project is not in allignment with the rest of the project. At this point, it is the default models given to us by Django that do not yet have a place in the database.

To reflect the changes in Django migrations run `python manage.py makemigrations`. Migrations are still written in Python, are stored in a `migrations` folder for each app that has migrations and give Django the ability to figure out what SQL needs to be executed on the database itself. The next step is to execute it.

Apply all changes reflected by your Django migrations using `python manage.py migrate`.

Once the migrations have been applied successfully (denoted by `OK` in green for each migration), the database should be up to date. We can now run `python manage.py runserver` again without error - however, we can't login with an account and nor can we create one through the website's own registration process (as it doesn't have one).

To create an administrative (or superuser) account, run the Django `createsuperuser` management command:
``` shell
python manage.py createsuperuser
```
Add the required `username` and `password` data when prompted. You can also optionally add an email address to be associated with the account.

Run the development server again and you should be able to enter your new account information. You should be directed to `/accounts/profile` and see a HTTP 404 error. This is because the urls we have defined do not match `/accounts/profile`.

Let's quickly resolve that error by changing the URL _in the settings_ (not a `urls.py` as you might expect). At the end of the `tutorial/settings.py` file add:
``` python
LOGIN_REDIRECT_URL = '/account/'
```
You should now see the `accounts/static/accounts/home.html` template being rendered in the browser as dictated by the view, which in turn was chosen by our url configuration.
