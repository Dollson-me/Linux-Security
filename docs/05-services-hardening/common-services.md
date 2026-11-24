# Common Linux Services & Protocols

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 83–83; Linux Security.pdf, s. 176–178.

## Mapa wiedzy

- The course introduces iptables, BIND/named, sendmail/SMTP and NTPD as common Linux services, then focuses on remote access and file-sharing protocols.
- SSH provides encrypted remote access and is associated with port 22; FTP uses separate control/data channels on ports 21 and 20 and is unencrypted.
- Samba implements Windows-compatible file/resource sharing with SMB/CIFS; the material notes NetBIOS/139 and direct TCP/445 variants.
- NFS is described as the Linux-side analogue to SMB, with interoperability complicated by differing authentication/security models.

## Komendy / pliki / składnia występujące w materiale

```text
iptables is a generic, highly versatile, firewall utility that is pre-installed on most Linux
iptables named sendmail ntpd
cat /etc/ssh/ssh_config
sudo apt install openssh-server
sudo apt install samba
systemctl restart samba
sudo apt install vsftpd
systemctl restart vsftpd.service
ftp 192.168.1.68
systemctl restart sshd
ssh Piotr@192.168.1.68 -p 4843
echo "piotr" > /etc/ssh/sshd.allow
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
systemctl start ssh
sudo systemctl restart ssh
sudo iptables -L -n
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/ssh/ssh_config`
- `sudo apt install openssh-server`
- `sudo apt install samba`
- `systemctl restart samba`
- `sudo apt install vsftpd`
- `/etc/vsftpd.conf`
- `systemctl restart vsftpd.service`
- `ftp 192.168.1.68`
- `systemctl restart sshd`
- `ssh Piotr@192.168.1.68 -p 4843`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`
- `systemctl start ssh`
- `sudo systemctl restart ssh`
- `sudo iptables -L -n`
- `sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 83:** | Chapter 5: Services & Hardening

Section 1: Common Services and Protocols

Linux Services

iptables is a generic, highly versatile, firewall utility that is pre-installed on most Linux

distributions. It is CLI-based, with no graphical interface, and looks for rules in its table

that match packets, and either allows them, or blocks them.

Named, which is part of the BIND DNS package, is a service that executes the DNS

server daemon, which converts host names to IP and vice versa.

Sendmail is a mail transfer agent (MTA) used to deliver pre-formatted email messages.

It comes pre-installed by default on most Linux distributions, and does not work with a

GUI, but only through the CLI. The SMTP protocol that is used by nearly all email

services communicates via sendmail.

Network Time Protocol Daemon (NTPD) is the most widely used method to sync Linux

system clocks with network time servers.

Linux Protocols

Secure Shell (SSH) is a secure network protocol with a range of uses. It can be used to

securely access remote servers and hosts, and operates by creating an encrypted

connection between a local client and a remote server over an insecure network such

as the internet.

The connection not only allows you to access remote servers and hosts but also to

securely transfer files using the SCP protocol via SSH. SSH is used by applications such as

PuTTY, MobaXterm, and many more. Port 22 is reserved for SSH.

File Transfer Protocol (FTP) is one of the oldest methods for transferring files among

hosts over TCP/IP connections. FTP is a client-server protocol that creates two

communication channels between a client and a server: one to control the

conversation, and another to transmit the data. FTP does not encrypt transferred files

and was eventually replaced with Secure Shell FTP (SFTP), which works over SSH.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 176:** Services and Hardening

Common Services

and Protocols

**Slides s. 177:** Common Services and Protocols

Linux Services

e ia e + *

iT off 9 —

YT TI Boo \

iptables named sendmail ntpd

5

**Slides s. 178:** (Co Common Services and Protocols

Pe SSH (Secure Shell) is a cryptographically secure

tae network protocol that operates on port 22. “

fal FTP (File Transfer Protocol) transfers files over

the network. It operates on ports 21 and 20 with

Vii default credentials.

Samba allows computers to communicate within

the local network via the SMB protocol. This

protocol operates on ports 137-139 and 445. se

</details>
