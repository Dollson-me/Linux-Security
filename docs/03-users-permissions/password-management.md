# Password Management & Policy

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 57–59; Linux Security.pdf, s. 108–112.

## Mapa wiedzy

- Password security includes setting/changing passwords, password aging and complexity policy.
- The course discusses `/etc/shadow`, `passwd`, PAM-related password quality configuration and the risks of weak/reused passwords.
- Class notes install `cracklib-runtime` and `libpam-pwquality` and edit PAM/common-password configuration for stronger policy.

## Komendy / pliki / składnia występujące w materiale

```text
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
vim /etc/quality/pwquality.conf
gpasswd
gpasswd -d piotr adm
ls -la /usr/bin/passwd
sudo apt install cracklib-runtime
sudo apt install libpam-pwquality
sudo vim /etc/pam.d/common-password
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `vim /etc/quality/pwquality.conf`
- `gpasswd`
- `gpasswd -d piotr adm`
- `ls -la /usr/bin/passwd`
- `sudo apt install cracklib-runtime`
- `sudo apt install libpam-pwquality`
- `sudo vim /etc/pam.d/common-password`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L2 — Creating Users](../labs/lnx-03-l2.md)
- [LNX-07-L2 — PAM Authentication Features](../labs/lnx-07-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 57:** Section 5: Password Management

The computing world has grown and developed over the years. In the earliest stages,

computers communicated through wires and carried one-way transmissions. Today’s

technology allows us to manage interfaces remotely and there is a management panel

for almost every device. As communication has increased in sophistication, people have

developed new ways to overcome security and leverage hacking techniques.

Hackers are always seeking to breach security with an administrator or root password.

In some cases, users are unaware of the importance of security measures, and in other

cases vulnerabilities exist due to programs or technological misconfigurations. To

effectively protect logins, a password must be complex enough so that it cannot be

guessed or cracked. The longer and more complex a password is, the harder it will be

for automated tools to crack it.

Such tools, however, can run through possible passwords and combinations faster than

humans can count, and will eventually guess the password if no security settings are

established to block them after a predetermined number of attempts. Passwords

should be changed every few months in accordance with a security policy that regulates

parameters such as password length.

Note that passwords of users who are not security-minded often include personal

information because it is easier to remember, and the first thing that comes to mind

when the password definition field appears. If a hacker has a person’s name, they can

access that person’s social media accounts, and see the date of birth and names of

family members.

Sometimes, a person’s previously used passwords can be easy to guess. Choosing a new

password that is significantly different from the current and previous passwords (not

just changing a single character) will ensure a higher level of security.

There are specially designed applications with databases that generate secure

passwords, such as KeePass, 1Password, SysPass, and LastPass. These are good

solutions for users who constantly forget their passwords, or who wish to have more

complex and randomly-generated passwords.

**Textbook s. 58:** Other consideration include keeping the password to yourself, not writing it down, and

avoid using common passwords (such as qwerty or 123456). A list of common

passwords can be downloaded from Google, and those are often the first passwords a

hacker tries when attempting to log in to another user’s account.

Login.defs

The login.defs file is located in the /etc directory and is responsible for retaining

password management information. This file contains configurations designating the

maximum length of passwords, password expiry periods, the generation of prompts to

change passwords that will soon expire, and more.

The file is referenced when a password is set using passwd, and does not depend on

other applications that require a password, such as SSH, Apache, and others.

Users & Passwords

Examples of files that need to be protected are shadow and passwd. They contain hash

and plain text passwords and users that exist in a system, and hackers often try to gain

access to those files.

The /etc/shadow file contains passwords for each user encrypted with one-way keys.

The /etc/passwd file includes a list of all users in the system.

Every user in the system has a unique user identifier (UID). The UID value is used for

identification and to define which system resources a user can access. New users

created in the system begin with UID 1000, while the root user has the value 0.

**Textbook s. 59:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/passwd

ffoot:x:0:0:root:/root:/bin/bash

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin

bin:x:2;:2:bin:/bin:/usr/sbin/nologin

sysixi3:3:sys:/dev:/usr/sbin/nologin

sync:X:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man:x:6;12:man:/var/cache/man:/usr/sbin/nologin

Lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news :X:9:9:news:/var/spooL/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp: /usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

Wwww-data:x:33:33:www-data:/var/www: /usr/sbin/nologin

backup:x:34:34:backup:/var/backups: /usr/sbin/nologin

List:x:38:38:Mailing List Manager:/var/List:/usr/sbin/nolog$

dnsmasq:x:106:65534;:dnsmasq,,,:/var/lib/misc: /usr/sbin/nolo$

usbmux:x:107:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/$

rtkit:x:108:113:RealtimeKit,,,:/proc:/usr/sbin/nologin

pulse:x:109;:116;:PulseAudio daemon,,,:/var/run/pulse:/usr/sb$

speech-dispatcher:x:110:29:Speech Dispatcher,,,:/var/run/sp$

avahi:x:111:118:Avahi mDNS daemon,,,:/var/run/avahi-daemon:$

saned:x:112:119::/var/lib/saned:/usr/sbin/nologin

folord:x:113:120:colord colour management daemon,,,:/var/li$

geoclue:x:114:121::/var/lib/geoclue:/usr/sbin/nologin

Debian-gdm:x:115:122:Gnome Display Manager: /var/lib/gdm3:/b$

john:x:1000:1000:John Doe,,,:/home/john:/bin/bash

systemd-coredump:x:999:999;:systemd Core Dumper:/:/usr/sbin/$

whoxadd:x:998:1::/var/run/vboxadd: /bin/false

Get Help Write oe Where Is a Cut Text Justify

is Exit i Read Filega}] Replace gj Uncut Texgy To Spell

Lab Assignment: LNX-03-L2 Creating Users

— Create new users and configure customized home directories and password

am policies.

Follow the instructions in lab document LNX-03-L2.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 108:** Users & Permissions

Password Management

**Slides s. 109:** (Sti Password Management

O6

Avoid using one password

Password length or

for all applications.

Do not include personal Don’t write a password

information. on paper. Memorize it.

Password history Keep the password

to yourself.

A combination of lowercase Avoid using common

and uppercase letters, passwords.

numbers, and special symbols

22

**Slides s. 110:** (pa Password Management

e

®@ pam.d controls user password policy.

®@ Itis activated during the useradd stage.

®@ Other utilities get default values from

the file.

| The file is in the fete directory. &-

Cc % = .

**Slides s. 111:** (Us Password Management

etc/shadow

A file with local user passwords that are encrypted

with special Linux encryption or hashed

/etc/passwd

A file that contains user information without

passwords and is displayed in plain text format

Every user has a user identifier (UID) for

resource access.

Lp

**Slides s. 112:** Password Management

SO a Create new users and configure customized home

Creating Users directories and password policies.

15-20 Min.

. > | FF @ Create users.

Si 2 : ® Seta minimum password length.

oe eae i ..

ae EP \ * ~ ,

i |@fFRE-

| : = ® i ® VirtualBox ®@ Lab document

’ %, ® Debian

. :

‘ .

.)

‘ a |

</details>
