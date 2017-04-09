---
layout: single
title: 6 How to Use Django Templates
category: tutorials
video: https://www.youtube.com/embed/wsoKEZRVC2Q?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj 
tags:
- django
- python
- html
---
To start utilising the Django templating language, let's pass some data through to the `accounts/login.html` template by editing the `home` view functon in the `accounts/views.html` to be rendered in the template:
``` python
def home(request):
    numbers = [1, 2, 3, 4, 5]
    name = 'Max Goodridge'

    args = {'myName': name, 'numbers': numbers}
    return render(request, 'accounts/login.html', args)
```
The dictionary `args` that is being passed in to `render` is optional, but passing it in here will give access to the contents of `name` and `numbers` in the corresponding template as `myName` and `numbers` respectively.

Now that the template has access to the data sent from the view, we can show it by simply doing for example:
``` html
<h1>{% raw %}{{ myName }}{% endraw %}</h1>
```
In a similar fashion, we can also use this style of templating to be able to iterate through any iterable object (the `numbers` list in this case) like so:
``` python
<ul>{% raw %}
    {% for number in numbers %}
        <li>{{ number }}</li>
    {% endfor %}
{% endraw %}</ul>
```
Now you should see all the content in the template at [localhost:8000/account](http://localhost:8000/account).
