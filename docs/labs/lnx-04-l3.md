# LNX-04-L3 — Install and Configure Apache

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 236–255.

## Cel, misja i środowisko

- G Lab Objective Get to know the Apache? service and its configuration options. bs Lab Mission Install the Apache2 service and configure it to manage local web server access options.
- bs Lab Mission Install the Apache2 service and configure it to manage local web server access options. LN] as ©) Lab Duration
- ©) Lab Duration 10-20 minutes {e Requirements e Knowledge of service commands
- {e Requirements e Knowledge of service commands e Knowledge of the installation process using the apt command e Knowledge of Isof and netstat to check port listening
- | Resources e¢ Environment & Tools o VirtualBox = Debian

## Komendy występujące w labie

```text
CD *
su -
fj
service apache2 start
service apache2 status
```

## Powiązana teoria

- [Apache](../04-network-system/apache.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 236:** Linux Security

and System

Management

oo innm LNX-04-L3

olin

JU Install and Configure Apache

All Rights Reserved.

**PDF s. 237:** Linux Security

and System

Management

oo innm LNX-04-L3

olin

JU Install and Configure Apache

All Rights Reserved.

**PDF s. 238:** G Lab Objective

Get to know the Apache? service and its configuration options.

bs Lab Mission

Install the Apache2 service and configure it to manage local web server access options.

LN] as

©) Lab Duration

10-20 minutes

{e Requirements

e Knowledge of service commands

e Knowledge of the installation process using the apt command

e Knowledge of Isof and netstat to check port listening

Lt

| Resources

e¢ Environment & Tools

o VirtualBox

= Debian

o Apache2

o Netstat must be installed

**PDF s. 239:** Lab Task: Install and Configure Apache2

Install the Apache2 service using Package Manager after checking for its existence in

the system. Then, verify the status of the service and restart it.

1 Open the terminal and use the su — command to switch to the root user.

2 Use the service --status-all command to check if the Apache2 service exists in the

system.

3. Use the netstat -I command to list all open ports in the operating system and

check to see if the HTTP protocol is listening.

Note: You should see that port 80 is not listening.

4 Use the apt install apache2 -y command to install HTTP server Apache2. Utilize

the Package Manager’s apt command to install the Apache2 application.

5 Use the service apache2 start command to start the Apache? service. Verify the

status is active using the service apache2 status command.

6 Use the service --status-all command to check if the Apache2 service exists in the

operating system. (After installation, it should appear.)

7 Use the netstat -I command to check if the HTTP protocol is listening (it should be

listening now).

8 Open the Firefox browser.

9 Browse to 127.0.0.1. An Apache2 default page should appear. Close the browser.

10 Inthe terminal, use the nano /etc/apache2/ports.conf command to open the

Apache2 configuration file.

11 Inthe file, change the listening number from 80 to 8080. This is the listening port

number. Save the file and exit.

**PDF s. 240:** 12 Use the service apache2 restart command to restart the Apache? service for the

settings to take effect. Verify the service is active using the service apache2

status command.

13. Use the Isof -i | grep apache2 command to check if the port number on which

Apache is listening is HTTP (80) or HTTP-alt (8080).

14 In Firefox, try to browse to 127.0.0.1 again and note that the webpage does not

appear.

15 Browse to 127.0.0.1:8080 and note that the webpage is displayed via the

appropriate port.

16 Change the listening port back to 80 and verify it was changed via the browser or

CLI.

**PDF s. 241:** Linux Security

& Solution and System

Management

oo innm LNX-04-LS3

olin

JU Install and Configure Apache

All Rights Reserved.

**PDF s. 242:** Linux Security

& Solution and System

Management

oo innm LNX-04-LS3

olin

JU Install and Configure Apache

All Rights Reserved.

**PDF s. 243:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Get to know the Apache? service and its configuration options.

» Lab Mission

Install the Apache2 service and configure it to manage local web server access options.

CD *

©) Lab Duration

10-20 minutes

fe Requirements

e Knowledge of service commands

e Knowledge of the installation process using the apt command

e Knowledge of Isof and netstat to check port listening

a=

| Resources

e Environment & Tools

o VirtualBox

=" Debian

o Apache2

o Netstat must be installed

**PDF s. 244:** Lab Task: Install and Configure Apache2

Install the Apache2 service using Package Manager after checking for its existence in

the system. Then, verify the status of the service and restart it.

1 Open the terminal and use the su — command to switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ su -

Password:

root@debian:-# fj

2 Use the service --status-all command to check if the Apache2 service exists in the

system.

john@debian: ~ x

File Edit View Search Terminal Help

[-] alsa-utils

[- ] anacron

[+] apparmor

[ +] avahi-daemon

[ - ] bluetooth

L - ] console-setup.sh

[+] cron

[+] dbus

[+] gdm3

L - ] hwelock.sh

[ - ] keyboard-setup.sh

[+ ] kmod

[+] network-manager

[4] networking

[- ] plymouth

[ - ] plymouth-log

[ - ] pppd-dns

[+] procps

[+]. rsyslog

[- ] saned

L - ] speech-dispatcher

[- ] sudo

[+] udev

[ +] unmattended-upgrades

[ - ] x11-common

root@debian:~#

**PDF s. 246:** 5 Use the service apache2 start command to start the Apache? service. Verify the

status is active using the service apache2 status command.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service apache2 start

root@debian:~# service apache2 status

apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service; enabled;

Active: since Tue 2020-09-29 07:25:20 EDT; 1m

Docs: https://httpd.apache.org/docs/2.4/

Main PID: 2183 (apache2)

Tasks: 55 (limit: 4689)

Memory: 10.0M

CGroup: /system.slice/apache2.service

2183 /usr/sbin/apache2 -k start

2184 /usr/sbin/apache2 -k start

2186 /usr/sbin/apache2 -k start

Sep 29 07:25:20 debian systemd[1]: Starting The Apache HTTP Serve

Sep 29 07:25:20 debian apachectl[2172]: AHO0558: apache2: Could n

Sep 29 07:25:20 debian systemd[1]: Started The Apache HTTP Server

[lines 1-15/15 (END) BBeLss) 2 ee

**PDF s. 248:** 8 Open the Firefox browser.

Activities Tue 07:54 2 Or

Q Type to search...

° g@ has & ©

& AisleR.. Calcul. Calen.. Cheese Chess Clocks

SBO@ewea:es==.

Conta... Docu... Docu... Evolut.. Files Firefo...

es : co

: > FR EF fe a

Five ou. Four-in. Hitori lagno Rlotski Libre...

‘J NJ =

BRB: 2

ro] ire... Dre iBre.. Uibre.. Lights... Mahjo..

Frequent All

**PDF s. 250:** 11 Inthe file, change the listening number from 80 to 8080. This is the listening port

number. Save the file and exit.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/apache2/ports.conf Modified

$

Listen s0soff

<IfModule ssl_module>

Listen 443

</IfModule>

<IfModule mod_gnutls.c>

Listen 443

Get Help Write Out Mf] Where Is MW Cut Text

Exit il Read File @N Replace (gj Uncut Text

</details>
