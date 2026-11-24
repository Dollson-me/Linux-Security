# User Management

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 55–56; Linux Security.pdf, s. 104–107.

## Mapa wiedzy

- Linux user management involves account creation/deletion, UID/GID information, home directories, shells and privilege boundaries.
- Account information is distributed across files such as `/etc/passwd` and `/etc/shadow`; the latter contains password-related data and requires elevated privilege.
- The material uses `adduser`/`useradd`, `deluser`, `usermod`, `id` and related commands.

## Komendy / pliki / składnia występujące w materiale

```text
adduser jane
which must be created separately.
useradd alice
root@debian :~#
adduser
useradd
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
cp /etc/shadow
for i in {5..7}; do deluser tempuser$i;done
usermod -aG adm piotr
usermod -a -G sudo piotr
sudo cat /etc/shadow
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `cp /etc/shadow`
- `for i in {5..7}; do deluser tempuser$i;done`
- `usermod -aG adm piotr`
- `usermod -a -G sudo piotr`
- `sudo cat /etc/shadow`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L2 — Creating Users](../labs/lnx-03-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 55:** Section 4: Users

User Types

Linux uses groups to manage users and set access permissions. User account types in

Linux can be personal accounts or the root account. The root account is a superuser

that has complete access to the operating system, including making changes and

managing other users.

As a best practice, the root user should not be able to log in to the OS freely, but should

do so using the sudo command, which allows switching to root-level access when

changes are necessary.

Linux is a multi-user system based on the UNIX concepts of file ownership and

permissions. Security begins at the file system level, whereby a file or directory owner

can restrict access based on whether or not a user requires it. This method helps build a

control scheme with varying levels of access for different users.

From a security perspective, regular users typically perform daily routine-like

operations. An attacker’s interest will be to obtain higher level permissions for

unrestricted and unlimited command execution, which the root user has. Not every

command that the root user can run can be executed by a regular user. For example,

the root user can access all other user accounts.

A regular user can be configured as a 'sudoer' which grants the privilege to execute

commands with root permission via the sudo command.

Creating & Deleting Users

During the installation of a Debian environment, the creation of a regular user account

is required. Only the root user can create and delete other users, and each user should

have a unique login name.

Two commands can be used to create a new user, adduser and useradd. The difference

between them is that adduser does not require additional information because it uses

the value specified in the command and default information from the operating system.

**Textbook s. 56:** For example:

john@debian: ~ x“ j

File Edit View Search Terminal Help

root@debian:~# adduser jane

Adding user ‘jane' ...

Adding new group ‘jane' (1001) ...

Adding new user ‘jane’ (1001) with group ‘jane’ ...

Creating home directory */home/jane' ...

Copying files from “/etc/skel' ...

New password:

Retype new password:

passwd: password updated successfully

Changing the user information for jane

Enter the new value, or press ENTER for the default

Full Name []:

Room Number []:

Work Phone []:

Home Phone []:

Other []:

Is the information correct? [Y/n] Y

root@debian:~#

The useradd command simply creates a user account, which is specified directly

following the command. The user is created without a password and home directory,

which must be created separately.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# useradd alice

root@debian :~#

/etc/skel

This is a directory that is used as a template for a new user's home directory.

Every file or directory created within it, will appear in the new user's home

directory.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 104:** Users & Permissions

Users

**Slides s. 105:** (Us Users

Cg

(,) Regular users do not have permission

to run system-related actions. “

Regular users configured as sudoers can use

oe, the sudo command to acquire privileges to

vis, run otherwise prohibited commands.

‘Se Root users have the highest permissions

cad and can run any action.

ee

**Slides s. 106:** (Cr Users

O

adduser

'®&®: Creates a user and sets its password and home

a | folder based on the content of /etc/skel

useradd

Creates a user without a password, which must

be set manually

| Use the command deluser to delete a user.

Lp ala

**Slides s. 107:** (/e Users

O

a ~ y ®@ Atemplate directory for new users

— ®@ |t contains several files and directories.

@ New users inherit them in their home

directories.

Cc % =

</details>
