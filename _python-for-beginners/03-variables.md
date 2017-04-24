---
layout: single
title: 3 How to Store Data in Variables
category: tutorials
video: https://www.youtube.com/embed/U3y_tLhym8Q?list=PLw02n0FEB3E2RDlD2cBULQjvXJ1K_jS1O
tags:
- python
- beginner
---
A variable is a container for other Python objects (such as a string, or anything else for that matter).

Let's define a variable:
``` python
someString = "This is a string!"
```
The variable `someString` has now been stored in memory. Its contents can easily be accessed by typing the variable name:
``` python
someString
```
This will output the same string as `'This is a string.'`. Remember that Python sees no difference between `'` and `"`. They are interchangeable.

Variables can also be multiplied using the `*` operator. For example:
``` python
someString * 2
```
This outputs `'This is a string.This is a string.'`. It quite literally multiplies the contents inside the variable called `someString`.

There is also a this called "string concatenation". That is a fancy way of saying "add some strings together". For example:
``` python
someString + "Some other string!"
```
This outputs `'This is a string.Some other string.'`.

A string is not the only type of data you can store in a variable in Python. There are more types and mathematical operators like the `*` and the `+` (seen in the examples above) in the next part.
