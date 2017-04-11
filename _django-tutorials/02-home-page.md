---
layout: single
title: 2 How to Make a Home Page
category: tutorials
video: https://www.youtube.com/embed/IxkMeFzh5pI?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
If you have the development server running, close it by doing `Ctrl-C`.

Now you can create a new Django app:
``` shell
django-admin startapp accounts
```
It is called accounts here because the longer term goal for this series will be to create an entire login authentication and registration system.

In your project you now need to "install" the Django app you just created. Go to the `tutorial` folder that you created in your project's `tutorial/settings.py` file add another element in the `INSTALLED_APPS` list:
``` python
    'accounts',
```
So now your entire `INSTALLED_APPS` list should look like this:

``` python
INSTALLED_APPS = [
    'accounts',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```
Now that the new `accounts` app has been installed, we also need to tell Django how we're going to get to the new accounts app.

In the main url configuration, point Django to the accounts app when the user goes to (in this case) `/account`. Go to `tutorial/urls.py` and add a line to the `urlpatterns` (which was defined on the initial creation of our Django project):
``` python
    url(r'^account/', include('accounts.urls')),
```
We also need to import `include` so that line 16 now reads:
``` python
from django.conf.urls import url, include
```
Putting that all together we should now have in `tutorial/urls.py`:
``` python
from django.conf.urls import url, include
from django.contrib import admin

urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^account/', include('accounts.urls')),
]
```
Including`'accounts.urls'` here means that when someone makes a request to `/account` that Django will point them to the `urls/py` file in the `accounts` app (that's the one that we installed earlier).

You may have noticed that that file doesn't exist yet so let's create a new file in `accounts/urls.py:
``` python
from django.contrib.urls import url
from . import views

urlpatterns = [
    url(r'^$', views.home),
]
```
This tells Django to go to the not yet defined `home` view function in search of a HTTP response of some kind to be able to send back to the user (or client) that made the initial request. Let's define that in accounts/views.py:
``` python
from django.shortcuts import render, HttpResponse

# Create your views here
def home(request):
    return HttpResponse('Home page!')
```
Now you should be able to go to [localhost:8000/account](http://localhost:8000/account) to see your brand new, Django powered home page!
