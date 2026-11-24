# LNX-07-L2 — PAM Authentication Features

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 421–449.

## Cel, misja i środowisko

- G Lab Objective This lab teaches students how to enforce strong user password policies in Linux. The policies will be applied to both new user creation and password resetting. bs Lab Mission
- bs Lab Mission Install PAM and use it to apply password policies to any user added in the machine, and to secure SSH login. x .
- © Lab Duration 20-30 minutes fe Requirements e Knowledge of PAM.
- fe Requirements e Knowledge of PAM. e Knowledge of sshd. Lt
- [ea] Resources e¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Library Installation Install required libraries for the completion of the lab. 1 Make sure your VM's adapter is set to Bridged Adapter. 2 ~Runthe command dhclient -r.
2. Lab Task 2: Password Complexity Define complex password policies in the Debian operating system. 1 Use the command nano /etc/pam.d/common-password to open the PAM (Pluggable Authentication Modules) file.
3. Lab Task 3: Disable Reuse of the 10 Oldest Passwords Apply additional restrictions to your Password Manager. 1. Use the command nano /etc/pam.d/common-password to open the PAM file. 2 Press Ctrl + w to search for "pam_unix.so" to find the correct line.
4. Lab Task 4: Restrict PAM SSH Authentication Generate and enforce a list that contains users that are permitted to connect to the workstation via SSH. 1 The sshd service should be installed on your VM, but if you are not sure, use the
5. Lab Task 1: Library Installation Install required libraries for the completion of the lab. 1. Make sure your VM's adapter is set to Bridged Adapter. [EM General Network
6. Lab Task 3: Disable Reuse of the 10 Oldest Passwords Apply additional restrictions to your Password Manager. 1 Use the command nano /etc/pam.d/common-password to open the PAM file. john@debian: ~ x

## Komendy występujące w labie

```text
SSH users and add your user to it.
IP Network
SS Serial Ports
dhclient -r |
dhclient |
apt update |
apt install cracklib-runtime -y |
apt install lLibpam-pwquality -y |
nano /etc/pam.d/common-password |
reboot |
adduser jorge
deluser jorge
su - jorge
passwd
Jj
cat /etc/security/opasswd |
apt install ssh |
echo "john" > /etc/ssh/sshd.allow
nano /etc/pam.d/sshd I
service ssh start
ip a
ff
```

## Powiązana teoria

- [Pam](../07-host-security/pam.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 421:** Linux Security

Lab Assignment Host Security

LNX-07-L2

o inn PAM Authentication

On 1U Features

Pa]

All Rights Reserved.

**PDF s. 422:** Linux Security

Lab Assignment Host Security

LNX-07-L2

o inn PAM Authentication

On 1U Features

Pa]

All Rights Reserved.

**PDF s. 423:** G Lab Objective

This lab teaches students how to enforce strong user password policies in Linux. The

policies will be applied to both new user creation and password resetting.

bs Lab Mission

Install PAM and use it to apply password policies to any user added in the machine, and

to secure SSH login.

x .

© Lab Duration

20-30 minutes

fe Requirements

e Knowledge of PAM.

e Knowledge of sshd.

Lt

[ea] Resources

e¢ Environment & Tools

o VirtualBox

= Debian

o Putty

**PDF s. 424:** Lab Task 1: Library Installation

Install required libraries for the completion of the lab.

1 Make sure your VM's adapter is set to Bridged Adapter.

2 ~Runthe command dhclient -r.

3 Run the command dhclient.

4 Open the terminal and use the command su — to switch to the root user.

5 Run the command apt update.

6 Use the command apt install cracklib-runtime -y to install the cracklib-runtime

library. This is a library that provides runtime support for password dictionary

generators.

7 Use the command apt install libpam-pwquality -y to install the libpam-pwquality

library. This library provides the capability to examine password strength.

**PDF s. 425:** Lab Task 2: Password Complexity

Define complex password policies in the Debian operating system.

1 Use the command nano /etc/pam.d/common-password to open the PAM

(Pluggable Authentication Modules) file.

2 Press Ctrl + w to search for "pam_pwauality" to find the correct line.

3 After the value "retry=3", add the following information:

minlen=8 ucredit=4 Icredit=4 dcredit=3 reject_username

minlen — minimum character length

Icredit — maximum amount of lowercase characters

ucredit — maximum amount of uppercase characters

dcredit — maximum amount of digits

reject_username — prevents users from using their names as passwords

Save and exit the file.

4 Run the command reboot to reboot the system.

5 Login, open the terminal, and switch to the root user using su -.

6 Use the command adduser [name] to try to add a user with password Aa123456.

Note the message that appears.

Press Ctrl + z to terminate the user creation process.

Note: Root users can still create users with password violations even after they

receive a message that the password does not comply with PAM requirements.

7 Use the command deluser [user] to remove the user that was partially created.

**PDF s. 426:** 8 Try to create the same user again but this time with the password AAAAaaaa123

and note that this time the password was accepted.

**PDF s. 427:** Lab Task 3: Disable Reuse of the 10 Oldest Passwords

Apply additional restrictions to your Password Manager.

1. Use the command nano /etc/pam.d/common-password to open the PAM file.

2 Press Ctrl + w to search for "pam_unix.so" to find the correct line.

3. Atthe end of the line, add remember=10. Then save and exit the file.

4 Use the command deluser [user] to delete the previously created user.

5 Use the command adduser [user] to add a user with the password ASDFzxcv123.

6 Switch to the new user with the command su — [user].

7 Use the command passwd to change the user’s password to POIUqwer12.

8 Use the command passwd to try to change the user's password to ASDFzxcv123.

Does it work?

You can see that the command returns an error and does not let you change the

password to one that was already used.

2] Use the command exit to return to the root user.

10 Use the command cat /etc/security/opasswd to display the hash value of the

old password.

**PDF s. 428:** Lab Task 4: Restrict PAM SSH Authentication

Generate and enforce a list that contains users that are permitted to connect to the

workstation via SSH.

1 The sshd service should be installed on your VM, but if you are not sure, use the

command apt install ssh to install it.

2 Use the command echo "[user]" > /etc/ssh/sshd.allow to create a file of allowed

SSH users and add your user to it.

3 Use the command nano /etc/pam.d/sshd to open the SSH PAM configuration

file.

4 Under @include common-auth add the following line:

auth required pam_listfile.so item=user sense=allow file=/etc/ssh/sshd.allow

onerr=fail

This line states that an authentication process is required to allow connection for

a user located in the file /etc/ssh/sshd.allow. If an error occurs, the connection

will fail.

Save and exit the file.

5 Run the command service ssh start.

6 Run the command ip a to check the IP address of the VM.

7 Run the Windows 10 VM that you worked with in the Services & Hardening

module and make sure its adapter is set to Bridged Adapter. The VM should

include the Putty software.

8 Start Putty and specify the IP address to open an SSH connection to the Debian

VM.

Note: In the Services & Hardening module you changed the connection port.

If port 22 does not work, use 4567.

**PDF s. 429:** 9 Try to connect with a user that is not listed in the sshd.allow file, and note that

access is denied.

10 Nowtry to open a connection again with the user listed in the sshd.allow file,

and note that access is granted.

**PDF s. 430:** Linux Security

Lab Assignment Host Security

& Solution Nears

o inn PAM Authentication

Oln 1U Features

Es]

All Rights Reserved.

**PDF s. 431:** Linux Security

Lab Assignment Host Security

& Solution Nears

o inn PAM Authentication

Oln 1U Features

Es]

All Rights Reserved.

**PDF s. 432:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

This lab teaches students how to enforce strong user password policies in Linux. The

policies will be applied to both new user creation and password resetting.

2 Lab Mission

Install PAM and use it to apply password policies to any user added in the machine, and

to secure SSH login.

esa .

©@) Lab Duration

20-30 minutes

fe Requirements

e Knowledge of PAM.

e Knowledge of sshd.

a=

| Resources

e Environment & Tools

o VirtualBox

=" Debian

o Putty

**PDF s. 433:** Lab Task 1: Library Installation

Install required libraries for the completion of the lab.

1. Make sure your VM's adapter is set to Bridged Adapter.

[EM General Network

[=] System Adapter 1 © Adapter? © Adapter3 Adapter 4 |

| [Bl disptay Enable Network adapt |

' Name: | Realtek Gaming GbE Family Controller 7

dp a B advanced

IP Network

SS Serial Ports

fog USB

[7 Shared Folders |

i User Interface

2 > Run the command dhclient -r.

jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# dhclient -r |

**PDF s. 434:** 3 Run the command dhclient.

jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# dhclient |

4 Open the terminal and use the command su — to switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ su -

Password:

root@debian:~#

5 Run the command apt update.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt update |

Hit:1 http://security.debian.org/debian-security buster

/updates InRelease

Hit:2 http://deb.debian.org/debian buster InRelease

Get:3 http://deb.debian.org/debian buster-updates InRel

6 Use the command apt install cracklib-runtime -y to install the cracklib-runtime

library. This is a library that provides runtime support for password dictionary

generators.

john@debian: ~ x ;

File Edit View Search Terminal Help

root@debian:~# apt install cracklib-runtime -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and

**PDF s. 435:** 7 Use the command apt install libpam-pwquality -y to install the libpam-pwquality

library. This library provides the capability to examine password strength.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install lLibpam-pwquality -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and

Page5

**PDF s. 436:** Lab Task 2: Password Complexity

Define complex password policies in the Debian operating system.

1 Use the command nano /etc/pam.d/common-password to open the PAM

(Pluggable Authentication Modules) file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/pam.d/common-password |

2 Press Ctrl + w to search for "pam_pwaquality" to find the correct line.

Activities [] Terminal + Thu 03:09 @ A) Or

john@debian: ~ x

File Edit View Search Terminal Help

password [suecess=1 default=ignore] pam unix.so obscure use authtok try fi$

password required pam_permit.so

password optional pam gnome keyring.so

ME Get Help MW write out Qj cut Text QB sustity @@ cur pos

is Exit Mi Read File (@} Replace WU Uncut Text MJ To Spell im Go To Line

**PDF s. 437:** 3 After the value "retry=3", add the following information:

minlen=8 ucredit=4 Icredit=4 dcredit=3 reject_username

minlen — minimum character length

Icredit — maximum amount of lowercase characters

ucredit — maximum amount of uppercase characters

dcredit — maximum amount of digits

reject_username — prevents users from using their names as passwords

Save and exit the file.

Activities [] Terminal + Thu 03:13 @ Av Or

john@debian: ~ x

File Edit View Search Terminal Help

password [success=1 default=ignore] pam_unix.so obscure use authtok try first pass sha512

password requisite pam_deny. so

password required pam_permit.so

password optional pam_gnome_keyring. so

ME cet Help 4 Where Ts i cut Text Justify Cur Pos z undo

fai Exit Wi Read File fi) Replace Uncut Text jf] To Spell Go To Line JB Redo

4 Run the command reboot to reboot the system.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# reboot |

**PDF s. 438:** 5 Login, open the terminal, and switch to the root user using su -.

john@debian: ~ x

File Edit View Search Terminal Help

1-$ Su -

Password:

root@debian:-~#

6 Use the command adduser [name] to try to add a user with password Aa123456.

Note the message that appears.

Press Ctrl + z to terminate the user creation process.

Note: Root users can still create users with password violations even after they

receive a message that the password does not comply with PAM requirements.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# adduser jorge

Adding user ‘jorge' ...

Adding new group “jorge' (1002) ...

Adding new user “jorge' (1002) with group ‘jorge’ ...

Creating home directory “/home/jorge' ...

Copying files from “/etc/skel' ...

New password:

BAD PASSWORD: The password fails the dictionary check -

it is too simplistic/systematic

Retype new password:

**PDF s. 439:** 7 Use the command deluser [user] to remove the user that was partially created.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# deluser jorge

Removing user ‘jorge’ ...

Warning: group -jorge' has no more members.

Done.

root@debian: ~#

8 Try to create the same user again but this time with the password AAAAaaaa123

and note that this time the password was accepted.

| john@debian: ~ x!

File Edit View Search Terminal Help

root@debian:~# adduser jorge

Adding user “jorge' ...

Adding new group ‘jorge’ (1002) ...

Adding new user “jorge' (1002) with group ‘jorge’ ...

The home directory ~/home/jorge' already exists. Not c

opying from */etc/skel'.

New password:

Retype new password:

passwd: password updated successfully

**PDF s. 440:** Lab Task 3: Disable Reuse of the 10 Oldest Passwords

Apply additional restrictions to your Password Manager.

1 Use the command nano /etc/pam.d/common-password to open the PAM file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/pam.d/common-password |

2 Press Ctrl + w to search for "pam_unix.so" to find the correct line.

I john@debian: ~ x

File Edit View Search Terminal Help

password requisite pam pwquality.so retry=3 minlen=8 ucre$

password requisite pam_deny.so

password required pam_permit.so

password optional pam_gnome_keyring.so

ie Get Help @ write out fj where Is iy cut Text @ Justify @ cur Pos

ia Exit Mii Read File @™} Replace @@ Uncut Text Qj To Spell @@ Go To Line

3. Atthe end of the line, add remember=10. Then save and exit the file.

**PDF s. 441:** john@debian: ~ x |

File Edit View Search Terminal Help

[cpa common penance

eed ee SOUR ce ene lee ieee eenee

password [success=1 default=ignore! pam_unix.se obscure use authtok try first pass shabl2[jremember=10)

eee meet ee ne feaen

4 Use the command deluser [user] to delete the previously created user.

john@debian: ~ x i

File Edit View Search Terminal Help

root@debian:~# deluser jorge

Removing user “jorge' ...

Warning: group “jorge' has no more members.

Done.

root@debian: ~#

5 Use the command adduser [user] to add a user with the password ASDFzxcv123.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# adduser jorge

Adding user “jorge' ...

Adding new group ‘jorge’ (1002) ...

Adding new user ‘jorge’ (1002) with group ‘jorge’ ..

The home directory ~/home/jorge' already exists. No

t copying from */etc/skel'.

New password:

Retype new password:

passwd: password updated successfully

6 Switch to the new user with the command su — [user].

**PDF s. 442:** jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# su - jorge

jorge@debian:~$ ff

7 Use the command passwd to change the user’s password to POIUqwer12.

jorge@debian: ~ x

File Edit View Search Terminal Help

jorge@debian:~$ passwd

Changing password for jorge.

Current password:

New password:

Retype new password:

passwd: password updated successfully

jorge@debian: ~$

8 Use the command passwd to try to change the user's password to

ASDFzxcv123delAa.

Does it work?

jorge @debian: ~ x

File Edit View Search Terminal Help

jorge@debian:~$ passwd

Changing password for jorge.

Current password:

New password:

BAD PASSWORD: The password is just rotated old one

passwd: Authentication token manipulation error

passwd: password unchanged

jorge@debian: ~$

You can see that the command returns an error and does not let you change the

password to one that was already used.

**PDF s. 443:** 9 Use the command exit to return to the root user.

jorge @debian: ~ x

File Edit View Search Terminal Help

:~$ exit

Logout

root@debian:~# Jj

10 Use the command cat /etc/security/opasswd to display the hash value of the

old password.

jorge@debian: ~ x |

File Edit View Search Terminal Help

root@debian:~# cat /etc/security/opasswd |

jorge: 1002:1:$1$Axr2yBJg$Gp2WkxbuAQKO8rsxpAade.

**PDF s. 444:** Lab Task 4: Restrict PAM SSH Authentication

Generate and enforce a list that contains users that are permitted to connect to the

workstation via SSH.

1 The sshd service should be installed on your VM, but if you are not sure, use the

command apt install ssh to install it.

jorge@debian: ~ x |

File Edit View Search Terminal Help

root@debian:~# apt install ssh |

2 Use the command echo "[user]" > /etc/ssh/sshd.allow to create a file of allowed

SSH users and add your user to it.

jorge @debian: ~ x

File Edit View Search Terminal Help

root@debian:~# echo "john" > /etc/ssh/sshd.allow

root@debian: ~#

3 Use the command nano /etc/pam.d/sshd to open the SSH PAM configuration

file.

jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/pam.d/sshd I

**PDF s. 445:** 4 Under @include common-auth add the following line:

auth required pam_listfile.so item=user sense=allow file=/etc/ssh/sshd.allow

onerr=fail

This line states that an authentication process is required to allow connection for

a user located in the file /etc/ssh/sshd.allow. If an error occurs, the connection

will fail.

Save and exit the file.

jorge@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 7ete/pam.d/sshd Woditied

]

leinclude common-auth

auth required pam listfile.so item=user sense=allow file=/etc/ssh/sshd.allow onerr=fail

account required pam_nologin.so

I@include common-account

session [success=ok ignore=ignore module_unknown=ignore default=bad] pam_seLinu$

session required pam loginuid.so

lms Get Help Mey Write Out gf] Where Is My Cut Text mw) Justify me Cur Pos

ay Exit fi Read File gy) Replace @@ Uncut Text gj To Spell im Go To Line

**PDF s. 446:** 5 Run the command service ssh start.

jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service ssh start

root@debian: ~#

6 Runthe command ip a to check the IP address of the VM.

jorge@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ip a

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN gro

up default qlen 1000

link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

inet 127.0.0.1/8 scope host lo

valid lft forever preferred lft forever

inet6 ::1/128 scope host

valid_lft forever preferred lft forever

2: enpOs3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_ fast

state UP group default glen 1000

link/ether 08:00:27:6d:00:ff brd ff:ff:ff: ff: ff: ff

inet 192.168.1.12/24 brd 192.168.1.255 scope global dynamic noprefi

xroute enp0s3

valid lft 3272sec preferred lft 3272sec

inet6 2a00:a040:19c:a2e7:206e:998d: ff2f:f20f/64 scope global tempor

lary dynamic

valid_lft 598138sec preferred_lft 79460sec

inet6 2a00:a040:19c:a2e7:a00:27ff: fe6d:ff/64 scope global dynamic m

ngtmpaddr noprefixroute

valid lft 808173sec preferred lft 330583sec

inet6 fe80::a00:27ff:fe6d:ff/64 scope link noprefixroute

valid lft forever preferred lft forever

root@debian:~# ff

**PDF s. 447:** 7 Run the Windows 10 VM that you worked with in the Services & Hardening

module and make sure its adapter is set to Bridged Adapter. The VM should

include the Putty software.

@ Windows 10 - Settings 2 “

[BB General | Network

[=] System. Adapter 1 Adapter 2 Adapter 3 Adapter 4

| (_} Display Enable Network Adapter

| ‘Name: | Realtek Gaming GbE Family Controller ,

& aia D Advanced

Ie Network

£SS serial Ports

i 4 USB

|

[7 Shared Folders |

FF] User interface

**PDF s. 448:** 8 Start Putty and specify the IP address to open an SSH connection to the Debian

VM.

Note: In the Services & Hardening module you changed the connection port.

If port 22 does not work, use 4567.

$8 PUTTY Configuration ? x

seen

Session Basic options for your PUTTY seesion

*» Logging edt racine rermat ioe ne

(=) Terminal

laine Host Name for IP address) Pott

‘S [feznee 2 | [ssa]

Eo Features Connection type

E} Window ORaw OTelnet ORlogin @SSH © Serial

i feemene Load, save or delete a stored session

Laila Saved Sessions

a8. Selection |

Colours oo

Lie ae | Defaut Settings bal

pe Data Save

p> Prony

o Telnet Delete

| Plogin

‘b. SSH

Sate Close window on ext

OaAways ()Never ©) Only on clean ext

About Help [Open Cancel

9 Try to connect with a user that is not listed in the sshd.allow file, and note that

access is denied.

@P 192.168.1.12 - PuTTY - oF x

@ Access denied

**PDF s. 449:** 10 Nowtry to open a connection again with the user listed in the sshd.allow file,

and note that access is granted.

gP john@debian: ~ = a x

i login as: john

Linux debian 4.19.0-10-amd64 #1 SMP Debian 4.19.132-1 (2020-07-24) x36_64

The programs included with the Debian GNU/Linux system are free software;

individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

permitted by applicable law.

Last login: Thu Oct 1 05:49:53 2020 from 152.168.1.14

</details>
