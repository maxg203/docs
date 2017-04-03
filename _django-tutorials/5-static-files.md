---
layout: single
title: 5 How to Use Django Static Files
category: tutorials
video: https://www.youtube.com/embed/3ETQf3TQ9gc?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
If we look at the `INSTALLED_APPS` in `tutorial/settings.py`, there is by default an app there called `django.contrib.staticfiles`. This is what Django uses as part of its very clever, built in static file management system. This allows it to collect the static files much like it does with the HTML templates, so that we can simply define where we want them to be stored in the `settings.py` file. Whether that means locally on disk or somewhere else like for example [Rackspace Cloudfiles]() or [Amazon S3]().
