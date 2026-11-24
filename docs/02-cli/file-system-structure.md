# File System Structure & Navigation

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 25–27; Linux Security.pdf, s. 55–59.

## Mapa wiedzy

- Navigation uses absolute paths beginning at `/` and relative paths based on the current directory.
- `cd`, `pwd` and shell shortcuts (`~`, `.`, `..`, `-`) are core navigation tools.
- The course reinforces the purpose of `/dev`, `/etc`, `/media`, `/usr`, `/var`, `/home` and other directories while navigating from the CLI.

## Komendy / pliki / składnia występujące w materiale

```text
cd ~ returns to the home directory.
cd - returns to the previous directory.
cd .. navigates to the parent directory of the current directory.
cd / navigates to the root directory of the entire system.
¢ cd <file system path>
cd means “Change
cd ~ :
cd /
cd -
cat /etc/ssh/ssh_config
grep -in Fire /var/log/dpkg.log --color
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
export PATH=/usr/sbin:$PATH
cp /etc/shadow
vim /etc/quality/pwquality.conf
chown root:adm /var/log/boot.log
chmod 640 /var/log/boot.log
chmod 644 /var/log/boot.log
chown root:root /var/log/boot.log
ls -la /usr/bin/passwd
sudo cat /etc/shadow
sudo vim /etc/pam.d/common-password
echo "piotr" > /etc/ssh/sshd.allow
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
sudo vim /etc/apache2/conf-available/security.conf
cd /etc/apache2/mods-enabled
IncludeOptional /usr/share/modsecurity-crs/*.conf
IncludeOptional /usr/share/modsurity-crs/rules/*.conf
IncludeOptional /usr/share/modsecurity-crs/rules/*.conf
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/ssh/ssh_config`
- `grep -in Fire /var/log/dpkg.log --color`
- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `more /var/log/dpkg.log`
- `less /var/log/dpkg.log`
- `export PATH=/usr/sbin:$PATH`
- `cp /etc/shadow`
- `vim /etc/quality/pwquality.conf`
- `chown root:adm /var/log/boot.log`
- `chmod 640 /var/log/boot.log`
- `chmod 644 /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `ls -la /usr/bin/passwd`
- `sudo cat /etc/shadow`
- `/etc/init.d/networking stop`
- `/etc/init.d/networking start`
- `/etc/vsftpd.conf`
- `file=/var/www/html/index.html`
- `/etc/grub.d/00_header`
- `sudo vim /etc/pam.d/common-password`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`
- `sudo vim /etc/apache2/conf-available/security.conf`
- `/etc/init.d/apache2 force-reload`
- `cd /etc/apache2/mods-enabled`
- `IncludeOptional /usr/share/modsecurity-crs/*.conf`
- `IncludeOptional /usr/share/modsurity-crs/rules/*.conf`
- `IncludeOptional /usr/share/modsecurity-crs/rules/*.conf`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L2 — Moving Files in the File System](../labs/lnx-02-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 25:** Section 3: File System Structure

The following are some important directories in the Linux system:

/dev points to the location of device-related files. For example, the file for the device

associated with a hard disk will be stored in this directory.

/etc stores configuration files, such as the host file, kernel configuration, and system

services. Some configurations have folders within the /etc directory.

/media stores information about removable media, such as CDs and USBs. In many

modern Linux distributions, when a removable disk is connected, a directory will

automatically be created with the disk contents.

/usr stores user binaries and read-only data.

/var stores variable data files, such as log files (/var/log) and HTTP server files

(/var/www), although these can be stored in the /srv directory as well.

® | Good to Know

Linux views everything, hardware, software, running processes, etc., as files

or filestreams.

File System Navigation

The most fundamental skills to master in Linux are manipulating files, navigating the

directory tree, and understanding the file system environment.

After logging in to a server, the initial location is often the user account's home

directory. This directory is designated for users to store files and create other

directories.

In a Linux system, files and directories typically contain different types of information,

such as application files, user documents, and images. The various types of data are

displayed in a GUI file system manager. In Linux (as in most other systems) files and

directories are navigated from the CLI, using the cd command.

**Textbook s. 26:** File navigation can be done from any directory location and can reach any other

directory via a single command.

Change Directory (cd)

There are two types of paths used for navigation: absolute and relative.

Absolute Path —A complete path that always starts from the root directory (/) which is

at the top of the file system hierarchy. The path should be used when the destination is

not located close to the current location.

For example, an absolute path command may be: cd /home/john

Relative Path — Navigation to directories without specifying the root. This path

command should be used when the destination is close to the current location.

For example, a relative path command may be: cd Documents/

'¢ Tip

o © ” | The tab key is an essential auto-complete tool in navigation and command

= execution.

The following example shows the step-by-step procedure for navigation to a

destination, with each command entering a different folder in the hierarchy.

john@debian: /usr/local/man x

File Edit View Search Terminal Help

2) Cd) /USH/

: $ cd local/

: $ cd man/

: $f

Note that from the second line, the cd command uses a relative path to navigate the file

system.

The following example shows how to enter the full path of a destination. If the

command starts with a forward slash, it will look for the destination beginning with the

root folder.

**Textbook s. 27:** john@debian: /usr/local/man x

File Edit View Search Terminal Help

:~$ cd /usr/local/man/

: $

The navigation command includes the following options:

cd ~ returns to the home directory.

cd - returns to the previous directory.

cd .. navigates to the parent directory of the current directory.

cd / navigates to the root directory of the entire system.

I john@debian: | x)

File Edit View Search Terminal Help

: $ cd ~

Bisa) (eto)

/usr/local/man

: cecda..

: Sco 7

:/$

sa+ | Tip

. © * | The tilde sign (~) indicates your home directory.

=

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 55:** CLI Fundamentals

File System Structure

**Slides s. 56:** ; File System Structure

(Dire ctories

/etc 6 /usr

/dev /media /var

13

**Slides s. 57:** john@debian:~/$¢ cd <file system path>

cd means “Change

Directory.”

It enables you to

navigate to a different

directory.

The location upon login

is typically the home

directory.

**Slides s. 58:** (Ch File System Structure

Absolute Path

“/” indicates the root folder. Navigating to a path

from the root is known as using an absolute path.

Ec Relative Path

Navigation to directories without specifying the

root and relative to the working directory is known

(} as using a relative path.

The cd command is used to navigate in the

file system.

Lp

**Slides s. 59:** File System Structure

john@debian: ~ x

File Edit View Search Terminal Help

cd. :~$ cd ..

Return to the parent :/home$ cd ~

folder :~$ cd /

r ; i/S cd, =

cd ~ :

Go to the user’s home /home/ john :~$

directory .

cd /

Go to the root folder

cd -

Return to the previous

folder

</details>
