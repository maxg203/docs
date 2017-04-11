---
layout: single
title: 3 How to Use Django HTML Templates
category: tutorials
video: https://www.youtube.com/embed/Giasdb04Tk4?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj 
tags:
- django
- python
- html
---
In your `accounts/views.py` file, update your `home` view function from using the `HttpResponse` to using the `render` method so that we can use a seperate HTML file (or template) in order to render the page:
``` python
def home(request):
    return render(request, 'accounts/login.html')
```
Now we need to create that `accounts/login.html'` file that our view is now referencing above. By default, Django is going to look for templates in a folder called `templates` _within each Django app_. Let's create `templates/accounts/login.html` within the `accounts` app.

Now that we've got the template created, add some HTML inside there so that we can test that it is being rendered as expected:
``` jinja
<html>
    <head>
        <title>Login</title>
    </head>
    <body>
        Welcome! You can login here!
    </body>
</html>
```
You should now be able to preview everything by going to the same url [localhost:8000/account](http://localhost:8000/account). There are many advantages of using HTML templates to design your website. They offer much greater flexibility when it comes to adding static or dynamic content, they are more flexible and much easier to style by using a CSS file.
