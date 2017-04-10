---
layout: single
title: 8 How to Build an Entire Functioning Login Page
category: tutorials
video: https://www.youtube.com/embed/p_n7g6tVloU?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
The first step is to import the Django login view in `accounts/urls.py`:
``` python
from django.contrib.auth.views import login
```

Now add a url for the login view that was just imported:
``` python
    url(r'^login/$', login, {'template_name': 'accounts/login.html'})
```
You can view the page in development at [localhost:8000/account/login](http://localhost:8000/account/login). That page you see is now utilising the Django login view.

The view we just rendered in the browser also gives us access to a functional login form, but before we can use it, we're going to need to display it in the corresponding template that we just associated with the view called `accounts/login.html`.

First though, let's clean up those templates. Since we already have the `head` and `body` tags in the base template, they can be removed everywhere except the base template. We'll leave only the `head` and `body` _blocks_ instead. In `home.html`, you should now have something along these lines:
``` jinja
{% raw %}{% extends 'base.html' %}{% endraw %}
<h1>Home</h1>
{% raw %}{% block head %}{% endraw %}
<title>Home</title>
{% raw %}{% endblock %}{% endraw %}

{% raw %}{% block body %}{% endraw %}
<h1>Home</h1>
{% raw %}{% endblock %}{% endraw %}
```

We can also refactor the `login.html` template in a similar fashion:
``` jinja
{% raw %}{% extends 'base.html' %}{% endraw %}

{% raw %}{% block body %}{% endraw %}
<div class="container">
    <h1>Welcome</h1>
    <p>You can log in here!</p>
    <h2>Login</h2>
</div>
{% raw %}{% endblock %}{% endraw %}
```
This template forms the base of the login page, the final step is to put the form itself on the page. Under the login header `<h2>Login</h2>` above let's add that:
``` jinja
    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Login</button>
    </form>
```
There you go, now you have a login page! We just need to fix our database to be able to use it...
