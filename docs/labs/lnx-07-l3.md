# LNX-07-L3 — Cron Security Vulnerability

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 450–465.

## Cel, misja i środowisko

- G Lab Objective Practice use cases for the Crontab application, and how to configure it to execute recurring tasks. In addition, learn about Crontab vulnerabilities. ba) Lab Mission
- ba) Lab Mission Set up a simple recurring task using Crontab, and exploit the task to gain access to files. CN) = @ Lab Duration
- @ Lab Duration 20-30 minutes tC) Requirements e Knowledge of Crontab.
- tC) Requirements e Knowledge of Crontab. on | Resources
- | Resources ¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Create a Crontab Task Set up a vulnerable Cron task that will be exploited in the next task. 1. Open the terminal. 2 Use the command nano /tmp/greeting.sh to create the script file "greeting.sh" in
2. Lab Task 2: Bypass Document Protection Create a protected file that other users cannot read, and see what can happen if a script that was set to be run by Crontab is not configured properly. 1 Use the command echo "super secret" > /home/[user]/Secret to create a file
3. Lab Task 1: Create a Crontab Task Set up a vulnerable Cron task that will be exploited in the next task. 1 Open the terminal. 2 Use the command nano /tmp/greeting.sh to create the script file "greeting.sh" in
4. Lab Task 2: Bypass Document Protection Create a protected file that other users cannot read, and see what can happen if a script that was set to be run by Crontab is not configured properly. 1. Use the command echo "super secret" > /home/[user]/Secret to create a file

## Komendy występujące w labie

```text
echo "Hello Sme!" > /tmp/crontabOutput.txt;
ls -l /home/john/
su - jorge
```

## Powiązana teoria

- [Cron Security](../07-host-security/cron-security.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 450:** Linux Security

Lab Assignment Host Security

Extra LNX-07-L3

°° —T— Cron Security Vulnerability

Ea

All Rights Reserved.

**PDF s. 451:** Linux Security

Lab Assignment Host Security

Extra LNX-07-L3

°° —T— Cron Security Vulnerability

Ea

All Rights Reserved.

**PDF s. 452:** G Lab Objective

Practice use cases for the Crontab application, and how to configure it to execute

recurring tasks. In addition, learn about Crontab vulnerabilities.

ba) Lab Mission

Set up a simple recurring task using Crontab, and exploit the task to gain access to files.

CN) =

@ Lab Duration

20-30 minutes

tC) Requirements

e Knowledge of Crontab.

on

| Resources

¢ Environment & Tools

o VirtualBox

= Debian

o Cron

e External Lab Links

© Crontab Guru: https://crontab.guru

**PDF s. 453:** Lab Task 1: Create a Crontab Task

Set up a vulnerable Cron task that will be exploited in the next task.

1. Open the terminal.

2 Use the command nano /tmp/greeting.sh to create the script file "greeting.sh" in

the /tmp directory.

3 Write the following commands in the file:

#!/bin/bash

me=$(whoami);

echo "Hello Sme!" > /tmp/crontabOutput.txt;

Save and exit the file.

4 Use the command chmod 777 /tmp/greeting.sh to assign all file permissions to

everyone.

5 Use the command crontab -e to invoke the crontab editor selector. Type 1 and

press Enter to select the nano editor.

6 Scroll to the bottom of the file and write the following line:

*** * * /tmp/greeting.sh

Save and exit the file.

Note: The five asterisks mean that the script will execute every minute.

7 Use the command Is /tmp/ , wait for 60 seconds, and execute the command

again. Note that the file "crontabOutput.txt was created.

8 Print the contents of the file using the command cat /tmp/crontabOutput.txt.

**PDF s. 454:** Lab Task 2: Bypass Document Protection

Create a protected file that other users cannot read, and see what can happen if a script

that was set to be run by Crontab is not configured properly.

1 Use the command echo "super secret" > /home/[user]/Secret to create a file

named "Secret" in your home directory, with "super secret” written inside the

file.

2 Use the command chmod 600 /home/user/Secret to grant read and write

permissions only to the file’s owner.

3 Use the command Is -I /home/[user]/ to verify the file's permissions.

4 Use the command su- [user] to switch to another non-root user (consider the

user from the previous lab).

5 Use the command cat /home/[user]/Secret to try to read the contents of the file

"Secret". Note that the user does not have the correct permissions.

6 Use the command nano /tmp/greeting.sh to open the greeting.sh script.

7 Atthe bottom of the script, add the command chmod 777 /home/[user]/Secret.

Save and exit the file.

8 Wait 60 seconds for the crontab task to take effect.

9 Try to display the contents of the "Secret" file again using the command cat

/home/[user]/Secret, and note that you have the required permissions.

Conclusion: A Crontab job can be useful, but also very dangerous if not

configured properly.

**PDF s. 455:** Linux Security

Lab Assignment Host Security

& Solution

Extra LNX-07-LS3

°° —T— Cron Security Vulnerability

EI

All Rights Reserved.

**PDF s. 456:** Linux Security

Lab Assignment Host Security

& Solution

Extra LNX-07-LS3

°° —T— Cron Security Vulnerability

EI

All Rights Reserved.

**PDF s. 457:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Practice use cases for the Crontab application, and how to configure it to execute

recurring tasks. In addition, learn about Crontab vulnerabilities.

ey Lab Mission

Set up a simple recurring task using Crontab, and exploit the task to gain access to files.

ea .

©) Lab Duration

20-30 minutes

fe Requirements

e Knowledge of Crontab.

Lt

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

o Cron

e External Lab Links

o Crontab Guru: https://crontab.guru

**PDF s. 458:** Lab Task 1: Create a Crontab Task

Set up a vulnerable Cron task that will be exploited in the next task.

1 Open the terminal.

2 Use the command nano /tmp/greeting.sh to create the script file "greeting.sh" in

the /tmp directory.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ nano /tmp/greeting.sh

3 Write the following commands in the file:

#!/bin/bash

me=$(whoami);

echo "Hello Sme!" > /tmp/crontabOutput.txt;

Save and exit the file.

File Edit View Search Terminal Help

me whoam1i

/tmp/crontabOutput.txt

lms Get Help f) Write Out Where Is if Cut Text [] Justify f@ Cur Pos

ee Exit a Read File @y Replace i) Uncut Texti™y To Spell Go To Line

**PDF s. 459:** 4 Use the command chmod 777 /tmp/greeting.sh to assign all file permissions to

everyone.

| john@debian: ~ x |

File Edit View Search Terminal Help

:~$ chmod 777 /tmp/greeting.sh

i-$

5 Use the command crontab -e to invoke the crontab editor selector. Type 1 and

press Enter to select the nano editor.

john@debian: ~ x

File Edit View Search Terminal Help

:-$ crontab -e

no crontab for john - using an empty one

Select an editor. To change later, run ‘'select-edit

or'

1. /bin/nano <---- easiest

2. /usr/bin/vim. tiny

Choose 1-2 [1]: J

**PDF s. 460:** 6 Scroll to the bottom of the file and write the following line:

*** * * /tmp/greeting.sh

Save and exit the file.

Note: The five asterisks mean that the script will execute every minute.

john@debian: ~ x

File Edit View Search Terminal Help

/tmp/crontab.X7JHy2/crontab Modified

* * * * * /tmp/greeting.sh

mo Get Help (@@ Write Out @i] Where Is @i Cut Text

Wa Exit Ms) Read File gay Replace MY Uncut Text

7 Use the command Is /tmp/ , wait for 60 seconds, and execute the command

again. Note that the file "crontabOutput.txt was created.

———LL ee

john@debian: ~ x“

File Edit View Search Terminal Help

:-$ Ls /tmp/

pulse-PKdhtXMmrién

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-apache2.service-lw6ycf

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-colord.service-c9W9ag

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-fwupd.service-aXYDKh

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-ModemManager . service-usna6h

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-rtkit-daemon.service-tvXxufj

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-upower.service-Outl2i

tracker-extract-files.1000

z-$ Ls /tmp/

icrontabOutput. txt

jpulse-PKdhtxmMmri1sn

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-apache2.service-lwoycf

sys temd-private-3563cb3c9f5b42b4858753ba45ac3673-colord.service-c9W9ag

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-fwupd.service-axYDKh

systemd-private-3563cb3c9f5b42b4858753ba45ac3673 -ModemManager .service-usna6h

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-rtkit-daemon.service-tvXxufj

systemd-private-3563cb3c9f5b42b4858753ba45ac3673-upower .service-Outl2i

jtracker-extract-files.1000

i~$ | |

Page5

**PDF s. 461:** 8 Print the contents of the file using the command cat /tmp/crontabOutput.txt.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat /tmp/crontabOutput.txt

Hello john!

ins

**PDF s. 462:** Lab Task 2: Bypass Document Protection

Create a protected file that other users cannot read, and see what can happen if a script

that was set to be run by Crontab is not configured properly.

1. Use the command echo "super secret" > /home/[user]/Secret to create a file

named "Secret" in your home directory, with "super secret” written inside the

file.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ echo “super secret" > /home/john/Secret |

2 Use the command chmod 600 /home/user/Secret to grant read and write

permissions only to the file’s owner.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ chmod 600 /home/john/Secret

**PDF s. 463:** 3 Use the command Is -I /home/[user]/ to verify the file's permissions.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ ls -l /home/john/

total 56

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Desktop

drwxr-xr-x 3 john john 4096 Sep 29 01:37 Documents

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Downloads

-rw-rw-rw- 1 john john 45 Sep 29 02:40 file.txt

-rw------- 1 john john 16 Sep 30 06:33 ftpTransfer.tx

iE

drwxr-xr-x 2 john john 4096 Sep 30 09:03 Hello

drwxr-xr-x 5 john john 4096 Sep 19 08:21 Music

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Pictures

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Public

-rw------- 1 john john 13 Oct 1 07:35 Secret

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Templates

drwxr-xr-x 2 john john 4096 Sep 29 03:14 test

-rw-r--r-- 1 john john 10 Sep 30 04:20 testFile

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Videos

john@debian:~$

4 Use the command su- [user] to switch to another non-root user (consider the

user from the previous lab).

j jorge@debian: ~ x 7

File Edit View Search Terminal Help

john@debian:~$ su - jorge

Password:

jorge@debian : ~$

**PDF s. 464:** 5 Use the command cat /home/[user]/Secret to try to read the contents of the file

"Secret". Note that the user does not have the correct permissions.

jorge@debian: ~ x

File Edit View Search Terminal Help

:~$ cat /home/john/Secret

cat: /home/john/Secret: Permission denied

:~$ I

6 Use the command nano /tmp/greeting.sh to open the greeting.sh script.

jorge@debian: ~ x

File Edit View Search Terminal Help

:~$ nano /tmp/greeting.sh |

7 Atthe bottom of the script, add the command chmod 777 /home/[user]/Secret.

Save and exit the file.

jorge @debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /tmp/greeting.sh Modified

me=s (whoami

Llo $me! /tmp/crontabOutput.txt

777 /home/john/Secret

mc Get Help @f@ Write Out @i) Where Is @i Cut Text

fd Exit fi Read File gy) Replace @Y Uncut Text

8 Wait 60 seconds for the crontab task to take effect.

**PDF s. 465:** 9 Try to display the contents of the "Secret" file again using the command cat

/home/[user]/Secret, and note that you have the required permissions.

Conclusion: A Crontab job can be useful, but also very dangerous if not

configured properly.

jorge@debian: ~ x

File Edit View Search Terminal Help

:~$ cat /home/john/Secret

super secret

:~$ fi

</details>
