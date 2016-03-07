---
layout: post
title: Print(a or b)
date: 2016-03-06 23:43:23
category: 
---

Using the `or` operator, you can print one variable or the other if one is `None` and the other is `not None`.  I discovered this when I wanted to print either an error or an output from a subprocess.Popen and did not want to write conditional logic to check which item contained output.


Python 3.4.3+ (default, Oct 14 2015, 16:03:50)
[GCC 5.2.1 20151010] on linux
Type "help", "copyright", "credits" or "license" for more information.

>>> a = "Hello"
>>> b = None
>>> print(a or b)
Hello

>>> a = None
>>> b = "Hello"
>>> print(a or b)
Hello

>>> a = "hello"
>>> b = "world"
>>> print(a or b)
hello
