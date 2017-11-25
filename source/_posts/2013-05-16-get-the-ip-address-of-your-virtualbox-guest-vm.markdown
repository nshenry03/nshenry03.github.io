---
layout: post
title: "Get the IP address of your VirtualBox guest VM"
date: 2013-05-16 08:46:56 -0700
comments: true
categories: 
- ops
- virtualbox
---

Make sure you have VirtualBox's Guest Additions installed on the VM and then
simply run the following command from your host:

```bash
VBoxManage guestproperty get 'CentOS 6' '/VirtualBox/GuestInfo/Net/0/V4/IP'
```
