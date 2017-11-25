---
layout: post
title: "Get wireless working on a Dell Inspiron 8500 in Ubuntu"
date: 2012-03-19 19:41:52 -0700
comments: true
categories: 
- it
---

First, you should check to be sure that you have the same wireless card (BCM4306
rev 02) that I do using the lspci command:

    maryjo@lubuntu-mjh:~$ lspci -vvnn | fgrep 14e4
    02:00.0 Ethernet controller [0200]: Broadcom Corporation BCM4401 100Base-T [14e4:4401] (rev 01)
    02:03.0 Network controller [0280]: Broadcom Corporation BCM4306 802.11b/g Wireless LAN Controller [14e4:4320] (rev 02)

If everything matches, you should be able to follow the steps below to get wireless working on your laptop.

<!-- more -->

Install firmware-b43legacy-installer
------------------------------------

```bash
sudo apt-get -y install firmware-b43legacy-installer
```
