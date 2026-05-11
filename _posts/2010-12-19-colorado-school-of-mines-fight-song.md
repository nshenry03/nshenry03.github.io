---
layout: post
title: "Colorado School of Mines Fight Song"
date: 2010-12-19 18:56:28 -0700
comments: true
categories: 
- perl
- school of mines
---

Earlier this week, a couple of co-workers and I somehow got onto the topic of
school songs.

I still had a copy of a small portion of the song from the 'mines.pl' t-shirt
that was popular with computer science majors; however, I wanted to find the
rest of the song. It took a little digging, but I was eventually able to find a
cached copy of the song from the old CSM Alumni site. I thought I would post a
copy online to make it easier for anyone else who may be looking for a copy.

<!-- more -->

Colorado School of Mines Fight Song - "The Mining Engineer"
-----------------------------------------------------------

> In 1876 the school passed to the control of the new state of Colorado. It was
> during this period that our famous song, "The Mining Engineer", was adapted
> from the old English drinking song, "The Son of a Gambolier".
>
> We find the song featured on early programs, and our oldest living graduates
> testify that they learned it at this time.
>
> Question often arises as to whether our song originated at Mines or at the
> Georgia School of Technology.  Georgia Tech was chartered in 1885, and
> instruction first began there in 1888.  We know that our inspiring song
> originated on our campus at least ten years before Georgia Tech ever held
> classes.

Verse I
-------

    I wish I had a barrel of rum and sugar three hundred pounds,
    The college bell to mix it in and clapper to stir it round.
    Like every honest fellow, I take my whisky clear,
    I'm a rambling wreck from Golden Tech, a helluva engineer.

Chorus
-------

    A helluva, helluva, helluva, helluva, helluva engineer,
    A helluva, helluva, helluva, helluva, helluva engineer,
    Like every honest fellow, I take my whisky clear,
    I'm a rambling wreck from Golden Tech, a helluva engineer.

Verse II
-------

    And if I had a daughter, I'd dress her up in green,
    I'd send her up to Boulder to Coach the football team,
    But if I had a son, sir, I'll tell you what he'd do,
    He'd yell "To hell with Boulder," like his daddy used to do.

Chorus
-------

    A helluva, helluva, helluva, helluva, helluva engineer,
    A helluva, helluva, helluva, helluva, helluva engineer,
    Like every honest fellow, I take my whisky clear,
    I'm a rambling wreck from Golden Tech, a helluva engineer.

Verse III
-------

    If you want to gear the planets that revolve around the sun,
    We'll do the job up nicely, and we'll only call it fun,
    And if you want a bridge to Mars, or a ten-foot shaft to hell,
    We're the engineers of a thousand years and we'll do the job right well.

Chorus
-------

    A helluva, helluva, helluva, helluva, helluva engineer,
    A helluva, helluva, helluva, helluva, helluva engineer,
    Like every honest fellow, I take my whisky clear,
    I'm a rambling wreck from Golden Tech, a helluva engineer.

Verse IV
-------

_Submitted by - Laurence Gardner '53_

    The Miner's 'M', a symbol of a brand of mining men,
    Whose courage knocks the mountains down and builds them up again,
    No matter in this paydirt world orediggers choose to roam,
    Mines is always with them, The 'M' still stands for home.

mines.pl T-Shirt
----------------

The code for the 'mines.pl' t-shirt was
'[designed](http://ore.mines.edu/phpBB/viewtopic.php?f=66&t=1024&start=0#p4827)'
by one of CSM's many awesome teachers, [Mike Colagrosso](http://colagrosso.net).

```pl
#!/usr/bin/perl -w
use strict;
 
  my$song="helluva";                                my$drink="whisky";
  my$g="Golden";my$csm                            ="Tech";my$w="wreck"
  ;my$demeanor="honest";                        my$conscience="clear";
  my$a="rambling";my$enemy                     ="engineer,";my$f="ll";
       my$sp=chr(32);my$line                 ="A";for(1..4){$line
       .=$sp.$song.","}$line.=             $sp.$song.$sp.$enemy;;
       for(1..2){print$line,"\n"         ;}$enemy=~tr/,/\./;print
       "\040\010\114\151\153\145",     "$sp\145\166\145\162\171",
       "$sp";my$p=  "\160\162\151";; $p.="\156\164";  my$q="\042"
       ;my$simile=    "$p$sp$q\044\144\145\155ea".    "\156\157".
       "\162$q$sp"      ;eval$simile;my$grade="f"     ;eval"$p$sp
       $q$sp\044".        "\147\162\141\144e".        qq($q);eval
       "print\"e\"          ,\"$f\157\167\",          \"\054$sp\"
       ;";$_='\111            $sp\164\141\            153\145$sp\
       155\171$sp\              044\144\              162\151\156
       \153$sp\044                \143\               157\156\163
       \143\151\14                  5                 \156\143\14
       5,\n\111\04                                    7\155$sp\14
       1$sp\044\14                                    1$sp\044\16
  7$sp\146\162\157\155$                          sp\044\147\044\163\16
  0\044c\163m\54$sp\141                          $sp\44s\157\156\147$s
  p\044\145\156\145\155                          \171\n';s#\s*##g;;$_=
  eval"qq($_)$sp";eval"                          $p$sp\"$_\"$sp"#mikec
```

    $ ./mines.pl
    A helluva, helluva, helluva, helluva, helluva engineer,
    A helluva, helluva, helluva, helluva, helluva engineer,
    Like every honest fellow, I take my whisky clear,
    I'm a rambling wreck from Golden Tech, a helluva engineer.
