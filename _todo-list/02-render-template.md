---
layout: single
title: 2 How to Render a Template in the Main Django Project Folder
category: tutorials
video: https://www.youtube.com/embed/Mif2UqI09AA?list=PLw02n0FEB3E0smsGO7EcnSqR-PCAWruJC
tags:
- angular-1
- django-rest-framework
- templates
---
The Django project root is where we are going to create a new folder in which to store all our templates for this project.
``` shell
mkdir -p templates/todo
```
Now inside that folder create a new file called `index.html` and put some identifiable HTML contents in there like `<h1>To Do List</h1>` to make it obvious to us that Django is serving the correct template when we see it rendered in the browser.

We have the template, but no url to point at it yet - so instead of defining a custom Django view we, for this use case, can take advantage of the handy `TemplateView`. Add a line to your `urlpatterns`:
``` python
    url(r'^$', TemplateView.as_view(template_name='todo/index.html')),
```
The final step is to update the settings to make Django look in the correct place for our templates (as our location isn't entirely conventional). Add the `'templates'` folder name to the `'DIRS'` key in the `TEMPLATES` Django setting.

The template should now show up as the website's home page.

Bonus: The vim command I used to clean up my settings file fast was `:g/^\(#\|$\)/d`.
