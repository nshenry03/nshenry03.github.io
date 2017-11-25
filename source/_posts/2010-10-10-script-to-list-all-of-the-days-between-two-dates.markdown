---
layout: post
title: "Script to list all of the days between two dates"
date: 2010-10-10 18:41:55 -0700
comments: true
categories: 
- bash
---

Occasionally I need a list of valid days between two dates. In the past, I
either generated this list manually or I hacked something else together to get
the job done. This week, I found myself in a situation where I needed to do this
task once again so I created a simple bash script to automate this process.

<!-- more -->

```bash
#!/bin/bash - 
#-------------------------------------------------------------------------------
#  Get parameters passed from the command line
#-------------------------------------------------------------------------------
sDate="${1}"
eDate="${2}"
 
#-------------------------------------------------------------------------------
#  Add a day to the eDate (so that it is included in the list as well)
#-------------------------------------------------------------------------------
eDate=$(date +%F --date "$eDate +1 days")
 
#-------------------------------------------------------------------------------
#  List the days
#-------------------------------------------------------------------------------
while [ "${sDate}" != "${eDate}" ]; do
  echo -e "${sDate}"
  sDate=$(date +%F --date "$sDate +1 days")# Increment sDate
done
```
