# LNX-03-L3 — Group Management

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 171–187.

## Cel, misja i środowisko

- G Lab Objective Become familiar with user permissions and group management. 5 Lab Mission Use groups to allow or deny user access to folders and files.
- 5 Lab Mission Use groups to allow or deny user access to folders and files. ea . ©) Lab Duration
- ©) Lab Duration 15 - 20 minutes tC) Requirements e Basic working knowledge of terminal commands.
- tC) Requirements e Basic working knowledge of terminal commands. e Understanding of Linux user and group management. os
- | Resources ¢ Environment & Tools o VirtualBox o Debian

## Zadania / etapy

1. Lab Task 1: Modify Groups to Enable or Restrict Access to Files Create and configure groups in accordance with the instructions below. 1 Open the terminal and change to the user root with the command su -. 2 Display the permissions of /var/log with the command Is -I /var/log.
2. Lab Task 1: Modify Groups to Enable or Restrict Access to Files Create and configure groups in accordance with the instructions below. 1 Open the terminal and change to the user root with the command su -. john@debian: ~ x

## Komendy występujące w labie

```text
nano /scripts/tux.sh.
echo “developers only”
chmod 777 /scripts/tux.sh
ls -l /var/log
groups john
exit
nano /var/log/auth.log
su -
usermod -a -G adm john
root@debian :~-#
su - john
nano /var/log/auth. log
mkdir /scripts
nano /scripts/tux.sh |
ls -l /scripts/
groupadd devs
chown -R root:devs /scripts
fj
sh /scripts/tux.sh
chmod -R 770 /scripts/ |
ls -1 /scripts/
```

## Powiązana teoria

- [Groups](../03-users-permissions/groups.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 171:** Linux Security

Lab Assignment Users and

Permissions

Pedi baka

on .03-

JU LNX-03-L3

Group Management

All Rights Reserved.

**PDF s. 172:** Linux Security

Lab Assignment Users and

Permissions

Pedi baka

on .03-

JU LNX-03-L3

Group Management

All Rights Reserved.

**PDF s. 173:** G Lab Objective

Become familiar with user permissions and group management.

5 Lab Mission

Use groups to allow or deny user access to folders and files.

ea .

©) Lab Duration

15 - 20 minutes

tC) Requirements

e Basic working knowledge of terminal commands.

e Understanding of Linux user and group management.

os

| Resources

¢ Environment & Tools

o VirtualBox

o Debian

o Terminal

**PDF s. 174:** Lab Task 1: Modify Groups to Enable or Restrict Access to Files

Create and configure groups in accordance with the instructions below.

1 Open the terminal and change to the user root with the command su -.

2 Display the permissions of /var/log with the command Is -I /var/log.

3 Note which group allows its members to view the log file auth.log.

Note: The adm group is used by Debian to define users with permissions to

perform monitoring tasks.

4 Check which groups your user is part of with the command groups <user>.

5 Switch to your user with the command exit and try to read auth.log with the

command nano /var/log/auth.log

Note: The user cannot view the file.

6 Exit the file and use the command su — to switch to the user root.

7 Add your user to that group with the command usermod -a -G adm <user>.

Verify that the user was added to the group.

8 Change the login session to your user with the command su - <user> and check if

you can read the logs.

9 Return to the user root with the command exit.

10 Create a folder called scripts in the / location with the command mkdir /scripts.

11 Inthe “scripts” folder, use nano to create a file named tux.sh, using the command

nano /scripts/tux.sh.

Note: The file that will be created is a Bash script. You will learn about Bash

scripting later in the course.

12 Add the following content to the file and save it using Ctrl + 0:

**PDF s. 175:** #!/bin/bash

echo “developers only”

13 Make the file executable for everyone by using the command

chmod 777 /scripts/tux.sh

14 Add a group named devs with the command groupadd devs.

15 Set the owner of both the folder and the file to the user root and the group devs,

with the command chown -R root:devs /scripts

16 Verify that the ownership changed using the command Is -l /scripts/

17 Return to your user with the command exit, and try to run the scripts with the

command sh /scripts/tux.sh

18 switch to the root user.

19 Grant all permissions to the /scripts directory and files only to the owner and the

dev group, using the command chmod -R 770 /scripts/

20 Verify that the permissions changed, and try to execute the file with your user.

**PDF s. 176:** Linux Security

Lab Assignment Users and

& Solution Permissions

Pedi baka

on .03-

JU LNX-03-LS3

Group Management

All Rights Reserved.

**PDF s. 177:** Linux Security

Lab Assignment Users and

& Solution Permissions

Pedi baka

on .03-

JU LNX-03-LS3

Group Management

All Rights Reserved.

**PDF s. 178:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Become familiar with user permissions and group management.

5 Lab Mission

Use groups to allow or deny user access to folders and files.

of .

© Lab Duration

15 - 20 minutes

{e Requirements

e Basic working knowledge of terminal commands.

e Understanding of Linux user and group management.

Lt

[ea] Resources

e¢ Environment & Tools

o VirtualBox

o Debian

o Terminal

**PDF s. 179:** Lab Task 1: Modify Groups to Enable or Restrict Access to Files

Create and configure groups in accordance with the instructions below.

1 Open the terminal and change to the user root with the command su -.

john@debian: ~ x

File Edit View Search Terminal Help

i~$ su -

Password:

root@debian:~#

2 Display the permissions of /var/log with the command Is -I /var/log.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:-# ls -l /var/log

total 3792

-rw-r--r-- 1 root root 45169 Sep 17 03:30 alternatives. log

drwxr-xr-x 2 root root 4096 Sep 17 03:30 apt

-Tw-r----- 1 root adm 54117 Sep 23 05:27 auth. log

tiwe=-0--e01 root root 60374 Sep 23 01:21 boot.log

-rw-rw---- 1 root utmp 768 Sep 23 01:37 btmp

drwxr-xr-x 2 root root 4096 Sep 23 01:21 cups

-MW-r-+--- 1 root adm 607600 Sep 23 04:17 daemon.log

Ewes. 2901 oot adm 119436 Sep 23 01:27 debug

-rw-r--r-- 1 root root 804562 Sep 17 03:30 dpkg. log

-rW-r--r-- 1 root root 32064 Sep 23 04:58 faillog

+rw-r--r-- 1 root root 3575 Sep 17 01:59 fontconfig.log

drwx--x--x 2 root Debian-gdm 4096 Feb 9 2019 gdm3

drwxr-xr-x 3 root root 4096 Sep 16 10:59 ho

**PDF s. 180:** 3 Note which group allows its members to view the log file auth.log.

Note: The adm group is used by Debian to define users with permissions to

perform monitoring tasks.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ls -l /var/log

total 3792

-rw-r--r-- 1 root root 45169 Sep 17 03:30 alternatives.log

drwxr-xr-x 2 root root 4096 Sep 17 03:30 apt

-rw-r----- 1 root adm 54117 Sep 23 05:27 auth.log

-fw------- 1 root root 60374 Sep 23 01:21 boot.log

-rw-rw---- 1 root utmp 768 Sep 23 01:37 btmp

drwxr-xr-x 2 root root 4096 Sep 23 01:21 cups

-rw-r----- 1 root adm 607600 Sep 23 04:17 daemon.log

-fWw-r----- 1 root adm 119436 Sep 23 01:27 debug

+fW-r--r-= 1 root root 804562 Sep 17 03:30 dpkg. log

-fw-r--r-- 1 root root 32064 Sep 23 04:58 faillog

-rw-r--r-- 1 root root 3575 Sep 17 01:59 fontconfig.log

drwx--x--x 2 root Debian-gdm 4096 Feb 9 2019 gdm3

drwxr-xr-x_ 3 root root 4096 Sep 16 10:59 hp

You can see that the log files are accessible to the adm group.

4 Check which groups your user is part of with the command groups <user>.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# groups john

john : john cdrom floppy audio dip video plugdev netdev lLpadmin scanner

root@debian:~#

5 Switch to your user with the command exit and try to read auth.log with the

command nano /var/log/auth.log

Note: The user cannot view the file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# exit

Logout

john@debian:~$ nano /var/log/auth.log

**PDF s. 181:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 New Buffer

@e Get Help @@ Write Out @i) Where Is @M Cut Text

@g Exit @i Read File @N Replace @@ Uncut Text

6 Exit the file and use the command su — to switch to the user root.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ su -

Password:

root@debian:~#

7 Add your user to that group with the command usermod -a -G adm <user>.

Verify that the user was added to the group.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# usermod -a -G adm john

root@debian:-# groups john

john : john cdrom floppy audio dip video plugdev netdev lpadmin scanner

root@debian :~-#

Page5

**PDF s. 182:** 8 Change the login session to your user with the command su - <user> and check if

you can read the logs.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# su - john

john@debian:~$ nano /var/log/auth. log

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /var/log/auth. log

Blep 16 11:05:06 debian systemd-logind[353]: New seat seato.

Sep 16 11:05:06 debian systemd-logind[353]: Watching system$

Sep 16 11:05:06 debian systemd-logind[353]: Watching system$

Sep 16 11:05:06 debian systemd-logind[353]: Watching system$

Sep 16 11:05:46 debian login[378]: pam_unix(login:auth): ch$

Sep 16 11:05:46 debian login[378]: pam_unix(login:auth): au$

Sep 16 11:05:50 debian login[378]: FAILED LOGIN (1) on ‘/de$

Sep 16 11:05:53 debian login[378]: pam_unix(login:session) :$

Sep 16 11:05:53 debian systemd-logind[353]: New session 1 o$

Sep 16 11:05:53 debian systemd: pam_unix(systemd-user:sessi$

Sep 17 01:23:11 debian systemd-logind[368]: New seat seato.

Sep 17 01:23:11 debian systemd-logind[368]: Watching system$

Sep 17 01:23:11 debian systemd-logind[368]: Watching system$

Sep 17 01:23:11 debian systemd-logind[368]: Watching system$

Sep 17 01:23:31 debian login[399]: pam_unix(login:session) :$

Me Get Help @@ Write Out@l) Where Is @M Cut Text @§) Justify

Ws Exit ii Read Fileg) Replace @@ Uncut Tex@jj To Spell

**PDF s. 183:** 9 Return to the user root with the command exit.

john@debian: ~ x

File Edit View Search Terminal Help

1=$ exit

logout

root@debian:~#

10 Create a folder called scripts in the / location with the command mkdir /scripts.

I john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# mkdir /scripts

root@debian:~#

**PDF s. 184:** 11 Inthe “scripts” folder, use nano to create a file named tux.sh, using the command

nano /scripts/tux.sh.

Note: The file that will be created is a Bash script. You will learn about Bash

scripting later in the course.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /scripts/tux.sh |

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /scripts/tux.sh

@¢ Get Help @@ Write Out Where Is i Cut Text

@sa Exit @x Read File Replace gl Uncut Text

**PDF s. 185:** 12 Add the following content to the file and save it using Ctrl + o:

#!/bin/bash

echo “developers only”

jehn@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /scripts/tux.sh Modified

"developers Only"f

Mc Get Help @@ Write Out @l Where Is @M Cut Text

a Exit lx) Read File @N Replace J Uncut Text

13 Make the file executable for everyone by using the command

chmod 777 /scripts/tux.sh

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# chmod 777 /scripts/tux.sh

root@debian:~# ls -l /scripts/

total 4

-rwxrwxrwx 1 root root 35 Sep 23 07:24 tux.sh

root@debian:~#

**PDF s. 186:** 14 Add a group named devs with the command groupadd devs.

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# groupadd devs

root@debian: ~#

15 Set the owner of both the folder and the file to the user root and the group devs,

with the command chown -R root:devs /scripts

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# chown -R root:devs /scripts

root@debian:~# fj

16 Verify that the ownership changed using the command Is -l /scripts/

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ls -l /scripts/

total 4

-rwxrwxrwx 1 root devs 35 Sep 23 07:24 tux.sh

root@debian:~#

17 Return to your user with the command exit, and try to run the scripts with the

command sh /scripts/tux.sh

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# exit

Logout

john@debian:~$ sh /scripts/tux.sh

developers Only

john@debian: ~$

**PDF s. 187:** 18 Switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Help

pohs GU) =

Password:

root@debian:~#

19 Grant all permissions to the /scripts directory and files only to the owner and the

dev group, using the command chmod -R 770 /scripts/

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# chmod -R 770 /scripts/ |

20 Verify that the permissions changed, and try to execute the file with your user.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ls -1 /scripts/

total 4

-rwxrwx--- 1 root devs 35 Sep 23 07:24 tux.sh

root@debian:~# exit

Logout

:~$ sh /scripts/tux.sh

sh: 0: Can't open /scripts/tux.sh

i~$

</details>
