---
layout: post
title: "Subversion log by user name"
date: 2012-04-29 08:42:02 -0700
comments: true
categories: 
---

Ever wanted to know how to get a subversion log by user name? Here's how to do
it...

<!-- more -->

Step One: Get the revision number of the first commit to the branch
-------------------------------------------------------------------

```bash
svn log -r1:HEAD -l1 branches/Iteration-ABCD/
```

The result:

    ------------------------------------------------------------------------
    r12805 | nickh | 2012-03-27 12:26:37 -0600 (Tue, 27 Mar 2012) | 1 line
     
    Branching Iteration-ABCD
    ------------------------------------------------------------------------

Step Two: Get all changes by nickh on trunk since the branch
------------------------------------------------------------

```bash
svn log -rHEAD:12805 -v trunk/ | sed -n '/nickh/,/-----$/ p'
```

The result:

    ------------------------------------------------------------------------
    r12827 | nickh | 2012-03-28 14:13:57 -0600 (Wed, 28 Mar 2012) | 1 line
    Changed paths:
       A /trunk/dev/images/anImageA.png
       A /trunk/dev/images/anImageB.png
       A /trunk/dev/images/anImageC.png
       A /trunk/dev/images/anImageD.png
       M /trunk/dev/images/anImageE.png
       A /trunk/dev/images/anImageF.png
     
    Updated branded sites with Customizer images
    ------------------------------------------------------------------------
    r12823 | nickh | 2012-03-28 14:08:56 -0600 (Wed, 28 Mar 2012) | 1 line
    Changed paths:
       M /trunk/dev/styles/aStyleA.css
       M /trunk/dev/styles/aStyleB.css
       M /trunk/dev/styles/aStyleC.css
       M /trunk/dev/styles/aStyleD.css
     
    Updated branded sites with Customizer styles
    ------------------------------------------------------------------------
