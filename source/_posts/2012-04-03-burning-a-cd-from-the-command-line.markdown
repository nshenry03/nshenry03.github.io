---
layout: post
title: "Burning a CD from the command line"
date: 2012-04-03 08:36:36 -0700
comments: true
categories: 
- it
---

Find your CD drive
------------------

```bash
cdrecord --devices
```

Burn your CD
------------

```bash
cdrecord -v --dev='/dev/sg1' ~/Downloads/ubuntu-12.04-beta1-alternate-amd64.iso
```
