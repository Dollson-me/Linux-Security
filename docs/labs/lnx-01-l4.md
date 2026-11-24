# LNX-01-L4 — Graphical Apps

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 53–76.

## Cel, misja i środowisko

- G Lab Objectives Understand how programs are often very similar when used in Linux and Windows, and learn how to customize Linux OS settings. ey Lab Mission
- ey Lab Mission Experience the Gnome desktop environment and Debian tools. es 7 ©) Lab Duration
- ©) Lab Duration 15-20 minutes fe Requirements Each student should have a completely installed Debian machine, with Gnome.
- fe Requirements Each student should have a completely installed Debian machine, with Gnome. The lab itself does not require any special knowledge, other than familiarity with basic desktop applications.
- | Resources e Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Guest Addition In this task, you will install VirtualBox Guest Additions and allow Debian to adapt to your full screen. Some commands that you may not be familiar with yet, will be covered later in the course.
2. Lab Task 2: Common Programs Learn how to find various programs using the built-in search function. For each step below, locate the equivalent application in the Windows environment, and mention any differences between them.

## Komendy występujące w labie

```text
sh ./ VBoxLinuxAdditions.run
su root
apt install linux-headers-$(uname -r)
chmod +x VBoxLinuxAdditions.run | |
chmod +x VBoxLinuxAdditions. run
sh ./VBoxLinuxAdditions.run fj
sh ./VBoxLinuxAdditions.run
systemctl reboot||
Ss io @* L
```

## Powiązana teoria

- [Terminal Emulators](../01-introduction/terminal-emulators.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 53:** Linux Security

Lab Assignment Introduction

to Linux

°

0 |= LNX-01-L4

jt: U Graphical Apps

All Rights Reserved.

**PDF s. 54:** Linux Security

Lab Assignment Introduction

to Linux

°

0 |= LNX-01-L4

jt: U Graphical Apps

All Rights Reserved.

**PDF s. 55:** G Lab Objectives

Understand how programs are often very similar when used in Linux and Windows, and

learn how to customize Linux OS settings.

ey Lab Mission

Experience the Gnome desktop environment and Debian tools.

es 7

©) Lab Duration

15-20 minutes

fe Requirements

Each student should have a completely installed Debian machine, with Gnome.

The lab itself does not require any special knowledge, other than familiarity with basic

desktop applications.

oo

| Resources

e Environment & Tools

o VirtualBox

= Debian

**PDF s. 56:** Lab Task 1: Guest Addition

In this task, you will install VirtualBox Guest Additions and allow Debian to adapt to

your full screen. Some commands that you may not be familiar with yet, will be covered

later in the course.

1 Open the terminal and execute the command su root to switch to root user.

Enter the password toor.

2 Execute the command apt install linux-headers-$(uname -r). When asked if you

want to continue, type Y, and then press Enter. This command installs required

kernel headers for guest additions installation.

3 Execute the command apt install build-essential. This is a package that is

required to compile other packages. When asked if your want to continue, type

Y, and then press Enter.

4 Close the terminal and in Devices, select Insert Guest Additions CD Image. When

asked to run it, click Cancel.

5 Open files and navigate to VBox_GAs_61.1.10.

6 Select all the files and folders, and copy them.

7 Navigate to Documents and create a new folder named Guest Addition.

8 Enter the folder and paste the copied files there.

9 Right-click empty space in the folder (not on a file or folder), and select Open in

Terminal.

10 Execute the command su root to switch to root user. Enter the password toor.

11. Execute the command chmod +x VBoxLinuxAdditions.run to provide execution

permission for the VBoxLinuxAdditions.run file.

12 Execute VBoxLinuxAdditions.run using the command:

sh ./ VBoxLinuxAdditions.run

13 Reboot the system using the command systemctl reboot.

**PDF s. 57:** 14 Log in with your user.

15. Expand the VirtualBox window and note that Debian adapts to the full screen.

**PDF s. 58:** Lab Task 2: Common Programs

Learn how to find various programs using the built-in search function.

For each step below, locate the equivalent application in the Windows environment,

and mention any differences between them.

1 To open the programs menu, open Activities and click the nine dots icon in the

menu on the left.

2 Locate the Firefox browser and open it. Find Firefox, and specify its name in

Gnome. Note that except for the name “Firefox ESR”, there are no other major

differences, and most menus look the same.

3. In Activities, find the Gnome equivalent of Microsoft Office. Open LibreOffice and

compare it with Microsoft Office.

4 Open LibreOffice, and note that although the theme and Ul are a bit different,

the main toolbars are very similar to MS Office.

Note that:

- Libre Writer is the equivalent of Microsoft Word

- Libre Impress is the equivalent of Microsoft PowerPoint

- Libre Calc is the equivalent of Microsoft Excel

5 Find the Gnome equivalent of Notepad, which is located in the second page

(scroll down).

6 Find the Gnome equivalent of Settings, which is located in the second page (scroll

down).

7 Settings looks like the Windows 10 settings, but includes non-graphical

configuration and customization. The customization settings are in a separate

application called “Tweaks.”

8 Change the wallpaper background to a different image by opening the settings

program, navigating to Background, and clicking Background.

**PDF s. 59:** Linux Security

Lab Assignment Introduction

& Solution to Linux

°o

oO ni LNX-01-LS4

jt: U Graphical Apps

All Rights Reserved.

**PDF s. 60:** Linux Security

Lab Assignment Introduction

& Solution to Linux

°o

oO ni LNX-01-LS4

jt: U Graphical Apps

All Rights Reserved.

**PDF s. 61:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objectives

Understand how programs are often very similar when used in Linux and Windows, and

learn how to customize Linux OS settings.

4 Lab Mission

Experience the Gnome desktop environment and Debian tools.

es .

©) Lab Duration

15-20 minutes

fe Requirements

Each student should have a completely installed Debian machine, with Gnome.

The lab itself does not require any special knowledge, other than familiarity with basic

desktop applications.

Lt

[ea] Resources

e Environment & Tools

o. VirtualBox

=" Debian

**PDF s. 62:** Lab Task 1: Guest Addition

In this task, you will install VirtualBox Guest Additions and allow Debian to adapt to

your full screen. Some commands that you may not be familiar with yet, will be covered

later in the course.

1 Open the terminal and execute the command su root to switch to root user.

Enter the password toor.

| john@debian: ~ x

File Edit View Search Terminal Help

$ su root

Password

root@debian: /home/john#

2. Execute the command apt install linux-headers-$(uname -r). When asked if you

want to continue, type Y, and then press Enter. This command installs required

kernel headers for guest additions installation.

I john@debian: ~ =|

File Edit View Search Terminal Help

j :~$ su root

root@debian:/home/john# apt install linux-headers-$(uname -r)

3. Execute the command apt install build-essential. This is a package that is

required to compile other packages. When asked if your want to continue, type

Y, and then press Enter.

john@debian: ~ x“

File Edit View Search Terminal Help

eee

**PDF s. 63:** 4 Close the terminal and in Devices, select Insert Guest Additions CD Image. When

asked to run it, click Cancel.

$B) Detsan (Snapshot 1) [Running] - Oracle VM VirtualBox: - o x

Fae Metin wnt ES tp

Activities @ optical Drives , 2 Or

(Audio ,

BP Network ,

oO se ,

DD Shorea Fotders ,

Eh Shared chpboard ,

[By Dragand Drop. ,

ee Gon Abin dr a te ited de Ome S Ie UO ele

Activities @ Run Software + Thu 03:34 3, O-

“VBox_GAs_6.1.10" contains software intended to be

automatically started. Would you like to run it?

you dont rusts acatln or aren sure, press Cancel

ne

**PDF s. 64:** 5 Open files and navigate to VBox_GAs_61.1.10.

Activities ‘Thu03:35 an Or

ny

-o)

Activities Files ¥ Thu 03:36 2% OF

1) > © VBox_GAs_6.110 + Qjri-7 = x

© Recent Contains software @ Run Software

We starres

@ Home } ber

D Documents v

4 paafaeaae autorun.sh AUTORUN.INE cert

2B Misi _ —

© Pictures bd

ta yioecs NT3x Os2 runasroot.sh

ten

i

© VBox_GAs._6.. _— yy

+ Other Locations TRANS.TBL ‘VBoxDarwinAddition \VBoxDarwinAddition

spkg ‘Uninstall tot

—-_

a ome

Page5

**PDF s. 65:** 6 Select all the files and folders, and copy them.

x) > © VBox_GAs_6.1.10 + Qiri-pe x

© Recent i

Open “

LSS Open With Other Application

@ Home i b

% Downloads

= cnn Gas

senda

va Videor ~ a yYy

© VBox_GAs_6.. 5 =

=n

Blders elected (crtaininga total o 3 items) i other lems selected (47-4 MB)

7 Navigate to Documents and create a new folder named Guest Addition.

® Starred Add to Bookma

@ Home faste

4 pownicaés | Openirrernian

Music

1 Pictures

sm Videos

wish Folder is Empty

© VeoesAs6.

+ otherLocations

**PDF s. 66:** cancel New Folder

Foti rae

8 Enter the folder and paste the copied files there.

_& > @Home / Documents | Guest Adetion ~ SEE E -

© Recent

We Starred

@ Home

1D. Documents

& Dowrioads NewFolder stitute

Paste cite]

amare Select All A

Fleurs Properties

va Viseot Open in Termin

aves Folder is Empty

© VecmcAs6. #

+ otherLocations |

**PDF s. 67:** 9 Right-click empty space in the folder (not ona file or folder), and select Open in

Terminal.

Activities Files + ‘Thu 03:42 2 “Or

<)> ee eee eerste ale |-|=

© Recent

starrea D

v

@ Home

erry AUTORUNINE oe

1D Documents

¥ Dowrioads — — :

B Musi wT

om Videos Paste sat

Solact Al .

B Tash Properties y

Be SLs tel

+ otherLocations

i

ial incl wo

10 Execute the command su root to switch to root user. Enter the password toor.

john@debian: ~/Documents/Guest Addition x

File Edit View Search Terminal Help

$ su root

Password:

root@debian: /home/john/Documents/Guest Addition#

11. Execute the command chmod +x VBoxLinuxAdditions.run to provide execution

permission for the VBoxLinuxAdditions.run file.

john@debian: ~/Documents/Guest Addition x

File Edit View Search Terminal Help

: $ su root

Password:

root@debian: /home/john/Documents/Guest Addition# chmod +x VBoxLinuxAdditions.run | |

12 Execute VBoxLinuxAdditions.run using the command:

sh ./ VBoxLinuxAdditions.run

john@debian: ~/Documents/Guest Addition x“

File Edit View Search Terminal Help

root@debian: /home/john/Documents/Guest Addition# chmod +x VBoxLinuxAdditions. run

root@debian: /home/john/Documents/Guest Addition# sh ./VBoxLinuxAdditions.run fj

**PDF s. 68:** 13 Reboot the system using the command systemctl reboot.

john@debian: ~/Documents/Guest Addition x

File Edit View Search Terminal Help

:~/Documents/Guest Addition$ su root

Password

root@debian: /home/john/Documents/Guest Addition# chmod +x VBoxLinuxAdditions. run

root@debian: /home/john/Documents/Guest Addition# sh ./VBoxLinuxAdditions.run

Verifying archive integrity ALL good

lUncompressing VirtualBox 6.1.10 Guest Additions for Linux..

VirtualBox Guest Additions installer

Copying additional installer modules

Installing additional modules

VirtualBox Guest Additions: Starting

VirtualBox Guest Additions: Building the VirtualBox Guest Additions kernel

Modules. This may take a while

VirtualBox Guest Additions: To build modules for other installed kernels, run

VirtualBox Guest Additions: /sbin/revboxadd quicksetup <version>

VirtualBox Guest Additions: or

VirtualBox Guest Additions: /sbin/revboxadd quicksetup all

VirtualBox Guest Additions: Building the modules for kernel 4.19.0-10-amd64

lupdate-initramfs: Generating /boot/initrd.img-4.19.0-10-amd64

VirtualBox Guest Additions: Running kernel modules will not be replaced until

root@debian: /home/john/Documents/Guest Addition# systemctl reboot||

14 Log in with your user.

‘Thu 03:53 O- aH Or

tf 10

©@debian

**PDF s. 69:** 15 Expand the VirtualBox window and note that Debian adapts to the full screen.

Activities Thu 03:54 2A O +

**PDF s. 70:** Lab Task 2: Common Programs

Learn how to find various programs using the built-in search function.

For each step below, locate the equivalent application in the Windows environment,

and mention any differences between them.

1 To open the programs menu, open Activities and click the nine dots icon in the

menu on the left.

Activities ‘Thu 02:44 2" Or

aeeeb:i®

. 68 es eo.

B

Ss io @* L

a 5

° a: 2

os Frequent Ai

**PDF s. 71:** 2 Locate the Firefox browser and open it. Find Firefox, and specify its name in

Gnome. Note that except for the name “Firefox ESR”, there are no other major

differences, and most menus look the same.

Activities ‘Thu 02:47 2 O-

Q, Typetosearch

a sek, Chee SUC wertMMr eRe Ges!) Coe

° 8 i a .

B

a 4

5 B -

- Frequent A

1G New Tob |B Firefox PrvacyNoice— x | + *

Co [Rsmnnorenraes |

@ Signintosjne

© Content Blocking Standard

New Window CtrleN

6° NewPrhate Window CulshitsP

You've got the i

browser. a

_ eae edit x & B

Meet the rest of uy ,

Firefox 0 Logins and Passwords

(Add-ons Ctrl+Shitt+a,

BI Useful Products HE Preferences

Get things done with a family of tools that 2 Customize,

respects your privacy across your devices. Sane ee

Fl Practical Knowledge Se Pee Se

Learn everything you need to know to stay a nit

**PDF s. 72:** 3 In Activities, find the Gnome equivalent of Microsoft Office. Open LibreOffice and

compare it with Microsoft Office.

Activities: Thu 02:51 2 Or

a 6 BAag®d

a sek, Chee SUC wertMMr eRe Ges!) Coe

. 68 esnetio.

B

a

Q 5 BE: &

4 Open LibreOffice, and note that although the theme and Ul are a bit different,

the main toolbars are very similar to MS Office.

Note that:

- Libre Writer is the equivalent of Microsoft Word

- Libre Impress is the equivalent of Microsoft PowerPoint

- Libre Calc is the equivalent of Microsoft Excel

Activities Thu 02:52 2 O°

268 eB xk ©

® 86 @ ®% & e

4

o BB BB: 8

**PDF s. 73:** Aathites Bi Libreoice © Thu02:54 0°

United -Libreoie Weiter x

B-g-3- ea &-\d QAI F-aeGaA -

Default Style ~ AL Ay Liberatimse|~ (122 |~ AAAS BRA AA *|

| &

iz

i”

Pave XOE1 a | Bare O charts [DaESSAS AT Tela] [_[ poo] -——o— + | 1008

5 Find the Gnome equivalent of Notepad, which is located in the second page

(scroll down).

Activities ‘Thu 02:57 2 Or

= Kv a =

e sxXxBEBR .

a e

a [213 1

2s $ One B

a ; + nese eo

9 Bev & am

— Frequent A

**PDF s. 74:** Activities GJ Text Editor + Thu 02:59 24 Or

Open = i United Document swe |=

PuinTet > TabWithis> inca) NS

6 Find the Gnome equivalent of Settings, which is located in the second page (scroll

down).

Activities ‘Thu 03:06 2 Or

rN © : Q@

= >a Fim =

e sX BEAR :

a 6. [213 Ny )

] f tin Ks

$oeameé h 2

a ; + nese eo

9 & ev & am

~ Frequent A

**PDF s. 75:** Activities 3% Settings + Thu 03:06 2 Or

a Se Bluetooth =

® Background

A. Nottctions

Q Search

Region® Language

@ Universal Access:

& one Accounts

No Bluetooth Found

Privacy Pugina dongle fo use lurtooth

Sharing

6 Sound

Ge Power

7 Settings looks like the Windows 10 settings, but includes non-graphical

configuration and customization. The customization settings are in a separate

application called “Tweaks.”

Rathites Th 03107 Aa Or

: Be oe ‘ Q

) = <* ® & @ RB

a e

es & (a | mm

2 £$ Bee hh B

a y H eo

A @& ev & MH fe

-_ Frequent Al

**PDF s. 76:** 3 ee i :

teal ‘imatons «@

Appearance Saspein we ploy of ered 6)

Extensions, ‘Qver-Amplfication

Kporsttese

Tepbar

nou Teta

vans

wrspces

8 Change the wallpaper background to a different image by opening the settings

program, navigating to Background, and clicking Background.

yo = 5

> aaa

6 Pane

ae marae SSS

Ge Power

© Dew >

</details>
