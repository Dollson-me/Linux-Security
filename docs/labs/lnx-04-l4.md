# LNX-04-L4 — Service Debugging

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 256–267.

## Cel, misja i środowisko

- *©) Lab Objective Understand how to troubleshoot service errors by identifying their cause. by Lab Mission Install the Apache and Nginx services, and resolve a port conflict.
- by Lab Mission Install the Apache and Nginx services, and resolve a port conflict. rN) A @) Lab Duration
- @) Lab Duration 20-30 minutes (© Requirements e Knowledge of networking, listening ports, and commands.
- (© Requirements e Knowledge of networking, listening ports, and commands. e Knowledge of Linux commands and configuration files. a=
- | Resources ¢ Environment & Tools o VirtualBox =" Debian

## Komendy występujące w labie

```text
su -
service apache2 start |
service apache2 status
apt install nginx -y |
root@debian :~#
systemctl status nginx.service
ls nginx.service - A high performance web server and a reverse proxy server
lsof -i :80
nano /etc/nginx/sites-enabled/default |
service nginx start |
service nginx status
fj
Lsof -i :8080
```

## Powiązana teoria

- [Other Applications](../04-network-system/other-applications.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 256:** Linux Security

Lab Assignment Networking

and System

Management

orn LNX-04-L4

Ff U Service Debugging

All Rights Reserved.

**PDF s. 257:** Linux Security

Lab Assignment Networking

and System

Management

orn LNX-04-L4

Ff U Service Debugging

All Rights Reserved.

**PDF s. 258:** *©) Lab Objective

Understand how to troubleshoot service errors by identifying their cause.

by Lab Mission

Install the Apache and Nginx services, and resolve a port conflict.

rN) A

@) Lab Duration

20-30 minutes

(© Requirements

e Knowledge of networking, listening ports, and commands.

e Knowledge of Linux commands and configuration files.

a=

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

o Nginx

o Apache

**PDF s. 259:** Lab Task

In the following scenario, the Nginx service does not operate.

Your task is to troubleshoot and solve the issue.

1 Open the terminal and use the command su — to switch to the root user.

2 Use the command service apache? start to turn on the Apache? service.

Verify that it is active using the command service apache2 status.

3 Use the command apt install nginx -y to install the Nginx service.

Nginx is a web server, similar to Apache2.

4 Use the command service nginx start to start the Nginx service.

Note the message that appears.

5 Use the command systemctl status nginx.service as suggested in the output.

Note that a message states that port 80 is already in use.

6 Check which service is listening on port 80 using Isof -i :80.

7 Use the command nano /etc/nginx/sites-enabled/default to open the nginx

configuration file.

8 Scroll down until you see server {..., and change port 80 to 8080.

Save the file and exit it.

9 Use the command service nginx start to start the nginx service. Verify that it is

active using the command service nginx status.

10 Verify that the Apache2 service is still active using the command service apache2

status.

11. Use the command Isof -i :80 to verify that Apache is listening to port 80.

12 Use the command Isof -i :8080 to verify that nginx is listening to port 8080.

**PDF s. 260:** Linux Security

Lab Assignment Networking

& Solution and System

Management

orn LNX-04-LS4

Ff U Service Debugging

All Rights Reserved.

**PDF s. 261:** Linux Security

Lab Assignment Networking

& Solution and System

Management

orn LNX-04-LS4

Ff U Service Debugging

All Rights Reserved.

**PDF s. 262:** Note: Solutions for the instructor are shown inside the green box.

»©) Lab Objective

Understand how to troubleshoot service errors by identifying their cause.

ba) Lab Mission

Install the Apache and Nginx services, and resolve a port conflict.

CN) ”

@ Lab Duration

20-30 minutes

{@ Requirements

e Knowledge of networking, listening ports, and commands.

e Knowledge of Linux commands and configuration files.

oo

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

o Nginx

o Apache

**PDF s. 263:** Lab Task

In the following scenario, the Nginx service does not operate.

Your task is to troubleshoot and solve the issue.

1 Open the terminal and use the command su — to switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ su -

Password:

root@debian: ~#

2 Use the command service apache2 start to turn on the Apache? service.

Verify that it is active using the command service apache2 status.

john@debian: ~ x j

File Edit View Search Terminal Help

root@debian:~# service apache2 start |

root@debian:~# service apache2 status

l@ apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service;

(EREEMEER)...skipping...

l@ apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service;

Active: active (running) since Tue 2020-09-29 08:10:

3 Use the command apt install nginx -y to install the Nginx service.

Nginx is a web server, similar to Apache2.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install nginx -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and

are no longer required:

cpp-8 hyphen-en-us libasan5 libc-dev-bin

libgcc-8-dev Libisl19 libmpx2

**PDF s. 264:** 4 Use the command service nginx start to start the Nginx service.

Note the message that appears.

————————

john@debian: ~ x

File Edit View Search Terminal Help

Job for nginx.service failed because the control process exited with error code.

see "systemctl status nginx.service" and "journalctl -xe" for details.

root@debian :~#

5 Use the command systemctl status nginx.service as suggested in the output.

Note that a message states that port 80 is already in use.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:-~# systemctl status nginx.service

ls nginx.service - A high performance web server and a reverse proxy server

Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)

Active; failed (Result: exit-code) since Tue 2020-09-29 08:24:26 EDT; 36s ago

Docs: man:nginx(8)

Process: 4783 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code-exited, status=0/SUCCE

Process: 4784 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=1/FAILURE)

Sep 29 98:24:25 debian nginx{474]: nginx: [emerg] bind() to [::]:80 failed (98: Address already in use)

sep 29 8:24:25 debian nginx{4784]: nginx: [emerg] bind() to 0.0.0.0:80 failed (98: Address already in use)

sep 29 8:24:25 debian nginx[4784]: nginx: [emerg] bind() to [::]:8@ failed (98: Address already in use)

sep 29 08:24:26 debian nginx[4784]: nginx: [emerg] bind() to 0.0.0.0:80 failed (98: Address already in use)

Sep 29 08:24:26 debian nginxl47@4]: nginx: [emerg] bind() to [::]:80 failed (98: Address already in use)

Sep 29 08:24:26 debian nginx[4784]: nginx: [emerg] still could not bind()

Sep 29 8:24:26 debian systemd[1]: nginx.service: Control process exited, code=exited, status=1/FAILURE

sep 29 08:24:26 debian systemd[1]: nginx.service: Failed with result ‘exit-code'.

Sep 29 8:24:26 debian systemd[1]: Failed te start A high performance web server and a reverse proxy server

6 Check which service is listening on port 80 using Isof -i :80.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# lsof -i :80

COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME

lapache2 3825 root 4u IPv6 38564 Oto TCP *:http (LISTEN)

lapache2 3826 www-data 4u IPv6 38564 Oto TCP *:http (LISTEN)

lapache2 3827 www-data 4u IPv6 38564 Oto TCP *:http (LISTEN)

root@debian:~#

According to the output, Apache? is listening on port 80.

**PDF s. 265:** 7 Use the command nano /etc/nginx/sites-enabled/default to open the nginx

configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/nginx/sites-enabled/default |

8 Scroll down until you see server {..., and change port 80 to 8080.

Save the file and exit it.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/nginx/sites-enabled/default Modified

$

$

server {

listen 8080 default_server;

listen [::];8080 default_server;

Get Help Write Out {MJ Where Is MM Cut Text (MJ Justify

Exit Read File gg} Replace @Y Uncut Text ij To Spell

Page5

**PDF s. 266:** 9 Use the command service nginx start to start the nginx service. Verify that it is

active using the command service nginx status.

I john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service nginx start |

root@debian:~# service nginx status

le nginx.service - A high performance web server and a reverse proxy se

Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor

(Eee). ..skipping...

ie nginx.service - A high performance web server and a reverse proxy se

Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor

Active: active (running) since Tue 2020-09-29 08:33:27 EDT; 58s ago

(STSMEEE)...skipping...

10 Verify that the Apache2 service is still active using the command service

apachez2 status.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service apache2 status

le apache2.service - The Apache HTTP Server

Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendo

Active: active (running) since Tue 2020-09-29 08:10:01 EDT; 25min a

Docs: https://httpd.apache.org/docs/2.4/

Main PID: 3825 (apache2)

Tasks: 55 (limit: 4689)

Memory: 21.5M

CGroup: /system.slice/apache2.service

3825 _/usr/sbin/apache2_-k start

11 Use the command Isof -i :80 to verify that Apache is listening to port 80.

I john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# lsof -i :80

COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME

lapache2 3825 root 4u IPv6 38564 OtO TCP *:http (LISTEN)

lapache2 3826 www-data 4u IPv6 38564 QtO TCP *:http (LISTEN)

lapache2 3827 www-data 4u IPv6 38564 Oto TCP *:http (LISTEN)

root@debian:~# fj

**PDF s. 267:** 12 Use the command Isof -i :8080 to verify that nginx is listening to port 8080.

————ooooooooOoOoOEOEOEOEOEOEOEOEOEOEOEOEOEOEOEOEOEOeeT

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:-# Lsof -i :8080

COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME

Inginx 4852 root 6u IPv4 45432 ote TCP *:http-alt (LISTEN)

Inginx 4852 root Ju IPw6 45433 ete TCP *:http-alt (LISTEN)

Inginx 4853 www-data 6u IPv4 45432 ete TCP *:http-alt (LISTEN)

Inginx 4853 www-data Ju IPv6 45433 ete TCP *:http-alt (LISTEN)

Inginx 4854 www-data 6u IPv4 45432 ote TCP *:http-alt (LISTEN)

Inginx 4854 www-data Ju IPv6 45433 ete TCP *:http-alt (LISTEN)

Inginx 4855 www-data 6u IPv4 45432 ote TCP *:http-alt (LISTEN)

Inginx 4855 www-data Ju IPv6 45433 ote TCP *:http-alt (LISTEN)

root@debian:~#

</details>
