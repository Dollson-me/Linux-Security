# Crontab / Cron Automation

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 116–118; Linux Security.pdf, s. 251–258.

## Mapa wiedzy

- Cron schedules recurring commands or scripts. `crontab -e` edits a user’s schedule and `crontab -l` lists it.
- Cron is powerful for backups and maintenance but becomes a security risk when privileged jobs execute writable/untrusted scripts or rely on unsafe paths.
- The course emphasizes trusted scripts, correct permissions and avoiding tasks that require interactive passwords.

## Komendy / pliki / składnia występujące w materiale

```text
Crontab is a tool that stores tasks that are scheduled to be executed by cron, such as
Crontab Text Editor
Crontab Structure
Crontab Parameter Format
Bash Scripting
Crontab
id s > ae |
crontab -e
echo "It works as $me" > /tmp/crontabout.txt
crontab -l
```

## Notatki z zajęć (PadRiseup)

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

**Textbook s. 116:** Section 7: Extra: Crontab (Cron Table)

Crontab is a tool that stores tasks that are scheduled to be executed by cron, such as

running a routine script or restarting a machine.

Since Cron is popular among IT system administrators, it is often considered a

vulnerable target by hackers. If the default is not changed, the configuration will remain

the same, and it will be unprotected.

Crontab Text Editor

When Cron is started for the first time, you need to specify the text editor. The crontab

-e command will start the johnd crontab file.

:/$ crontab -e

no crontab for johnd - using an empty one

Select an editor. To change later, run 'select-editor'.

1. /bin/nano <---- easiest

2. /usr/bin/vim. tiny

Choose 1-2 [1]:

The default and recommended editor is Nano.

Crontab Structure

60 18 * * 2 /root/scripts/script.sh

The following is an explanation of the command above:

e The zeroes represent minutes, with a range of 0-59.

e The hour specified in the example is 6 PM, the range is 0-23.

e All days are specified in the example (*), the range is 1-31 days.

e All months are specified in the example (*), the range is 1-12 months, or the name

of the month.

**Textbook s. 117:** e Tuesday is specified as the third day of the week in the example (the count starts

at 0), the range is 0-6, or the names of the days.

e The file path navigates to the script for execution.

The example above sets a task to run a script every Tuesday at 18:00.

The same script is shown below in the Nano text editor.

SGNU nano 32

The example in Nano includes a description of how the command must be entered for

Cron to run it.

The crontab -! command can display the file to verify changes.

The following are additional examples:

Cron for every 2 minutes: * /2 * * * *

Cron for every 6 hours: * * /6 * * *

**Textbook s. 118:** Crontab Parameter Format

m-— minutes (0-59)

h—hours (0-23)

dom - day of month (1-31)

mon — month of year (0-11)

dow - day of week (0-6, 0 represents Sunday)

Command — the command chosen to be run

Dash — time range

Another tool, called at, is similar to Cron, but is typically used to create one-time

scheduled tasks in Linux. Cron is generally used for more periodic task scheduling, such

as daily, monthly, and yearly.

Lab Assignment: LNX-06-L4 Scripting for Security

— Use all learned commands to build a security script while learning how to

am think outside of the box.

Follow the instructions in lab document LNX-06-L4.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 251:** Bash Scripting

Extra: Crontab

**Slides s. 252:** (Cr Crontab

e Crontab is a tool that stores scheduled tasks for cron’s

: (1) execution.

| 4, e Cron tasks can only be run for users who created them,

j with the exception of a root user.

e Task settings are configured using commands.

e Croncan be edited (as a file) using any text editor.

Important cron flags include:

e: Edits the file

I: Lists tasks

r: Removes tasks

Q\ = “

**Slides s. 253:** Crontab

File Edit View Search Terminal Help

T /$ crontab -e

no crontab for johnd - using an empty one

Select an editor. To change later, run ‘select-editor'.

1. /bin/nano <---- easiest

2. /usr/bin/vim. tiny

Choose 1-2 [1]:

When cron is started for the first time, you need to specify the text editor.

**Slides s. 254:** (Cr Crontab

O

MIN HOUR DOM MON DOW CMD

@@ 18 * * 2 /root/scripts/script.sh

Command breakdown:

e The minutes equal zero.

e The hour specified is 6 p.m.

e All days in the month are specified.

e All months are specified.

e The day specified is Tuesday since it is the third day of the week (the count starts at 0).

e The system will navigate to the path of the script and execute it.

| The example above sets a task to run a script every Tuesday at 6 p.m.

47

**Slides s. 255:** Crontab

Crontab Structure

S

00 18 * * 2 /root/scripts/script.sh

This is the same script as the one

in the previous slide, but it is

shown here in the Nano text editor

with a description of how the

command must be entered for

cron to run it.

48

**Slides s. 256:** Crontab

Task Scheduling

| : 1-12

or name of the month

. day of |1-31 day of | 0-6 (O=Sunday)

0-59 minutes days of the month or name of the day

hp tis.

**Slides s. 257:** (Cr Crontab

Off

Use external scripts from Avoid using tasks that

trusted sources. require passwords.

Use the proper permissions in Run the task as a user utilizing

the script that cron runs. only the required privileges.

: Chain commands for fewer

Use allow-list users.

processes and less exposure.

(4) Disable root entry. Do not allow unusual tasks.

50

**Slides s. 258:** Crontab

Scripting for Secu rity Use all learned commands to build a security script

40, j while thinking outside the box.

30-40 Min. 3

ee \ : ¢ Create a log file and collect the logs.

~ 3 : e Filter the listening ports.

. See oy ¢ Print the changes in the listening ports.

Lv [ Y/ a

7 ¥ és NN 4 ® dt

P ; 4 a a ~~ I _ Cn, 2. Ty ols Palated Eilec

F » T =

| : we () @ r ° Bash ¢ Lab document

‘ e Text editor

| . % e Netstat

] & |

id s > ae |

</details>
