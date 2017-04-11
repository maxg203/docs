---
layout: single
title: 5 How to Use Django Static Files
category: tutorials
video: https://www.youtube.com/embed/3ETQf3TQ9gc?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
If we look at the `INSTALLED_APPS` in `tutorial/settings.py`, there is by default an app there called `django.contrib.staticfiles`. This is what Django uses as part of its very clever, built in static file management system. This allows it to collect the static files much like it does with the HTML templates, so that we can simply define where we want them to be stored in the `settings.py` file. Whether that means locally on disk or somewhere else like for example [Rackspace Cloudfiles](https://www.rackspace.com/cloud/files) or [Amazon S3](https://aws.amazon.com/s3/).

Let's create a CSS file in `accounts/static/accounts/style.css` and add a little CSS to make it clear when the file has been loaded:
``` css
body {
    background-color: blue;
}
```
At this point if you go to [localhost:8000/account](http://localhost:8000/account) you will not yet see the CSS being applied. This is because it has not been added to the page because it has not been linked in the HTML file that we want to style. To do this, add the link in the `head` of the file:
``` jinja
<link rel="stylesheet" href="{% raw %}{% static 'accounts/style.css' %}{% endraw %}" type="text/css">
```
Django will automatically detect the CSS file in the `static` folder (or within a subfolder of it like in this example). It will also resolve that dynamic url for us so that we can move where we store the static files without breaking all of the links.

It is often the case that you _will_ want to store your static files in a different place depending on the environment (in other words, whether the code is running in development or on the live site) so doing the links as above makes that much easier.
