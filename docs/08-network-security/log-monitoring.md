# Log Monitoring & Security Analysis

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 138–139; Linux Security.pdf, s. 319–323.

## Mapa wiedzy

- Logs provide evidence for authentication failures, service errors and suspicious behavior. The course uses shell pipelines to reduce large logs into useful indicators.
- Examples combine `awk`, `grep`, `cut`, `uniq` and redirection to count IPs associated with HTTP 404 responses.
- Logwatch and service-specific logs are part of the monitoring workflow.

## Komendy / pliki / składnia występujące w materiale

```text
grep -in Fire /var/log/dpkg.log --color
chown root:adm /var/log/boot.log
chmod 640 /var/log/boot.log
chmod 644 /var/log/boot.log
chown root:root /var/log/boot.log
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
```

## Notatki z zajęć (PadRiseup)

- `grep -in Fire /var/log/dpkg.log --color`
- `more /var/log/dpkg.log`
- `less /var/log/dpkg.log`
- `chown root:adm /var/log/boot.log`
- `chmod 640 /var/log/boot.log`
- `chmod 644 /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`

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

**Textbook s. 138:** Section 4: Log Monitoring

A log file is a file that holds records of events that occur in an operating system or

software. In Linux, most of the actions performed on the system, either by the user or

the system, are recorded in a log in the /var/log directory. The kernel has a log that

records every kernel-related action and change.

Logs record nearly everything that happens in Linux, including memory usage, disk

space changes, services, applications, tasks, authentications, commands, and more.

They are useful for administrators to monitor system activity and troubleshoot the

system when necessary.

Logs are divided into three categories:

Information Logs: Record information without requiring an event or trigger. These

logs include information on lists, authentications, services, and more.

Warning Logs: Include informational messages that require attention, which can be,

for example, warnings for an application that does not function properly, or a firewall

that unexpectedly switches to a backup server.

Error Logs: Incidents that require the system administrator’s immediate attention.

They often indicate when a service or application is not operable.

Because there are so many logs to keep track of, the need arose to make this task more

efficient. Software was developed to collect the data from log files and aggregate it toa

single interface for easier management.

Nagios is a solution that provides monitoring for any kind of network, server, web

service, or application, using a simple, easy-to-work-with graphical user interface that

can be customized. The Nagios configuration wizard makes it easy to set up the

software and collect data from different sources.

In Linux servers, logs are generated at a rapid pace. A web server, for instance, has a lot

of traffic and can generate more than 10GB of log data per day. Having so much data in

a single file can lead to high CPU and memory consumption. Logrotate allows the

sysadmin to configure how big of a log the system should keep, at what frequency the

logs should be rotated and backed up, and how long they should be retained.

**Textbook s. 139:** Logrotate is used to rotate log files, by removing old logs from the system and creating

new files. The criteria for rotation can be the age of the file or the file size, and usually

runs automatically through the cron utility. Logrotate can also compress log files, and

can be configured to send emails to users when logs are rotated. Logrotate can be

configured by editing the logrotate.conf file, located at /etc/logrotate.conf.

johnd@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/ logrotate. cont

weekly

rotate 4

create

include /etc/logrotate.d

eq Get Help @% write Out @i) Where Is i Cut Text (§] Justify @e cur Pos

Wy Exit Mm Read File @y Replace @ Uncut Text@j To Spell @§ Go To Line

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 319:** Network Security

Log Monitoring

**Slides s. 320:** *UserLog Example*

2019-04-22 17:46:34 [unknown:usermod] root(@):wheel(@):Charlie &:/root:/bin/sh

2019-04-22 17:46:34 [unknown:useradd] admin(@) home /root made

Or ae 17:46:34 [unknown:useradd] vpn_guest(200@) home /home/vpn_guest

made

. 2019-04-22 17:46:34 [unknown:groupmod] al1(1998)

Logs are the technological 2019-04-22 17:46:34 [unknown:groupmod] admins(1999)

equivalent of recording. 2019-04-28 14:13:11 [unknown:userdel] admin(@) account removed

2019-04-28 14:13:11 [unknown:userdel] vpn_guest(200@) account removed

They are located in the 2019-04-28 14:13:11 [unknown:groupmod] al1(1998)

/var/log directory. 2019-04-28 14:13:11 [unknown:usermod] root(@):wheel(@):Charlie &:/root:/bin/sh

2019-04-28 14:13:11 [unknown:useradd] admin(@) home /root made

Many types of logs are 2079-04-28 14:13:11 [unknown:useradd] vpn_guest(200@) home /home/vpn_guest

collected, such as logins, 2019-04-28 14:13:11 [unknown:groupmod] a11(1998)

permissions, actions, etc. 2019-04-28 14:13:11 [unknown:groupmod] admins(1999)

2019-04-28 14:18:25 [unknown:userdel] admin(@) account removed

2019-04-28 14:18:25 [unknown:userdel] vpn_guest(200@) account removed

2019-04-28 14:18:25 [unknown:groupmod] al1(1998)

**Slides s. 321:** (Lo Log Monitoring

Information logs — list messages from application

processes, and track execution. toa

Warning logs — store information about

potentially harmful situations.

Error logs — record critical errors and terminate

program execution.

aa

**Slides s. 322:** (Lo Log Monitoring

Auth.log - displays information about

authentication events. toa

Apache2 has two main log files: access.log

and error.log.

An iptables log file in /var/log/kern.log stores

information about access attempts. (The log is

generated by the kernel.)

**Slides s. 323:** (ivi Log Monitoring

Ve ® Generating logs and saving them in files

| O requires considerable disk space.

—— ®@ Linux works in ‘Logrotate’ configuration.

@ The system maintains a fixed number of

vr logs and appends and erases them when

Kelc = necessary.

®@ For example, syslog files are kept for a week,

and logs older than seven days are deleted.

Lp dle

</details>
