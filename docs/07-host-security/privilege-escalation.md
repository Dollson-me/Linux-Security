# Privilege Escalation

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 127–128; Linux Security.pdf, s. 286–294.

## Mapa wiedzy

- Privilege escalation is the transition from a lower-privileged context to higher privileges through misconfiguration, weak permissions or vulnerable software.
- The material highlights SUID/SGID, writable scripts/files, PATH issues and enumeration of the local system as common investigation areas.
- LinEnum appears in the class resources as an enumeration aid; the security objective is to find and remove unnecessary escalation paths.

## Komendy / pliki / składnia występujące w materiale

```text
done
export PATH=/usr/sbin:$PATH
md5sum $file > $temppath
```

## Notatki z zajęć (PadRiseup)

- `export PATH=/usr/sbin:$PATH`
- `5 backup_path="/home/piotr/Desktop"`
- `9 dest_path="/tmp"`
- `21 tar -czvf dest ath/filename $backup_path`
- `hashpath=/tmp/wwwhash`
- `temppath=/tmp/temphash`
- `md5sum $file > $temppath`
- `Sprawdz czy dwa hashe temppath oraz hashpath`
- `status="$(cmp --silent $hashpath $temppath; echo $?)"`
- https://github.com/rebootuser/LinEnum

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 127:** AppArmor is deployed with several default policies, along with learning-based tools, so

virtually every application can be deployed with AppArmor.

Policy violations can be set to notify users via email or a pop-up notification on the

desktop.

Section 5: Privilege Escalation

Most operating systems are designed with the idea that multiple users may be using the

same machine. Therefore, operating systems have the ability to set different privilege

levels for different users. For example, an administrator will have higher privileges than

a basic user.

Privilege escalation (PE) happens when a user gains privileges they are not entitled to.

These privileges can provide an attacker with the ability to wreak havoc upon the

system by stealing sensitive information, installing malicious software, or deleting

crucial OS files, rendering the OS unusable. An attacker strives to get the highest

available privileges in the system, which the root user has in Linux.

PE is usually achieved by exploiting bugs in the OS or by misusing installed programs,

taking advantage of design flaws to use applications in ways they were not intended to

be used.

Large amounts of tools are created and customized for the purpose of elevating a

regular user's privileges. In addition, there are CVEs that describe system vulnerabilities

that can be exploited to achieve PE.

One of the first things an attacker will do upon gaining access to a machine is to look for

sensitive data such as passwords, user names, network schemes, and IPs to maximize

the attack surface and gain access to more machines on the network. Lack of cyber

awareness is a serious issue that hackers exploit.

In one scenario, an attacker sends an email to an employee in an organization. The

email seems legitimate and has a harmless-looking attached file, which the user

downloads and opens.

**Textbook s. 128:** The file evades security measures since it does not perform suspicious activities; it

simply copies the contents of the /proc/version file and sends it back to the attacker.

This file holds the system version information. The attacker then looks for a CVE for that

version and now has a list of vulnerabilities they can exploit for the machine.

CVE, Common Vulnerabilities and Exposures, is a catalog of known security threats

sponsored by the US Department of Homeland Security.

A wildcard is a single character that represents one or more characters. For example, an

asterix (*) matches any number of characters; searching for dev* will yield: developer,

development, devops, and other similar results beginning with the letters dev.

Wildcard injection is an older UNIX hacking trick that takes advantage of unsanitized

input in the Linux shell. For example, when an argument is used as a file name,

including the hyphen (-), the Linux shell will interpret it as a command-line argument for

the executed command.

Misconfiguration refers to insufficiently securing assets or incorrectly implementing

security measures. An example would be not changing default login credentials on a

router or IP webcam.

LinEnum is an enumeration tool that is used to gather information and check for

escalation points on a machine. Once a shell is accessed on a targeted machine, running

LinEnum will launch a search for kernel and distribution release details, and provide

system information such as current IP, routing details, and DNS information. It will

collect data about users, services, permissions, privileges, and more. LinEnum performs

numerous automated checks and presents you with a detailed report.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 286:** Host Security

Privilege Escalation

**Slides s. 287:** (Se Privilege Escalation

@ After a successful attack, an attacker will search for

sensitive information on a workstation.

® Do not store sensitive information on a workstation.

®@ Sensitive information must be strongly protected

using permissions or encrypted storage.

Cc % =

**Slides s. 288:** (Lo Privilege Escalation

@ Suppose a web server hosts at least three websites.

@ Anattacker’s purpose will be to look for a vulnerability

in the sites and log in as root.

®@ In this case, the attacker will have a broader scope of

attack possibilities due to the numerous hosted web

resources.

An attacker can upload a PHP file from one of the

websites using the name of a common host server.

Cc % = .

**Slides s. 289:** (Pr Privilege Escalation

@ PE =privilege escalation

@ Attackers typically try to get root passwords through PE.

@ They often use tools customized for this purpose.

@ CVEs for specific versions and systems should be studied.

Cc % =

**Slides s. 290:** (Ro Privilege Escalation

@ Must be complex and should not appear in

dictionaries

®@ Upon a successful PE, an attacker may get

access to a root password and change it.

®@ Do not use root credentials in services

and crontab.

® Root passwords must be different in

— each machine.

Passwords generally are not easy to crack, but of

all the password types, local passwords are the

easiest to crack.

Lp ‘.

**Slides s. 291:** (w Privilege Escalation

®@ Wildcards are symbols that represent one or more

characters.

®@ Wildcards are used because characters they represent

may be reserved for special system operations.

@ Wildcards are interpreted by the shell before they are

executed.

Inserting commands as data in files can lead

to PE without having to use tools.

Cc % = .

**Slides s. 292:** (ivi Privilege Escalation

/ | ® Configuration mistakes are made by system

>< administrators.

“™ @ File misconfiguration can lead to backdoors

and weak spots.

@ Keeping the default configuration for services

invites attackers to execute simple attacks.

@ Some Linux interfaces require a high level of

knowledge, which means hackers with such

knowledge often have an advantage.

Lp

**Slides s. 293:** Privilege Escalation

[-] Debug Info

Gathers information

for PE

Checks for application

misconfigurations

Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-2+deb10ul (2019-09-20) x86_64 GNU/Lin

ux

Linux version 4.19.6-6-amd64 (debian-kernel@lists.deblan.org) (gcc version 8.3.0 (Debia

In &.3.0-6)) #1 SMP Debian 4.19.67-2+deb1l0ul (2019-09-20)

**Slides s. 294:** Privilege Escalation

:~/DownLoads$ ./pspy64

pspy - version: v1.2.0 - Commit SHA: 9c63e5d6c58T7bcdc235db663T5e3felc33b8e55

Config: Printing events (colored=true): processes=true | file-system-events=false ||| $

cannning for processes every 100ms and on inotify events ||| Watching directories: [/us

r ftmp fetc fhome /var fopt] (recursive) | [] (non-recursive)

Draining file system events due to startup...

done

2019/11/20 10:50:54 CMD: UID=0 PID=9998 | fusr/lib/packagekit/packagekitd

2019/11/20 10:50:54

2019/11/20 10:50:54 CMD: UID=6 PID=9930 |

pspy displays commands executed from the host.

</details>
