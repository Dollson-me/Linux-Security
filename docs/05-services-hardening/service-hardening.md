# Service Hardening Principles

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 92–93; Linux Security.pdf, s. 196–200.

## Mapa wiedzy

- Hardening reduces attack surface by removing unnecessary services, changing weak defaults, restricting authentication/access and applying updates.
- The course applies hardening to SSH, FTP and Samba and later expands the idea to Apache, firewalling and intrusion prevention.
- Configuration files and listening-port inspection are central: verify what is exposed before and after each change.

## Komendy / pliki / składnia występujące w materiale

```text
SSH Hardening
FTP Hardening
FTP service hardening options include those described above for SSH, but some
Ss Back up the configuration file. G) Change the default ports.
sudo netstat -tulpn
fail2ban
```

## Notatki z zajęć (PadRiseup)

- `sudo netstat -tulpn`
- `/etc/vsftpd.conf`
- `fail2ban`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-05-L3 — Securing Services](../labs/lnx-05-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 92:** Section 5: Hardening

Hardening is the practice of enhancing security, checking configurations, creating rules

and policies, updating and patching software and systems, and a variety of other

measures, with the aim of decreasing the surface vulnerability of programs, services,

protocols, and operating systems.

SSH Hardening

The following steps are recommended to provide a higher level of security for the SSH

service:

- Back up configuration file — It is recommended to back up the original file, so that it

can be recovered if a configuration issue arises.

- Disable root login — To prevent remote connections with high level privileges, the

option to log in with the root user must be disabled.

- Allow list users — Specify which users can log in to the system to lower the potential

attack surface.

- Change default ports — Changing the ports assists in reducing the attack surface, and

can mitigate potential attacks performed by inexperienced attackers.

- Seta certificate — Use this option to control the login security level without

monitoring the usage of strong passwords.

- Configure Fail2Ban — A brute-force prevention solution.

- Audit connections — Monitor requests to connect to the service, to keep track of

potential threats.

FTP Hardening

FTP service hardening options include those described above for SSH, but some

additional options address its unique vulnerabilities, as follows:

- Disable anonymous connections — Prevent the option to log in without credentials.

- Set disk quotas — Restrict the size of files that can be uploaded.

- Set access time restrictions — Prevent users from connecting to the server at specific

times, such as after work hours.

**Textbook s. 93:** Samba Hardening

The following hardening options are suggested for the samba service:

- Allow list the host access segment.

- Turn off the option to save passwords.

- Don’t publish the service to the world.

- Use the relevant SMB version.

Note: When the share is configured, the ‘browsable’, ‘writeable’, and ‘guest ok’ options

must be considered carefully, since they can increase the attack surface in the server.

Lab Assignment: LNX-05-L3 Securing Services

_ Make installed services more secure and less vulnerable, and learn about

== | Windows tools.

Follow the instructions in lab document LNX-05-L3.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 196:** Services and Hardening

Hardening

**Slides s. 197:** (ss Hardening

Off

Ss Back up the configuration file. G) Change the default ports.

2) Edit the configuration file. (6) Set the certificate.

(3) Disable root login. 7) Configure Fail2Ban.

(4) Allow list. Audit connections.

25

**Slides s. 198:** (FT Hardening

e

r* @ Set a strong password policy.

®@ Disable anonymous connection.

@ Set disk quotas.

A ®@ Set log on restrictions at specific times.

Since FTP has unique vulnerabilities, various

hardening measures are required.

Cc % = P

**Slides s. 199:** (Sa Hardening

.

@ Allow list host access segment.

®@ Turn off the option to save the password.

. ® Don’t publish it to the world.

= ®@ Keep only the relevant SMB version.

Cc % =

**Slides s. 200:** Hardening

Lab: LNX-05-L3 [eee

i e VIISSIOT

a ee Make existing installed services more secure and less

Securing Services | vulnerable and learn about Windows tools.

40-50 Min. a

ae ik r ; yA ® Secure the SSH protocol.

— " I @ Secure the FTP protocol.

’ ames Bi i ; ® Secure the Samba protocol.

—_ XS ® § id

4 > ~~ yr

| iY ® ® Debian ®@ Lab document

| ® Windows

‘ ® PuTTY and FileZilla

{ << “=

</details>
