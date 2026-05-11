---
layout: post
title: "How to split a large file into several smaller files"
date: 2012-03-22 19:45:30 -0700
comments: true
categories: 
- it
---

Many thumb drives are formatted with FAT32, making the maximum file size just
shy 4GB. If you need to copy a large file like this to a thumb drive, follow the
instructions below.

<!-- more -->

Search for files too big to fit on your thumb drive
---------------------------------------------------

```bash
find ~/ -type f -size +4095M | xargs ls -lh
```

Split the large file into several smaller files on the thumb drive
------------------------------------------------------------------

```bash
split --bytes=4095m ~/largeFile /media/thumbDrive/largeFilePrefix
```

Put the smaller files back together as one large file on another computer
-------------------------------------------------------------------------

```bash
cat /media/thumbDrive/largeFilePrefix* > ~/largeFile
```

For Example:
------------

```bash
split --bytes=4095m IE9.ova /media/MyPassport/VirtualBoxVMs/IE9.ova_
```
