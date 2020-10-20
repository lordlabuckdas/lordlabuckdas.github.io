---
title: "Linux PrivEsc - TryHackMe (draft)"
author: krishna
description: "Walkthrough of Linux PrivEsc from TryHackMe"
date: 2020-10-20 00:00:00 +0530
categories: [writeups, tryhackme]
tags: [privesc]
---

**[Linux PrivEsc](https://tryhackme.com/room/linuxprivesc)**

## Task 1 - Deploy the Vulnerable Debian VM

1. Deploy the machine and login to the "user" account using SSH.

	yea, `ssh user@MACHINE_IP`, then password = `password321`

2. Run the "id" command. What is the result?

	`uid=1000(user) gid=1000(user) groups=1000(user),24(cdrom),25(floppy),29(audio),30(dip),44(video),46(plugdev)`

	linuxprivesc1.png)

## Task 2 - Service Exploits

nice, good **mysql** exploit

## Task 3 - Weak File Permissions - Readable /etc/shadow

1. What is the root user's password hash?

	linuxprivesc2.png)

2. What hashing algorithm was used to produce the root user's password hash?

	`SHA512Crypt`

3. What is the root user's password?

	linuxprivesc3.png)

## Task 4 - Weak File Permissions - Writable /etc/shadow

## Task 5 - Weak File Permissions - Writable /etc/passwd

## Task 6 - Sudo - Shell Escape Sequences 

## Task 7 - Sudo - Environment Variables

## Task 8 - Cron Jobs - File Permissions

## Task 9 - Cron Jobs - PATH Environment Variable

## Task 10 - Cron Jobs - Wildcards

## Task 11 - SUID / SGID Executables - Known Exploits

## Task 12 - SUID / SGID Executables - Shared Object Injection

## Task 13 - SUID / SGID Executables - Environment Variables

## Task 14 - SUID / SGID Executables - Abusing Shell Features (#1)

## Task 15 - SUID / SGID Executables - Abusing Shell Features (#2)

## Task 16 - Passwords & Keys - History Files

## Task 17 - Passwords & Keys - Config Files

## Task 18 - Passwords & Keys - SSH Keys

## Task 19 - NFS

## Task 20 - Kernel Exploits

## Task 21 - Privilege Escalation Scripts
