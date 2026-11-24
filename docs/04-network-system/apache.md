# Apache HTTP Server

[← 04 · Networking & System Management](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 78–80; Linux Security.pdf, s. 159–165.

## Mapa wiedzy

- Apache is an open-source HTTP server. The course installs, starts, stops, restarts and reconfigures it as a central service used by later security labs.
- HTTP is shown on port 80 and HTTPS on 443. Configuration and site files live under `/etc/apache2`.
- Service/process inspection uses tools such as `systemctl`, `service`, `ps`, `lsof` and `netstat`.
- Later chapters harden Apache with access controls, reduced information disclosure, TLS and ModSecurity.

## Komendy / pliki / składnia występujące w materiale

```text
Service Debugging
service is activated, it is important to check its status using the command service
journalctl --unit=apache2
service status, use Active: since Tue 2020-09-29 04:35:56 EDT; 195 ago
service <service_name> Docs: https://httpd.apache.org/docs/2.4/
sudo apt install apache2
systemctl status apache2
sudo vim ports.conf
sudo systemctl restart apache2
curl -v http://localhost
sudo vim /etc/apache2/conf-available/security.conf
sudo apt install libapache2-mod-security2
cd /etc/apache2/mods-enabled
sudo vim /etc/apache2/sites-available/default-ssl.conf
sudo vim /etc/apache2/sites-available/000-default.conf
```

## Notatki z zajęć (PadRiseup)

- `sudo apt install apache2`
- `systemctl status apache2`
- `sudo vim ports.conf`
- `sudo systemctl restart apache2`
- `curl -v http://localhost`
- `sudo vim /etc/apache2/conf-available/security.conf`
- `sudo apt install libapache2-mod-security2`
- `/etc/init.d/apache2 force-reload`
- `cd /etc/apache2/mods-enabled`
- `sudo vim /etc/apache2/sites-available/default-ssl.conf`
- `sudo vim /etc/apache2/sites-available/000-default.conf`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-04-L3 — Install and Configure Apache](../labs/lnx-04-l3.md)
- [LNX-08-L3 — Configure ModSecurity](../labs/lnx-08-l3.md)
- [LNX-08-L4 — SSL Encryption](../labs/lnx-08-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 78:** Section 4: Apache

Apache is a common server program in Linux that provides web hosting services.

Apache is run as a service itself, called apache2. The service operates by default on port

80 for HTTP and needs to be configured to use port 443 for HTTPS.

Apache is not a physical server. It operates via software that can be installed on a

machine and used as a server. It creates a connection between the server and web

browsers. One of the reasons for its popularity is the fact that Apache is cross-platform

and works on UNIX-based and Windows OS systems.

The default Apache webpage appears as follows, when installed on Debian systems:

Apache2 Debian Default Pac % | +

S ea ® localhost OW iN |=

( ) Apache2 Debian Default Page |

This is the default welcome page used to test the correct operation of the Apache2 server after

installation on Debian systems. If you can read this page, it means that the Apache HTTP server

installed at this site is working properly. You should replace this file (located at /var/www

/html/index. html) before continuing to operate your HTTP server.

If you are a normal user of this web site and don't know what this page is about, this probably means

that the site is currently unavailable due to maintenance. If the problem persists, please contact the

site's administrator.

Configuration Overview

Debian's Apache? default configuration is different from the upstream default configuration, and split int

several files optimized for interaction with Debian tools, The configuration system is fully documented

in jusr/share/doc/apache2/README. Debian.gz. Refer to this for the full documentation.

Documentation for the web server itself can be found by accessing the manual if the apache2-doc

**Textbook s. 79:** Apache Configuration

The web files are located by default in /var/www/html/index.html. This is the root

folder and contains Apache webpages. You can change it by editing the apache2.conf

file, which is usually located in /etc/apache2/ along with many other Apache

configuration files. apache2.conf is also responsible for loading the other configuration

files in the /etc/apache2 directory.

Starting the Service

Since not all daemons (servers) boot with the OS, it is a best-practice to know some

basic service commands, such as service <daemon_name> <action> or the newer

version of the service command, systemctl <action> < daemon_name>. The most

common actions are start, restart, stop, and status.

You can configure a service to start with the system boot using the command systemcl

enable < daemon_name>. Another important command is journalctl, which is a utility

that retrieves messages from the kernel, system daemons, journals, and other log

sources.

Service Debugging

In some cases, services may encounter errors when activated or used daily. When a

service is activated, it is important to check its status using the command service

<service name> status, and verify that it is active. If the service fails to start, a brief

description of the problem will often be provided.

Another command that can be used to view service status is systemctl status <service

name>.

**Textbook s. 80:** john@debian: / x

File Edit View Search Terminal Help

le apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enable

Active: active (running) since Tue 2020-09-29 64:35:56 EDT; 19s ago

Docs: https://httpd.apache.org/docs/2.4/

Main PID: 3118 (apache2)

Tasks: 55 (limit: 4689)

Memory: 11.3M

CGroup: /system.slice/apache2.service

3118 /usr/sbin/apache2 -k start

3120 /usr/sbin/apache2 -k start

3121 /usr/sbin/apache2 -k start

Sep 29 04:35:56 debian systemd[1]: Starting The Apache HTTP Server

Sep 29 04:35:56 debian apachectl[3107]: AH@@558: apache2: Could not reliably determine

Sep 29 04:35:56 debian systemd[1]: Started The Apache HTTP Server.

lines 1-15/15 (END) |

The command journalctl can be used to retrieve service data, such as messages, from

the kernel, system services, and additional sources. The command journalctl --

unit=<service name> can be used to display logs for specific services.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# journalctl --unit=apache2

-- Logs begin at Wed 2020-09-30 61:29:55 EDT, end at Wed 2020-09-30 02:41:46 EDT

Sep 3@ 61:29:59 debian systemd[1]: Starting The Apache HTTP Server

Sep 3@ 61:29:59 debian apachectl[653]: AHOO558: apache2: Could not reliably dete

Sep 38 61:29:59 debian systemd[1]: Started The Apache HTTP Server

root@debian:~#

Lab Assignment: LNX-04-L3 Install & Configure Apache

—_ Install and configure an Apache service and create a local web server.

m=z:

Follow the instructions in lab document LNX-04-L3.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 159:** Linux Security

Apache

**Slides s. 160:** c: Apache

O

@ Open-source project for UNIX-based operating systems

@ AnHTTP web server that hosts web applications

@ By default, it is configured to use port 80.

@ Can be configured to use port 443 (HTTPS)

| Apache2 is installed using apt install apache2. &-

Cc % = 4

**Slides s. 161:** Apache

Apache Confi ti

O L_]

= Apache? Debian Default Pa: x | +

€ Cc @ @ localhost = OF In O =

Apache2 Debian Default Page

The /var/www/html

directory contains the main :

ASTCHE WEES RABE A re

he2 he2 This is the default welcome page used to test the correct operation of the Apache? server after

/etc/apac e. /apac e. -conf installation on Debian systems. If you can read this page, it means that the Apache HTTP server

is the configuration file that installed at this site is working properly. You should replace this file (located at /var/www

includes global settings. /html/index.htm1) before continuing to operate your HTTP server.

If you are a normal user of this web site and don't know what this page is about, this probably means

7 . on that the site is currently unavailable due to maintenance. If the problem persists, please contact the

| index.html is the main file by site's administrator.

default. Configuration Overview

Debian's Apache? default configuration is different from the upstream default configuration, and split int

several files optimized for interaction with Debian tools. The configuration system is fully documented

in /usr/share/doc/apache2/README. Debian.gz. Refer to this for the full documentation.

Documentation for the web server itself can be found by accessing the manual if the apache2-doc

29

**Slides s. 162:** (Sti Apache

‘ogg, Starting Services

co O \ A service can be started using

Sag service <service_name> <action>

. systemctl <action> <service_name>.

y Service Continuity

. Va Not all services are started when the OS is booted.

« y) Services can be enabled using systemctl.

Lp ala

**Slides s. 163:** Apache

x4

john@debian: / *

File Edit View Search Terminal Help

apache2.service - The Apache HTTP Server

To check the Apache Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enable

service status, use Active: since Tue 2020-09-29 04:35:56 EDT; 195 ago

service <service_name> Docs: https://httpd.apache.org/docs/2.4/

status. Main PID: 3118 (apache2)

Tasks: 55 (limit: 4689)

journalctl is another way HEWES Eth eh —

P h ice status CGroup: /system.slice/apache2. service

TOVIEW Tne SeRvICRIS . Sau /usr/sbin/apache2 -k start

3120 /usr/sbin/apache2 -k start

journalctl retrieves 3121 /usr/sbin/apache2 -k start

messages from the kernel,

systemd services, and Sep 29 04:35:56 debian systemd[1]: Starting The Apache HTTP Server...

other sources. Sep 29 04:35:56 debian apachectl[3107]: AHO0558: apache2: Could not reliably determine

Sep 29 04:35:56 debian systemd[1]: Started The Apache HTTP Server.

|

**Slides s. 164:** (Ca Apache

/

CR ps (without arguments): Displays current

° (on running services for the specified shell “

a= v top: Displays information about running

processes, CPU, and memory in real-time

ae

LA htop (not installed by default): Displays a

= graphical view of the top command output

ee

**Slides s. 165:** Apache

_ SS Install the Apache2 service and configure it

Install and Configu re Apache to manage local web server access options.

10-20 Min |

oo : ® Install the Apache2 package.

a > : a : @ Check the service status.

q : = - y ~~ @ Change the listening port.

" b NN ® e di

| ea fr @ Debian @ Lab document

} ®@ Apache2

| if 4 . NI

</details>
