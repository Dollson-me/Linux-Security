# LNX-02-L1 — System Information

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 77–87.

## Cel, misja i środowisko

- G Lab Objective In this lab, you will learn more about the basic commands for getting information about the Linux operating system. s Lab Mission
- s Lab Mission Practice using text editors and web browsers to learn more about Linux operating system. Cs ss
- © Lab Duration 10-15 minutes tC) Requirements e Working knowledge of the CLI interface
- tC) Requirements e Working knowledge of the CLI interface Lt | Resources
- | Resources Environment and tools: ¢ Debian environment from LNX-01-L3 ¢ Terminal

## Komendy występujące w labie

```text
UNAME (1) User Commands UNAME (1) ij
uname - print system information
uname [OPTION]...
uname -s jj
uname -r
uname -a
whoami
w
who
ff
pwd I
fj
ps
Jj
ps -aux
```

## Powiązana teoria

- [Shells System Awareness](../02-cli/shells-system-awareness.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 77:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-L1

RO ibaa System Information

itl

**PDF s. 78:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-L1

RO ibaa System Information

itl

**PDF s. 79:** G Lab Objective

In this lab, you will learn more about the basic commands for getting information about

the Linux operating system.

s Lab Mission

Practice using text editors and web browsers to learn more about Linux operating

system.

Cs ss

© Lab Duration

10-15 minutes

tC) Requirements

e Working knowledge of the CLI interface

Lt

| Resources

Environment and tools:

¢ Debian environment from LNX-01-L3

¢ Terminal

¢ Web browser

**PDF s. 80:** Lab Task

Learn about and practice using command to find information about Linux operating

system.

1 Open the terminal.

2. From the terminal, use the command man uname to learn more about this

command.

3 Use the commands uname -s, uname -r and uname -a to find out more about

your operating system.

4 Use the commands whoami, who to check current users.

5 Use the command pwd to get information about current system location.

6 Use the command ps and ps -aux to list the currently running processes and their

PIDs.

**PDF s. 81:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS1

RO ibaa System Information

itl

**PDF s. 82:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS1

RO ibaa System Information

itl

**PDF s. 83:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

In this lab, you will learn more about the basic commands for getting information about

the Linux operating system.

5 Lab Mission

Practice using text editors and web browsers to learn more about Linux operating

system.

es .

©) Lab Duration

10-15 minutes

rt ) Requirements

e Working knowledge of the CLI interface

oo

| Resources

Environment and tools:

© Debian environment from LNX-01-L3

© Terminal

¢ Web browser

**PDF s. 84:** Lab Task

Learn about and practice using command to find information about Linux operating

system.

1. Open the terminal:

Activites Mon 04:23 Or

Q terminal a

ae” © terminatorX

E Mare Terminal

© soture

**PDF s. 85:** 2 From the terminal, use the command man uname to learn more about this

command.

>| Terminal - john@debian: ~ a —- ox

File Edit View Terminal Tabs Help

UNAME (1) User Commands UNAME (1) ij

NAME

uname - print system information

SYNOPSIS

uname [OPTION]...

DESCRIPTION

Print certain system information. With no OPTION, same as -s.

sa, --all

print all information, in the following order, except omit -p

and -i if unknown:

-s, --kernel-name

print the kernel name

-n, --nodename

print the network node hostname

-r, --kernel-release

print the kernel release

Manual page uname(1) line 1 (press h for help or g to quit) q

3 Use the commands uname -s, uname -r and uname -a to find out more about

your operating system.

> | Terminal - john@debian: ~ a — oO x

File Edit View Terminal Tabs Help

john@debian:~$ uname -s jj

Linux

john@debian:~$ uname -r

5.10.0-22-amd64

john@debian:~$ uname -a

Linux debian 5.10.0-22-amd64 #1 SMP Debian 5.10.178-3 (2023-04-22) x86_64 GNU

/Linux

**PDF s. 86:** 4 Use the commands whoami, w, who to check current users:

>. | Terminal - john@debian: ~ a - 9X

File Edit View Terminal Tabs Help

john@debian:~$ whoami

john

john@debian:~$ w

06:49:23 up 1:36, 1 user, load average: 0.00, 0.01, 0.00

USER TTY FROM LOGING IDLE JICPU PCPU WHAT

john tty7 70 05:50 1:36m 3.255 @.12s xfce4-sessio

john@debian:~$ who

john tty7 2023-07-01 05:50 (:0)

john@debian:~$ ff

5 Use the command pwd to get information about current system location:

& Terminal - john@debian: ~ a - ox

File Edit View Terminal Tabs Help

john@debian:~$ pwd I

/home/ john

john@debian:~$ fj

6 Use the command ps and ps -aux to list the currently running processes and their

PIDs:

> | Terminal - john@debian: ~ a. aX

File Edit View Terminal Tabs Help

john@debian:~$ ps

PID TTY TIME CMD

2306 pts/O 90:00:00 bash

2870 pts/O 90:00:00 ps

john@debian:~$ Jj

**PDF s. 87:** >. | Terminal - john@debian: ~ a — 8 x

File Edit View Terminal Tabs Help

john@debian:~$ ps -aux

USER PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND

root 1 0.0 0.2 99036 10988 ? Ss 05:12 0:01 /sbin/init

root 2 0.0 0.0 0 0? s 05:12 0:00 [kthreadd]

root 3 0.0 0.0 0 0? T< 05:12 0:00 [rcu_gp]

root 4 0.0 0.0 i) 0? I< 05:12 9:00 [rcu_par_g

root 6 0.0 0.0 io] 0? I< 05:12 0:00 [kworker/O

root 8 0.0 0.0 Q Qo? I< 05:12 @:00 [mm_percpu

root 9 0.0 0.0 0 0? Ss 05:12 @:00 [rcu_tasks

root 10 0.0 0.0 6 0? Ss 05:12 6:00 [rcu_tasks

root 11 0.60 6.0 6 0? Ss 05:12 0:00 [ksoftirqd

root 12 0.0 0.0 @ 0? ad 05:12 @:00 [rcu_sched

root 13 0.0 0.0 Q 0? Ss 05:12 @:00 [migration

root 15 0.60 0.0 0 0? 5 05:12 @:00 [cpuhp/0]

root 17. 0.60 0.0 0 0? Ss 05:12 0:00 [kdevtmpfs

root 18 0.0 0.0 0 0? I< 05:12 0:00 [netns]

root 19 0.0 0.0 0 0? s 05:12 0:00 [kauditd]

root 20 0.0 0.0 0 0? Ss 05:12 @:00 [khungtask

root 21 0.0 0.0 0 0? Ss 05:12 @:00 [oom_reape

root 22 0.0 0.0 Q 0? I< @5:12 @:00 [writeback

root 23 0.0 0.0 Q 0? Ss @5:12 0:00 [kcompactd

root 24 0.0 6.0 (3) 0? SN 05:12 6:00 [ksmd]

root 25 0.0 0.0 0 0? SN 05:12 0:00 [khugepage

root 43 0.0 0.0 Q 0? I< 05:12 @:00 [kintegrit

</details>
