# Linux Distributions & Dedicated Environments

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 9–11; Linux Security.pdf, s. 11–19.

## Mapa wiedzy

- Distributions share the Linux kernel but differ in installed applications, desktop environments, package managers, intended use and support model.
- The course discusses Debian, Ubuntu, Red Hat/RHEL, CentOS and OpenSUSE, and identifies Kali as a Debian-based penetration-testing distribution.
- Linux is used on desktops, servers, cloud services, Android/IoT devices and dedicated security environments.
- Enterprise distributions such as RHEL emphasize server use and commercial support; Debian is used as the base for many other distributions.

## Komendy / pliki / składnia występujące w materiale

```text
wget https://archive.kali.org/archive-key.asc
sudo rm kali.list
echo "testowy plik" > plikzubuntu.txt
scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop
put pliktubuntu.txt
delete plikzubuntu.txt
Redirect "/" "https://Debian/"
```

## Notatki z zajęć (PadRiseup)

- http://debian.uz/debian-cd/10.3.0/amd64/iso-cd/debian-10.3.0-amd64-netinst.iso
- https://ubuntu.com/download/desktop
- https://www.kali.org/
- https://blackarch.org/
- https://www.parrotsec.org/
- https://www.whonix.org/
- https://tails.boum.org/
- `polska wersja dla debiana - jako ciekawostka:`
- https://wiki.ubuntu.com/PolonizacjaUbuntu
- `debian sources list https://wiki.debian.org/SourcesList`
- `deb https://http.kali.org/kali kali-rolling main non-free contrib`
- `wget https://archive.kali.org/archive-key.asc`
- `sudo rm kali.list`
- `echo "testowy plik" > plikzubuntu.txt`
- `scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop`
- `put pliktubuntu.txt`
- `delete plikzubuntu.txt`
- `Redirect "/" "https://Debian/"`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-01-L1 — Distribution Research](../labs/lnx-01-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 9:** Section 2: Linux Distributions

There are many Linux distributions, some of which are fully customized, and some that

are compiled to a ready image and uploaded to the internet as ISO files. Common

distributions of the Linux family include Debian, Ubuntu, RedHat, CentOS, SUSE, and

others. Some have different command execution syntax, and some are completely

different in their user interface and experience.

Debian, for example, contains basic utilities that can be used to customize the

environment.

Computers & Servers

Over time, Linux became more and more user friendly, and evolved to include a

modern, convenient desktop environment. This opened Linux to a larger volume of

users, and the Linux personal computer OS today features an excellent GUI experience

and numerous applications, such as those in the Ubuntu desktop.

Linux operating systems designed for servers often do not implement GUI features and

desktop experiences. Ubuntu has a server version without GUI features, which makes it

“lighter” and requires less resources for its basic operations.

Linux servers can be used to host cloud services such as OwnCloud and NextCloud.

Other Uses of Linux

In addition to servers and personal computers, Linux is also used as a core component

in Android and loT devices. Since the Android OS is based on the Linux OS, every

Android phone, smart watch, and multimedia device runs on the Linux kernel.

Distribution Variety

The fact that Linux is an open-source project, enabled it to branch out to form many

different distributions. Each distribution has its own purpose, strong points, and

weaknesses. Some distributions are dedicated to server management, such as Ubuntu

and CentOS. Some distributions are dedicated to penetration testing and hacking, such

as Parrot and Kali.

**Textbook s. 10:** Due to the flexibility of the Linux architecture, many distributions are based on older

ones. For example, Kali Linux is based on Debian, and CentOS is based on Fedora Linux.

Although there are many distributions with different GUI experiences and file

managers, they all share a common Kernel.

Lab Assignment: Distribution Research

— Become familiar with Linux-based operating systems and search online for

m= | differences among the most common distributions.

Follow the instructions in lab document LNX-01-L1.

Basic Linux Components

File manager — software that provides an interface for file and directory management.

Desktop environment — software that provides a user-friendly GUI.

Package manager — software that provides the ability to download, install, and update

applications.

Debian is a basic distribution of Linux. It does not contain a desktop experience or a

graphical interface other than the basic UNIX terminal. Users can install many utilities in

Debian to enhance their work with the operating system.

Even if a Linux distribution does not come with a GUI environment, one can easily be

installed. The GUI helps users perform many actions without having to run terminal

commands, and is especially helpful for new users who may be unfamiliar with the

command line interface (CLI). For example, the GUI interface simplifies file

management tasks, such as moving directories, copying and pasting files and folders,

and accessing directory listings.

**Textbook s. 11:** Dedicated Environment

Users can choose the Linux distribution that suits their needs. For example, because Kali

OS contains hacking tools, it is often used by penetration testers. Although Kali includes

a GUI interface, the terminal within the GUI is used for many operations, since most of

the hacking tools are supported only via the terminal.

To build an operating system, programmers rely on some of the more commonly used

distributions, such as Debian, to customize the repository, applications, and the entire

look.

© | Good to Know

) In addition to Kali, an operating system called the SANS Investigative

Forensic Toolkit (SIFT), designed by SANS, is used for malware analysis and

forensics.

There are also dedicated Linux distributions such as RHEL and CentOS, which are

enterprise-grade versions for servers. Unlike other distributions, RHEL is licensed, and

requires a fee for support. CentOS is a free alternative to RHEL, with several differences

and without RHEL’s enterprise support.

® More Information

D |g Some images in this textbook are taken from the Debian OS or Kali OS.

Note that there aren’t many differences between the two systems, since

Kali is based on Debian.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 11:** Introduction to Linux

Distributions

**Slides s. 12:** (Ca Distributions

e

Modern Linux OS’s for desktop users include

excellent GUIs (Graphical User Interfaces)

and numerous applications.

Distributions intended for servers do not use

GUls, and only run server-related

applications.

<p aia

**Slides s. 13:** (ot Distributions

. .

Linux can host cloud services:

¢ OwnCloud

e NextCloud

Some mobile OS’s are based on Linux:

e Android

e Ubuntu Touch

Linux variations are installed on many loT

devices and network equipment.

<p

**Slides s. 14:** Distributions

(Linux Distributions

© Ubuntu () CentOS (©

Debian RHEL OpenSUSE

**Slides s. 15:** Distributions

an : —s 6 ee Become familiar with Linux-based operating systems and

Distribution Research search online for the main differences among the most

: : | common Linux distributions.

10-15 Min ;

—— a e Read about common Linux OS distributions.

med 2 ; e Answer the questions in the lab document.

, ae Le + ~

. *

x ‘) ® = - e Web browser e Lab document

‘ |

**Slides s. 16:** &

The main differences are ro} ay 2 x

the applications installed B SE SE eee ee at =e

on the kernel. m

a = w

Each distribution can 9 =. 2B B B

have a different file 7 °

manager or DE. - a :

a & © @

no GUI components at

all. % = ) :

**Slides s. 17:** (Ba Distributions

O

File manager - allows users to access

files in the system. ial

Li Desktop Environment - provides a

= user-friendly GUI.

Package manager - used to download,

install, and update applications.

i

**Slides s. 18:** Distributions

Applications * Places > set 9:40 @ « ¢wo-

Kali is a Debian-based OS, | fa a“ ao oy hs

similar to Ubuntu. ; | ;

_ ” RR RE: —as im. 4) Bo

Kali Linux has many : || win WS aN % 7® ,

built-in Penetration = eo — + 4o»o@- _

Testing tools. Ti

: 4@ 60 ese v4

#: 3 i

® @®@@t:

**Slides s. 19:** 4

Linux can be used for Al a Ee i in @

both homes and “

enterprises. / = , ee é

i x 0 @ a

RHEL and CentOS are te oS = a ms

: ‘ | |

enterprise-grade Linux om

versions for servers. oO

Unlike other Fy

distributions, RHEL is _

licensed, and requires a nee

fee for support.

</details>
