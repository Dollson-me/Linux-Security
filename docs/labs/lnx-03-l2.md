# LNX-03-L2 — Creating Users

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 154–170.

## Cel, misja i środowisko

- G Lab Objective Become familiar with commands used to create and manage users. 4 Lab Mission Create new users and configure customized home directories and password policies.
- 4 Lab Mission Create new users and configure customized home directories and password policies. esa rl ©) Lab Duration
- ©) Lab Duration 15-20 minutes fe Requirements e Basic working knowledge of terminal commands
- fe Requirements e Basic working knowledge of terminal commands Lt | Resources
- | Resources e Environment & Tools o VirtualBox o Debian environment from LNX-01-L3

## Komendy występujące w labie

```text
Find the option password [success=1 default=ignore] pam_unix.so obscure
nano /etc/pam.d/common- password
mkdir /etc/skel/template
1s /etc/skel/
adduser jane
su - jane
Ls
nano /etc/passwd
|
passwd test
pwck
```

## Powiązana teoria

- [Users](../03-users-permissions/users.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 154:** Linux Security

Lab Assignment Users and

Permissions

eo inn

aU LNX-03-L2

Creating Users

All Rights Reserved.

**PDF s. 155:** Linux Security

Lab Assignment Users and

Permissions

eo inn

aU LNX-03-L2

Creating Users

All Rights Reserved.

**PDF s. 156:** G Lab Objective

Become familiar with commands used to create and manage users.

4 Lab Mission

Create new users and configure customized home directories and password policies.

esa rl

©) Lab Duration

15-20 minutes

fe Requirements

e Basic working knowledge of terminal commands

Lt

| Resources

e Environment & Tools

o VirtualBox

o Debian environment from LNX-01-L3

o Terminal

**PDF s. 157:** Lab Task: Modify Password Length and Create and Modify

New Users

Use su and text editors to change the minimum required length to eight characters for

new user passwords. Then, use this configuration to create and modify new users.

1 Loginas the root user by running the su command.

2 Open the common-passwords file with the /etc/pam.d/common-password

command. The file contains the configuration for a login package.

3. Change the minimum password length requirement to at least eight characters.

Find the option password [success=1 default=ignore] pam_unix.so obscure

sha512 and append minlen=8 to the end of it.

4 Save the change by pressing Ctrl + o and Enter. Then, press Ctrl + x to exit the file.

5 Which folder’s content in the /etc/ directory is copied to new users?

6 Create a folder named template in /etc/skel with the mkdir /etc/skel/template

command.

7 Create a new user called jane with the adduser jane command and verify the

new settings were applied. Provide the user with a shorter password than the

one you specified previously.

Note: The system will accept the short password due to the root permissions.

8 Switch to the jane user with the su - jane command. Execute Is to view the

contents of the home directory and note the template directory.

9 Try to change the user’s password to 123 with the passwd command and note

the error message. Change the password to a more appropriate option.

10 switch back to the root user with the exit command.

11 Open the /etc/passwd file with the nano /etc/passwd command.

**PDF s. 158:** 12 Scroll to the bottom of the page and manually add a record for a new user based

on the following template:

<name>:X:<UID>:<GID>:,,,:/home/<name>:/bin/bash

Save the file and exit.

13 To create a user without using the adduser command, set a password for the

user with the passwd <name> command.

14 Check the integrity of the file using the pwck command. Note that pwck creates

an alert that the new user is missing a corresponding group, home directory, and

password entry in the shadow file, but it will not notice that it was added

incorrectly.

**PDF s. 159:** Linux Security

Lab Assignment Users and

& Solution Permissions

eo inn

aU LNX-03-LS2

Creating Users

All Rights Reserved.

**PDF s. 160:** Linux Security

Lab Assignment Users and

& Solution Permissions

eo inn

aU LNX-03-LS2

Creating Users

All Rights Reserved.

**PDF s. 161:** Note: Solutions for the instructor are shown in the green box.

G Lab Objective

Become familiar with commands used to create and manage users.

bs) Lab Mission

Create new users and configure customized home directories and password policies.

es .

©) Lab Duration

15-20 minutes

{e Requirements

e Basic working knowledge of terminal commands

Lt

| Resources

e Environment & Tools

o VirtualBox

o Debian environment from LNX-01-L3

o Terminal

**PDF s. 162:** Lab Task: Modify Password Length and Create and Modify

New Users

Use su and text editors to change the minimum required length to eight characters for

new user passwords. Then, use this configuration to create and modify new users.

1 Loginas the root user by running the su command.

john@debian: ~ x

File Edit View Search Terminal Help

t~$ su -

Password:

root@debian: ~#

2 Open the common-passwords file with the /etc/pam.d/common-password

command. The file contains the configuration for a login package.

Activities Terminal ¥ Wed 14:04

user@debian: ~

File Edit View Search Terminal Help

root@debian:~# nano /etc/pam.d/common- password

**PDF s. 163:** user@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/pam.d/common-password Modified

password [success=1 default=ignore] pam_unix.so obscure sha512 ff

password requisite pam deny.so

password required pam_permit.so

password optional pam_gnome_keyring.so

mc) Get Help Write Out (i) Where Is fg Cut Text Wy) Justify We Cur Pos

es Exit R Read File jg] Replace WY Uncut Text yj To Spell @ Go To Line

**PDF s. 164:** 3. Change the minimum password length requirement to at least eight characters.

Find the option password [success=1 default=ignore] pam_unix.so obscure

sha512 and append minlen=8 to the end of it.

Activities [) Terminal + Wed 13:59 a 0) ff ~

user @debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/pam.d/common-password Modified

password [success=1 default=ignore] pam_unix.so obscure sha512 minlen=sff

password requisite pam_deny.so

password required pam permit.so

password optional pam_gnome_keyring.so

is Get Help @ Write Out @@] Where Is Wy cut Text @) Justify We cur Pos

xian RECE Te BN Replace MU Uocut Text Mi To Spel Oe Go To a

**PDF s. 165:** 4 Save the change by pressing Ctrl + o and Enter. Then, press Ctrl + x to exit the file.

user@debian: ~

File Edit View Search Terminal Help

GNU nano 3.2 /etc/pam.d/common-password Modified

password [success=1 default=ignore] pam_unix.so obscure sha512 fj

password requisite pam_deny.so

password required pam_permit.so

password optional pam_gnome_keyring.so

ime Get Help @? Write Out i Where Is Ms Cut Text we) Justify Ms Cur Pos

is Exit i Read File gy Replace ly Uncut Text gy To Spell @ Go To Line

5 Which folder’s content in the /etc/ directory is copied to new users?

Jetc/skel

6 Create a folder named template in /etc/skel with the mkdir /etc/skel/template

command.

I jane@debian: ~ x j

File Edit View Search Terminal Help

root@debian:~# mkdir /etc/skel/template

root@debian:~# 1s /etc/skel/

template

root@debian: ~#

**PDF s. 166:** 7 Create a new user called jane with the adduser jane command and verify the

new settings were applied. Provide the user with a shorter password than the

one you specified previously.

Note: The system will accept the short password due to the root permissions.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# adduser jane

Adding user “jane' ...

Adding new group “jane' (1001) ...

Adding new user “jane' (1001) with group “jane' ...

Creating home directory “/home/jane' ...

Copying files from “/etc/skel' ...

New password:

Retype new password:

passwd: password updated successfully

Changing the user information for jane

Enter the new value, or press ENTER for the default

Full Name []:

Room Number []:

Work Phone []:

Home Phone []:

Other []:

Is the information correct? [Y/n] Y

root@debian: ~#

8 Switch to the jane user with the su - jane command. Execute Is to view the

contents of the home directory and note the template directory.

I jane @debian: ~ x ;

File Edit View Search Terminal Help

roote@debian:~# su - jane

jane@debian:~$ Ls

template

jane@debian:~$ ff

**PDF s. 167:** 9 Try to change the user’s password to 123 with the passwd command and note

the error message. Change the password to a more appropriate option.

jane@debian: ~ oo

File Edit View Search Terminal Help

:~$ passwd

Changing password for jane.

Current password:

New password:

Retype new password:

You must choose a Longer password

New password:

10 switch back to the root user with the exit command.

jane @debian: ~ x

File Edit View Search Terminal Help

Boshi) ekalie

Logout

roote@debian: ~#

**PDF s. 168:** 11 Open the /etc/passwd file with the nano /etc/passwd command.

jane@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/passwd

root@debian: ~# |

jane@debian: ~ x)

File Edit View Search Terminal Help

GNU nano 3.2 /etc/passwd

foot :x:0:0:root:/root:/bin/bash

daemon: x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

sync:X:4:65534:sync:/bin: /bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

We Get Help @@ Write Out @i] Where Is @M Cut Text

yi Exit x Read File gy Replace @e) Uncut Text

**PDF s. 169:** 12 Scroll to the bottom of the page and manually add a record for a new user based

on the following template:

<name>:X:<UID>:<GID>:,,,:/home/<name>:/bin/bash

Save the file and exit.

jane@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/passwd Modified

Debian-gdm:x:116:124:Gnome Display Manager: /var/lib$

vboxadd: x:998:1::/var/run/vboxadd: /bin/false

jane:x:1001:1001:,,,:/home/jane:/bin/bash

test:X:1002:1002:,,,:/home/test:/bin/bashff

We Get Help @@ Write Out @i} Where Is @M Cut Text

sy Exit x Read File gi Replace J Uncut Text

13 To create a user without using the adduser command, set a password for the

user with the passwd <name> command.

jane@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# passwd test

New password:

Retype new password:

passwd: password updated successfully

root@debian:~#

**PDF s. 170:** 14 Check the integrity of the file using the pwck command. Note that pwck creates

an alert that the new user is missing a corresponding group, home directory, and

password entry in the shadow file, but it will not notice that it was added

incorrectly.

jane@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# pwck

user ‘lp': directory '/var/spool/lpd' does not exist

user ‘news': directory '/var/spool/news' does not exist

user ‘uucp': directory ‘/var/spool/uucp' does not exist

user 'www-data': directory '/var/www' does not exist

user ‘list’: directory ‘/var/list' does not exist

user ‘irc': directory '/var/run/ircd' does not exist

user ‘gnats': directory ‘/var/lib/gnats' does not exist

user ‘'nobody': directory '/nonexistent' does not exist

user ‘_apt': directory ‘/nonexistent' does not exist

user ‘messagebus': directory '/nonexistent' does not exist

user ‘saned': directory '/var/lib/saned' does not exist

user ‘hplip': directory ‘/var/run/hplip' does not exist

user ‘usbmux': directory '/var/lib/usbmux' does not exist

user ‘pulse’; directory '/var/run/pulse' does not exist

user ‘vboxadd': directory '/var/run/vboxadd' does not exist

user 'test': no group 1002

user ‘test’: directory '/home/test' does not exist

Ino matching password file entry in /etc/shadow

add user ‘'test' in /etc/shadow?

</details>
