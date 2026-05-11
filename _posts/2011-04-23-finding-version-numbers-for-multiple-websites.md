---
layout: post
title: "Finding version numbers for multiple websites"
date: 2011-04-23 19:25:03 -0700
comments: true
categories: 
- bash
---

As a Systems Administrator, I often need to find out which version multiple
websites are on. With Linux, this often can be achieved with a surprisingly
quick one-liner:

<!-- more -->

```bash
for tarFile in $(ls)
do

  echo -n "$tarFile: "

  tar -O -xzf $tarFile "${tarFile%%.*}/config.php" \
  | fgrep sugar_version \
  | sed \
    -e "s/\s*'sugar_version' => '//" \
    -e "s/',$//"

done | sort -k2
```

    Acme.tar.gz: 5.2.0a
    BestBuy.tar.gz: 5.2.0k
    Chipotle.tar.gz: 5.2.0k
    DEWALT.tar.gz: 5.2.0k
    Exelon.tar.gz: 5.2.0k
    Ford.tar.gz: 5.2.0k
    GNC.tar.gz: 5.2.0k
    HP.tar.gz: 5.2.0k
    Igloo.tar.gz: 5.2.0k
    Jeep.tar.gz: 5.2.0k
    IllegalPetes.tar.gz: 5.5.4
    Salvagios.tar.gz: 6.0.3
    RadioShack.tar.gz: 6.1.2
