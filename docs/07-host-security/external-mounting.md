# Linux External Mounting & Removable Media

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 119–119; Linux Security.pdf, s. 263–267.

## Mapa wiedzy

- External storage is mounted into the Linux directory tree rather than assigned Windows-style drive letters.
- Mounting untrusted media expands the attack surface; administrators should control mount points, permissions and execution behavior.
- The material connects `/mnt` and `/media` usage with host-security concerns.

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 119:** | Chapter 7: Host Security

Section 1: Linux External Mounting

Most major Linux distributions come with the option to live-boot the operating system.

Live-booting means running the OS entirely from RAM, complete with all the programs

and features, without making any changes to the local hard drive, while still having

access to it.

This is accomplished by creating a bootable USB flash drive or a CD/DVD and burning

the OS image file (.iso) using a tool like Rufus. Then, during the boot sequence of your

computer, choose from which medium the BIOS will boot.

There are benefits to this method. If you are thinking of switching to Linux, you could

try different Linux distributions and flavors before making your choice. Another good

use would be to have a bootable flash drive of a preferred OS handy for use on public

computers, both for security purposes and since public computers usually limit

capabilities, there are Linux distributions tailored for these purposes. Linux live boots

can also be used for forensics and recovery purposes, for which there are special

distributions as well, such as DEFT Linux.

There are two significant limitations to the Live-booting method. The first is that this

instance of the OS runs entirely from RAM. Therefore, if there isn’t sufficient RAM, the

OS can be sluggish, crash, or fail to boot entirely. The second is that this instance of the

OS will be gone after a reboot.

RAM is volatile memory, meaning it is cleared upon reboot. However, there is an option

to add persistence to the instance. This involves repartitioning the hard drive and

allocating space for the live instance. This is not the same as a dual boot setup. With

dual boot, you have the option at any point to reboot to the alternate OS, while in

persistent live booting, the bootable medium with the OS image on it must be inserted

in the computer for the OS to load. Additionally, in this live OS setup, operating system

files are not stored on the computer’s persistent memory.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 263:** Host Security

Linux External

Mounting

**Slides s. 264:** (Gu Linux External Mounting

>. @ Have you ever thought about what would happen if

\Q you loaded a live OS on your computer when an OS is

already installed?

i" " "2 @ What happens to the folders of the original OS?

J @ What happens to the resources (RAM and HDD)?

Cc % =

**Slides s. 265:** d yh j | I 7

~~ A : .

“the quieter you become, the more you are able to hear”

| Boot menu |

Live Camd6$

Live (amd64 failsafe)

Live (forensic modeJ

Live USE, Persistence (check kali.org/prst)

Live USE Encrypted Persistence (check kali.org/prst)

Install

Graphical install

Install with speech synthesis

Advanced options >

Kali Live mode does not install instances but instead uses guest resources.

**Slides s. 266:** (Re Linux External Mounting

: Folders of the original operating system are

visible in the file system of the live OS after

year SESorD mounting.

fecene On This Computer |

Starred 9) ‘Computer 2.0GB/2.1GBavailable /

me Netware When the live OS is running, it can use

arate BB ween the HDD for storage if configured to do

Live OS does not need to be installed; it

custo —————SS can run from memory without an HDD or

——oO SSD in the computer.

vA

**Slides s. 267:** Linux External Mounting

(Partitions

/boot /dev /sys /proc

8

</details>
