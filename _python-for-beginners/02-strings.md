---
layout: single
title: 2 What are Strings in Python
category: tutorials
video: https://www.youtube.com/embed/J2fcKDk-B6E?list=PLw02n0FEB3E2RDlD2cBULQjvXJ1K_jS1O
tags:
- python
- beginner
---
A string in almost any popular programming language is always in either `"double quotes"` or `'single quotes'`. As far as the computer is concerned, these two different syntax are the same.

A string is a simple way of telling a computer that you want to store some data as is. In other words, when a string is output - the contents of the string will read exactly the same as you had typed it.

``` python
"This is a string."
```
The output is `'This is a string.'` so the same. Remember that the surrounding quotes are usually interchangeable.

Now why do I say "_usually_"? Let's look at another example:
``` python
'let's go'
```
This is invalid Python code as it raises a `SyntaxError`. To get around this, you can you a backslash (`\`) to tell Python to ignore the second single quote.
``` python
'let\'s go'
```
Python will carry on interpreting your code as a string until the final single quote as we expected. The output is `"let's go"` and we now have a string that has our desired contents. Have a go in your own Python shell by typing a string yourself.
