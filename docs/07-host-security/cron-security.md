# Cron Security & Scheduled-Task Abuse

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 129–129; Linux Security.pdf, s. 295–298.

## Mapa wiedzy

- Cron jobs become escalation opportunities when a privileged scheduler executes files writable by less-privileged users.
- The lab demonstrates creating a recurring task and exploiting/protecting a cron-related weakness.
- Correct file ownership, permissions, absolute paths and trusted script locations are core mitigations.

## Komendy / pliki / składnia występujące w materiale

```text
Crontab Security
chmod +x VBoxLinuxAdditions.run
chown root:adm /var/log/boot.log
chmod 640 /var/log/boot.log
chmod 644 /var/log/boot.log
chown root:root /var/log/boot.log
chmod +x ping_sweep.sh
chmod +x backup.sh
crontab -e
echo "It works as $me" > /tmp/crontabout.txt
crontab -l
```

## Notatki z zajęć (PadRiseup)

- `chmod +x VBoxLinuxAdditions.run`
- `chown root:adm /var/log/boot.log`
- `chmod 640 /var/log/boot.log`
- `chmod 644 /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `chmod +x ping_sweep.sh`
- `chmod +x backup.sh`
- `crontab -e`
- `echo "It works as $me" > /tmp/crontabout.txt`
- `crontab -l`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-07-L3 — Cron Security Vulnerability](../labs/lnx-07-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 129:** I johnd@debian: ~/Desktop/LinEnum-master x

File Edit View Search Terminal Help

[-] Debug Info

Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-2+debl0ul (2019-09-20) x86_64 GNU/Lin

ux

Linux version 4.19.0-6-amd64 (debian-kernel@lists.debian.org) (gcc version 8.3.0 (Debia

In 8.3.0-6)) #1 SMP Debian 4.19.67-2+debl0ul (2019-09-20)

PRETTY NAME="Debian GNU/Linux 10 (buster)"

Pspy is a command-line tool that collects information about processes without the need

for root permissions. The information it gathers includes commands run by other users,

cron jobs, and more. The tool sets up inotify watchers that trigger procfs scans the

moment a process accesses the /usr folder.

Section 6: Extra - Crontab Security

Cron is a useful tool that provides the ability to automate and schedule tasks and

events. Crontab is a file in which cron jobs to be executed are listed. Manipulating the

file can potentially lead to a compromised system.

By examining the crontab file, an attacker can see which scripts are set to run and

change the scripts to perform malicious actions.

Extra Lab Assignment: LNX-07-L3 Cron Security Vulnerability

— Practice using the Crontab application, configure recurring tasks, and exploit

== =| Crontab vulnerabilities.

Follow the instructions in lab document LNX-07-L3.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 295:** Host Security

Extra:

Crontab Security

**Slides s. 296:** (Sc Crontab Security

Script Tasks

g ®@ Use scripts to maintain the domain or network.

®@ Scripts are taken from external resources or

ae “ctor

internal directories.

—_

a @ Using Bash scripts as automated tasks makes a

F 3 system administrator’s work easier.

— ®@ Attackers can use scripts for malicious purposes.

C1 . pe

Scripts can be edited, and lines can be injected in scripts

for maintenance purposes or as part of an attack.

Lp

**Slides s. 297:** (Ta: Crontab Security

— - ®@ PE can be achieved via crontab with scripts

that have Everyone permissions.

qT Pp @ Attackers can modify scripts run by crontab.

y @ Attackers can replace script files with malicious

files.

Cc % =

**Slides s. 298:** Crontab Security

Lab: LNX-07-L3 ie

{=o i Practice using the crontab application, configure

Extra: Cron Secu rity Vulnerabilit recurring tasks, and exploit crontab vulnerabilities.

20-30 Min.

&, ® Create a crontab task.

2 ; @ Protect document bypass.

- — —S n » * , ~ | ® Display vulnerability.

| ; = & me @ Crontab @ Lab document

Pes, »

| \ %,

‘ :

*

Nl > ry —— 7

</details>
