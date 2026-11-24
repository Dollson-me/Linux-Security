# Linux File Permissions & Ownership

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 62–66; Linux Security.pdf, s. 118–126.

## Mapa wiedzy

- Permissions are modeled for user/owner, group and others, with read (`r`=4), write (`w`=2) and execute (`x`=1).
- Numeric modes such as `640`, `644`, `755` and `777` are sums of these bits for the three classes.
- `chmod` changes mode bits; `chown` changes ownership. The course repeatedly checks permissions with `ls -l`/`ls -la`.
- Overly broad permissions are a recurring security problem, especially for scripts executed by privileged services or cron.

## Komendy / pliki / składnia występujące w materiale

```text
chmod
Read
Read and write (rw-) 6
Read and execute (r-x) 5
Read only (r--) 4
Groups and others can only execute.
Groups and others can only read and execute.
Groups and others can only read.
chown
Read and write (rw-) | | 6
Read and execute (r-x) | | 5
Read only (r--) | G | 4
chmod +x VBoxLinuxAdditions.run
chown root:adm /var/log/boot.log
chmod 640 /var/log/boot.log
chmod 644 /var/log/boot.log
chown root:root /var/log/boot.log
ls -la /usr/bin/passwd
chmod +x ping_sweep.sh
chmod +x backup.sh
```

## Notatki z zajęć (PadRiseup)

- `chmod +x VBoxLinuxAdditions.run`
- `chown root:adm /var/log/boot.log`
- `chmod 640 /var/log/boot.log`
- `chmod 644 /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `ls -la /usr/bin/passwd`
- `chmod +x ping_sweep.sh`
- `chmod +x backup.sh`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L3 — Group Management](../labs/lnx-03-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 62:** GNU nano 4.9.2 fetc/s

Defaults env_reset

Defaults mail_badpass

Defaults secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin: /usr/bin: /sbin: /bin*

root ALL=(ALL:ALL) ALL

%sudo ALL=(ALL:ALL) ALL

Section 7: Permissions

There are three main file permissions (for non-owners): read, write, and execute.

Permissions will appear in the terminal as -rwxrwxrwx, and can vary among owners,

groups, and users.

Typically, the root user is the only one who has the permissions to work with system

configuration files.

chmod

Permissions for a file are set with the chmod command using numerical input (such as

777 for full permissions), or r/w/x.

Permissions Classes

Read

User

Group Write

Sinet Execute

drwxrwxrwx rwx

File Type

**Textbook s. 63:** The letters determine the permissions of read, write, and execute for a file, and the

format is divided into the following parts:

1. The first three characters are the file permissions that apply to the creator

(owner) of the file.

2. The next three characters determine the group permissions.

3. The last three characters represent ‘other’ or ‘public’.

Numerical values can also be applied:

e 4: Read only

e 2: Write only

e 1: Execute only

For numbers higher than three, you add the permissions together to get the final

permission.

Examples:

e@ Read and Execute =4+1=5

e Read and Write=4+2=6

e Read, Write, and Execute=1+2+4=7

Letter Numeric

Values Equivalent

Read, write, and execute (rwx) 7

Read and write (rw-) 6

Read and execute (r-x) 5

Read only (r--) 4

Write and execute (-wx) 3

Write only (-w-) 2

Execute only (--x) 1

**Textbook s. 64:** © | Good to Know

The method of representation may seem counterintuitive at first, but it is

like that because the representations are of “octal permissions”. For more

information, see: https://docs.nersc.gov/filesystems/unix-file-permissions/

Setting permissions with the numerical format requires three numbers, one for each

permission section: owner, group, and public. For example, chmod 777 <file name>

grants full permissions for anyone to use the file.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ chmod 777 file.txt

i~$ ls -1

total 32

drwxr-xr-x 2 john john 4096 Sep 19 06:50

drwxr-xr-x 3 john john 4096 Sep 29 01:37

drwxr-xr-x 2 john john 4096 Sep 19 06:50

-rwxrwxrwx 1 john john © Sep 29 01:47

idrwxr-xr-x 5 john john 4096 Sep 19 08:21

drwxr-xr-x 2 john john 4096 Sep 19 06:50

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

drwxr-xr-x 2 john john 4096 Sep 19 06:50

i$ 4H

The second method, known as UGO, is to specify the entity and the permission using

letters. Each section has a representative letter:

User—u

Group -g

Other—o

**Textbook s. 65:** The chmod command can use this method with a plus sign (+) for addition, minus sign

(-) for removal, and an equals sign (=) to apply a permission.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ chmod ugo=rw file. txt

i~$ Is -1

total 32

ldrwxr-xr-x 2 john john 4096 Sep 19 06:50

idrwxr-xr-x 3 john john 4096 Sep 29 01:37

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

-rw-rw-rw- 1 john john 0 Sep 29 01:47 file.txt

idrwxr-xr-x 5 john john 4096 Sep 19 08:21

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

ldrwxr-xr-x 2 john john 4096 Sep 19 06:50

idrwxr-xr-x 2 john john 4096 Sep 19 06:50

i$ fl

Common File Permissions

-rwxrwxrwXx 777 Anyone can read, write, and execute.

-rw-rw-rw- 666 Anyone can read and write.

Users can read, write, and execute.

-TWX--X--X 711

Groups and others can only execute.

Users can read, write, and execute.

-fWXr-xr-X 755

Groups and others can only read and execute.

-FWX------ 700 Only users can read, write, and execute.

Users can read and write.

-fW-r--r-- 644

Groups and others can only read.

-1W---=--- 600 Only the user can read and write.

**Textbook s. 66:** File & Directory Ownership

Every file and directory in the system has a user owner and a group. The owner can be

identified by the first name that appears after the permission, and the group is the

second name.

Blue —user

Orange — group

john@debian: ~ x

File Edit View Search Terminal Help

:~-$ ls -l

total 32

-rw-r--r-- 1 }john}ijohn Q Sep 22 06:53 accounts.txt

drwxr-xr-x 2 |john||john|4096 Sep 22 04:36

drwxr-xr-x 3 |john||john|4096 Sep 17 03:40

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06

-rw-r--r-- 1 ]john}ijohn © Sep 22 06:53 file.txt

drwxr-xr-x 2 {john||john|4096 Sep 17 02:06

drwxr-xr-x 2 |john||john|4096 Sep 21 02:36

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06

-rw-r--r-- 1 }john}}john © Sep 22 06:53 work.txt

chown

The file owner and group can be changed using the chown command. By changing the

owner or the group of the file or directory, the permissions will be applied to the

specified entity.

For example: chown <user>:<group> <file name>

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 118:** Users & Permissions

Permissions

**Slides s. 119:** (Fil Permissions

O

®@ Files have three main action permissions:

read, write, and execute.

@ Permissions can be different for users, file

owners, and groups.

Root typically is the only user that has

permission to work with configuration files.

Cc % = .

**Slides s. 120:** Permissions

File Edit View Search Terminal Help

:~$ chmod 777 file.txt

Setting permissions is

done using the chmod

command.

The number in the

command represents

the permission level.

From: ThriveDX

**Slides s. 121:** (UC Permissions

UGO vs. Numeric

'

faa UGO Numeric

Read, write, and execute (rwx) | | 7

Read and write (rw-) | | 6

Read and execute (r-x) | | 5

Read only (r--) | G | 4

Write and execute (-wx) | | 3

Write only (-w-) | | 2

Execute only (--x) | | 1

34

**Slides s. 122:** Permissions

john@debian: ~ x

File Edit View Search Terminal Help

:~$ Ls -l

The first three letters total 32

(orange) are user -[fw-|r--r-- 1 john john © Sep 22 06:53 accounts.txt

permissions. drwxXr-xr-x 2 john john 4096 Sep 22 04:36 Desktop

COnthiacceee co rwxr-xr-x 3 john john 4096 Sep 17 03:40 Documents

(blue) are group drwxr-xr-x 2 john john 4096 Sep 17 02:06 Downloads

permissions. -rw-r--r-- 1 john john ® Sep 22 06:53 file.txt

“tive Sind @hrexilesffers drwxr-xr-x 2 john john 4096 Sep 17 02:06 Music

_ drwxr-xr-x 2 john john 4096 Sep 21 02:36 Pictures

(purple) are permissions : é x

for everyone else. drwxr-xr-x 2 john john 4096 Sep 17 02:06 Public

drwxr-xr-x 2 john john 4096 Sep 17 02:06 Templates

drwxr-xr-x 2 john john 4096 Sep 17 02:06 Videos

-rw-r--r-- 1 john john ® Sep 22 06:53 work.txt

**Slides s. 123:** Permissions . . .

(Common File Permissions

3g

fan UGO Numeric

-rwxrwxrwx | | 777

-rW-rw-rw- | | 666

-WX--X--X | | 711

Wie | | 700

-fW-l--r-- | | 644

-1W------- | | 600

36

**Slides s. 124:** Permissions

john@debian: ~ x

File Edit View Search Terminal Help

i~$ ls -l

total 32

The first column (blue) -rw-r--r-- 1 |john||john 0 Sep 22 06:53 accounts.txt

refers to the object’s drwxr-xr-x 2 |john||john|}4096 Sep 22 04:36 Desktop

owner. drwxr-xr-x 3 |john||john}4096 Sep 17 03:40 Documents

Theeessnd salar drwxr-xr-x 2 john john 4096 Sep 17 02:06 Downloads

farengahoetentiatthe -rw-r--r-- 1 john john 0 Sep 22 06:53 file.txt

group to which the drwxr-xr-x 2 |john||john|}4096 Sep 17 02:06 Music

object belongs. drwxr-xr-x 2 |john}!john|4096 Sep 21 02:36 Pictures

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06 Public

drwxr-xr-x 2 |john||john|}4096 Sep 17 02:06 Templates

drwxr-xr-x 2 |john||john|4096 Sep 17 02:06 Videos

-rw-r--r-- 1 |john}}john 0 Sep 22 06:53 work.txt

**Slides s. 125:** Permissions

john@debian: ~ x

File Edit View Search Terminal Help

:~$ chown jane:jane file.txtf

From: ThriveDX

Setting permissions is done using the chown command.

The first name is for the user, while the second name is for the group.

**Slides s. 126:** Permissions

—_—_—S aos Practice group management and changing file

Group Management permissions.

15-20 Min. —

ee ¢ ; @ Check group permissions.

__ a ‘ ® Restrict user actions via group

ie, Lg Sg

=a o permissions.

>»

i b NN s e yr

| . ma a ® VirtualBox ® Lab document

; ® Debian

7 a ® Text editors

i 4 . S |

s Pi .

3; —a

</details>
