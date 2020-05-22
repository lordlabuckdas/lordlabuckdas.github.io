---
layout: page
title: "Bandit Walkthrough"
subtitle: "From OverTheWire"
date:   2020-05-22 16:42:22 +0530
categories: write-ups
---

# OverTheWire - Bandit

write-up for overthewire's [bandit](https://overthewire.org/wargames/bandit/)

**note :**

* i haven't included the passwords because 1. i was too lazy to note them down and 2. because otw wants it that way

* the username for login is `bandit#` where `#` is the level number

* if you are ssh-ing into another user while in the machine, use `ssh bandit#@localhost`, where `#` is as defined

* the cut commands can be ignored, they're just to print only the password

### Login / Level 0

```
ssh -l bandit0 -p 2220 bandit.labs.overthewire.org
```

### Level 1

```
cat readme
```

### Level 2

```
cat ./-
```

### Level 3

```
cat spaces\ in\ this\ filename
```

### Level 4

```
cat inhere/.hidden
```

### Level 5

```
cat $(file ./* | grep text | cut -f 1 -d ':')
```

### Level 6

```
cat $(find inhere -size 1033c -readable)
```

### Level 7

```
cat $(find / -size 33c -user bandit7 -group bandit6 2>&1 | grep -v "find: ")
```

### Level 8

```
cat data.txt | grep millionth | cut -f 2
```

### Level 9

```
cat data.txt | sort | uniq -u
```

### Level 10

```
strings data.txt | grep ==== | tail -n 1 | cut -f 2 -d ' '
```

### Level 11

```
base64 -d data.txt | cut -f 4 -d ' '
```

### Level 12

```
cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
```

### Level 13

```
mkdir /tmp/xyz; cp data.txt /tmp/xyz; cd /tmp/xyz; xxd -r data.txt > bandit12;
```

repatedly use `tar xvf`, `gunzip` and `bzip2` with `mv` and `file`

```
cat data8 | cut -f 4 -d ' '
```

### Level 14

```
ssh bandit14@localhost -i sshkey.private
```

### Level 15

```
nc localhost 30000 < /etc/bandit_pass/bandit14 | tail -n 2 | head -n 1
```

### Level 16

```
openssl s_client -connect localhost:30001
```

enter pwd obtained from lvl 14

### Level 17

```
nmap localhost -p 31000-32000 -sV -vv; openssl s_client -connect localhost:31790
```

copy key and create temp file in /tmp/bandit16, then `chmod 600 key`

```
ssh bandit17@localhost -i key
```

### Level 18

```
diff passwords.*
```

### Level 19

```
ssh -T bandit18@localhost
```

enter passwd obtained from bandit17

```
cat readme
```

### Level 20

```
./bandit20-do cat /etc/bandit_pass/bandit20
```

### Level 21

open two instances of bandit20, in one of them run,

```
nc -l -p 4200 < /etc/bandit_pass/bandit20
```

and in the other,

```
./suconnect 4200
```

### Level 22

```
cd /etc/cron.d; cat cronjob_bandit22; cat /usr/bin/cronjob_bandit22.sh
```

```
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

### Level 23

```
cat /etc/cron.d/cronjob_bandit23; cat /usr/bin/cronjob_bandit23.sh; echo I am user bandit23 | md5sum | cut -d ' ' -f 1
```

```
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

### Level 24

```
cat /etc/cron.d/cronjob_bandit24; cat /usr/bin/cronjob_bandit24.sh; mkdir -p /tmp/lmao; cd /tmp/lmao; vi test.sh
```

code for test.sh:

```
#!/bin/bash
cat /etc/bandit_pass/bandit24 > password.txt
```

change permissions: `chmod 777 test.sh; chmod 666 password.txt`

```
cp test.sh /var/spool/bandit24
```

wait for a minute,

```
cat password.txt
```

### Level 25

```
vi script.sh
```

code for script.sh:

```
#!/bin/bash

for i in {0..9}
do
    for j in {0..9}
    do
        for k in {0..9} 
        do
            for l in {0..9}
            do
                echo $(cat /etc/bandit_pass/bandit24) $i$j$k$l >> brut.txt
            done
        done
    done
done
```

then, run:

```
bash script.sh; cat brut.txt | nc localhost 30002 > key.txt; cat key.txt | tail
```

### Level 26

amazing level

```
cat /etc/passwd | grep bandit26; cat /usr/bin/showtext; ssh -i bandit26.sshkey bandit26@localhost
```

make sure you decrease the size of the terminal so that the `more` command doesn't executed completely

type v to access vim, then type, ```:e /etc/bandit_pass```

copy password, then type ```:set shell:/bin/bash` and `:shell```

### Level 27

```./bandit27-do cat /etc/bandit_pass/bandit27```

### Level 28

```
mkdir -p /tmp/testrepo; cd /tmp/testrepo; git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
```

```
cat repo/README
```

### Level 29

```
mkdir -p /tmp/tetsrepo; cd /tmp/tetsrepo; git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
```

```
cd repo; cat README.md; git log; git show c086d11a00c0648d095d04c089786efef5e01264
```

### Level 30

```
mkdir -p /tmp/randomname; cd /tmp/randomname; git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
```

```
cd repo; cat README.md; git branch -a; git checkout dev; cat README.md
```

### Level 31

```
mkdir -p /tmp/rand1; cd /tmp/rand1; git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
```

```
cd repo; git tag; git show secret
```

### Level 32

```
mkdir -p /tmp/rand2; cd /tmp/rand2; git clone ssh://bandit31-git@localhost/home/bandit31-git/repo
```

```
cd repo; cat README.md; echo echo "May I come in?" > key.txt; git add key.txt -f; git commit -m "done"; git push origin master
```

### Level 33

```$0```

```
cat /etc/bandit_pass/bandit33
```