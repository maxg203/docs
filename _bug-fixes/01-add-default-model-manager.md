---
layout: single
title: Bug Fix 1 - Adding the Original "objects" Django Model Manager (Introduction)
category: tutorials
video: https://www.youtube.com/embed/KZoyeqrX3xk?list=PLw02n0FEB3E3_lL08MjkmrY4A7CJsrx9C
tags:
- introduction
- bug
- bug fix
- django
- python
---
Welcome to this ongoing series of bug fixes!

In this one, there is a bug related to the registration process in the social network built in the Django Tutorials series. When the registration form is submitted, we see a Django traceback:
>type object 'UserProfile' has no attribute 'objects'

To fix it, we just need to add the default manager again as an attribute on the UserProfile class so that we can refer to it again without getting rid of the `london` custom model manager.
``` python
objects = models.Manager()
```
And now there's a different error, great!
