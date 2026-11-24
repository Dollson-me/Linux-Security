# LNX-06-L4 — Scripting for Security

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 385–398.

## Cel, misja i środowisko

- G Lab Objective Use all learned commands to build a security script, while learning how to think outside the box. be Lab Mission
- be Lab Mission Design a script that checks for open ports listening on the machine. CQ . © Lab Duration
- © Lab Duration 30-40 minutes rt ) Requirements e Knowledge of hashing.
- rt ) Requirements e Knowledge of hashing. e Practical knowledge of Bash operators and variables. e Practical knowledge of piping.
- [ea] Resources ¢ Environment & Tools o VirtualBox = Debian VM

## Zadania / etapy

1. Lab Task1: Write a Script that Checks for Listening Ports At the mitigation stage, during a current ongoing breach in your organization, you need to take action until the developers troubleshoot the attacked website. Write a script that checks the listening ports, and notifies when new ports are added to

## Komendy występujące w labie

```text
chmod +x CheckPortListen.sh
nano CheckPortListen.sh
[ff
netstat -1 LISTEN v unix
./CheckPortListen.sh
ff
nc -lv
fj
apt update
apt install cron
```

## Powiązana teoria

- [Conditions](../06-bash/conditions.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 385:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L4

Scripting for Securi

ona pting ty

Ooln

Ee

All Rights Reserved.

**PDF s. 386:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L4

Scripting for Securi

ona pting ty

Ooln

Ee

All Rights Reserved.

**PDF s. 387:** G Lab Objective

Use all learned commands to build a security script, while learning how to think outside

the box.

be Lab Mission

Design a script that checks for open ports listening on the machine.

CQ .

© Lab Duration

30-40 minutes

rt ) Requirements

e Knowledge of hashing.

e Practical knowledge of Bash operators and variables.

e Practical knowledge of piping.

e Knowledge of how to create Crontab tasks.

Lt

[ea] Resources

¢ Environment & Tools

o VirtualBox

= Debian VM

o Bash

o Text editor

o Netstat

o Cron

**PDF s. 388:** Lab Task1: Write a Script that Checks for Listening Ports

At the mitigation stage, during a current ongoing breach in your organization, you need

to take action until the developers troubleshoot the attacked website.

Write a script that checks the listening ports, and notifies when new ports are added to

the listening list.

1. Make sure that you are logged in as the root user with the command su -.

Then create a file for the script using nano and name it CheckPortListen.sh.

2 Define a new variable logFile for the file path /var/log/openPorts, which will be

used later on to save a report about open ports.

Remember: Capitalization matters in scripting, since it is case-sensitive.

3 Write an if-then statement that uses netstat and grep to create a new log file in

the previously defined /var/log/openPorts path, if one does not exist. It should

contain only the tcp and tcp 6 listening ports.

4 Define two new variables that will use md5 to hash the original log file and

current netstat log, and use cat, grep and echo to filter and print only the

required information and hashes.

5 Write an if-then statement that compares the two variables from step 4, and

prints whether or not the list of open ports changed. If the list changed, the if-

then statement should also print the current list of open ports.

6 Grant the CheckPortListen.sh script execute permission with the command

chmod +x CheckPortListen.sh

7 ‘Next, run it for the first time to build the baseline.

8 Use another terminal tab and create another port listener with the nc tool, using

the command nc with the -I flag which opens the port in the workstation.

For example: nc -Ilv

**PDF s. 389:** This command uses the netcat tool to open a random port on the local

workstation. The -v (verbose) flag is used to view what netcat is doing.

Note: You will learn later in the program about netcat.

9 Rerun the script while the port listener used in step 7 is active, to check if the

port listing changed. Use the following command: ./CheckPortListen.sh

10 Is there any change in the output?

The output changed since the port listing changed.

**PDF s. 390:** Task 2 (Extra): Combine Crontab with the Script

Note: Perform this extra task only if you reviewed the extra crontab material with the

instructor.

1 Install the Crontab tool by first using the apt update command.

Then run apt install cron.

2 Use the crontab -e command, and select the nano text editor to create a routine

process that will run the CheckPortListen.sh script every five minutes.

**PDF s. 391:** Linux Security

Lab Assignment Bash Scripting

& Solution iNmneiea

Scripting for Securi

ona pting ty

Ooln

EI

All Rights Reserved.

**PDF s. 392:** Linux Security

Lab Assignment Bash Scripting

& Solution iNmneiea

Scripting for Securi

ona pting ty

Ooln

EI

All Rights Reserved.

**PDF s. 393:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Use all learned commands to build a security script, while learning how to think outside

the box.

5) Lab Mission

Design a script that checks for open ports listening on the machine.

CN) a

@ Lab Duration

30-40 minutes

fe Requirements

¢ Knowledge of hashing.

e Practical knowledge of Bash operators and variables.

e Practical knowledge of piping.

¢ Knowledge of how to create Crontab tasks.

Lt

[ea] Resources

¢ Environment & Tools

o VirtualBox

= Debian VM

o Bash

o Text editor

o Netstat

o Cron

**PDF s. 394:** Lab Task1: Write a Script that Checks for Listening Ports

At the mitigation stage, during a current ongoing breach in your organization, you need

to take action until the developers troubleshoot the attacked website.

Write a script that checks the listening ports, and notifies when new ports are added to

the listening list.

1. Make sure that you are logged in as the root user with the command su -.

Then create a file for the script using nano and name it CheckPortListen.sh.

root@debian:~# nano CheckPortListen.sh

root@debian:~# [ff

2 Define a new variable logFile for the file path /var/log/openPorts, which will be

used later on to save a report about open ports.

Remember: Capitalization matters in scripting, since it is case-sensitive.

3 Write an if-then statement that uses netstat and grep to create a new log file in

the previously defined /var/log/openPorts path, if one does not exist. It should

contain only the tcp and tcp 6 listening ports.

4 Define two new variables that will use md5 to hash the original log file and

current netstat log, and use cat, grep and echo to filter and print only the

required information and hashes.

orgHash=s(md5sum -t Ted

newHash netstat LISTEN -v unix mdSsum -fl ae

**PDF s. 395:** 5 Write an if-then statement that compares the two variables from step 4, and

prints whether or not the list of open ports changed. If the list changed, the if-

then statement should also print the current list of open ports.

$orgHash $newHash

“[-] There are changes in ports, this is the new port lists: "

netstat -1 LISTEN v unix

“[+] The port lists hasn't changed"

O

6 Grant the CheckPortListen.sh script execute permission with the command

chmod +x CheckPortListen.sh

7 Next, run it for the first time to build the baseline.

root@debian:~# ./CheckPortListen.sh

[+] The original hash is: 5bebee044167eae16572b6f85b07417e

[+] The new hash is: b346a20524332723e9b57caac3c5b8f1

[-] The following changes have occured:

tcp 0 ® localhost:ipp 0.0.0.0:* LIs

TEN

tcp 0 © 0.0.0.0:1337 O2OL0505* LIS

TEN

tcp6 0 ® localhost:ipp [asl LIS

TEN

tcp6 () © [::]:1337 [rs]: LIS

TEN

tcp6 ic} 0 [::]:http (ede: LIS

TEN

root@debian:~# ff

8 Use another terminal tab and create another port listener with the nc tool, using

the command ne with the -I flag which opens the port in the workstation.

For example: nc -Ilv

johnd@debian:~$ nc -lv

listening on [any] 33963 ...

This command uses the netcat tool to open a random port on the local

workstation. The -v (verbose) flag is used to view what netcat is doing.

Note: You will learn later in the program about netcat.

**PDF s. 396:** 9 Rerun the script while the port listener used in step 7 is active, to check if the

port listing changed. Use the following command: ./CheckPortListen.sh

10 Is there any change in the output?

The output changed since the port listing changed.

root@debian:~# ./CheckPortListen.sh

[+] The original hash is: 5bebee044167eae16572b6f85b07417e

[+] The new hash is: 623c9e190543051e3c35e4621c3e591c

[-] The following changes have occured:

tcp 6 © localhost: ipp 0.0.0.0:* LIS

TEN

tcp 6 © 0.0.0.0:1337 0.0.0.0:* LIS

TEN

tcp () © 0.0.0.0:44875 0.0.0.0:% LIS

TEN

tcp6 0 © localhost: ipp egies? LIs

TEN

tcp6 @ © [::]:1337 ileeile LIS

TEN

tcp6 6 @ [::]:http [issiie LIS

TEN

root@debian:~# fj

**PDF s. 397:** Task 2 (Extra): Combine Crontab with the Script

Note: Perform this extra task only if you reviewed the extra crontab material with the

instructor.

1 Install the Crontab tool by first using the apt update command.

root@debian:~# apt update

Hit:1 http://security.debian.org/debian-security buster/updates InRelea

se

Hit:2 http://deb.debian.org/debian buster InRelease

IHit:4 http://deb.debian.org/debian buster-updates InRelease

Hit:3 https://mirror.karneval.cz/pub/linux/kali kali-rolling InRelease

Reading package lists... Done

Building dependency tree

Reading state information... Done

1181 packages can be upgraded. Run ‘apt list --upgradable' to see them.

Then run apt install cron.

root@debian:~# apt install cron

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and are no longer r

lequired:

cpp-8 libfluidsynthl lLibilmbase23 Libisl19 Libmozjs-60-0

libopenexr23 python3.7-minimal

Use ‘apt autoremove' to remove them.

Suggested packages:

anacron checksecurity

Recommended packages:

default-mta | mail-transport-agent

The following packages will be upgraded:

cron

1 upgraded, 90 newly installed, 0 to remove and 1180 not upgraded.

Need to get 99.3 kB of archives.

After this operation, © B of additional disk space will be used.

Get:1 https://mirror.karneval.cz/pub/linux/kali kali-rolling/main amd64

cron amd64 3.0pl1-136 [99.3 kB]

Fetched 99.3 kB in 35s (2,811 B/s)

**PDF s. 398:** 2 Use the crontab -e command, and select the nano text editor to create a routine

process that will run the CheckPortListen.sh script every five minutes.

no crontab for root - using an empty one

Select an editor. To change later, run ‘select-editor'.

2. /usr/bin/vim.tiny

Choose 1-2 [1]:|1]

GNU nano 3.2 /tmp/crontab.ACdrlA/crontab

5 * + * * /root/CheckPortListen. sh

</details>
