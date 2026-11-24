# Course Structure, Metadata & Legend

[← Indeks wiki](../index.md)

Ta strona przechowuje informacje organizacyjne i strukturę kursu, które nie należą do jednego tematu technicznego.

## Zakres kursu

Textbook opisuje kurs jako pełny materiał **Linux Security**, prowadzony chronologicznie od podstaw do zagadnień zaawansowanych. Legenda rozróżnia cztery typy bloków:

- **Lab Assignment** — ćwiczenie praktyczne / pytania,
- **Good to Know** — wiedza dodatkowa, wzbogacająca,
- **Tip** — wskazówka praktyczna,
- **More Information** — link lub źródło rozszerzające temat.

## Course Path

1. Introduction to Linux
2. CLI Fundamentals
3. Users & Permissions
4. Networking & System Management
5. Services & Hardening
6. Bash Scripting
7. Host Security
8. Network Security
9. Final Project / integracja wiedzy

## Pełny spis treści textbooka

### Chapter 1 — Introduction to Linux
- Linux History — s. 6
- Linux Distributions — s. 9
- Open-Source Philosophy — s. 12
- Linux Installation — s. 13
- System Libraries — s. 14
- Users — s. 16
- Command Line Interface — s. 17
- Terminal Emulator — s. 18

### Chapter 2 — CLI Fundamentals
- CLI & Terminal Emulators — s. 20
- Command Structure — s. 23
- File System Structure — s. 25
- Listing Files — s. 28
- Working with Files & Folders — s. 33
- Data Streams — s. 38
- Grep Basics — s. 43
- Find & Locate — s. 44
- History Command — s. 45

### Chapter 3 — Users & Permissions
- Piping — s. 46
- Advanced Grep & AWK — s. 48
- Additional Commands — s. 50
- Users — s. 55
- Password Management — s. 57
- Groups — s. 60
- Permissions — s. 62
- SUID, SGID, and PATH — s. 67

### Chapter 4 — Networking & System Management
- Network Testing Using Ping & Traceroute — s. 70
- Networking Files & Configuration — s. 71
- Updating and Upgrading — s. 75
- Apache — s. 78
- Other Applications — s. 81

### Chapter 5 — Services & Hardening
- Common Services and Protocols — s. 83
- SSH and SCP — s. 84
- FTP — s. 87
- Samba — s. 89
- Hardening — s. 92
- Bash Scripting — s. 94

### Chapter 6 — Bash Scripting
- Bash Scripting Introduction — s. 97
- Script Input & Output — s. 100
- Conditions — s. 102
- Arithmetic Operators — s. 108
- Archives — s. 110
- File Integrity — s. 113
- Extra: Crontab (Cron Table) — s. 116

### Chapter 7 — Host Security
- Linux External Mounting — s. 119
- Boot Protection — s. 120
- PAM — s. 121
- SELinux & AppArmor — s. 124
- Privilege Escalation — s. 127
- Extra: Crontab Security — s. 129

### Chapter 8 — Network Security
- iptables — s. 130
- firewalld — s. 132
- Fail2Ban (F2B) — s. 136
- Log Monitoring — s. 138
- Bash Scripting to Counter Apache Enumeration — s. 140
- Secure Apache Configuration — s. 143
- Banner Hiding for SSH & Apache — s. 144
- SSL Encryption — s. 146
- SFTP — s. 149

## PadRiseup — organizacja nauki

Materiały z zajęć podkreślają, że wiedza jest budowana warstwami. Zalecenia po każdych zajęciach:

1. powtórzyć cały materiał,
2. przejść ponownie przez laby,
3. przeczytać materiały dodatkowe,
4. uzupełnić zaległości i brakującą wiedzę,
5. zapisać niezrozumiałe tematy i wrócić z pytaniami.

Riseup jest opisany jako pomoc do prowadzenia zajęć, a nie zamiennik własnych notatek. Kurs był prowadzony w blokach 8-godzinnych. W wersji repo pominięto prywatny numer telefonu z sekcji kontaktowej; techniczne notatki i linki są zachowane w [Class Notes](class-notes.md).

<details>
<summary>Textbook — strony 1–5 (okładka, TOC, legenda; OCR)</summary>

**Textbook s. 1:** Cybersecurity Professional Program

Linux Security

Textbook

ae

Copyright © 1996-2020 HackerU Ltd.

All Rights Reserved.

**Textbook s. 2:** Table of Contents

SECTION 5: WORKING WITH FILES & FOLDERS. ..........::c::cceceeceeeceeeeeeeeeeeeeeeeeseesteetetseees 3

**Textbook s. 3:** CHAPTER 4: NETWORKING & SYSTEM MANAGEMENT ...........ssscssssssssesessesesseessseeseeees 10

SECTION 1: NETWORK TESTING USING PING & TRACEROUTE...........:eessseeseetteeeeee ZO

SECTION 2: NETWORKING FILES & CONFIGURATION .........csseeesseseseeeeteteetteeteetteeeeee ZL

SECTION 1: COMMON SERVICES AND PROTOCOLS ...........::ccccsssseeseeeseetsseeeeetereeees OS

SECTION 1: BASH SCRIPTING INTRODUCTION ............:cceesceesssseessesesseeesseesseeserseeserseeees OF

SECTION 7: EXTRA: CRONTAB (CRON TABLE) ..........:ssseeseesseseeeeseeeeeeteeteteteesterereeeeees £16

**Textbook s. 4:** SECTION 1: LINUX EXTERNAL MOUNTING... .cccsscesseeeseeesssesessesessetesssstsesessereseee LIQ

SECTION 5: BASH SCRIPTING TO COUNTER APACHE ENUMERATION................:.:.:. 140

SECTION 6: SECURE APACHE CONFIGURATION ...........::cccceessessseeseetesteeesstesseesseee LAB

SECTION 7: BANNER HIDING FOR SSH & APACHE..........:cesecesesseeeeeetereteeeseetteterteeeeees L4G

**Textbook s. 5:** | About this Textbook

This document is a textbook for the entire Linux Security course. It includes all the

information the lecturer will present in class.

The textbook proceeds through the entire course in chronological order, from the

beginning phase through the advanced material.

| Legend

Colored text blocks appear throughout this document to redirect the reader toa

specific source, or enrich them with additional information.

Colored text boxes include the following:

Lab Assignment

— Review the corresponding lab files to practice what has been taught so far.

mm This box may also include specific questions to practice.

® | Good to Know

Additional information or insight regarding a topic. This is for enrichment

purposes only and is not part of the exam materials.

vie Tip

= © * | Useful information that may help students study the material or work with

- specific tools.

@ More Information

) 1g Links or references to external material that can be used to expand one’s

knowledge on a subject.

</details>

<details>
<summary>Slajdy — strony sekcyjne, course path, objectives i „Questions?” pominięte przez strony tematyczne</summary>

**Slides s. 1:** Cybersecurity Professional Program

Introduction

to Linux

Linux Security

Copyright © 1996-2020 HackerU Ltd. All Rights Reserved.

**Slides s. 2:** Linux Security

Course Path

f

0

Introduction CLI Users & Networking

: . & System

To Linux Fundamentals Permissions

Management

a Host a Bash a Services &

Security Scripting Hardening

2

**Slides s. 3:** (Ok Introduction to Linux

Objectives

O G This lesson is an introduction to Linux-based operating

systems. The goal of the lesson is to understand what Linux

is and perform a basic installation of a Linux distribution.

e Linux History

e Linux Distributions

e Open-source philosophy

e Linux installation

e System libraries

e Users

e CLI interface

e Install Gnome as a DE

e Terminal emulator

3

**Slides s. 43:** Thank You

Questions?

**Slides s. 44:** Cybersecurity Professional Program

ae ae ee

Fundamentals

Linux Security

Copyright © 1996-2020 HackerU Ltd. All Rights Reserved.

**Slides s. 45:** (Co Linux Security

:

0

Introduction CLI Users & Networking

. i, & System

to Linux Fundamentals Permissions

Management

Network . i. Services &

2 [tse | [merce

5

**Slides s. 46:** (Ok CLI Fundamentals

Obtain a deeper understanding of how to work with Linux and

its tools, and how to execute commands in the terminal.

@ CLI & Terminal Emulators ® Data Streams

® Command Structure ® Grep Basics

®@ File System Structure ®@ Find and Locate

® Listing Files ® History Command

®@ Working with Files & Folders

3

**Slides s. 87:** Thank You

Questions?

**Slides s. 88:** Cybersecurity Professional Program

Users & Permissions

Linux Security

**Slides s. 89:** (Ca Linux Security

4

0

Introduction CLI Users & Nenvorking

. a & System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services &

Security Security Scripting Hardening

2

**Slides s. 90:** (Ok Users & Permissions

This module covers piping, redirections, operators, and

users in the Linux environment.

® Piping ® Password Management

® Advanced Grep & AWK ® Groups

® Additional Commands ® Permissions

@ Users @ SUID, SGID, & PATH

3

**Slides s. 132:** Thank You

Questions?

**Slides s. 133:** Cybersecurity Professional Program

Networking and

System Management

Linux Security

**Slides s. 134:** (Ca Linux Security

4

0

Introduction CLI Users and NE SMEIT

. . and System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services and

Security Security Scripting Hardening

2

**Slides s. 135:** (Ok Networking and System Management

This module covers all aspects of networking in Linux, including

services, common interfaces, configuration files, and logs.

® Network Testing Using Ping and Traceroute

® Networking Files and Configuration

® Updating and Upgrading

® Apache

® Other Applications

3

**Slides s. 172:** Thank You

Questions?

**Slides s. 173:** Cybersecurity Professional Program

Services and ©

Hardening

Linux Security

Copyright © 1996-2021 HackerU Ltd. All Rights Reserved.

**Slides s. 174:** (Co Linux Security

4

0

Introduction CLI Users and Nenwerking

. . and System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services and

Security Security Scripting Hardening

2

**Slides s. 175:** (Ok Services and Hardening

Become familiar with known services in a Linux environment,

understand the purposes and vulnerabilities of the services, and

learn how to close backdoors and weak spots.

® Common Services and @ Samba

Protocols @ Hardening

® SSH and SCP ® Bash Scripting

@ FTP

3

**Slides s. 207:** Thank You

Questions?

**Slides s. 208:** Cybersecurity Professional Program

Bash Scripting

Linux Security

**Slides s. 209:** (Co Linux Security

f

0

Introduction CLI Users & Networking

. a & System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services &

Security Security Scripting Hardening

2

**Slides s. 210:** (Ok Bash Scripting

Objectives

| Learn to automate processes using the Bash scripting language.

e Bash Scripting Introduction

e Script Input & Output

e Conditions

e Arithmetic Operators

e Archives

e File Integrity

e Crontab

3

**Slides s. 259:** Thank You

Questions?

**Slides s. 260:** Cybersecurity Professional Program

ee eee ee

e

Host Security

Linux Security

Copyright © 1996-2021 HackerU Ltd. All Rights Reserved.

**Slides s. 261:** (Co Linux Security

4

0

Introduction CLI Users & Nenwerking

. i. & System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services &

Security Security Scripting Hardening

2

**Slides s. 262:** (Ok Host Security

Acquire a better understanding of how to protect a

workstation from frequent attacks and how some

vulnerabilities are exploited.

®@ Linux External Mounting ©@ SELinux & AppArmor

® Boot Protection ® Privilege Escalation

@ PAM ® Crontab Security

3

**Slides s. 299:** Thank You

Questions?

**Slides s. 300:** Cybersecurity Professional Program

Network Security

Linux Security

Copyright © 1996-2020 HackerU Ltd. All Rights Reserved.

**Slides s. 301:** (Co Linux Security

f

O

Introduction CLI Users & Networking

. i, & System

to Linux Fundamentals Permissions

Management

Network a Host a Bash a Services &

Security Security Scripting Hardening

5

**Slides s. 302:** (Ok Network Security

This module focuses on network security, with topics such as

traffic control, network hardening, and security-related services.

® |ptables ® Secure Apache

@ Firewalld configuration

@ Fail2ban ® Banner hiding for

®@ Log monitoring SSH & Apache

® Bash scripting to counter Skee) Gnenypuel

Apache enumeration @ SFTP

3

**Slides s. 349:** Thank You

Questions?

</details>
