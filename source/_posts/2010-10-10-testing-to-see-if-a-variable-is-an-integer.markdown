---
layout: post
title: "Testing to see if a variable is an integer"
date: 2010-10-10 18:49:06 -0700
comments: true
categories: 
- bash
---

Bash unfortunately does not include a built-in function to test if a variable is
an integer. There is however a simple pattern matching hack that you can use to
test this on your own:

Check for Unsigned Integer
--------------------------

```bash
[[ $number =~ ^[0-9]+$ ]] && echo "match found : integer"
```

Check for Signed Integer
------------------------

```bash
[[ $number =~ ^[+-]?[0-9]+$ ]] && echo "match found : (signed) integer"
```
