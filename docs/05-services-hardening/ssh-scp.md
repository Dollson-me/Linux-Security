# SSH & SCP

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 84–86; Linux Security.pdf, s. 179–185.

## Mapa wiedzy

- SSH creates an encrypted client/server channel for remote login and command execution. A daemon listens for connection requests.
- The canonical CLI pattern is `ssh user@IP`; the course also uses PuTTY/MobaXterm as graphical clients.
- SCP transfers files through SSH and therefore uses the same secure channel/port 22.
- Hardening topics include changing defaults, controlling allowed users/authentication methods, using keys and minimizing information exposure.

## Komendy / pliki / składnia występujące w materiale

```text
FTP uses two ports: port 21, to set the connection between both communicating
SSH Remote Connection
ssh 10.0.2.15 -1 johnd
SSH Connection
SCP is a protocol that provides the ability to transfer files among parties securely, via
SCP allows file uploads to and downloads from a server, via port 22. Different flags can
SCP Flags Meaning
scp test.txt root@10.10.10.12:/home/john
scp root@10.10.10.12:/home/john/test.txt /root
SSH and SCP
SSH connection is es :
SSH daemon constantly am
SSH <ip address> a Ai A shell appears.
SCP is installed on Linux distributions by default
scp file.txt root@10.10.10.12:/home/johnd
IP Separator || Remote Directory
scp root@10.10.10.12:/home/johnd/file.txt /root
IP Remote Directory
sudo apt install openssh-server
scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop
ssh Piotr@192.168.1.68 -p 4843
```

## Notatki z zajęć (PadRiseup)

- `sudo apt install openssh-server`
- `scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop`
- `ssh Piotr@192.168.1.68 -p 4843`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-05-L1 — Install and Configure SSH](../labs/lnx-05-l1.md)
- [LNX-05-L3 — Securing Services](../labs/lnx-05-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 84:** FTP uses two ports: port 21, to set the connection between both communicating

parties, and port 20, to transfer the data.

Samba is an open-source software suite that runs on Linux-based operating systems

and communicates with Windows clients. Samba enables the sharing of resources such

as printers and files through the Common Internet File System (CIFS) and the Server

Message Block (SMB) protocols. SMB is used by applications and services to talk to each

other over a network.

SMB uses two protocols: 139 when it runs on top of NETBIOS as an older version, and

port 445 when it runs on top of TCP.

The SMB2 version, which Microsoft released in 2006, featured reduced communication

chatter. SMB3, released in 2012, introduced enhanced capabilities such as support for

virtualized environments, and end-to-end encryption.

NFS is the Linux equivalent of SMB. Interoperability between the two is achievable but

tricky due to the difference in authentication and security policies.

Section 2: SSH and SCP

SSH Remote Connection

A remote connection to an SSH server can be established from a CLI with a dedicated

command or a dedicated third-party application, such as PuTTy.

In every connection, one side has the role of the server and the other has the role of

the connecting client. The SSH daemon constantly listens to the service's port and waits

for a client's request to connect.

To connect via CLI, the service command must be used with the credentials of the

server and a user to connect to: ssh [user]@[IP address]

**Textbook s. 85:** File Edit View Search Terminal Help

root@debian:~# ssh 10.0.2.15 -1 johnd

The authenticity of host '10.0.2.15 (10.0.2.15)' can't be established

ECDSA key fingerprint is SHA256:mxKxI9Wd018apNuNnSwoWn7 Qj B/qX1FSkI+P 3gwhbx

c.

Are you sure you want to continue connecting (yes/no)? yes

Warning: Permanently added '10.0.2.15' (ECDSA) to the list of known hosts

johnd@10.0.2.15's password

Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-2+deb10ul (2019-09-20) x

86 64

The programs included with the Debian GNU/Linux system are free software;

the exact distribution terms for each program are described in the

individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

permitted by applicable law.

Last login: Thu Nov 7 94:11:23 2019 from 10.9.2.15 va

=$

:/$ ifconfig

enpQs3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST> mtu 1500

inet 10.0.2.15 netmask 255.255.255.0 broadcast 10.0.2.255

Initiation of an SSH connection via the Terminal

SSH Connection

The connection process consists of several steps. The first step is to set the command

with the server's credentials to initiate the connection. Upon initiation, the client is

asked about continuing or not, and then sends a password for the specified user. If the

password is correct, a shell appears.

Secure Copy Protocol

SCP is a protocol that provides the ability to transfer files among parties securely, via

SSH. Like SSH, SCP also has an authentication level in the connection process.

SCP allows file uploads to and downloads from a server, via port 22. Different flags can

be used to control the bandwidth, cypher, and ports of the connection.

The SCP protocol is easy-to-use and pre-installed on Linux distributions.

**Textbook s. 86:** The following command flags can be used to transfer files to a remote location:

SCP Flags Meaning

-P <port> Specifies the remote connection port.

Sends original modification details such as date created,

P access times, etc.

1 Copies the entire directory (recursive).

y Used in debug mode to observe the connection details

between SCP and SSH.

-S (program) Use a third-party program for the connection.

-| Bandwidth limitation.

The following command is used to transfer the file test.txt to a remote location, john's

home directory:

scp test.txt root@10.10.10.12:/home/john

The following command is used to copy the file test.txt from a remote location to the

local system:

scp root@10.10.10.12:/home/john/test.txt /root

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 179:** Services and Hardening

SSH and SCP

**Slides s. 180:** SSH and SCP

File Edit View Search Terminal Help

rootia3debian:~# ssh 10.0.2.15 -l johnd

The authenticity of host '10.0.2.15 (10.0.2.15)' can't be established.

ECDSA key fingerprint is SHA256:mxKxI9Wd0L8apNuNnSwOWn7Qj B/qX1FSkjJ+P3gwhbx

SSH connection is es :

. Are you sure you want to continue connecting (yes/no)? yes

established from the CLI Warning: Permanently added '10.0.2.15' (ECDSA) to the list of known hosts.

or third-party johnd@10.0.2.15's password:

. . Linux debian 4.19.0-6-amd64 #1 SMP Debian 4.19.67-2+debl0ul (2019-09-20) x

applications, such as 86 64

PUTTY.

The programs included with the Debian GNU/Linux system are free software;

. . . the exact distribution terms for each program are described in the

One side isa client, and individual files in /usr/share/doc/*/copyright.

the other side is an SSH ;

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

server. permitted by applicable law. |

Last login: Thu Nov 7 04:11:23 2019 from 10.0.2.15 x

SSH daemon constantly am

listens to the port and

waits for connection :/$ ifconfig

requests. enpOs3: flags=4163<UP, BROADCAST , RUNNING, MULTICAST> mtu 1500

inet 10.0.2.15 netmask 255.255.255.0 broadcast 10.0.2.255

**Slides s. 181:** (ss SSH and SCP

Enter a password

password to connect.

SSH <ip address> a Ai A shell appears.

“Are you sure you want to

continue connecting”

(yes/no)? ©.

**Slides s. 182:** (Se SSH and SCP

Op, @ SCP securely transfers files between remote or

r=, local stations. _

; ®@ Like SSH, it provides an authentication level.

— ® Transfers can be controlled using flags that set

-~ parameters, such as bandwidth, cypher, and

| port.

SCP is installed on Linux distributions by default

and is known for its simplicity and security.

Cc % = .

**Slides s. 183:** (Se SSH and SCP

Secure Copy Protocol Flags

0

| Flag Meaning

| -P <port> Specifies the remote connection port

Sends original modification details such as date

| P created, access time, etc.

| -r Copies the entire directory (recursive) ™ e

| yy Used in debugging mode to observe the connection

details between SCP and SSH

| -S (program) Invokes a third-party program for the connection

| -| Bandwidth limitation é

11

**Slides s. 184:** SSH and SCP

Secure Copy Protocol Example

Transfer files to a remote location (such as to the johnd folder):

scp file.txt root@10.10.10.12:/home/johnd

™ e

IP Separator || Remote Directory

Copy a remote file to a local system using the scp command:

scp root@10.10.10.12:/home/johnd/file.txt /root

‘

IP Remote Directory

12

**Slides s. 185:** SSH and SCP

1 Install the SSH service for remote connection, use SCP

Install and Configure SSH | to transfer files, and work with the Ubuntu distribution.

40-50Min. ~~~

en ‘S yA : @ Install the SSH package.

: ~ sa ~ a I ® Configure and install Ubuntu.

. ee 7 — ® Create a file in Ubuntu.

ia f y/, ~~ ® View the file’s content.

| .) as > aM

| a) @ 4 ® Debian ® Lab document

® Ubuntu

| 3. %; @ SSH

) |

ib % ia. >. “=

</details>
