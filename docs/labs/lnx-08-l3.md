# LNX-08-L3 — Configure ModSecurity

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 498–512.

## Cel, misja i środowisko

- G Lab Objective Understand how to use ModSecurity WAF to protect a web server from malicious surveillance and attacks. ba) Lab Mission
- ba) Lab Mission Install ModSecurity with proper configuration and secure the Apache? service. oe : © Lab Duration
- © Lab Duration 30-35 minutes tC) Requirements e Experience with configuring the Apache web service.
- tC) Requirements e Experience with configuring the Apache web service. e Practical knowledge of Linux commands. oo
- | Resources e¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Configure ModSecurity for Apache2 Set up Apache2 and secure the service with a ModSecurity firewall. 1 Login to the Debian VM and switch to the root user by running su -. Check if the Apache2 service is running using systemctl status apache2.

## Komendy występujące w labie

```text
apt install libapache2-mod-security2 -y
mv /etc/modsecurity/modsecurity.conf-recommended
mv /usr/share/modsecurity-crs /usr/share/modsecurity-crs.bk
Git is a version control application and package manager for Linux.
git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git
cp /usr/share/modsecurity-crs/crs-setup.conf.example
IncludeOptional /usr/share/modsecurity-crs/*.conf
IncludeOptional /usr/share/modsecurity-crs/rules/*.conf
systemctl status apache2
systemctl start apache2
nano /etc/apache2/conf-available/security.conf
nc 127.0.0.1 80
ff
/etc/init.d/apache2 force-reload
mv /etc/modsecurity/modsecurity.conf-recommended /etc/modsecurity|
git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git /usr/s
cp /usr/share/modsecurity-crs/crs-setup.conf.example /usr/share/modsecur
nano /etc/apache2/mods-enabled/security2.conf
IncludeOptional /etc/modsecurity/*.conf
IncludeOptional /usr/share/modsecurity-crs/*. load
IncludeOptional /usr/share/modsecurity-crs/rules/*. conf
```

## Powiązana teoria

- [Secure Apache](../08-network-security/secure-apache.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 498:** Linux Security

Lab Assignment Network Security

LNX-08-L3

o fmm Configure ModSecurity

Ol

Ea

All Rights Reserved.

**PDF s. 499:** Linux Security

Lab Assignment Network Security

LNX-08-L3

o fmm Configure ModSecurity

Ol

Ea

All Rights Reserved.

**PDF s. 500:** G Lab Objective

Understand how to use ModSecurity WAF to protect a web server from malicious

surveillance and attacks.

ba) Lab Mission

Install ModSecurity with proper configuration and secure the Apache? service.

oe :

© Lab Duration

30-35 minutes

tC) Requirements

e Experience with configuring the Apache web service.

e Practical knowledge of Linux commands.

oo

| Resources

e¢ Environment & Tools

o VirtualBox

= Debian

o ModSecurity

o Apache

**PDF s. 501:** Lab Task 1: Configure ModSecurity for Apache2

Set up Apache2 and secure the service with a ModSecurity firewall.

1 Login to the Debian VM and switch to the root user by running su -.

Check if the Apache2 service is running using systemctl status apache2.

If it is not running, use the command systemctl start apache2.

2 Prevent information leakage by removing the version of the Apache server from

the HTTP header request, which is done by editing the security.conf file, which is

located at /etc/apache2/conf-available/security.conf.

Open the file with nano, as follows:

3 Find the lines with the ServerTokens and Server Signature options and change

them to:

ServerTokens Prod

ServerSignature Off

4 Save the file and restart the Apache2 service using service apache2 restart.

5 Verify that the changes were made by connecting your Apache server via Netcat.

To do so, run the command nc 127.0.0.1 8080 and press Enter twice.

Note that if you didn’t perform all of the labs up to this point, the HTTP port in

the Apache server may be set to 80. In that case, run nc 127.0.0.1 80, and press

Enter twice.

The command will return the following output:

Verify that the server header (token) is Server: Apache, and that there is no

identifying information (signature) at the end of the output.

6 Install ModSecurity to allow traffic monitoring in real-time, by running

apt install libapache2-mod-security2 -y

7 Use the following command to reload the Apache server with ModSecurity:

/etc/init.d/apache2 force-reload

**PDF s. 502:** 8 The configuration file for ModSecurity is called “modsecurity.conf-

recommended”, so it needs to be changed to “modsecurity.conf”.

To do so run the following command:

mv /etc/modsecurity/modsecurity.conf-recommended

/etc/modsecurity/modsecurity.conf

9 ModSecurity has default rules located at /usr/share/modsecurity-crs. However, it

is recommended to download the rule set from GitHub.

Before you do so, you will need to rename the default rule directory from

/usr/share/modsecurity-crs to /usr/share/modesecurity-crs.bk, using the

following command:

mv /usr/share/modsecurity-crs /usr/share/modsecurity-crs.bk

10 Install “git” using the command apt install git -y.

Git is a version control application and package manager for Linux.

-y will answer “yes” to all installation options.

11 Download the new rules from GitHub using the following command:

git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git

/usr/share/modsecurity-crs

Note: Place a space in the command between git and /usr/.

12 Copy the sample configuration file from the downloaded rules, using the

following command:

cp /usr/share/modsecurity-crs/crs-setup.conf.example

/usr/share/modsecurity-crs/crs-setup.conf

Note that the file name was changed when this command was run. The original

name crs-setup.conf.example was changed to crs-setup.conf.

13 Edit the /etc/apache2/mods-enabled/security2.conf file using the Nano editor,

and add the following two lines before the line </IfModule>:

IncludeOptional /usr/share/modsecurity-crs/*.conf

IncludeOptional /usr/share/modsecurity-crs/rules/*.conf

**PDF s. 503:** 14 Save the file and restart the Apache service using systemctl restart apache2.

15 Check if Apache is active using service apache2 status.

**PDF s. 504:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS3

o fmm Configure ModSecurity

Ol

EI

All Rights Reserved.

**PDF s. 505:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS3

o fmm Configure ModSecurity

Ol

EI

All Rights Reserved.

**PDF s. 506:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to use ModSecurity WAF to protect a web server from malicious

surveillance and attacks.

ey Lab Mission

Install ModSecurity with proper configuration and secure the Apache? service.

esa .

©) Lab Duration

30-35 minutes

fe Requirements

e Experience with configuring the Apache web service.

e Practical knowledge of Linux commands.

a=

| Resources

e Environment & Tools

o VirtualBox

=" Debian

o ModSecurity

o Apache

**PDF s. 507:** Lab Task 1: Configure ModSecurity for Apache2

Set up Apache2 and secure the service with a ModSecurity firewall.

1 Login to the Debian VM and switch to the root user by running su -.

Check if the Apache2 service is running using systemctl status apache2.

t~$ su

Password:

root@debian:~# systemctl status apache2

apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabl

Active since Wed 2020-09-30 07:26:58 EDT; 4h 57min ago

Docs: https://httpd.apache.org/docs/2.4/

Main PID: 690 (apache2)

Tasks: 55 (limit: 4689)

Memory: 40.4M

CGroup: /system.slice/apache2.service

690 /usr/sbin/apache2 -k start

698 /usr/sbin/apache2 -k start

699 /usr/sbin/apache2 -k start

Sep 30 07:26:56 debian systemd[1]: Starting The Apache HTTP Server...

Sep 30 07:26:57 debian apachect1[514]: AHO0558: apache2: Could not reliably determine

Sep 30 07:26:58 debian systemd[1]: Started The Apache HTTP Server

If it is not running, use the command systemctl start apache2.

root@debian:~# systemctl start apache2

root@debian:~#

2 Prevent information leakage by removing the version of the Apache server from

the HTTP header request, which is done by editing the security.conf file, which is

located at /etc/apache2/conf-available/security.conf.

Open the file with nano, as follows:

root@debian:~# nano /etc/apache2/conf-available/security.conf

**PDF s. 508:** 3 Find the lines with the ServerTokens and Server Signature options and change

them to:

ServerTokens Prod

ServerSignature Off

GNU nano 3.2 /etc/apache2/conf-available/security.conf Modified

Servertokens Prod

ServerSignature off

4 Save the file and restart the Apache2 service using service apache2 restart.

5 Verify that the changes were made by connecting your Apache server via Netcat.

To do so, run the command nc 127.0.0.1 8080 and press Enter twice.

Note that if you didn’t perform all of the labs up to this point, the HTTP port in

the Apache server may be set to 80. In that case, run nc 127.0.0.1 80, and press

Enter twice.

**PDF s. 509:** The command will return the following output:

root@debian:~# nc 127.0.0.1 80

HTTP/1.1 400 Bad Request

Date: Wed, 30 Sep 2020 16:31:21 GMT

Server: Apache

X-Frame-Options: DENY

X-Content-Type-Options: nosniff

Content-Length: 226

Connection: close

Content-Type: text/html; charset=iso-8859-1

k!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">

<html><head>

<title>400 Bad Request</title>

</head><body>

<hl>Bad Request</h1>

<p>Your browser sent a request that this server could not understand.<br />

</p>

</body></html>

root@debian:~# ff

l

Verify that the server header (token) is Server: Apache, and that there is no

identifying information (signature) at the end of the output.

6 Install ModSecurity to allow traffic monitoring in real-time, by running

apt install libapache2-mod-security2 -y

root@debian:~# apt install libapache2-mod-security2 -y

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following additional packages will be installed:

Liblua5.1-0 modsecurity-crs

7 Use the following command to reload the Apache server with ModSecurity:

/etc/init.d/apache2 force-reload

root@debian:~# /etc/init.d/apache2 force-reload

[ ] Reloading apache2 configuration (via systemctl): apache2.service

root@debian:~#

**PDF s. 510:** 8 The configuration file for ModSecurity is called “modsecurity.conf-

recommended”, so it needs to be changed to “modsecurity.conf”.

To do so run the following command:

mv /etc/modsecurity/modsecurity.conf-recommended

/etc/modsecurity/modsecurity.conf

root@debian:~# mv /etc/modsecurity/modsecurity.conf-recommended /etc/modsecurity|

/modsecurity.conf

9 ModSecurity has default rules located at /usr/share/modsecurity-crs. However, it

is recommended to download the rule set from GitHub.

Before you do so, you will need to rename the default rule directory from

/usr/share/modsecurity-crs to /usr/share/modesecurity-crs.bk, using the

following command:

mv /usr/share/modsecurity-crs /usr/share/modsecurity-crs.bk

root@debian:~# mv /usr/share/modsecurity-crs /usr/share/modsecurity-crs.bk

10 Install “git” using the command apt install git -y.

Prooedepionne ptesen neta git

Git is a version control application and package manager for Linux.

-y will answer “yes” to all installation options.

11 Download the new rules from GitHub using the following command:

git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git

/usr/share/modsecurity-crs

Note: Place a space in the command between git and /usr/.

root@debian:~# git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git /usr/s

hare/modsecurity-crs

Cloning into ‘/usr/share/modsecurity-crs'...

remote: Enumerating objects: 27, done

remote: Counting objects: 100% (27/27), done.

|remote Compressing objects: 100% (25/25), done

tremote: Total 10292 (delta 8), reused 7 (delta 2), pack-reused 10265

Receiving objects: 100% (10292/10292), 3.31 MiB | 12.01 MiB/s, done.

Resolving deltas: 100% (7539/7539), done.

|root@debian :~# |

**PDF s. 511:** 12 Copy the sample configuration file from the downloaded rules, using the

following command:

cp /usr/share/modsecurity-crs/crs-setup.conf.example

/usr/share/modsecurity-crs/crs-setup.conf

root@debian:~# cp /usr/share/modsecurity-crs/crs-setup.conf.example /usr/share/modsecur

ity-crs/crs-setup.conf

root@debian:~#

Note that the file name was changed when this command was run. The original

name crs-setup.conf.example was changed to crs-setup.conf.

13 Edit the /etc/apache2/mods-enabled/security2.conf file using the Nano editor,

and add the following two lines before the line </IfModule>:

IncludeOptional /usr/share/modsecurity-crs/*.conf

IncludeOptional /usr/share/modsecurity-crs/rules/*.conf

root@debian:~# nano /etc/apache2/mods-enabled/security2.conf

root@debian:~#

GNU nano 3.2 security2.cont Modified

<IfModule security2 module>

SecDataDir /var/cache/modsecurity

IncludeOptional /etc/modsecurity/*.conf

IncludeOptional /usr/share/modsecurity-crs/*. load

IncludeOptional /usr/share/modsecurity-crs/*.conf

IncludeOptional /usr/share/modsecurity-crs/rules/*. conf

</IfModule>

14 Save the file and restart the Apache service using systemctl restart apache2.

**PDF s. 512:** 15 Check if Apache is active using service apache2 status.

|root@debian:~# service apache? status

le apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enable

Active since Wed 2020-04-08 12:44:52 EDT; 285 ago

Docs: https://httpd. apache.org/docs/2.4/

Process: 3722 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)

Main PID: 3726 (apache2)

| ‘Tasks: 6 (Limit: 4689)

</details>
