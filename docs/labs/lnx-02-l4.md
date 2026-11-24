# LNX-02-L4 — Search

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 128–140.

## Cel, misja i środowisko

- G Lab Objective In this lab, you will learn new commands to search for data in text files. s Lab Mission Use search commands to locate files and find specific text within the files.
- s Lab Mission Use search commands to locate files and find specific text within the files. es 7 ©) Lab Duration
- ©) Lab Duration 15-20 minutes fe Requirements e Working knowledge of the CLI interface
- fe Requirements e Working knowledge of the CLI interface e Knowledge of finding and filtering information by using CLI commands os
- | Resources Environment and tools: © Debian environment from LNX-01-L3 ¢ Terminal

## Zadania / etapy

1. Lab Task 1: Search Content Learn about and practice using new commands to find files and information within them. 1. Open the terminal.
2. Lab Task 2: View Command History Learn how to view previously executed commands and how they can be erased. 1 View the contents listed by the history command and the .bash_history file by using cat .bash_history.
3. Lab Task 1: Searching Content Learn about and practice using new commands to find files and information within them. 1 Open the terminal.

## Komendy występujące w labie

```text
locate the results.
grep firefox /var/log/dpkg.log
john@debian :~$
find /bin/ -name *.sh 2>/dev/null
grep -rw password . --colorf
```

## Powiązana teoria

- [Find Locate](../02-cli/find-locate.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 128:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L4

I Search

o inn

olf

au

**PDF s. 129:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L4

I Search

o inn

olf

au

**PDF s. 130:** G Lab Objective

In this lab, you will learn new commands to search for data in text files.

s Lab Mission

Use search commands to locate files and find specific text within the files.

es 7

©) Lab Duration

15-20 minutes

fe Requirements

e Working knowledge of the CLI interface

e Knowledge of finding and filtering information by using CLI commands

os

| Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

¢ Text editors

**PDF s. 131:** Lab Task 1: Search Content

Learn about and practice using new commands to find files and information within

them.

1. Open the terminal.

2 Use the command find /var/ -name dpkg.log to locate the historical records of

the installation package called dpkg.log within the /var/ directory.

Note: The system displays permission denied messages, and it is difficult to

locate the results.

3 Now use the command find /var/ -name dpkg.log 2>/dev/null to redirect the

error messages and prevent them from being displayed.

4 Use the command grep firefox /var/log/dpkg.log to find the time that Firefox

was installed. Search for the line that contains the word installed.

5 Use the command find /bin/ -name *.sh 2>/dev/null to find how may .sh scripts

there are in the /bin directory.

6 Use the grep -rw password . --color command to find how many times the word

password appears in files located in your home directory.

Note: -r searches recursively, -w searches for an exact word, and --color paints

the result.

**PDF s. 132:** Lab Task 2: View Command History

Learn how to view previously executed commands and how they can be erased.

1 View the contents listed by the history command and the .bash_history file by

using cat .bash_history.

If you read the output, you will see that the .bash_history file is rather small and

only contains the first lines of the history command. History displays all

commands run only during the last session of the terminal (including those when

-bash_history was updated).

2 Tocompletely hide the history, you must run two commands:

e echo >.bash_history

e history -c

3 Verify that the history was erased.

**PDF s. 133:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS4

I Search

ona

a

**PDF s. 134:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS4

I Search

ona

a

**PDF s. 135:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

In this lab, you will learn new commands to search for data in text files.

5 Lab Mission

Use search commands to locate files and find specific text within the files.

es .

©) Lab Duration

15-20 minutes

tC) Requirements

e Working knowledge of the CLI interface

e Knowledge of finding and filtering information by using CLI commands

oo

| Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

© Text editors

**PDF s. 136:** Lab Task 1: Searching Content

Learn about and practice using new commands to find files and information within

them.

1 Open the terminal.

Activities Mon 04:23 dO

Q terminal a

@ (2) Terminator

E] Mare Terminat

©) somure

**PDF s. 137:** 2 Use the command find /var/ -name dpkg.log to locate the historical records of

the installation package called dpkg.log within the /var/ directory.

Note: The system displays permission denied messages, and it is difficult to

locate the results.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ find /var/ -name dpkq.log

find: ‘/var/spool/cups’: Permission denied

find: ‘/var/spool/cron/crontabs’: Permission denied

find: ‘/var/spool/rsyslog’: Permission denied

find: ‘/var/lib/fwupd/gnupg’: Permission denied

find: ‘/var/lib/udisks2’: Permission denied

find: ‘/var/lib/apt/lists/partial’: Permission denied

find: ‘/var/lib/gdm3/.config/gnome-session’: Permission denied

find: ‘/var/lib/gdm3/.config/ibus’: Permission denied

find: ‘/var/lib/gdm3/.config/pulse’: Permission denied

find: ‘/var/lib/gdm3/.cache/libgweather’: Permission denied

find: ‘/var/lib/gdm3/.gnupg’: Permission denied

find: ‘/var/lib/gdm3/.local/share/gnome-shell’: Permission deni

ed

3 Now use the command find /var/ -name dpkg.log 2>/dev/null to redirect the

error messages and prevent them from being displayed.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ find /var/ -name dpkg.log 2>/dev/null

/var/log/dpkg. log

:-$ ff

**PDF s. 138:** 4 Use the command grep firefox /var/log/dpkg.log to find the time that Firefox

was installed. Search for the line that contains the word installed.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ grep firefox /var/log/dpkg.log

2020-09-17 01:57:50 install firefox-esr:amd64 <none> 68.12.0esr|

-1~deb10ul

2020-09-17 01:57:50 status half-installed firefox-esr:amd64 68.

12.0esr-1~deb10u1

2020-09-17 01:57:55 status unpacked firefox-esr:amd64 68.12.0es

r-1~deb1l0ul

2020-09-17 02:00:58 configure firefox-esr:amd64 68.12.@esr-1~de

b10ul <none>

2020-09-17 02:00:58 status unpacked firefox-esr:amd64 68.12.0es

r-1~deb10ul1

2020-09-17 02:00:58 status half-configured firefox-esr:amd64 68

-12.Qesr-1~deb10ul

2020-09-17 02:00:58 status installed firefox-esr:amd64 68.12.0e

sr-1~deb10u1

john@debian :~$

5 Use the command find /bin/ -name *.sh 2>/dev/null to find how may .sh scripts

there are in the /bin directory.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ find /bin/ -name *.sh 2>/dev/null

/bin/gettext.sh

6 Use the grep -rw password. --color command to find how many times the word

password appears in files located in your home directory.

Note: -r searches recursively, -w searches for an exact word, and --color paints

the result.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ grep -rw password . --colorf

You should see that the word password appears around seven times.

**PDF s. 139:** Lab Task 2: View Command History

Learn how to view previously executed commands and how they can be erased.

1 View the contents listed by the history command and the .bash_history file by

using cat .bash_history.

If you read the output, you will see that the .bash_history file is rather small and

only contains the first lines of the history command. History displays all

commands run only during the last session of the terminal (including those when

-bash_history was updated).

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat .bash_history

shutdown

clear

poweroff

john@debian: ~ x

File Edit View Search Terminal Help

:~$ history

1 shutdown

2 clear

3 poweroff

4 halt

5 iclear

2 Tocompletely hide the history, you must run two commands:

e echo >.bash_history

e history -c

john@debian: ~ x

File Edit View Search Terminal Help

:~$ echo > .bash_history

:~$ history -c

$i

**PDF s. 140:** 3 Verify that the history was erased.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ echo > .bash_history

i~$ history -c

:~$ history

1 history

:~$ cat .bash_history

in$

</details>
