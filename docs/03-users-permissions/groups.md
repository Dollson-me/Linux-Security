# Groups & Membership

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 60–61; Linux Security.pdf, s. 113–117.

## Mapa wiedzy

- Groups simplify permission assignment to multiple users and are central to least-privilege administration.
- The course uses group creation/deletion, membership changes and inspection with commands such as `gpasswd`, `usermod -aG`, `groups` and `id`.
- Group ownership of files is managed together with user ownership and mode bits.

## Komendy / pliki / składnia występujące w materiale

```text
Usermod is a Linux command that adds existing users to existing groups. Two common
groups john
groupadd Employees
usermod -a -G Employees john
Groups
chown root:adm /var/log/boot.log
usermod -aG adm piotr
chown root:root /var/log/boot.log
gpasswd
gpasswd -d piotr adm
groups
```

## Notatki z zajęć (PadRiseup)

- `chown root:adm /var/log/boot.log`
- `usermod -aG adm piotr`
- `chown root:root /var/log/boot.log`
- `gpasswd`
- `gpasswd -d piotr adm`
- `groups`

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

**Textbook s. 60:** Section 6: Groups

Creating groups of users is done to simplify the application of settings and permissions.

Any user who belongs to a group will have the settings and permissions assigned to the

entire group.

Linux identifies groups by their Group Identification (GID), which is similar to UID for

users. Each GID value is unique, and group names are case sensitive. For example, a

group named staff and a group named Staff would be recognized as two different

groups.

Creating and deleting groups can be done with the groupadd and groupdel commands.

When a user is created during system installation, they are automatically assigned to a

standard group (unless defined as root). They are not added to any group other than

the standard group upon creation, unless specified during the user definition process.

Usermod is a Linux command that adds existing users to existing groups. Two common

flags are -a for append, and -G for groups.

The groups <username> command can be run to find out what groups a user belongs

to. The command groups johnd, may, for example, display johnd: root staff admins.

Jenn@debiare ~ 5

Fa SESE View RSearchil Terminal ely

root@debian:~# groups john

john : john cdrom floppy audio dip video plugdev netdev lLpadmin scanner

root@debian:~# groupadd Employees

root@debian:~# usermod -a -G Employees john

root@debian:~# groups john

john : john cdrom floppy audio dip video plugdev netdev lpadmin scanner

Emp Loyees

root@debian: ~#

The /etc/group file lists all users and the groups they are associated with. The file

displays several groups of characters, each separated with a colon. The first shows the

group name, and in most cases the second displays x, which stands for password

(/etc/shadow file), followed by the unique GID number, and users that are listed in the

group. If no users are listed in the group, the last section will be empty.

**Textbook s. 61:** John@debian: ~ =

Fae Ese ews Search Teal “Help

j :~$ tail -n 15 /etc/group

saned:x:116:

colord:x:117:

john:x:1000:

systemd-coredump:x:999:

rtkit:x:118:

Ess 1 Os

bluetooth: x:120:

pulse:x:121;

pulse-access:x:122:

geoclue:x:123:

Debian-gdm:x:124:

vboxsf :x:998:

jane:x:1001:

alice:x:1002:

Emp Loyees: x: 1003: john

es:

Besides the built-in groups and groups created after service installation, there is a group

called ‘sudo’ (superuser). Members of this group can add sudo in a command to obtain

high-level permissions for that particular command. Another way to use the sudo

command is by installing a sudo package and adding users to the related file that

configures the sudo users. The file can be found in /etc/sudoers after the package

installation.

To edit the sudoers file, you can use the visudo command or any text editor, but you

must have sudo permissions to view or edit the file.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 113:** Users and Permissions

Groups

**Slides s. 114:** (Gr Groups

e

@ Users are identified by UIDs.

@ Users can be added to groups.

imp ~ @ Groups are identified by GIDs.

“Sart, ®@ Groups apply permissions to all

Y aay included objects without exception.

Lp ala

**Slides s. 115:** Groups

(Creating & Deleting Groups

.

®@ Creating groups requires high-level

eo: permissions.

PS Ky) @ Group names must be unique.

f } ® Groups do not contain users upon

i f creation.

Use groupadd <name> to create a new group.

Use groupdel <group_name> to delete a group.

el

**Slides s. 116:** Groups

Activities G-) Terminal v Tue 03:56 2, @ Ov

johnd@debian: / x

File Edit View Search Terminal Help Use the usermod

netdev:x:109:emily

messagebus: x: 110: command to change or

ssl-cert:x:111:

ssh:x: 112: add a user group.

lpadmin:x:113:emily

scanner:x:114:saned,emily

avahi:x:115:

saned:x:116: The -a flag means append,

colord:x:117: .

linea: while -G means groups.

systemd-coredump:x:999:

rtkit:x:118: ;

tssix:119: The command consists

bluetooth:x:120: .

pulse: x:121: of two parts: The first

pulse-access:x:122:

geoclue:x:123: | argument is the group

Debian-gdm:x:124: -

a:x:1001: name. The second is the

test:x:1002:

class:x:1003:emily username.

teachers :x: 1004:

johnd: x: 1005: |

i :/$ usermod -a -G class johnd

From: ThriveDX

**Slides s. 117:** (Su Groups

Ve |

@ To add a user to a sudo group, edit

the /etc/sudoers file.

@ Sudoers contains a list of users with

high-level permissions.

F @ Another way to grant users sudo

° 9 permissions is to add them to the sudo

0.9 group.

as @ Sudo groups are built-in groups created

during the OS installation process.

By default, sudo group users have the same

permissions as root users.

Lp

</details>
