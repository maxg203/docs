---
layout: single
title: 7 How to Write Better Django Templates
category: tutorials
video: https://www.youtube.com/embed/_fsJe_DeL94?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
- html
---
The goal of these template improvements is to allow us to write templates that are structures well and are more reusable so as to be able to reduce code duplication as much as possible.

Let's start firstly by creating the `home.html` template in the same folder as the `login.html` template and rendering it in `accounts/views.py` instead of the `login.html` template:
``` python
    return render(request, 'accounts/home.html', args)
```
There's no need to delete the `login.html` template because we can use that later to render the login form itself. For now, it just makes more sense to have the `home` view render the `home.html` template to render what is essentially the _home_ page.

Let's also create a new file in the parent directory of the current templates called `accounts/templates/base.html`. This will hold all the HTML for everything that we want to look consistent through more than one template (or even our entire site as necessary). This can eliminate a vast amount of superfluous, duplicated code in the other templates.

To be able to use that `base.html` template when the `home.html` template is rendered (like in the `home` view), it needs to be "extended". In `home.html`:
``` jinja
{% raw %}
{% extends 'base.html' %}
{% endraw %}
<h1>Home</h1>
```

In the newly created `accounts/templates/base.html`:
``` jinja
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet"
            href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
            integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u"
            crossorigin="anonymous">
        {% raw %}{% block head %}
        <title></title>
        {% endblock %}{% endraw %}
    </head>
    <body>
        <h1>Base</h1>
        {% raw %}{% block body %}
        {% endblock %}{% endraw %}
    </body>
</html>
```

Now again in `home.html` we can further utilise the `base.html` template from which it extends:
``` jinja
<!DOCTYPE html>
<html>
    <head>
        {% raw %}{% block head %}
        <title>Home</title>
        {% endblock %}{% endraw %}
    </head>
    <body>
        {% raw %}{% block body %}
        <h1>Home</h1>
        {% endblock %}{% endraw %}
    </body>
</html>
```
Any block tags defined in the `home.html` template will completely replace the contents of the ones defined inside the `base.html` template. You should notice now that even though the view is rendering `home.html` (without a link to the Bootstrap CDN), it still has access to it because that was defined explicitly _above_ `{% raw %}{% block head %}{% endraw %}` in the `base.html` template. If it was instead inside the `head` block, it would not be linked in the `home.html` template as the `head` block in that template takes precedence.
