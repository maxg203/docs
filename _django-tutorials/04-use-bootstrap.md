---
layout: single
title: 4 How to Use Bootstrap with Django
category: tutorials
video: https://www.youtube.com/embed/eAZS41vMSjI?list=PLw02n0FEB3E3VSHjyYMcFadtQORvl1Ssj
tags:
- django
- python
---
Let's improve the login template that we created in the last part by leveraging a powerful CSS framework called [Twitter Bootstrap](http://getbootstrap.com).

In `accounts/templates/accounts/login.html`, before we can start using Bootstrap, we need to add it to our page somehow. There are a few ways you can do this but for this example I'm going to use the CDN, which is one of the easiest ways to get up and running really fast.

I recommend that you refer to the [official Bootstrap getting started guide](http://getbootstrap.com/getting-started/#download-cdn) in order to get the latest CDN for this example. If you also want to use this, make sure you grab the link that corresponds with the Bootstrap CSS file, rather than the optional theme or the JavaScript file (unless you also want those things of course).

In my case, I added this just below the title tag in the `head` of the HTML template:
``` jinja
<link rel="stylesheet"
    href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
    integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u"
    crossorigin="anonymous">
```
We now have access to the Bootstrap CSS, so let's go ahead and use some of the new classes in the `body`:
``` jinja
<body>
    <div class class="container">
      <h1>Welcome</h1>
      Welcome! You can login here!
      <button type="button" class="btn btn-default">Login</button>
    </div>
    <div class="jumbotron">
      <h1>Welcome!</h1>
    </div>
</body>
```
Hopefully, now you can start to see how quick it can be to create good looking front end websites with Bootstrap. This allows us - especially back end developers - to be able to devote more of their time to developing the proper functionality of the site.
