# Linux Installation & Virtual Machines

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 13–13; Linux Security.pdf, s. 23–26.

## Mapa wiedzy

- The installation workflow covers creating a VM, selecting the distribution/ISO, assigning RAM and disk, selecting installation type and localization, creating users/passwords, choosing packages and installing GRUB.
- The course recommends a minimal/non-graphical Debian installation first so the student becomes comfortable with the CLI, then adds a desktop environment later.
- Virtualization is used as the laboratory platform; the lab material uses Oracle VirtualBox and Debian ISO images.

## Komendy / pliki / składnia występujące w materiale

```text
ss ja rr
Systemctl poweroff
scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop
Redirect "/" "https://Debian/"
```

## Notatki z zajęć (PadRiseup)

- http://debian.uz/debian-cd/10.3.0/amd64/iso-cd/debian-10.3.0-amd64-netinst.iso
- `Systemctl poweroff`
- `instalacja guest additions:`
- `polska wersja dla debiana - jako ciekawostka:`
- `debian sources list https://wiki.debian.org/SourcesList`
- `scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop`
- `Redirect "/" "https://Debian/"`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-01-L2 — Debian Installation](../labs/lnx-01-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 13:** Section 4: Linux Installation

Linux, similar to other operating systems, can be installed as an operating system on the

host computer or as a virtual machine. As an operating system, Linux can interact with

and support many hardware components.

Before installing Linux on a virtual machine, a few things should be preconfigured.

VirtualBox requires the preparation of an installation surface that applies RAM and disk

size and matches and marks the platform (type and version) prior to inserting the ISO.

Some Linux versions include a live version along with a full installation, but all have

several common installation-related steps, such as creating a user, setting a password,

configuring the installation path, updating the OS (during installation), and choosing a

language.

When installing Debian, the first step is to choose the installation type: graphical

experience (32/64-bit), standard installation, or graphical installation that does not

include the GUI interface. The next step is to choose the language and country, and

then the hostname, domain name, and root password. After those steps, the user

specifies his/her actual name, and a username and password for non-admin users.

Debian does not use the root as the main user, for security reasons. The final steps are

to save the configuration details and choose the installation path.

After installation, Debian configuration is required, including HTTP proxy and mirroring.

During the configuration process, options are chosen for the desktop experience or

server installation. Since Debian does not install a desktop experience or server by

default, this stage includes several options for faster installation: Debian Desktop

Environment, Print Server, and Standard System Utilities. The last step is GRUB

installation, after which the machine reboots.

Lab Assignment: Debian Installation

— Learn how to configure primary settings and resources for a Linux

== installation and install a Debian environment from an image disk.

Follow the instructions in lab document LNX-01-L2: Debian Installation.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 23:** Introduction to Linux

Linux Installation

**Slides s. 24:** Linux Installation

Preparation for Installation

Set disk size

Create new virtual Set memory size Import ISO for

machine installation

Specify name and

choose OS ©.

hp tis.

**Slides s. 25:** Linux Installation

Linux Configuration

Choose minimal

desktop experience

Keep standard Create a new user Take a snapshot

installation and set a password P

Select language, » €

location, and time

**Slides s. 26:** Linux Installation

— ; 2 eee Learn how to configure primary settings for Linux

3 7 installation, set resources, and install the Debian

Debian Installation | environment from an image disk.

40-45 Min —# :

eee |e : e Prepare Oracle VirtualBox for Debian

ae * Linux installation.

; ree... = , 4 . t e Install a non-graphical Debian instance.

rn 4a 4)

; yY e d di

1% F > i ; yr

| - - ; ® al e VirtualBox e¢ Lab document

~- W ¢ Debian-10.3.0-amd64-

| \, ; netinst.iso

; ‘ ;

| | . ss

ss ja rr

</details>
