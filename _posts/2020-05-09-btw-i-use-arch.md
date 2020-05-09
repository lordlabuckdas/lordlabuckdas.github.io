---
layout: page
title: "Oh, BTW I use Arch"
subtitle: "4 hours and 43 tabs later..."
date:   2016-05-09 22:22:22 +0530
categories: misc
---

## bro, do you even linux?

so i used to think linux was some os used by hackers and hard-core developers until my college's club gave us an intro about open-source. "what do you mean we can do anything we want from the command line?" "so you're telling me we can do **all** of this in a few commands?" linux and open-source was really fascinating. to have a lively community address your problems and not just a guy telling us the basic troubleshooting methods and later replying, "sorry to hear your problem, please send us a mail with screensho--- cmon we all know it's a dead-end." and so i delved into linux.

## the arch install

it doesn't take one long enough to know ```arch``` users are at the top of the linux chain. so curiouser and curiouser, i decided to try my hand at the dreaded-but-fun arch install. enter mid-sem holidays and lockdown. arch wiki had me confused at some points because i was a script-kiddie using ubuntu. so i tried to follow a tutorial - my biggest regret, because it was outdated. i followed the tutorial, and ended up with a broken ```grub loader```. fortunately, i was installing it on a vm, so two clicks and i start again from the beginning. few tries later, after some intense googling i realise the packages had been changed and the we had to install the ```kernel``` separately. ok fine, i was an idiot. fast forward an hour and i can't get internet connection for some reason. time for some more *intense googling*. on a whim, tried to install ```dhcpcd``` separately using pacman and boom! i get a working connection. i had kinda wasted another hour because ```dhcpcd``` came separately and not with ```network-manager``` ***sighs*** 

![aaaaaaaaaa](https://github.com/lordlabuckdas/lordlabuckdas.github.io/raw/master/assets/img/posts/arch-install.png "arch install")

## and that, is 

how i ended installing ```minimal arch```. oh, and it took half of all these efforts again for a desktop environment because - no cookies for guessing - of new packages. so ```moral``` of the story: if it doesn't work, 3/3 times it is the package. but tbh it was really fun and enlightening. really puts bloated oses into perspective. have an incredibly fast system with only the required packages is a delight. ok gtg, have to rice my arch for the 743rd time this month.