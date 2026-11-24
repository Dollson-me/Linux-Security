# SUID, SGID & PATH Security

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 67–69; Linux Security.pdf, s. 127–131.

## Mapa wiedzy

- SUID allows an executable to run with the file owner’s effective privileges; SGID has analogous group-related behavior and can also affect directory group inheritance.
- These bits are useful but dangerous when applied to vulnerable or user-controlled programs.
- PATH determines command lookup order. A manipulated PATH can cause the wrong executable to run, especially in privileged scripts.
- The lab focuses on the security impact of SUID and privilege boundaries.

## Komendy / pliki / składnia występujące w materiale

```text
Id rwx------ 2 root root 16384 Sep 19 06:28
export PATH=/usr/sbin:$PATH
ls -la /usr/bin/passwd
md5sum $file > $temppath
```

## Notatki z zajęć (PadRiseup)

- `export PATH=/usr/sbin:$PATH`
- `ls -la /usr/bin/passwd`
- `5 backup_path="/home/piotr/Desktop"`
- `9 dest_path="/tmp"`
- `21 tar -czvf dest ath/filename $backup_path`
- `hashpath=/tmp/wwwhash`
- `temppath=/tmp/temphash`
- `md5sum $file > $temppath`
- `Sprawdz czy dwa hashe temppath oraz hashpath`
- `status="$(cmp --silent $hashpath $temppath; echo $?)"`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L4 — The Power of SUID](../labs/lnx-03-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 67:** J john@debian: ~/test x j

File Edit View Search Terminal Help

: $ 1s -l

total 0

-rw-r--r-- 1 john john © Sep 29 03:14 file.txt

i $ sudo chown jane:root file.txt

: $ 1s -l

total 0

-rw-r--r-- 1 jane root © Sep 29 03:14 file.txt

: $

Lab Assignment: LNX-03-L3 Group Management

or Use groups to allow or deny user access to folders and files.

=m

Follow the instructions in lab document LNX-03-L3.

Section 8: SUID, SGID, and PATH

SUID and SGID are special characters (bits) that can be attached to files or directories to

provide additional permission capabilities. In some cases, these capabilities may be

beneficial for the system's operation. However, they can also be viewed as potential

vulnerabilities.

SUID and SGID

These are flags that can be added to the owner permission section of a file.

SUID — The flag s provides other users with the ability to execute the file as its owner.

SGID — provides the ability to execute a file for anyone in the owning group.

The permissions are based on UGO or numerical settings. The numerical settings are

Axxx for setuid, 2xxx for setgid, and 6xxx for both. For example, to assign full

premissions and setuid and setgid to a file, the command would be: chmod 6777

filename

**Textbook s. 68:** The PATH is the location the command references. Commands are located in the bin or

sbin directory, and the command path is configured so that it first references the bin

and then navigates to the sbin if it is not found in the bin directory. The path can be

manually configured and comes with default settings depending on the commands,

libraries, application settings, and location. Each file path is separated with a colon (:).

Lab Assignment: LNX-03-L4 - The Power of SUID

— Configure a SUID on one of the system’s binaries to allow a simple

== =| user to copy classified data.

Follow the instructions in lab document LNX-03-L4.

Extra - Symbolic and Hard Links

There is a difference between saving a file in a directory that is saved directly to a hard

disk, and saving a file on a hard disk but navigating to it from another location in the

system, such as a shortcut in the Windows OS.

Symbolic link — Also known as a soft link, and is similar to a shortcut in Windows. The

link is written to a different directory than the one it is saved in.

Hard link — Files that are saved to the hard drive (regularly created and saved files). Any

change in a hard link will also cause a change in its associated soft link.

**Textbook s. 69:** I john@debian: / —|

File Edit View Search Terminal Help

Lirwx rwx rwx 1 root root 10 Sep 19 06:28 ->

Id rwx------ 2 root root 16384 Sep 19 06:28

drwxr-xr-X 3 root root 4096 Sep 19 06:28

ldrwxr-xr-X 2 root root 4096 Sep 19 06:28

drwxr-xr-x 3 root root 4096 Sep 29 01:39

ldr-xr-xr-x 162 root root 0 Sep 29 01:47

drwx------ 4 root root 4096 Sep 29 01:46

ldrwxr-xr-x 22 root root 620 Sep 29 01:40

LL rwx rwXx rwx 1 root root 8 Sep 19 06:28 ->

drwxr-xr-X 2 root root 4096 Sep 19 06:28

ldr-xr-xr-x 13 root root @ Sep 29 01:40

drwxrwxrwt 13 root root 4096 Sep 29 03:41

idrwxr-xr-x 14 root root 4096 Sep 19 06:46

idrwxr-xr-x 11 root root 4096 Sep 19 06:28

LL rwx rwx rwx 1 root root 28 Sep 19 06:32 -> boot/

lvmlinuz-4.19.0-10-amd64

TL rwx rwx rwx 1 root root 27 Sep 19 06:29 -> b

oot/vmlinuz-4.19.0-8-amd64

/$ Hl

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 127:** Users & Permissions

SUID, SGID, & PATH

**Slides s. 128:** (Su SUID, SGID, & PATH

.

SUID (Set User ID)

A flag used to provide permissions

to run a file as its owner

— SGID (Set Group ID)

A flag used to provide permissions

i to run a file using group privileges

Lp ala

**Slides s. 129:** - bash: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

PATH is an environment

variable.

It instructs the shell to find

an executable path.

The shell follows the path

order from left to right.

Paths are separated with

colons (:).

**Slides s. 130:** SUID, SGID, & PATH

a Configure an SUID on one of the system’s binaries to

The Power of SUID enable a simple user to copy classified data.

15-25 Min. —

a « ® Copy classified content without SUID.

es a : ® Copy classified content with SUID.

a: =

" b NN ® e di

| : van ig ® VirtualBox ® Lab document

= & ON

, % ® Debian

{ ‘ ‘,

| 4 4 >

**Slides s. 131:** (Ex Links

O

® A soft link is like a shortcut in Windows.

@ The link is written to a different directory

than the one in which it is saved.

° ®@ Hard links are files that are saved to

the hard drive.

4 @ Any change ina hard link will cause a

= $ change in the soft link.

Lp ala

</details>
