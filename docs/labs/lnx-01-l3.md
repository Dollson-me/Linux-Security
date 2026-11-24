# LNX-01-L3 — GNOME DE Installation

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 36–52.

## Cel, misja i środowisko

- G Lab Objective Become familiar with the Linux command line and graphical user interface configuration. ba) Lab Mission
- ba) Lab Mission Create a more interactive virtual environment that includes graphical interfaces and tools. ea :
- © Lab Duration 20-30 minutes tC) Requirements Each student should have a completely installed Debian machine, with basic utilities.
- tC) Requirements Each student should have a completely installed Debian machine, with basic utilities. Lt | Resources
- | Resources e@ Environment & Tools o Debian VM from the LNX-01-L2 lab oO. Internet connection

## Zadania / etapy

1. Lab Task 1: Gnome and Net-Tools Installation In this task, you will install Gnome to provide a graphical user interface in Debian. 1 Run the Debian virtual machine and log in as root. 2 Execute the command apt update to download updated package information.
2. Lab Task 2: GUI Orientation In this task, you will log in via the GUI option and get to know Debian’s basic structure. 1 When the machine starts, the graphical interface will present a login screen with the primary user. Click your user name to select it, and log in with it.

## Komendy występujące w labie

```text
systemctl reboot.
_
apt install net-tools
```

## Powiązana teoria

- [Cli Interface](../01-introduction/cli-interface.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 36:** Linux Security

Lab Assignment Introduction

to Linux

Pedi baka

° nT LNX-01-L3

Pa] Gnome DE Installation

All Rights Reserved.

**PDF s. 37:** Linux Security

Lab Assignment Introduction

to Linux

Pedi baka

° nT LNX-01-L3

Pa] Gnome DE Installation

All Rights Reserved.

**PDF s. 38:** G Lab Objective

Become familiar with the Linux command line and graphical user interface

configuration.

ba) Lab Mission

Create a more interactive virtual environment that includes graphical interfaces and

tools.

ea :

© Lab Duration

20-30 minutes

tC) Requirements

Each student should have a completely installed Debian machine, with basic utilities.

Lt

| Resources

e@ Environment & Tools

o Debian VM from the LNX-01-L2 lab

oO. Internet connection

**PDF s. 39:** Lab Task 1: Gnome and Net-Tools Installation

In this task, you will install Gnome to provide a graphical user interface in Debian.

1 Run the Debian virtual machine and log in as root.

2 Execute the command apt update to download updated package information.

Execute the command apt install gnome to install the graphical user

environment. When you are asked about continuing the installation, type y, and

press Enter. Note: Gnome is a meta-package that installs other packages. The

installation may take anywhere from 10 to 30 minutes, depending on the internet

speed.

3 Execute the command apt install net-tools, this installs a variety of networking

tools into your Linux Debian box.

4 When the installation finishes, reboot the system by executing the command

systemctl reboot.

**PDF s. 40:** Lab Task 2: GUI Orientation

In this task, you will log in via the GUI option and get to know Debian’s basic structure.

1 When the machine starts, the graphical interface will present a login screen with

the primary user. Click your user name to select it, and log in with it.

2 Enter your password and click Sign In.

3 Open Activities by clicking it or pressing the Win Key.

4 Search for Files and open it.

5 what is the initial directory location? Why is that the location?

6 Via the home directory, locate the core folder structure and navigate to it by

clicking Other Locations.

7 Click Computer to list the folders under the root directory. Note that some of the

folders are actually links to other locations. The main folders you should be aware

of are: bin, boot, etc, home, mnt, proc, root, sys, and tmp.

**PDF s. 41:** Lab Tasks 3: Terminal Customization

In this task, you will open the terminal program and change its theme.

1 Open Activities again, search for the terminal, and open it.

2 Inthe program, click Edit, select Preferences, select Color, and set it to dark

mode. Close the window by clicking the X (which may appear a bit outside the

screen).

3 You should now have a graphical DE installed, a file explorer to navigate the

system, and a dark-themed terminal.

**PDF s. 42:** Linux Security

Lab Assignment Introduction

& Solution to Linux

Pedi baka

° nT LNX-01-LS3

Pa] Gnome DE Installation

All Rights Reserved.

**PDF s. 43:** Linux Security

Lab Assignment Introduction

& Solution to Linux

Pedi baka

° nT LNX-01-LS3

Pa] Gnome DE Installation

All Rights Reserved.

**PDF s. 44:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Become familiar with the Linux command line and graphical user interface

configuration.

» Lab Mission

Create a more interactive virtual environment that includes graphical interfaces and

tools.

Cs ss

@ Lab Duration

20-30 minutes

tC) Requirements

Each student should have a completely installed Debian machine, with basic utilities.

oo

| Resources

e@ Environment & Tools

o Debian VM from the LNX-01-L2 lab

oO. Internet connection

**PDF s. 45:** In this task, you will install Gnome to provide a graphical user interface in Debian.

1 Run the Debian virtual machine and log in as root.

(Debian GNU/Linux 10 debian ttyl

debian login: root

Password:

Linux debian 4.19.0-10-amd64 #1 SMP Debian 4.19.132-1 (2020-07-24) x86_64

The programs included with the Debian GNU/Linux system are free software;

the exact distribution terms for each program are described in the

individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

permitted by applicable law.

root@debian:“# _

2 Execute the command apt update to download updated package information.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

bermitted by applicable law.

rootédebian:“# apt update|

Hits1 http://secUrTty+webian.org/debian-security buster/updates InRelease

Hit:2 http://deb.debian.org/debian buster InRelease

Get:3 http://deb.debian.org/debian buster-updates InRelease [51.9 kB]

Fetched 51.9 kB in 1s (68.1 kB/s)

Reading package lists... Done

Building dependency tree

Reading state information... Done

All packages are up to date.

Execute the command apt install gnome to install the graphical user

environment. When you are asked about continuing the installation, type y, and

press Enter. Note: Gnome is a meta-package that installs other packages. The

installation may take anywhere from 10 to 30 minutes, depending on the internet

speed.

yelp-xs1 zenity zenity-common

0 upgraded, 1017 newly installed, 0 to remove and O not upgraded.

Need to get 712 MB of archives.

After this operation, 2,315 MB of additional disk space will be used.

Do you want to continue? fyi fo

**PDF s. 46:** 3 Execute the command apt install net-tools, this installs a variety of networking

tools into your Linux Debian box.

root@debian:~# apt install net-tools

Reading package lists Done

Building dependency tree

Reading state information Done

The following NEW packages will be installed

net-tools

© upgraded, 1 newly installed, ® to remove and © not upgraded

Need to get 248 kB of archives.

After this operation, 1,002 kB of additional disk space will be used.

let:1 http://deb.debian.org/debian buster/main amd64 net-tools amd64 1.60+git201

80626.aebd88e-1 [248 kB]

Fetched 248 kB in Os (1,400 kB/s)

Selecting previously unselected package net-tools

(Reading database 137417 files and directories currently installed.)

Preparing to unpack /net-tools 1.60+git20180626.aebd88e-1 amd64.deb

Unpacking net-tools (1.60+git20180626.aebd88e-1)

Setting up net-tools (1.60+git20180626.aebd88e-1)

Processing triggers for man-db (2.8.5-2)

root@debian:~#

4 When the installation finishes, reboot the system by executing the command

systemctl reboot.

Setting up gnome (1:3.90+1) ...

Processing triggers for libgdk-pixbuf2.0-O:amd64 (2.38.1+dfsg-1) ...

Processing triggers for libc-bin (2.28-10) ...

Processing triggers for dbus (1.12.20-O+deb1oul) ...

Processing triggers for systemd (241-7“debloud) ...

iroot@debian: “#) systemct] reboot

**PDF s. 47:** Lab Task 2: GUI Orientation

In this task, you will log in via the GUI option and get to know Debian’s basic structure.

1 When the machine starts, the graphical interface will present a login screen with

the primary user. Click your user name to select it, and log in with it.

‘Thu 02:03 Q- aH Or

© debian”

2 Enter your password and click Sign In.

‘Thu 02:04 o- 2 Or

cancel Signin

© debian”

**PDF s. 48:** 3 Open Activities by clicking it or pressing the Win Key.

Activities ‘Thu 02:07 2 “Or

a

~

4 Search for Files and open it.

**PDF s. 49:** Activities Files + Thu 02:09 2 Or

© Home © aje-|e| «

© Recent BP - BP

* _ a)

re in rn &

@ Home 7 —

D Documents

4 Dowrioads = > _

wm Videos — a

G Trash iB] |

+ Other Locations Templates Videos

5 what is the initial directory location? Why is that the location?

The initial directory location is often the current user’s home directory. This is the

default even when you log in with a command line interface. This has always been

the standard in most operating systems.

6 Via the home directory, locate the core folder structure and navigate to it by

clicking Other Locations.

Activities Files ¥ Thu 02:09 24 Or

<> eee ale -/=| «

© Recent

Ke

Starred we — & ;

@ Home .

1D Documents

B Music dd (©) a

sa Videos B Be

Trash fa) =

Templates Videos

**PDF s. 50:** 7 Click Computer to list the folders under the root directory. Note that some of the

folders are actually links to other locations. The main folders you should be aware

of are: bin, boot, etc, home, mnt, proc, root, sys, and tmp.

Activities Files ¥ Thu 02:12 24 Or

> oe al- -l=ne

© Recent (On This Computer

@ Home Networks

D Documents = Windows Network

% Downloads

Music

Picures

sa Videos

Trash

+ otherLocations

Connect to Sever Enter server ad ole

Activities Files » Thu 02:14 % % O +

oe ale -|2| «

© Recent

— —

starred

@ Home (cal

bin bect ey

TD Documents

Downloads — —

va Videot BP B

G Trash

+ OtherLocations intraimg.otd i wns

ly by >

ibba ibs media

**PDF s. 51:** Lab Tasks 3: Terminal Customization

In this task, you will open the terminal program and change its theme.

1 Open Activities again, search for the terminal, and open it.

Activities ‘Thu 02:17 an Or

2 Inthe program, click Edit, select Preferences, select Color, and set it to dark

mode. Close the window by clicking the X (which may appear a bit outside the

screen).

john@debian: ~ x

File Edit View Search Terminal Help

johnc

Select Alt

**PDF s. 52:** Preferences Profle “Unnamed”

_ Text and BackgroundColor

Shortuts Built-in schemes:

ies Beers |]

ighigh color |

Palette

euitesnscheries (GEES =

orm: BEER EEH

EES SB

© Show bldtextinbrightcolors

3 You should now have a graphical DE installed, a file explorer to navigate the

system, and a dark-themed terminal.

john@debian: ~ x

File Edit View Search Terminal Help

</details>
