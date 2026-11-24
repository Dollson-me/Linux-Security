# GRUB, Boot Protection & Disk Encryption

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 120–120; Linux Security.pdf, s. 268–273.

## Mapa wiedzy

- GRUB is the boot loader used in the course and can be password-protected to restrict boot-menu modification.
- Physical access can bypass simple boot-menu protection, so the material distinguishes GRUB password protection from full-disk encryption.
- LUKS is presented as the standard Linux disk-encryption format; full-disk encryption requires appropriate installation/storage setup.
- Class notes configure a GRUB superuser/password hash and run `update-grub`.

## Komendy / pliki / składnia występujące w materiale

```text
fdisk -l | grep -i "/dev/sd"
password_pbkdf2 admin
sudo update-grub
```

## Notatki z zajęć (PadRiseup)

- `/etc/grub.d/00_header`
- `password_pbkdf2 admin`
- `sudo update-grub`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-07-L1 — Encrypt GRUB & System](../labs/lnx-07-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 120:** Section 2: Boot Protection

When you turn on your computer, several tasks begin to run in sequence in the time it

takes for your desktop to appear. One of them is the boot loader. The boot loader is a

small block of code with instructions for the CPU to prepare the machine and pass it on

to the kernel for more complex processes, like managing the OS. The boot loader code

is in a predefined location on the HDD, and from there it is pulled to the RAM for the

CPU to run.

GNU GRUB (GRand Unified Bootloader) is a boot loader package that allows you to boot

multiple operating systems. Its interface has an easy-to-use selection menu and can list

more than 150 operating systems. GRUB is freeware and is used mostly on Linux-based

systems, although there are versions that support Windows as well. GRUB can be

reconfigured on the spot using an interactive command line. It can run an OS froma

variety of mediums, even from the network. It provides the capability to view files on

supported file systems.

GRUB has the ability to password-protect its menus from unauthorized access.

However, a person with access to the physical computer can gain access to the file

system through ways that simple password protection cannot prevent, which is why full

disk encryption is necessary. Full disk encryption encrypts the operating system

partition and second stage of the boot loader, which consists of the Linux kernel and

initial RAM disk.

In Linux systems an entire disk can be encrypted together with all the data stored on it.

For full disk encryption, LVM must be enabled during the installation of the Debian

distribution. After the encryption the files will be available in readable form only when

the system is unlocked by a trusted user. If it is not necessary to encrypt the entire disk,

file-level encryption can be performed to encrypt only specific files.

Linux Unified Key Setup (LUKS) is the standard for Linux hard disk encryption. LUKS

provides a standard on-disk format, which facilitates compatibility among distributors.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 268:** Host Security

Boot Protection

**Slides s. 269:** (Ww Boot Protection

What Is Grub?

® A bootloader available from the GNU project

@ Allows OS boot selection and resource linking and loading

@ Contains names of drivers and disk and partition locations

e

>,

Cc % =

**Slides s. 270:** (Gr Boot Protection

Grub configuration is based on a configuration

Me Meee aa file located in /etc/grub.d called grub.cfg.

Grub configuration is accessed by pressing

the e key during the boot process.

It is recommended to back up the password hash

—________S2neenoetvarc and configuration file for recovery purposes.

a

**Slides s. 271:** (Di Boot Protection

®@ To encrypt an entire disk, it is essential to enable

LVM during the Debian installation.

@ Files will be available in readable form after the

system is unlocked by a trusted user.

pom) a Cony @ Some organizations may decide to use file-

level encryption instead of disk encryption.

®@ Encrypting disks has advantages and

disadvantages.

Lp ala

**Slides s. 272:** Boot Protection

File Edit View Search Terminal Help

root@debian:~# fdisk -l | grep -i "/dev/sd"

Disk /dev/sda: 64 GiB, 68719476736 bytes, 134217728 sectors

fdev/sdal + 2048 125829119 125827072 60G 83 Linux

. _ /dev/sda2 125831166 134215679 8384514 4G 5 Extended

Linux Unified Key Setup /dev/sda5 125831168 134215679 8384512 4G 82 Linux swap / Solaris

uses the dm-crypt module root@debian:~#

as a kernel mapper.

Provides a strong

passphrase based on the

AES cipher method

A good solution for

protection of removable

storage media and disk

drives

**Slides s. 273:** Boot Protection

Lab: LNX-07-L1 [ree

( e VIISSION

2 eee Enhance your knowledge of Linux host security, which

Encrypt Grub & System attacks hackers can perform on machines after gaining

el . | _ | access, and how to mitigate the attacks.

30-40 Min. a“

ee @ oO : ® Generate a password hash.

— . ‘ @ Edit the header file.

=| — S. . j = I ® Encrypt Grub with a password.

rit : y/, @!) ® Reboot and enter with the password.

—— ® 8 d

j ep a yr

| .. @ > - ® Grub ® Lab document

; W ® Debian

| ; %;

: 4

| ) |

{ \ % ia. >. “=

</details>
