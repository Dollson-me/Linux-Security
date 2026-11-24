# Fail2Ban

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 136–137; Linux Security.pdf, s. 315–318.

## Mapa wiedzy

- Fail2Ban monitors logs for repeated authentication/service failures and dynamically blocks sources that match configured filters/jails.
- It is presented as protection for exposed services such as SSH and Apache, complementing—not replacing—secure configuration and firewalling.
- Log location, filter patterns, thresholds and ban actions determine its behavior.

## Komendy / pliki / składnia występujące w materiale

```text
Fail2Ban is installed separately, using the apt command: apt install fail2ban -y.
Fail2Ban
cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
cat /etc/fail2ban/jail.local
fail2ban
```

## Notatki z zajęć (PadRiseup)

- `fail2ban`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-08-L2 — Summary Exercise](../labs/lnx-08-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 136:** Section 3: Fail2Ban (F2B)

F2B is an Intrusion Prevention System (IPS) designed mainly to prevent brute-force

attacks on UNIX-based operating systems. F2B uses Python scripts to scan logs located

in directories such as /var/log/auth.log, /var/log/httpd/error_log, and

/var/log/apache/access.log. Once it identifies suspicious behavior, such as multiple

incorrect password entries from the same source IP, it adds a corresponding rule to the

local firewall or other packet filtering system to ban traffic from that IP, either

temporarily or permanently. F2B can also send email notifications regarding events.

Fail2Ban is installed separately, using the apt command: apt install fail2ban -y.

F2B comes with filters for common services like Apache, SSH, and others. The filters are

regular Python expressions (regex) that can be modified. The configuration file for F2B

is located in /etc/fail2ban/jail.conf. It is not recommended to make changes to this file,

since it will be overwritten when the package is updated. Instead, copy it to jail.local

and make changes there. It is important to keep the name jail.local for F2B to recognize

the file. To copy the file, use cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

Jail.local has the following global configurations:

ignoreip F2B ignores traffic from this IP, meaning the IP is allow listed and will not

be blocked. A single IP or a network can be entered. Multiple entries should be

separated with spaces.

bantime How long a ban should last, in seconds.

maxretry Number of failed attempts before the ban.

findtime The period of time during which failed attempts are counted.

**Textbook s. 137:** johnd@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/fail2ban/jail. local Modified

ignoreip = 127.0.0.1/8 85.174.220.10

bantime = 10m

findtime = 16m

maxretry = 5

Me Get Help gf Write Out @) Where Is gM Cut Text #) Justify @e Cur Pos

Ws Exit fai Read File gi} Replace @@ Uncut Textgyj To Spell gf Go To Line

Important notes:

1. Fail2Ban is not a replacement for a firewall. It is meant to work in conjunction

with an existing firewall or packet filtering system.

2. F2B cannot handle a distributed brute-force attack, meaning an attacker can use

a large number of machines to perform separate attempts from multiple IPs and

bypass F2B altogether.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 315:** Network Security

Fail2Ban

**Slides s. 316:** (w Fail2Ban

What is Fail2Ban?

®@ Scans log files.

®@ Bans suspicious IP addresses and limits login attempts.

® Good security measure against brute-force attacks.

®@ Failed attempts can be sent as a report.

=

**Slides s. 317:** Fail2Ban

johnd@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

root@debian:~# cat /etc/fail2ban/jail.local

# Jail.conf is a configuration

# WARNING: heavily refactored in 6.9.0 release. Please review and . , 5

# customize settings for your setup. file that contains Fail2Ban

# settings.

# Changes: in most of the cases you should not modify this

# file, but provide customizations in jail.local file, :

# or separate .conf files under jail.d/ directory, e.g.: It should be copied or

# overwritten to the .local

# HOW TO ACTIVATE JAILS: file format

# YOU SHOULD NOT MODIFY THIS FILE.

# It is recommended to be

# It will probably be overwritten or improved in a distribution update. : :

i cautious when applying

# Provide customizations in a jail.local file or a jail.d/customisation. local. Fail2Ban settings.

# For example to change the default bantime for all jails and to enable the

# ssh-iptables jail the following (uncommented) would appear in the .local file

# See man 5 jail.conf for details.

**Slides s. 318:** (Configuring Fail2ban

@

— (©) OUT

</details>
