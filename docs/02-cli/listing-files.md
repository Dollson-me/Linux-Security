# Listing Files, Hidden Files & File Types

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 28–32; Linux Security.pdf, s. 60–64.

## Mapa wiedzy

- `ls` and its flags expose file names, types, permissions, owners, groups, sizes, timestamps and links.
- Hidden files begin with a dot and commonly store shell or application configuration such as `.bashrc` and `.profile`.
- The course distinguishes regular files, directories and special files such as block/character devices, pipes, symbolic links and sockets.
- `man`, `whatis`, `whereis`, `which` and `find` are used to understand or locate commands and files.

## Komendy / pliki / składnia występujące w materiale

```text
ls -l
man - Opens the manual for a specified binary.
ls - list directory contents
Whatis - Displays an informative line from a binary’s manual.
find -Searches for files and directories. For example, if you create a document in the
Whereis - Finds the locations of specific binaries, their manual, and source file.
Which - Shows where the execution location is for specific binaries. Typing it before a
Ss Listing Files
Ls -L
man
whatis
find
which
find / -name *.sh 2>/dev/null
ls -la /usr/bin/passwd
```

## Notatki z zajęć (PadRiseup)

- `find / -name *.sh 2>/dev/null`
- `ls -la /usr/bin/passwd`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L1 — System Information](../labs/lnx-02-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 28:** Section 4: Listing Files

The Is command is used to list the contents of a directory.

File Edit View Search Terminal Help

root@debian: /home/emily/Desktop# ls -l

total 8

-rw-r--r-- 1 root root © Oct 28 04:38 bigtable.csv

drwxr-xr-x 2 root root 4096 Oct 28 04:38 mess

drwxr-xr-x 2 root root 4096 Oct 28 04:38 torshammer

Permissions Bytes Y

# of links to File Owner re

Note that in the example above, every line begins with d or -. These characters indicate

the type of file listed, as follows:

Regular files (-): Contain programs, executables, and text files.

Directory files (d): Contain lists of files.

Special files:

Block file (b)

Character device file (c)

Named pipe file (p)

Symbolic link file (I)

Socket file (s)

Hidden Files

Invisible files are represented by dots (.) at the beginning of the file name.

Examples of hidden files include the following:

-bashrc — The Bourne shell configuration file.

-kshre - The Korn shell (ksh) configuration file.

.cshre - The C shell (csh) configuration file.

**Textbook s. 29:** -rhosts - The remote shell configuration file.

-profile — User settings related to a shell, such as the location of a shell-based search

for executed commands.

Configuration files enable shell customization, such as new function creation, coloring,

and control over the command completion mechanism.

To list invisible files, specify the -a option in the Is command, as follows:

| john@debian: ~ x

File Edit View Search Terminal Help

:~$ ls -a

.bash_history

.bash Logout . profile

. bashre

. test.swo

.vboxclient-clipboard.pid

. vboxclient-display-svga-x11.pid

. vboxclient-draganddrop. pid

.ICEauthority .vboxclient-seamless.pid

i-$ |

**Textbook s. 30:** Understanding Commands

When some commands are entered without any options, their usage and format are

displayed. However, the man command can be used to display help for a command

from the Linux manual.

man - Opens the manual for a specified binary.

john@debian: ~ x

File Edit View Search Terminal Help

@ :-$ man Ls |

LS(1) User Commands LS(1)

NAME

ls - list directory contents

SYNOPSIS

Ts [OPTION]... [FILE]...

DESCRIPTION

List information about the FILEs (the cur-

rent directory by default). Sort entries

alphabetically if none of -cftuvSUX nor

--sort is specified.

IL page 1s(1) line 1 (press h for help or q to quit)

--help — A flag that can be used together with the name of almost any other Linux

command to display helpful information on how to use the binary.

I john@debian: ~ x!

File Edit View Search Terminal Help

:~$ cd --help |

cd: cd [-L|[-P [-e]] [-@]] [dir]

Change the shell working directory.

**Textbook s. 31:** Whatis - Displays an informative line from a binary’s manual.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ whatis ls

ts, (1) - list directory contents

find -Searches for files and directories. For example, if you create a document in the

Home folder but your current CLI location (working directory) is in the /root directory,

the results will display “no such file or directory”.

This is because the command looks for the file in the current working directory. You can

use the following syntax to run a search in all directories: find / -name “Document”

jehn@debian: ~ |

File Edit View Search Terminal Help

:~$ find /home -name Desktop

/home/john/Desktop

=o)

Whereis - Finds the locations of specific binaries, their manual, and source file.

=,

john@debian: ~ x

File Edit View Search Terminal Help

i~$ whereis pwd

pwd: /usr/bin/pwd /usr/include/pwd.h /usr/share/man/man1/pwd.1.gz

:=$

Which - Shows where the execution location is for specific binaries. Typing it before a

command or set of commands will show the location of the command, which will

typically be /usr/bin.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ which find

/usr/bin/find

i$

**Textbook s. 32:** © | Good to Know

) Earlier it was mentioned that an important Linux path is /usr because it

contains distribution documentation. Manual pages are listed in the

/usr/share/doc directory. Erasing the directory will cause commands that

display manual content to fail.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 60:** CLI Fundamentals

Listing Files

**Slides s. 61:** Ss Listing Files

=)

==)

en

File Edit View Search Terminal Help

root@debian: /home/emily/Desktop# Ls -L

He ‘Is’ command lists items total 8

. . -rw-r--r-- 1 root root 0 Oct 28 04:38 bigtable.csv

in the directory. drwxr-xr-x 2 root root 4096 Oct 28 04:38 mess

drwxr-xr-x 2 root root 4096 Oct 28 04:38 torshammer

The command can also show | |

file permissions. File Types & File Size in

Permissions Bytes v

# of Links to File Owner a

the File Group

18

**Slides s. 62:** Listing Files

Hidden Fil

O

= john@Debian:/# 1s -la

john@debian: ~ x

File Edit View Search Terminal Help

i~$ ls -la

1 ‘i 1 total 112

-a lists all hidden files dae eee 16 john john 4096 Sep 21 06:29

. . age . ldrwxr-xr-xX 3 root root 4096 Sep 16 11:03

.profile contains definitions for a shell environment [Rtseeeeeemmeas Clune iimmnNNe Ws >On OME Ia7

-rw-r--r-- 1 john john 22@ Sep 16 11:03 .bash logout

re . . . -rw-r--r-- 1 john john 3526 Sep 16 11:03 .bash

.bashrc initializes an interactive shell session fog fons jenn jonnieaese eeu 17 83°58 edehe.

idrwx------ 17 john john 4096 Sep 17 03:58

1 1 1 id rwxr-xr- 2 jot joh 4096 Sep 17 02:06

.bash_history stores historical user commands Pe ae ee ae eo ae ee

. . id rwxr-xr- 2 john joh 4096 Sep 17 02:06

A single dot represents the current directory Jrwm-.--- 3 John John 4096 Sep 17 02:05

-rw------- 1 john john 28 Sep 21 Boe , [CEauthority

Double dots represent the parent directory rwe.-c.-. 8 John John 4096 Sep 17 62:47

ldrwxr-xr-x 2 john john 4096 Sep 17 02:06

idrwxr-xr-x 2 john john 4096 Sep 21 02:36

-rw-r--r-- 1 john john 807 Sep 16 11:03 .profile

idrwxr-xr-x 2 john john 4096 Sep 17 02:06

19

**Slides s. 63:** (He Listing Files

man

Opens the manual for a specified binary. aa

--help

Displays helpful information about binary

usage.

whatis

Displays an informative line from a binary’s

manual.

**Slides s. 64:** (He Listing Files

O

find

Used to search for files in the file system. toa

pp whereis

Displays the location of a binary, its source,

and its manual in the file system.

which

Displays the location of an executable.

aa

</details>
