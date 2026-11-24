# LNX-03-L4 — The Power of SUID

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 188–203.

## Cel, misja i środowisko

- G Lab Objective Understand the potential of SUID in Linux systems. 5 Lab Mission Configure a SUID on one of the system’s binaries to copy classified data with a simple
- 5 Lab Mission Configure a SUID on one of the system’s binaries to copy classified data with a simple user. oe :
- © Lab Duration 15 - 25 minutes fe Requirements e Basic working knowledge of the terminal.
- fe Requirements e Basic working knowledge of the terminal. e Understanding of SUID. Lt
- | Resources ¢ Environment & Tools o VirtualBox o Debian

## Zadania / etapy

1. Lab Task 1: Setting a Binary with SUID Set a binary with SUID to allow simple user access to classified data. 1 Log in to Debian with your user and open the terminal. 2 Create a file named “secret.txt” on your desktop with the command touch
2. Lab Task 2: Sudo In this task, you will provide your user with the ability to use high-level permissions in the system. This will allow you perform sensitive operations without having to switch to the root user.
3. Lab Task 1: Setting a Binary with SUID Set a binary with SUID to allow simple user access to classified data. 1 Log in to Debian with your user and open the terminal. Activities D2) Terminal ~ Thu 05:49 24, Or

## Komendy występujące w labie

```text
cp /etc/shadow ~/Desktop/secret.txt. Note the permission error.
ls -l /usr/bin/ | grep -w "cp"
fj
chmod uts /usr/bin/cp
ls -l /usr/bin/ | grep -w “cp”
exit
chmod 755 /usr/bin/cp
1s -l /usr/bin/ | grep -w "cp"
fj |
apt update
apt install sudo -y
sudo
visudo| |
```

## Powiązana teoria

- [Suid Sgid Path](../03-users-permissions/suid-sgid-path.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 188:** Linux Security

Lab Assignment Users and

Permissions

LNX-03-L4

°

we == The Power of SUID

El

All Rights Reserved.

**PDF s. 189:** Linux Security

Lab Assignment Users and

Permissions

LNX-03-L4

°

we == The Power of SUID

El

All Rights Reserved.

**PDF s. 190:** G Lab Objective

Understand the potential of SUID in Linux systems.

5 Lab Mission

Configure a SUID on one of the system’s binaries to copy classified data with a simple

user.

oe :

© Lab Duration

15 - 25 minutes

fe Requirements

e Basic working knowledge of the terminal.

e Understanding of SUID.

Lt

| Resources

¢ Environment & Tools

o VirtualBox

o Debian

**PDF s. 191:** Lab Task 1: Setting a Binary with SUID

Set a binary with SUID to allow simple user access to classified data.

1 Log in to Debian with your user and open the terminal.

2 Create a file named “secret.txt” on your desktop with the command touch

Desktop/secret.txt. Verify that the file was created with the command Is

Desktop.

3 Try to copy the content of the shadow file to secret.txt with the command

cp /etc/shadow ~/Desktop/secret.txt. Note the permission error.

4 Print the content of secret.txt with the command cat Desktop/secret.txt and

note that it is still empty.

5 Print the permissions of the shadow file with the command

Is -| /etc/ | grep shadow.

Why did you get a permission denied message?

6 Switch to the user root with the command su-

7 Print the permissions of the cp binary with the command

Is -| /usr/bin | grep -w “cp”

Note that it does not use SUID.

8 Set a SUID on the cp binary to allow its execution with root permissions.

Use the command chmod ut+s /usr/bin/cp.

Verify that it was activated.

9 Return to your user with the command exit.

10 Try to copy the content of shadow to secret.txt again. Note that this time the

command was successful and the content was copied.

11. Return the binary permissions to their former state by switching to the root

user and running the command chmod 755 /usr/bin/cp.

**PDF s. 192:** 12 How does SUID affect Linux OS security?

**PDF s. 193:** Lab Task 2: Sudo

In this task, you will provide your user with the ability to use high-level permissions in

the system. This will allow you perform sensitive operations without having to switch to

the root user.

1 Switch to the root user with the command su -

2 Execute the command apt update

3 Execute the command apt install sudo -y

4 Use the command visudo to open and edit the soduers file.

5 Scroll to the bottom of the file and add your user in the following format:

<user> ALL=(ALL:ALL) ALL

Add it below the root configuration.

Save the file and close it.

6 To verify that your user now has the ability to work with root permissions, return

to the user and run the command sudo cat /etc/shadow. Provide the password

when prompted.

**PDF s. 194:** Linux Security

Lab Assignment Users and

& Solution Permissions

LNX-03-LS4

°

we == The Power of SUID

El

All Rights Reserved.

**PDF s. 195:** Linux Security

Lab Assignment Users and

& Solution Permissions

LNX-03-LS4

°

we == The Power of SUID

El

All Rights Reserved.

**PDF s. 196:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand the potential of SUID in Linux systems.

5 Lab Mission

Configure a SUID on one of the system’s binaries to copy classified data with a simple

user.

esa .

©) Lab Duration

15 - 25 minutes

r Requirements

e Basic working knowledge of the terminal.

e Understanding of SUID.

oo

| Resources

e¢ Environment & Tools

o VirtualBox

o Debian

**PDF s. 197:** Lab Task 1: Setting a Binary with SUID

Set a binary with SUID to allow simple user access to classified data.

1 Log in to Debian with your user and open the terminal.

Activities D2) Terminal ~ Thu 05:49 24, Or

john@debian: ~ x

File Edit View Search Terminal Help

$f

2 Create a file named “secret.txt” on your desktop with the command touch

Desktop/secret.txt. Verify that the file was created with the command Is

Desktop.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ touch Desktop/secret.txt

:~$ Ls Desktop/

secret .txt

a |

**PDF s. 198:** 3 Try to copy the content of the shadow file to secret.txt with the command

cp /etc/shadow ~/Desktop/secret.txt. Note the permission error.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cp /etc/shadow Desktop/secret.txt

Cp: cannot open '/etc/shadow’ for reading: Permission denied

==>

4 Print the content of secret.txt with the command cat Desktop/secret.txt and

note that it is still empty.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat Desktop/secret.txt

=$

5 Print the permissions of the shadow file with the command

Is -| /etc/ | grep shadow.

Why did you get a permission denied message?

john@debian: ~ x 7

File Edit View Search Terminal Help

:~$ ls -l /etc/ | grep shadow

-rw-r----- 1 root shadow 774 Sep 17 03:49 gshadow

-rw-r----- 1 root shadow 763 Sep 17 02:01 gshadow-

-rw-r----- 1 root shadow 1280 Sep 24 05:20 shadow

-rw-r----- 1 root shadow 1258 Sep 17 02:01 shadow-

Bons

According to the output of the command, all users who are not root users, or are not

part of the shadow group, are not allowed to read the file.

**PDF s. 199:** 6 Switch to the user root with the command su -

john@debian: ~ x

File Edit View Search Terminal Help

:~$ SU -

Password:

root@debian:~#

7 Print the permissions of the cp binary with the command

Is -| usr/bin | grep -w “cp”

Note that it does not use SUID.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~-# ls -l /usr/bin/ | grep -w "cp"

-rwxr-xr-x 1 root root 146880 Feb 28 2019 cp

root@debian:~# fj

8 Set a SUID on the cp binary to allow its execution with root permissions.

Use the command chmod u+s /usr/bin/cp.

Verify that it was activated.

john@debian: ~ = |

File Edit View Search Terminal Help

root@debian:~# chmod uts /usr/bin/cp

root@debian:~# ls -l /usr/bin/ | grep -w “cp”

-rwsr-xr-x 1 root root 146880 Feb 28 2019 cp

root@debian:~#

9 Return to your user with the command exit.

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# exit

Logout

:-$ ff

**PDF s. 200:** 10 Try to copy the content of shadow to secret.txt again. Note that this time the

command was successful and the content was copied.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cp /etc/shadow Desktop/secret.txt |

:~$ cat Desktop/secret.txt

root: $6$j4ktAsk2mB6YXnu1$M1/qDX3nzXOCO97TnzWg fFXXckgOj mN3

nBmJxugoFeysNRIs 1hi6E5zQAA01cRRetgSTL4wJTryTMTuMoKeest/ :

18521:0:99999:7:::

daemon: *:18521:0:99999:7:::

11 Return the binary permissions to their former state by switching to the root

user and running the command chmod 755 /usr/bin/cp.

john@debian: ~ x

File Edit View Search Terminal Help

p=) EM) =

Password:

root@debian:~# chmod 755 /usr/bin/cp

root@debian:~#

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# chmod 755 /usr/bin/cp

root@debian:~# 1s -l /usr/bin/ | grep -w "cp"

-rwxr-xr-x 1 root root 146880 Feb 28 2019 cp

root@debian:~# fj |

12 How does SUID affect Linux OS security?

When root configures SUID on a binary that can potentially access sensitive information

(as in this lab), that is considered a major vulnerability. Simple users may view or even

manipulate data in the system.

**PDF s. 201:** Lab Task 2: Sudo

In this task, you will provide your user with the ability to use high-level permissions in

the system. This will allow you perform sensitive operations without having to switch to

the root user.

1 Switch to the root user with the command su -

2 Execute the command apt update

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt update

Hit:1 http://security.debian.org/debian-security buster/updates InRelease|

Hit:2 http://deb.debian.org/debian buster InRelease

Get:3 http://deb.debian.org/debian buster-updates InRelease [51.9 kB]

Fetched 51.9 kB in 1s (77.3 kB/s)

Reading package lists... Done

Building dependency tree

Reading state information... Done

ALL packages are up to date.

root@debian:~#

3 Execute the command apt install sudo -y

i john@debian: ~ =|

File Edit View Search Terminal Help

root@debian:~# apt install sudo -y

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following NEW packages will be installed:

sudo

® upgraded, 1 newly installed, © to remove and © not upgraded.

Need to get 1,245 kB of archives.

After this operation, 3,878 kB of additional disk space will be used.

iGet:1 http://deb.debian.org/debian buster/main amd64 sudo amd64 1.8.27-1+

deb10u2 [1,245 kB]

Fetched 1,245 kB in 1s (1,026 kB/s)

4 Use the command visudo to open and edit the soduers file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# visudo| |

**PDF s. 202:** John@debian: ~ |

File Edit_View Search Terminal_Help

GNU_nano 3.2 /etc/sudoers.tmp

Defaults env_reset

Defaults mail badpass

Defaults secure_path="/usr/local/sbin:/usr/local/bin: /usr/sbin: /u$|

Ime Get Help @@ Write Out Where Is x Cut Text ee) Justify

lee Exit fax Read File Ny Replace @e Uncut Text @j To Spell

5 Scroll to the bottom of the file and add your user in the following format:

<user> ALL=(ALL:ALL) ALL

Add it below the root configuration.

Save the file and close it.

john@debian: ~ eo]

File Edit View Search Terminal Help

GNU_nano 3.2 /etc/sudoers.tmp Modified

root ALL=(ALL:ALL) ALL

john ALL=(ALL:ALL) ALL

Ssudo ALL=(ALL:ALL) ALL

Get Help Write Out @i) Where Is @N Cut Text @@ Justify

( Exit iW Read File gay Replace @Y Uncut Text @ij To Spell

**PDF s. 203:** 6 To verify that your user now has the ability to work with root permissions, return

to the user and run the command sudo cat /etc/shadow. Provide the password

when prompted.

i John@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# exit

‘Logout

:~$ sudo cat /etc/shadow

[sudo] password for john:

root :$6$j4ktAsk2mB6YXnu1$M1/qDX3nzX0C097 TnzWgfXXckgOjmN3nBmJxugoFeysNRIs1|

IhiGE5ZQAAO1cRRetgSTL4wJTryTMTuMoKeest/:18521:0:99999:7:::

daemon: *:18521:0:99999:7:::

bins*:18521;0:99999 770: :

sys:*;18521:0:99999:7:;;

sync: *:18521:0:99999:7:::

games: = 1185210: 9999927: 3:

Iman: *; 18521;0:99999:7:;;;

Up: *:18521:0:99999:7::

mail: *:18521:0:99999:7::;

news :*:18521:0:99999:7:::

uucp: *:18521:0:99999:7:::

proxy: *:18521:0:99999:7:::

Iwww- data: *:18521:0:99999:7::

</details>
