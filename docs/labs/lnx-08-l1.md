# LNX-08-L1 — Configure a Whitelist

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 466–481.

## Cel, misja i środowisko

- G Lab Objective Become familiar with iptables and firewall rules by configuring your own ruleset in a Debian Linux environment. 2 Lab Mission
- 2 Lab Mission Use iptables to learn how to block all connections through SSH, then modify your configuration to allow list a client’s IP address. UA] F
- ©) Lab Duration 20-25 minutes {© Requirements e Knowledge of firewalls and networking rules
- {© Requirements e Knowledge of firewalls and networking rules e Knowledge of services, their configuration files, and their functions oo
- | Resources ¢ Environment & Tools o VirtualBox =" Debian VM

## Zadania / etapy

1. Lab Task 1: Block SSH Connection Using Iptables Use iptables to block all connections through SSH. 1 Loginto the Debian VM and switch to the root user with the command su -. Then, make sure the SSH service is running using the command service ssh
2. Lab Task 2: Allow List a Client IP for SSH Connection Use the previous commands for iptables and what you know about allow lists to configure an allow list for your firewall. 1 Find the IP address of the Windows host; use ipconfig to find the IP address on

## Komendy występujące w labie

```text
netstat | grep ssh.
iptables -A INPUT -p tcp --dport 22 --source <client IP> -j ACCEPT.
service ssh status
Delete
netstat | grep ssh
iptables -L
| iptables -F INPUT
fj
iptables -A INPUT -p TCP --dport 22 --source fle.0.0.5/24) -j ACCEPT
iptables -A INPUT -p TCP --dport 22 -j DROP
Jj
iptables -L |
```

## Powiązana teoria

- [Iptables](../08-network-security/iptables.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 466:** Linux Security

Lab Assignment Network Security

LNX-08-L1

ofan Configure a Whitelist

om

EJ

All Rights Reserved.

**PDF s. 467:** Linux Security

Lab Assignment Network Security

LNX-08-L1

ofan Configure a Whitelist

om

EJ

All Rights Reserved.

**PDF s. 468:** G Lab Objective

Become familiar with iptables and firewall rules by configuring your own ruleset in a

Debian Linux environment.

2 Lab Mission

Use iptables to learn how to block all connections through SSH, then modify your

configuration to allow list a client’s IP address.

UA] F

©) Lab Duration

20-25 minutes

{© Requirements

e Knowledge of firewalls and networking rules

e Knowledge of services, their configuration files, and their functions

oo

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian VM

o SSH

o Iptables

o PuTTY

**PDF s. 469:** Lab Task 1: Block SSH Connection Using Iptables

Use iptables to block all connections through SSH.

1 Loginto the Debian VM and switch to the root user with the command su -.

Then, make sure the SSH service is running using the command service ssh

status. You should see a message in green saying active (running).

If you see inactive (dead) with no colored lines, run the command service ssh

Start to start the service.

2 Verify that the Debian VM network adapter is set to bridge mode.

3 Using the IP address from the host Debian machine, open PuTTY and connect

with SSH from the Windows host by entering the Debian IP and clicking Open.

Verify that the SSH option is selected.

4 Inthe PuTTY Security Alert window, select Yes to save the SSH key to PUTTY’s

cache.

5 When the connection is established, use the login credentials of the user johnd

on the Debian VM.

6 Switch back to the Debian VM to view the SSH connection to it.

Note: Use the commands netstat and grep to find the connection.

Use the netstat command with filtration to view the link as follows:

netstat | grep ssh.

Verify that the IP address matches your client’s IP address.

Troubleshooting Note: if netstat is not found, install it with apt install net-tools.

On the right, you can see an indication of the established connection.

7 Close PuTTY, and, on the Debian machine, block the SSH connection using

iptables. Try to connect again from Windows. SSH operates on port 22, so the

following syntax should block it: iptables -A INPUT -p tcp --dport 22 -j DROP.

After running the command, the client should receive a Connection timed out

error from PUTTY.

**PDF s. 470:** 8 List the existing rules using iptables -L, and clear the INPUT rules using iptables -F

INPUT (where the —-F flag means flush).

The top-most rule will be deleted after you run iptables -F INPUT.

**PDF s. 471:** Lab Task 2: Allow List a Client IP for SSH Connection

Use the previous commands for iptables and what you know about allow lists to

configure an allow list for your firewall.

1 Find the IP address of the Windows host; use ipconfig to find the IP address on

the Windows machine.

2 Use iptables to allow list the Windows machine for SSH. Then, reapply the

previously used rule to block list all other IP addresses for SSH connection.

The command to allow list an IP is:

iptables -A INPUT -p tcp --dport 22 --source <client IP> -j ACCEPT.

3 Verify that the iptables rules were applied in the correct order, and then test the

firewall by connecting your client through SSH. To do so, use iptables -L to verify

that the rules were applied.

Test the iptables configuration by connecting to SSH from your client.

Note: The connection should be successful.

**PDF s. 472:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS1

ofan Configure a Whitelist

om

EJ

All Rights Reserved.

**PDF s. 473:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS1

ofan Configure a Whitelist

om

EJ

All Rights Reserved.

**PDF s. 474:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Become familiar with iptables and firewall rules by configuring your own ruleset in a

Debian Linux environment.

5 Lab Mission

Use iptables to learn how to block all connections through SSH, then modify your

configuration to allow list a client’s IP address.

x) :

@ Lab Duration

20-25 minutes

{© Requirements

e Knowledge of firewalls and networking rules

e Knowledge of services, their configuration files, and their functions

oo

| Resources

¢ Environment & Tools

o VirtualBox

= Debian VM

o SSH

o Iptables

o PuTTY

**PDF s. 475:** Lab Task 1: Block SSH Connection Using Iptables

Use iptables to block all connections through SSH.

1 Loginto the Debian VM and switch to the root user with the command su -.

Then, make sure the SSH service is running using the command service ssh

status. You should see a message in green saying active (running).

johnd@debian: ~ x

File Edit View Search Terminal Help

root@debian:/# service ssh status

ssh.service - OpenBSD Secure Shell server

Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: enab

Active: since Thu 2019-11-28 06:50:52 EST; 7min ago

Docs: man:sshd(8)

man:sshd_config(5)

Process: 7180 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)

Main PID: 7181 (sshd)

Tasks: 1 (limit: 4689)

Memory: 1.5M

CGroup: /system.slice/ssh.service

7181 /usr/sbin/sshd -D

Nov 28 06:50:52 debian systemd[1]: Starting OpenBSD Secure Shell server...

Nov 28 06:50:52 debian sshd[7181]: Server listening on 0.6.6.0 port 22

Nov 28 06:50:52 debian sshd[7181]: Server Listening on :: port 22.

Nov 28 06:50:52 debian systemd[1]: Started OpenBSD Secure Shell server

Nov 28 06:50:57 debian sshd[7182]: Accepted password for johnd from 10.21.9.11 p

Nov 28 06:50:57 debian sshd[7182]: pam_unix(sshd:session) session opened for us

Nov 28 06:53:25 debian sshd[7214]: Accepted password for johnd from 10.21.0.11 p

Nov 28 06:53:25 debian sshd[7214]: pam unix(sshd:session): session opened for us

Nov 28 66:54:41 debian sshd[7228]: Accepted password for johnd from 10.21.8.11 p|

Nov 28 06:54:41 debian sshd[7228]: pam_unix(sshd:session): session opened for us

If you see inactive (dead) with no colored lines, run the command service ssh

Start to start the service.

**PDF s. 476:** 2 Verify that the Debian VM network adapter is set to bridge mode.

= General Network

{a} System Adapter 1 Adapter 2 Adapter3 Adapter 4

( disptey enable Network Adapter

Paes Attached to: Bridged Adapter ¥

Name: | Realtek Gaming GbE Family Controller ~

\Qp Audio

| D Advanced

| Network

2

GS: seria! Ports

| use

[7 Shared Folders

FF] User interface

OK Cancel

**PDF s. 477:** 3 Using the IP address from the host Debian machine, open PuTTY and connect

with SSH from the Windows host by entering the Debian IP and clicking Open.

Verify that the SSH option is selected.

Basic options for your PuTTY session

Specty the destination you want to connect to

Host Name (or IP address) Port

Connection type:

Raw OTehet © Rlogn[@ SSH] © Seral

Load, save or delete a stored session

Saved Sessions

Defauit Settings Load

Save

Delete

Close window on ext:

OAlways ~O)Never © Only on clean exit

4 Inthe PuTTY Security Alert window, select Yes to save the SSH key to PUTTY’s

cache.

PuTTY Security Alert x

The server's host key is not cached in the registry. You

have no guarantee that the server is the computer you

think itis.

The server's ssh-ed25519 key fingerprint is:

ssh-ed25519 255 4e:eb:38:d 5:05: 14:96:23:9e: cred: 20:10:53: 79:Fe

Ifyou trust this host, hit Yes to add the key to

PuTTY's cache and carry on connecting

If you want to carry on connecting just once, without

adding the key to the cache, hit No.

If you do not trust this host, hit Cancel to abandon the

connection

5 When the connection is established, use the login credentials of the user johnd

on the Debian VM.

**PDF s. 478:** 6 — Switch back to the Debian VM to view the SSH connection to it.

Note: Use the commands netstat and grep to find the connection.

Use the netstat command with filtration to view the link as follows:

netstat | grep ssh.

Verify that the IP address matches your client’s IP address.

root@debian:~# netstat | grep ssh

tcp C) ® debian:ssh 10.0.0.5:49674 ESTABLISHED

root@debian:~#

Troubleshooting Note: if netstat is not found, install it with apt install net-tools.

On the right, you can see an indication of the established connection.

if? login as: johnd

7 Close PuTTY, and, on the Debian machine, block the SSH connection using

iptables. Try to connect again from Windows. SSH operates on port 22, so the

following syntax should block it: iptables -A INPUT -p tcp --dport 22 -j DROP.

Footeseionn tales “AAT p top ere ON

After running the command, the client should receive a Connection timed out

error from PUTTY.

PuTTY Fatal Error x

x) Network error: Connection timed out

**PDF s. 479:** 8 List the existing rules using iptables -L, and clear the INPUT rules using iptables -F

INPUT (where the —-F flag means flush).

root@debian:-# iptables -L

Chain INPUT (policy ACCEPT)

taraet prot opt source destination

DROP tcp -- anywhere anywhere tcp dpt:ssh

Chain FORWARD (policy ACCEPT)

target prot opt source destination

Chain OUTPUT (policy ACCEPT)

target prot_opt source destination

root@debian:~#| iptables -F INPUT

root@debian:~# iptables -L

Chain INPUT (policy ACCEPT)

target prot opt source destination

Chain FORWARD (policy ACCEPT)

target prot opt source destination

Chain OUTPUT (policy ACCEPT)

target prot_opt source destination

root@debian:~# fj

The top-most rule will be deleted after you run iptables -F INPUT.

**PDF s. 480:** Lab Task 2: Allow List a Client IP for SSH Connection

Use the previous commands for iptables and what you know about allow lists to

configure an allow list for your firewall.

1 Find the IP address of the Windows host; use ipconfig to find the IP address on

the Windows machine.

Ethernet adapter Ethernet:

Subnet Mask... ~~... . . . . : 255.255.255.6

Default Gateway... .. 2. 2s. 3 10.0.0.1

2 Use iptables to allow list the Windows machine for SSH. Then, reapply the

previously used rule to block list all other IP addresses for SSH connection.

The command to allow list an IP is:

iptables -A INPUT -p tcp --dport 22 --source <client IP> -j ACCEPT.

root@debian:~# iptables -A INPUT -p TCP --dport 22 --source fle.0.0.5/24) -j ACCEPT

root@debian:~-#

root@debian:~# iptables -A INPUT -p TCP --dport 22 -j DROP

root@debian:~# Jj

3 Verify that the iptables rules were applied in the correct order, and then test the

firewall by connecting your client through SSH. To do so, use iptables -L to verify

that the rules were applied.

root@debian:~# iptables -L |

Chain INPUT (policy ACCEPT)

target rot opt source destination

ACCEPT tcp -- 10.0.0.0/24 anywhere tcp dpt:ssh

DROP tcp -- anywhere anywhere tcp dpt:ssh

Chain FORWARD (policy ACCEPT)

target prot opt source destination

Chain OUTPUT (policy ACCEPT)

target prot opt source destination

root@debian:~#

**PDF s. 481:** Test the iptables configuration by connecting to SSH from your client.

[login as: johnd

permitted by applicable law.

Last login: Fri May 29 11:11:10 2020 from 10.0.0.5

Note: The connection should be successful.

</details>
