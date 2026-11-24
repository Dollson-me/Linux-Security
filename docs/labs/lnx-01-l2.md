# LNX-01-L2 — Debian Installation

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 11–35.

## Cel, misja i środowisko

- »@) Lab Objective Practice the basic installation of Linux in a virtual environment. ba Lab Mission Learn how to configure primary settings and resources for a Linux installation, and
- ba Lab Mission Learn how to configure primary settings and resources for a Linux installation, and install a Debian environment from an image disk. It is recommended to perform this lab together with the instructor.
- ©@ Lab Duration 40-45 minutes {e Requirements e Basic understanding of the Linux installation process.
- {e Requirements e Basic understanding of the Linux installation process. e Anunderstanding of Linux components. e Basic knowledge of CLI commands.
- Learn how to configure primary settings and resources for a Linux installation, and install a Debian environment from an image disk. It is recommended to perform this lab together with the instructor. ea 7

## Powiązana teoria

- [Installation](../01-introduction/installation.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 11:** Linux Security

Introduction

Lab Assignment .

to Linux

ona LNX-01-L2

On TU Debian Installation

Ea)

All Rights Reserved.

**PDF s. 12:** Linux Security

Introduction

Lab Assignment .

to Linux

ona LNX-01-L2

On TU Debian Installation

Ea)

All Rights Reserved.

**PDF s. 13:** »@) Lab Objective

Practice the basic installation of Linux in a virtual environment.

ba Lab Mission

Learn how to configure primary settings and resources for a Linux installation, and

install a Debian environment from an image disk.

It is recommended to perform this lab together with the instructor.

ea 7

©@ Lab Duration

40-45 minutes

{e Requirements

e Basic understanding of the Linux installation process.

e Anunderstanding of Linux components.

e Basic knowledge of CLI commands.

LT

[ra] Resources

¢ Environment & Tools

o Oracle VirtualBox

e ISO Files

o debian-10.3.0-amd64-netinst.iso

**PDF s. 14:** Lab Task

Install the Debian distribution in VirtualBox and complete all the installation steps. After

installation, make sure the new system boots and that you can log in to the OS.

1 Open VirtualBox and create a new virtual machine.

2 Name the virtual machine Debian, for type, select Linux, and for version select

Debian(64-bit). Click Next to continue.

3 Set the RAM to 4096 MB, but make sure not to use more than half of the entire

RAM in your computer. Click Next to continue.

Note:The RAM can also be configured to 2048 MB if the host machine does not

have enough resources.

4 For the hard disk, select Create a virtual hard disk now and click Create.

5 For the hard disk file type, select VDI and click Next.

6 Set the hard disk to Dynamically allocated, and click Next.

7 Set the size of the hard drive to 64 GB and click Create.

Note: Debian can work with 8 GB, but during the course you will install additional

programs that may consume space.

8 Once the VM is created, double-click it, to start it.

9 Select the provided Debian ISO file when asked for a startup disk, and click Start.

10 Select the non graphical installation.

Note: It is recommended to use the regular “Install” option rather than the

“Graphical install” option. The aim is to be comfortable working without a

graphical interface.

11 Select English for the language.

**PDF s. 15:** 12 Select United States for the location.

13 Select American English for the keymap.

14 Inthe hostname configuration, leave the default name, debian.

15 Leave the domain name field empty and continue.

16 Set the word toor for root password and repeat it in the next step.

17 Provide a full name for a new user account.

18 Set the user’s login name for the account.

19 Set a password for the account and repeat it in the next step.

Note: Consider using the password toor.

20 Select a suitable timezone.

21 For partition configuration, choose the Guided — use entire disk option for a

simplified process.

22 Select the only disk that appears for the partition.

23 Choose the partition scheme All files in one partition.

24 Inthe partitioning overview, choose Finish partitioning and write changes to

disk. Select Yes when asked to write the changes.

25 The installation will continue and install all the necessary files to the drive. When

asked if you want to scan another CD or DVD for installation files, select “No.”

26 The installation will attempt to configure the package manager and the source for

application installation. Select your location and then choose deb.debian.org.

Note: The purpose of the settings is to locate the nearest repository for the

package manager.

**PDF s. 16:** 27 Leave the HTTP Proxy configuration blank (“None”).

28 You can decide if you want to participate in the package usage survey.

29 Use the spacebar to select or deselect features. Since Debian should be installed

as a clean version, without desktop experience, unmark the asterisk for “Debian

desktop environment.”

30 When prompted with “Install the GRUB boot loader to the master boot

recorder?”, select “Yes”.

31. Use the arrow keys to navigate to /dev/sda (ata-VBOX_HARDDISK_[Drive ID]) and

select it as the destination for the boot manager installation.

32 When the installation is done, select “Continue” to finish the process, and wait

for the machine to reboot.

33 If the installation process was performed correctly, you should see a black screen

with a login prompt. Enter the credentials for your user (not root) and verify that

you can successfully log in.

34 Shut down the system by running the command systemctl poweroff.

**PDF s. 17:** Linux Security

. Introduction

Lab Assignment .

: to Linux

Solution

oir LNX-01-LS2

° TU Debian Installation

Ba

All Rights Reserved.

**PDF s. 18:** Linux Security

. Introduction

Lab Assignment .

: to Linux

Solution

oir LNX-01-LS2

° TU Debian Installation

Ba

All Rights Reserved.

**PDF s. 19:** Note: Solutions for the instructor are shown inside the green box.

bs Lab Mission

Learn how to configure primary settings for a Linux installation, configure resources,

and install a Debian environment from an image disk.

It is recommended to perform this lab together with the instructor.

es .

@ Lab Duration

40-45 minutes

f Requirements

e Basic understanding of the Linux installation process.

e Anunderstanding of Linux components.

e Basic knowledge of CLI commands.

=

| Resources

¢ Environment & Tools

o Oracle VirtualBox

o Debian ISO

e External Links

o VirtualBox download:

https://download.virtualbox.org/virtualbox/6.0.14/VirtualBox-6.0.14-133895-Win.exe

o Debian ISO download:

https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-10.1.0-amd64-

netinst.iso

Note: New versions of Debian and Oracle may be released, and the links may change.

**PDF s. 20:** (= Textbook References

e LPI Linux Essentials Certification All-in-One Exam Guide

**PDF s. 21:** Lab Tasks

Install Debian distribution in a virtual environment (Oracle VitrualBox) and complete all

the installation steps. After installation, make sure the new system boots and that you

can log in to the OS.

1 Download Oracle VirtualBox if it is not already installed, and install the program

with all the default settings.

You can use the following link to download Oracle VirtualBox, and follow all the steps:

https://download.virtualbox.org/virtualbox/6.0.14/VirtualBox-6.0.14-133895-Win.exe

2 Download Debian ISO.

It is highly recommended to download the latest version of Debian.

Go to https://www.debian.org/ and click “Getting Debian.”

Search ©

eE About Debian [Géttinig/DEbIah!) Documentation Support Developers’ Comer

debian /

{-) . (GLOLFC Nato ton

\ debian

The universal operating system

Debian is a free operating system (OS) for your computer. An operating system is the set of basic programs and

utilities that make your computer run.

Debian provides more than a pure OS: it comes with over 59000 packages, precompiled software bundled up in

a nice format for easy installation on your machine. Read more...

About Getting Debian News ‘Support Site map

» Social Contract » Network install » Project News » Debian intemetional Search

» Code of Conduct »CDIUSBISO images» Events » Seourty information The Debian Biog

» Free Software » CD vendors Documentation » Bug reports

» Partners » Pre-installed » Release Info » Mailing Lists

» Donations Pure Blends » Insalaion manval Mating List Archives

» Legal nfo Debian Packages » Debian Books » Ports/Architectures

» Data Privacy Developers’ Comer» Debian Wiki

» Contact Us

Select “Download an installation image” to download the ISO file.

**PDF s. 22:** Search ©

Ee About Debian Getting Debian Documentation Support Developers’ Corner

debian / getting debian

Getting Debian

Debian is distributed freely over Internet. You can download all of it from any of our mirrors. The Installation

Manual contains detailed installation instructions. And, the release notes can be found here.

If you simply want to install Debian, these are your options:

- Download an installation image — Use a Debian cloud image

Depending on your Internet connection, you may « An official cloud image: can be used directly on

download either of the following: your cloud provider, built by the Debian Cloud

Team.

+ A small installation image: can be

downloaded quickly and should be recorded ==) G4-bit AMD/Intel OpenStack (Qcow2),

onto a removable disk. To use this, you will 64-bit ARM OpenStack (Qcow2)

need a machine with an Internet connection.

a Try Debian live before installing

i 64-bit PC netinst iso, 32-bit PC netinst iso J

Most computers are of amd64 architecture, so select the amd64 link. Otherwise, locate

the link that has your computer’s architecture.

Search ©

@E About Debian Getting Debian Documentation Support Developers’ Corer

debian / setting debian /instaling debian via the internet

Installing Debian via the Internet

This method of installing Debian requires a functioning Internet connection during installation. Compared to

other methods you end up downloading less data as the process will be tailored to your requirements. Ethernet

and wireless connections are supported. Internal ISDN cards are unfortunately not supported.

There are three options for installs over the network:

‘Small CDs or USB sticks

Tiny CDs, flexible USB sticks, ete

Network boot

Small CDs or USB sticks

The following are image files. Choose your

processor architecture below.

‘=. /amd64, arm64, armel, armhf, i386, mips, P

Download the ISO file and save it on your computer.

**PDF s. 23:** 3. Create a virtual machine that will be used for the Debian installation. Set the

memory size to 4096 MB, and 64 GB for disk size.

Create a new virtual machine using the New button in the main view or the Machine >

New menu.

Oracle VM VirtualBox Manager —- a x

rite [Magia] Help

eso fe 2. 22 Ow

‘welcome to Virtualsoxt |

The tou ofcokaton vino ras nl arise al vil machines end it

‘ie bons Yeu cr pooans bus cPeureny sdecaderent ine cxreberde cent |

ee

In the new window, fill in the details as follows:

- Name: Debian

- Location: [fill in the path where the VM files will be saved. Note that they tend to

grow, so make sure to save the machine in a location with enough space]

- Type: Linux

- Version: Debian (64-bit)

After completing the VM description, click “Next.”

**PDF s. 24:** J

| Create Virtual Machine

Name and operating system

Please choose a descriptive name and destination folder for the new virtual

machine and select the type of operating system you intend to install on it.

The name you choose will be used throughout VirtualBox to identify this

machine.

Expert Mode Next Cancel

Determine the amount of RAM. The preferable size is 4096 MB, but make sure not to

use more than half of the entire RAM in your computer. If you are using an older model

with a total of 8 GB RAM, select 2048 MB.

| Create Virtual Machine

Memory size

Select the amount of memory (RAM) in megabytes to be allocated to the

virtual machine.

The recommended memory size is 1024 MB.

4MB 32768 MB

In the following window, make sure to select “Create a virtual hard disk now”, and click

Create.

**PDF s. 25:** j

| © Create Virtual Machine

Hard disk

If you nish you can add a virtual hard disk to the new machine. You can

either create a new hard disk fle or select one fram the list or from another

location using the folder icon.

If you need a more complex storage set-up you can skip this step and make

the changes to the machine settings once the machine is created,

The recommended size of the hard disk is 8.00 GB.

© Bo not add a virtual hard disk

O Use an existing virtual hard disk fle

Empty

Create Cancel

Keep the default selections for the next two configurations:

- Hard Disk file type: DVI

- Storage on physical hard disk: dynamically allocated

Finally, set the file location and size. The location can remain the default, but the size

should be changed to 64 GB. Debian can work with 8 GB, but during the course you will

install additional programs that may consume space. Make sure not allocate too much

space, and note the amount of free space on the drive.

After configuring the drive, click “Create.”

**PDF s. 26:** | ba |

| |

© Create Virtual Hard Disk

File location and size

Please type the name of the new virtual hard disk file into the box below or dick

on the folder icon to select a different folder to create the fie in.

Select the size of the virtual hard disk in megabytes. This size is the limit on the

amount of file data that a virtual machine will be able to store on the hard disk,

4,00 MB 2,00 7B

Create Cancel

4 Configure the boot device to use the Debian installation media (ISO file).

The new machine was created, but still lacks an installation CD. You can add an

installation drive in one of two ways:

Click “Start” to start the machine and wait for VirtualBox to prompt you for an

installation media.

**PDF s. 27:** }

Select start-up disk

Please select a virtual optical ds Fie or physical optical

drive containing a disk to start your new virtual machine

rs

“The disk should be suitable for starting a computer from and

should contain the operating system you wish to install on

the vtul machine yeu want to do thet nom, The ds

be ejected from the virtual drive automatically next time you

snitch the vu methine oF but you cn aso do ts

yourself if needed using the Devices menu,

Empty 7|@

5 cored

DORE SIGH OG wretcei

Alternatively, navigate to Settings > Storage > Controller: IDE and choose the

installation drive there.

+

DAS ots t >.

CO Poneretor — Debian

@ Debian - settings ? x Debian

[EH Gener storage |

Bl stem Ss tributes $n

Im pny @& Controller: DE Optical Drive: DESecondary Master |@

hl (© tionse-somndctretsti.| Cuveeopio 1G). Choose Vital Opin Disk ile

Bisse | om concte: sre inorestn deban 0 mab netics

Qp aucio G) debian vi Type: Tage astinue-ble-20193-amd6 ico

See 280008

| GBB Network Location: C:\sesLiretoomioadsiiet @ Remove Disk rom Vital Dive

prod “Attached to:

So 0

ED Shae Fotders

FE) User interface

eo5G

Tne .

After configuring the VM to use the ISO file, click Start again.

**PDF s. 28:** 5 Install a non-graphical Debian interface and configure the basic settings.

Note: It is recommended to use the regular “Install” option rather than the

“Graphical install” option.

The first step offers two relevant options: “Graphical install” and “Install.” To keep the

standard installation, use the arrow keys to select the “Install” option, and press Enter

to proceed.

Debian GNU/Linux installer menu (BIOS mode) q

Graphical install

Advanced options >

Accessible dark contrast installer menu >

Help

Install with speech sunthesis

= DOws SOBEL SRxncn |

The next few steps determine the language and localization.

In the first configuration window, choose English, even if it is not your mother tongue.

This will ensure consistency with the other guides.

Use the arrow keys to navigate, the space bar to mark checkboxes, and the Enter key

for selection.

**PDF s. 29:** ja

(11) Select a language

Choose the language to be used for the installation process. The selected language will

also be the default language for the installed system.

Langueges

C = No locetization +

Albanian — Shgip

Arabic - yet

Asturian - AStUPianu

Bascue = Euskara

Belerusion = Benapyexan

Bosnien = Bosanski 5

fulgerian = Benrapci

Catalan - Catala,

Chinese (Simplified) - oe

Chinese (Traditional) - 3 (HERB)

Crostian = Hevatsid

czech. = CeStina

Danish > Dansk

Dutch. — Neder lends

English SERGI Est

Esperanto = Esperanto

Estonian - Eestl

Finnish - Suomi

French - Francais

Galician = Galego

Georgian - dohmgan

German - Deutsch +

Go Back>

GOW FSCAGDESrrecet

For localization, choose your actual location to ensure time synchronization and usage

of the best repository for installation.

‘a

(1!) Select your location

The selected location will be used to set your time zone anc also for example to help

select the system locale. Normally this should be the country where you Live.

This Ls a shortlist of locations based on the language you selected. Choose "other" lf

your location is not Listed.

Country, territory or area

Antigua and Barbuda

fustraLia

eotsuane

Canada

fiong Kong

India

Ireland

israel

New Zealand

Nigeria

Philippines

Seychelles

Singapore

South africa

United See

zambia

Zimbabwe

other

<GO Back?

DOUsP10HO GH mw

**PDF s. 30:** For keyboard layout, select “American English” and proceed with the installation.

The process may take several minutes, depending on your Internet speed.

Loading additional components

Retrieving partmen-md

BOE SOBEO OW ronce

The next step is to set the hostname, which is the name of the computer. You can leave

the name “debian”, and click “Continue.”

[1] Configure the network

Please enter the hostname for this system.

The hostname is a single word that identifies your system to the network. If you don't

know what your hostname should be, consult your network administrator. If you are setting

Up your own home network, you can make something up here.

Hostname:

<GO Back> <Continue>

You can skip the next step, domain configuration, since this is a standalone installation.

**PDF s. 31:** 6 Configure the root user and primary user, for use in the system.

For credentials, enter: root PaSSwOrd and johnd Aa123456!

The next step is to configure the root user and set the password. It is recommended to

use a strong password for the root user. For consistency with the labs, use “PaSSwOrd”

[11] Set up users and passwords

You need to set a password for ‘root’, the system administrative account. A malicious or

ungualified user with root access can have disastrous results, so you should take care to

choose a root password that is not easy to guess. It should not be a word found in

dictionaries, or a word that could be easily associated with you.

A good password will contain a mixture of letters, numbers and punctuation and should be

changed et regular intervals.

The root user should not heve an empty password. If you leave this empty, the root

account will be disabled and the system's initial user account will be glven the power to

become root using the "sudo" command.

Note that you will not be able to see the password as you type it.

Root password:

<Go Back> <Cont inue>

Before creating another user, the installation will ask you to reconfirm the password.

Immediately afterwards, you will be prompted to create a regular user.

[!!] Set up users and passwords

A user account will be created for you to use instead of the root account for

non-administrative activities.

Please enter the real name of this user. This information will be used for instance as

default origin for emails sent by this user as well as any program which displays or uses

the user's real name. Your full name is a reasonable choice.

Full name for the new user:

<Go Back> <Cont inue>

For consistency with the lab, use the following configuration:

- Full name: John Doe

- Username: johnd

- Password: Aa123546!

The installation should continue on, until the drive partitioning step.

**PDF s. 32:** 7 For disk partitioning, use the default configuration.

Disk partitioning defines how partitions should be saved in the disk. Use the default

configuration, as follows:

- Partition method: Guided — use entire disk

- Select disk to partition: SCS/1 (0,0,0) (sda) — 68.7 GB ATA VBOX HARDDISK

- Partitioning scheme: All files in one partition (recommended for new users)

The configuration should appear as follows:

(!!] Partition disks

This is an overview of your currently configured partitions and mount points. Select a

partition ta modify its settings (file system, mount point, etc.), a free space to create

partitions, or a device to initialize its partition table.

Guided partitioning

Configure software RAID

Configure the Logical Volume Manager

Configure encrypted volumes:

Configure iSCSI volumes

SGSI1 (0,0,0) (sda) - 68.7 GB ATA VBOX HARDDISK

#1 primary 64.4 GB f extd f

#5 logical 4.3 GB # swap. swap

Undo changes to partitions

<Go Back>

Click “Finish partition and write changes to disk”. When asked “Write the changes to

disk?”, use the arrow keys to select “Yes.”

(1!] Partition disks

If you continue, the changes listed below will be written to the disks. Otherwise, you

will be able to make further changes manually.

The partition tables of the following devices are changed:

SCSI1 (0,0,0) (sda)

The following partitions are going to be formatted:

partition #1 of SCSI1 (0,0,0) (sda) as ext4

partition #5 of SC5I1 (0,0,0) (sda) as swap

Write the changes to disks?

<No>

The installation will continue and install all the necessary files to the drive. When asked

if you want to scan another CD or DVD for installation files, select “No.”

**PDF s. 33:** 8 Configure the package manager for the main deb.debian.org archive.

At this point, don’t install a graphical interface, since this will be done later.

The installation will attempt to configure the package manager and the source for

application installation. Select your location:

finited States a

For the Debian archive, choose deb.debian.org. The purpose of the settings is to locate

the nearest repository for the package manager. To maintain consistency with the labs

and not miss any packages, use the main archive.

**PDF s. 34:** Leave the HTTP Proxy configuration blank (“None”) and press Enter to continue.

You can decide if you want to participate in the package usage survey.

The following step is important! Use the space bar to mark or unmark features. Since

Debian should be installed as a clean version, without desktop experience, unmark the

asterisk for “Debian desktop environment.”

LC} (GNOME

Lo] mars Ktce:

[.] ... KDE Plasma

I]... Cinnamon

ES] sat MATE:

Ee) exit KBE:

IC]... Lxat

IC ] web server

4] print server

[ ] SSH server

lea Sane San utilities

Press Enter to continue the configuration.

9 Set the boot loader to be installed on the main drive, and complete the

installation.

The configuration is done, and you will now continue with the grub installation.

Be careful with these steps, because missing a “Yes” or a “No” may result in not being

able to boot the VM.

When prompted with “Install the GRUB boot loader to the master boot recorder?”,

select “Yes”. Use the arrow keys to navigate to /dev/sda (ata-VBOX_HARDDISK_[Drive

ID]) and select it as the destination for the boot manager installation.

**PDF s. 35:** {!] Install the GRUB boot loader on a hard disk

You need to make the newly installed system bootable, by installing the GRUB boot loader

on a bootable device. The usual way to do this is to install GRUB on the master boot

record of your first hard drive. If you prefer, you can install GRUB elsewhere on the

drive, or to another drive, or even to a floppy.

Device for boot loader installation:

Enter device manually

<Go Back>

When the installation is done, select “Continue” to finish the process, and wait for the

machine to reboot.

If the installation process was performed correctly, you should see a black screen with a

login prompt.

Enter the credentials for johnd and verify that you can successfully log in.

ia

Debian GNU/Linux 10 debian tty1

debian login: johnd

Password:

ast login: Sat Nov 2 16:08:00 IST 2019 on ttyl

Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-24+deb10u1 (2019-09-20) x86_64

The programs included with the Debian GNU/Linux system are free software;

the exact distribution terms for each program are described in the

individual files in /usr/share/docé*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

permitted by applicable law.

johnd@debian:~$ _

BOE SOGHO 6 Bronce

At this point, it may be a good idea to take a snapshot.

</details>
