---
layout: post
title: "Adding an admin user to WordPress from the Command Line"
date: 2012-03-19 19:34:05 -0700
comments: true
categories: 
- wordpress
- sql
---

Ever wanted to know how to add a WordPress administrator from the command line?
Here's how to do it...

<!-- more -->

Insert a user into the 'wp\_users' table and get that user's ID
---------------------------------------------------------------

```sql
INSERT INTO wp_users (user_login, user_pass, user_nicename, user_email, user_registered, user_status, display_name)
VALUES ('nickh', MD5('someRandomPassword'), 'Nick', 'nickh@someemail.com', NOW(), 0, 'Nick Henry');

SET @lid := LAST_INSERT_ID();
```

Make the user that you just inserted an administrator
-----------------------------------------------------

```sql
INSERT INTO wp_usermeta(user_id, meta_key, meta_value)
VALUES (@lid, 'wp_capabilities', 'a:1:{s:13:"administrator";b:1;}');

INSERT INTO wp_usermeta(user_id, meta_key, meta_value)
VALUES (@lid, 'wp_user_level', '10');
```
