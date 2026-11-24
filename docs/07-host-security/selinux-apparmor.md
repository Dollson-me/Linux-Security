# SELinux & AppArmor

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 124–126; Linux Security.pdf, s. 281–285.

## Mapa wiedzy

- SELinux and AppArmor implement mandatory access-control policies beyond traditional Unix mode bits.
- Their purpose is to constrain what processes may access even when ordinary user/group permissions would permit more.
- The course compares their policy approaches and positions them as host-hardening controls.

## Komendy / pliki / składnia występujące w materiale

```text
sudo apt install policycoreutils-gui -y
Export system settings toa file Export
which privileges. By default, access is denied if no profile is set to ‘allow’.
```

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 124:** Section 4: SELinux & AppArmor

Security-Enhanced Linux (SELinux) is a set of security enhancements to the Linux kernel

that allow more granular control over access measures using a labeling system and a

policy enforced by the kernel. SELinux can be traced back to earlier projects by the

United States National Security Agency (NSA). It was designed to enforce the security of

information to better address threats of tampering and malicious or flawed

applications. It comes with a default set of policy configurations that can easily be

changed.

Standard Linux access controls restrict files with read, write, and/or execute

permissions. The permissions can be changed by the user or a program the user is

running. SELinux, on the other hand, governs file access controls using policies deployed

on the system that cannot be changed by a user or program. SELinux uses a system that

labels every process, file, directory, and system object on the machine. The policy rules

define which labels have access to each other.

Multi-Level Security (MLS) is a security scheme that enforces the

four hierarchal levels of clearance of the Bell-LaPadula Model.

Each level is comprised of a sensitivity and a category.

Under MLS, dynamic entities such as users and processes are

referred to as subjects, and static entities such as files,

directories, and devices are referred to as objects. Both subjects

and objects are labeled with a security level: a clearance security

level for subjects and a classification security level for objects.

The purpose of MLS is to prevent access to information by

unauthorized users and machines.

Subjects can read the same or lower levels and write to the same

or higher levels. As defined by the BLP model, they cannot read

up or write down.

Note: MLS access rules are typically used alongside conventional access permissions.

Top-level clearance does not grant administrative rights on the system.

**Textbook s. 125:** MLS is not installed by default and can be installed with the apt command:

johnd@debian:”s sudo apt install selinux-policy-mls -y

johnd@debian: ~ x

File Edit View Search Terminal Help

[sudo] password tor johnd

Reading package Lists... Done

Building dependency tree

Reading state information... Done

Suggested packages:

logcheck syslog-summary

The following NEW packages will be installed:

selinux-policy-mls

®@ upgraded, 1 newly installed, 9 to remove and 6 not upgraded

Need to get 3,398 kB of archives

After this operation, 4,856 kB of additional disk space will be used

Get:1 http://deb.debian.org/debian buster/main amd64 selinux-policy-mls all 2:2.

20190201-2 [3,398 kB]

Fetched 3,398 kB in 2s (2,084 kB/s)

Selecting previously unselected package selinux-policy-mls.

(Reading database ... 181109 files and directories currently installed.)

Preparing to unpack .../selinux-policy-mls_2%3a2.20190201-2 all.deb ...

Unpacking selinux-policy-mls (2:2.20190201-2) ...

Setting up selinux-policy-mls (2:2.20190201-2) 5

Updating selinux mls policy (this step might take a moment) ..

The SELinux Policy Management Tool is a GUI interface that is installed separately:

johnd@debian:~$ sudo apt install policycoreutils-gui -y

After installation, it can be started from Applications > System Tools > SELinux Policy

Management Tool.

**Textbook s. 126:** SELinux Configuration x

System ~ | System — Lockdown a

System Mode

Select the system mode when the system first boots UP 1.4 ..04 om Disabled to Enforcing mode

DE ig _) Permissive \_) Disabled echamchegaen mode from Disabled to Permissive

e e \e = Reboot, so that the system can relabel,

inceds. * Change the system mode to Enforcing

System Configuration

Import system settings from another machine Import

Export system settings toa file Export

Relabel all files back to system defaults on reboot Yes (No

System Status: Disabled

A targeted policy is the default policy enforced by SELinux to control processes. When

using a targeted policy, processes that are targeted run in their own confined domain

with limited access to process-relevant files, and processes that are not targeted run in

an unconfined domain. If a targeted process is compromised by an attack, the attacker

will only have access to files in the domain.

AppArmor is a Linux security module (LSM) that creates restrictions for program

capabilities based on individual program profiles. AppArmor is a mandatory access

control (MAC) system, which allows the OS to restrict a subject’s access to objects and

the operations it can run on them. AppArmor profiles operate in one of two modes:

enforcement or complain.

Enforcement mode will enforce the policy defined in the profile and report policy

violations. Complain mode will only report policy violations.

AppArmor policies completely define what resources applications can access, and with

which privileges. By default, access is denied if no profile is set to ‘allow’.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 281:** Host Security

SELinux & AppArmor

**Slides s. 282:** SELinux & AppArmor

Johnd@debian: / x

File Edit View Search Terminal Help

. :/$ apt-get install selinux-

A security feature that seLinux-basics selinux-policy-doc seLlinux-utils

selinux-policy-default selinux-policy-mls

allows more enhanced seLinux-policy-dev selinux-policy-src

user control :/$ apt-get install selinux-

Grants control over who

can edit, upload, and

move files in the system

SELinux has several

installation packages,

each containing its own

control management.

**Slides s. 283:** (SE SELinux & AppArmor

@ A policy is a set of rules that power the SELinux security engine.

@ Policies grant access to files, devices, users, applications, and

processes.

@ Processes run in domains, and denied process access requests

are logged.

Multi-Layer Security (MLS):

@ The security level is based on sensitivity and category.

@ Users and processes are called subjects, and files and

devices are called objects.

Lp ala

**Slides s. 284:** (Ww SELinux & AppArmor

What Is AppArmor?

®@ Loads modules as profiles and analyzes them

® Can enforce profile rules and alert when rules are

J violated

®@ Includes a learning mode that can block profiles

based on unusual behavior

Cc % =

**Slides s. 285:** SELinux & AppArmor

SELinux vs. AppArmor

O

= SELinux AppArmor

Manually configured | | Has self-learning features

Complex configuration | | Easier configuration

Recommended for advanced users | Vs. | Can be used by beginners

ndlades decomeantation Most documentation files are in the

OpenSUSE operating system

Supports auditing and logging | | Includes reports and allows alerting

26

</details>
