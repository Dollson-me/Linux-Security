# LNX-05-L2 — Install and Configure Samba and FTP

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 286–311.

## Cel, misja i środowisko

- G Lab Objective Understand how to transfer files between Windows and Linux using Samba and FTP. La Lab Mission Perform a basic configuration of Samba, provide access to Samba shares via an MS
- La Lab Mission Perform a basic configuration of Samba, provide access to Samba shares via an MS Windows client machine, and create an FTP server to transfer files from another machine.
- © Lab Duration 30-40 minutes {e Requirements e Knowledge of FTP commands.
- {e Requirements e Knowledge of FTP commands. e Knowledge of the Samba protocol. e Working knowledge of operating systems.
- | Resources e¢ Environment & Tools o VirtualBox =" Debian

## Zadania / etapy

1. Lab Task 1: Samba Setup In this task you will install the Samba service in the Debian VM. 1 Open the terminal in the Debian machine and use the command su — to switch to the root user.
2. Lab Task 2: Connect to the Share In this task you will connect to the directory shared in Debian from a Windows machine. Use an existing Windows machine (virtual or host). If you don’t have a Windows machine, follow the Windows 10 installation guide to create one.
3. Lab Task 3: Install the FTP Server Create an FTP server and transfer files to it. 1 Inthe Debian machine, use the command apt install ftp -y to install the FTP service.
4. Lab Task 4: Connect to the FTP Server In this task you will connect from the Windows machine to the FTP service installed on the Debian machine. 1 Inthe Windows machine, open the CMD.
5. Lab Task 4: Connect to the FTP Server In this task you will connect from the Windows machine to the FTP service installed on the Debian machine. 1. Inthe Windows machine, open the CMD.

## Komendy występujące w labie

```text
read only = no - if users can write to the share
apt install samba -y |
read only = no
smbpasswd -a john
service smbd restart |
service smbd status
IP Network
ip a
Jf
Ping statistics for 192.168.1.12:
apt install ftp -y |
apt install vsftpd -y |
nano /etc/vsftpd.conf |
chmod a+w /home/john/
ls -l /home/
service vsftpd restart
service vsftpd status
ls -l /home/john
```

## Powiązana teoria

- [Samba](../05-services-hardening/samba.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 286:** Linux Security

Lab Assignment Services and

Hardening

LNX-05-L2

Install and Configure Samba

°Arr

"OIF and FTP

E-

All Rights Reserved.

**PDF s. 287:** Linux Security

Lab Assignment Services and

Hardening

LNX-05-L2

Install and Configure Samba

°Arr

"OIF and FTP

E-

All Rights Reserved.

**PDF s. 288:** G Lab Objective

Understand how to transfer files between Windows and Linux using Samba and FTP.

La Lab Mission

Perform a basic configuration of Samba, provide access to Samba shares via an MS

Windows client machine, and create an FTP server to transfer files from another

machine.

x .

© Lab Duration

30-40 minutes

{e Requirements

e Knowledge of FTP commands.

e Knowledge of the Samba protocol.

e Working knowledge of operating systems.

Lt

| Resources

e¢ Environment & Tools

o VirtualBox

=" Debian

o Windows

**PDF s. 289:** Lab Task 1: Samba Setup

In this task you will install the Samba service in the Debian VM.

1 Open the terminal in the Debian machine and use the command su — to switch to

the root user.

2 Use the command apt install samba -y to install the Samba service.

3 Use the command nano /etc/samba/smb.conf to access the service

configuration file.

4 Scroll to the end of the file and add the following information:

[Files] - the name of the share

comment = my files - brief comment describing the share

path = /home/<your user> - absolute path to the share

browsable = yes - if users can browse to the share

read only = no - if users can write to the share

guest ok = yes - if guests can access the share

Save and exit the file.

5 Use the command smbpasswd -a <user> to add your user the smb service.

Enter a new password when asked.

6 Use the command service smbd restart to activate the service.

Use the command service smbd status to verify that it is active.

**PDF s. 290:** Lab Task 2: Connect to the Share

In this task you will connect to the directory shared in Debian from a Windows machine.

Use an existing Windows machine (virtual or host). If you don’t have a Windows

machine, follow the Windows 10 installation guide to create one.

Note: If you install a new Windows VM, follow only the first three procedures in the

installation guide.

1 Open your Windows VM settings by right-clicking the VM and selecting Settings...

2 Inthe settings window, navigate to Network and make sure the adapter is set to

Bridged Adapter.

3 In your Debian machine, use the command ip a to check its IP address.

4 Open the CMD in the Windows machine.

5 Use the command ping <Debian IP> to verify that both machines can

communicate.

6 Open the File Explorer in Windows and insert the path to Debian's shared file as

follows: \\<IP>\Files.

**PDF s. 291:** Lab Task 3: Install the FTP Server

Create an FTP server and transfer files to it.

1 Inthe Debian machine, use the command apt install ftp -y to install the FTP

service.

2 Use the command apt install vsftpd -y to install the VSFTPD service.

3 Use the command nano /etc/vsftpd.conf to open the services configuration file.

4 Use Ctrl + w to search for the option write_enable = YES and uncomment it. This

option enables uploading files to Debian.

5 Use Ctrl + w to search for the option chroot_local_user=YES and uncomment it.

This option prevents all local users from leaving their home directory.

6 Add to the end of the file the option allow_writeable_chroot=YES and

uncomment it. This option bypasses the check for write permission in the vsftpd

config file.

Save and exit the file.

7 Use the command chmod a+w /home/<your user> to provide everyone with

write permission to your home directory. Verify it with the command Is -I /home/

8 Use the command service vsftpd restart to restart the service. Then use the

command service vsftpd status to verify that the service is active.

**PDF s. 292:** Lab Task 4: Connect to the FTP Server

In this task you will connect from the Windows machine to the FTP service installed on

the Debian machine.

1 Inthe Windows machine, open the CMD.

2 Use the command echo "Hello World" > ftpTransfer.txt to create a new file with

the text "Hello World".

3 Inthe CMD use the command dir to verify that the file was created.

4 Inthe CMD use the command ftp <Debian IP> to open the connection to the FTP

server. Specify your user name and password when requested.

5 Use the command put ftpTransfer.txt to upload the file ftpTransfer.txt to the FTP

server.

6 Inthe Debian machine, check if the file exists in your home directory by running

the command Is -I /home/[user].

**PDF s. 293:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS2

Install and Configure Samba

°Arr

"OIF and FTP

E-

All Rights Reserved.

**PDF s. 294:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS2

Install and Configure Samba

°Arr

"OIF and FTP

E-

All Rights Reserved.

**PDF s. 295:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to transfer files between Windows and Linux using Samba and FTP.

bs) Lab Mission

Perform a basic configuration of Samba, provide access to Samba shares via an MS

Windows client machine, and create an FTP server to transfer files from another

machine.

ea rl

©) Lab Duration

30-40 minutes

fe Requirements

e Knowledge of FTP commands.

e Knowledge of the Samba protocol.

e Working knowledge of operating systems.

os

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

o Windows

**PDF s. 296:** Lab Task 1: Samba Setup

In this task you will install the Samba service in the Debian VM.

1 Open the terminal in the Debian machine and use the command su — to switch to

the root user.

john@debian: ~ x

File Edit View Search Terminal Help

i~$ su -

Password:

root@debian:~#

2 Use the command apt install samba -y to install the Samba service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install samba -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

3 Use the command nano /etc/samba/smb.conf to access the service

configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

rootGdebian:~# nano /etc/samba/smb. conf |

**PDF s. 297:** 4 Scroll to the end of the file and add the following information:

[Files] - the name of the share

comment = my files - brief comment describing the share

path = /home/<your user> - absolute path to the share

browsable = yes - if users can browse to the share

read only = no - if users can write to the share

guest ok = yes - if guests can access the share

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/samba/smb. cont Modified

$

$

$

$

5 write List = root, @lpadmin

[Files]

comment = my files

path = /home/john

browsable = yes

read only = no

guest ok = yes

Mg Get Help @ Write out Mi) Where Is @i¢ Cut Text

@y Exit Mil Read File @N Replace @™ Uncut Text

**PDF s. 298:** 5 Use the command smbpasswd -a <user> to add your user the smb service.

Enter a new password when asked.

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# smbpasswd -a john

New SMB password:

Retype new SMB password:

Added user john.

root@debian:~#

6 Use the command service smbd restart to activate the service.

Use the command service smbd status to verify that it is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service smbd restart |

root@debian:~# service smbd status

smbd.service - Samba SMB Daemon

Loaded: loaded (/lib/systemd/system/smbd.service; en

Active: since Wed 2020-09-30 05:24:

Docs: man:smbd(8)

**PDF s. 299:** Lab Task 2: Connect to the Share

In this task you will connect to the directory shared in Debian from a Windows machine.

Use an existing Windows machine (virtual or host). If you don’t have a Windows

machine, follow the Windows 10 installation guide to create one.

Note: If you install a new Windows VM, follow only the first three procedures in the

installation guide.

1 Open your Windows VM settings by right-clicking the VM and selecting Settings...

@ Orecle VM VirtualBox Manager - ao x

Fle Machine Snapshot Help

tid — a2 Smo 822.

ia Name —— i : Taken

@ > Rurning = Current State

g ‘CentOS (Snapshot 1)

© Ponered OF

a

fo ee aay

cone cts0

D show

MW Pause

© Reset

(¥en , Take Reset

**PDF s. 300:** 2 Inthe settings window, navigate to Network and make sure the adapter is set to

Bridged Adapter.

© Windows 10 - Settings ? x

[BB General Network

[=| Systern Adapter 1 © Adapter2 © Adapter3 © Adapter 4

I) disptay Enable Network Adapter

Name: Realtek Gaming GbE Family Controller ~

& Sudo D Advanced

IP Network

£39 serie! Ponts

s&s USB

[7 Shared Folders

ic User Interface

[a] | cert

**PDF s. 301:** 3 Inyour Debian machine, use the command ip a to check its IP address.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ip a

1: lo: <LOOPBACK,UP,LOWER UP> mtu 65536 qdisc noqueue state UNKNOWN gro

up default qlen 1000

link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

inet 127.0.0.1/8 scope host lo

valid lft forever preferred lft forever

inet6 ::1/128 scope host

valid lft forever preferred lft forever

2: enpOs3: <BROADCAST,MULTICAST,UP,LOWER UP> mtu 1500 qdisc pfifo fast

state UP group default qlen 1000

link/ether 08:00:27:6d:00:ff brd ff: ff:ff:ff:ff:ff

inet 192.168.1.12/24 brd 192.168.1.255 scope global dynamic enpQs3

valid lft 2993sec preferred lft 2993sec

inet6 2a00:a040:19c:a2e7:a82a:7cb9:a720:5abd/64 scope global tempor

ary dynamic

valid lft 602587sec preferred lft 83892sec

inet6 2a00:a040:19c:a2e7:a00:27ff:fe6d:ff/64 scope global dynamic m

ngtmpaddr noprefixroute

valid lft 808165sec preferred lft 330575sec

inet6 fe80::a00:27ff:fe6d:ff/64 scope Link noprefixroute

valid_lft forever preferred lft forever

root@debian:~# Jf

**PDF s. 302:** 4 Open the CMD in the Windows machine.

= Command Prompt

Ee

a Web

e Be =

> oe ” =

9 emd commands

2 cmd 5

PD emda [

emda devotions

2 cmd markciown _———

=

o Ete 2 web

= o = a 0) Fl granu

**PDF s. 303:** 5 Use the command ping <Debian IP> to verify that both machines can

communicate.

BEY Command Prompt - Oo x

Microsoft Windows [Version 16.0.16246] “

(c) 2615 Microsoft Corporation. All rights reserved.

C:\Users\John>ping 192.168.1.12

Pinging 192.168.1.12 with 32 bytes of data:

Reply from 192.168.1.12: bytes=32 time<ims TTL=64

Reply from 192.168.1.12: bytes=32 time-ims TTL=64

Reply from 192.168.1.12: bytes-32 time<ims TTL-64

Reply from 192.168.1.12: bytes=32 time<ims TTL=64

Ping statistics for 192.168.1.12:

Packets: Sent = 4, Received = 4, Lost = @ (6% loss),

Approximate round trip times in milli-seconds:

Minimum = @ms, Maximum = ims, Average = Oms

Cc: \Users\John>,

v

6 Open the File Explorer in Windows and insert the path to Debian's shared file as

follows: \\<IP>\Files.

Bl & Oj = Fites - Oo x

PP ome share View e

a isis Name “ Date modified yee see

I Desktop [1 Desktop 9/19/2020 3:50AM File folder

§ Downloads [1 Documents 9/28/2020 10:37 PM File folder

Be iscumedis a Downloads 9/19/2020 3:50AM File folder

Music 9/19/2020 5:21AM File folder

=] Pictures ; Seaman mise

( Pictures 9/19/2020 3:50AM File folder

oD Music (1 Pubic 9/19/2020 2:50AM File Folder

IB Videos | Templates 9/19/2020 3:50AM File folder

Pore Gites 9/29/2020 12:14AM File folder

(1) Videos 9/19/20203:50AM File folder

Gi This Pc file 9/28/2020 11:40 PM Text Document 1KB

ge testfile 9/30/2099 1:20AM File 1 KB

11 items Ee

**PDF s. 304:** Lab Task 3: Install the FTP Server

Create an FTP server and transfer files to it.

1 Inthe Debian machine, use the command apt install ftp -y to install the FTP

service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install ftp -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and are no lo

2 Use the command apt install vsftpd -y to install the VSFTPD service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install vsftpd -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and are no lo

3 Use the command nano /etc/vsftpd.conf to open the services configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/vsftpd.conf |

**PDF s. 305:** 4 Use Ctrl + w to search for the option write_enable = YES and uncomment it. This

option enables uploading files to Debian.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/vsftpd. conf Modified

anonymous_enable=NO

Local_enable=YES

write enable=YES

$

[ Search Wrapped ]

fq Get Help gi Write Out @i) Where Is @ Cut Text ga) Justify

Exit ij Read File gy Replace YJ Uncut Textggy To Spell

**PDF s. 306:** 5 Use Ctrl + w to search for the option chroot_local_user=YES and uncomment it.

This option prevents all local users from leaving their home directory.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/vsftpd.cont Modified

$

chroot_local_user=YES

$

$

@e Get Help gi) Write Out gf Where Is gia Cut Text (a) Justify

Wy Exit Mi) Read File gy Replace gl Uncut Textggj To Spell

**PDF s. 307:** 6 Add to the end of the file the option allow_writeable_chroot=YES and

uncomment it. This option bypasses the check for write permission in the vsftpd

config file.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/vsftpd. conf Modified

rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem

rsa_private_key file=/etc/ssl/private/ssl-cert-snakeoil. key

ssl_enable=NO

allow_writeable_chroot=YES

Get Help @ write out @y Where Is QM cut Text [M) Justify

Exit i Read File gy Replace gj Uncut Text To Spell

7 Use the command chmod a+w /home/<your user> to provide everyone with

write permission to your home directory. Verify it with the command Is -I /home/

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# chmod a+w /home/john/

root@debian:~# ls -l /home/

total 8

drwxr-xr-x 2 jane jane 4096 Sep 29 03:13 jane

drwxrwxrwx 17 john john 4696 Sep 30 06:06 john

root@debian:~#

**PDF s. 308:** 8 Use the command service vsftpd restart to restart the service. Then use the

command service vsftpd status to verify that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service vsftpd restart

root@debian:~# service vsftpd status

vsftpd.service - vsftpd FTP server

Loaded: loaded (/lib/systemd/system/vsftpd.service; enabled; v

Active: since Wed 2020-09-30 06:22:55 EDT; 29

Process: 3020 ExecStartPre=/bin/mkdir -p /var/run/vsftpd/empty

Msin DTM: 32A91 fweftnA\

**PDF s. 309:** Lab Task 4: Connect to the FTP Server

In this task you will connect from the Windows machine to the FTP service installed on

the Debian machine.

1. Inthe Windows machine, open the CMD.

= Fae

Desktop app

a web

e Bia ir

P emder

Fs

2 ema commands

Pema

2 mda

DP cemda devotions

emd markdown

O Eterg 2D Web

= oernma 0) gaan

2 Use the command echo "Hello World" > ftpTransfer.txt to create a new file with

the text "Hello World".

EH Command Prompt - oa x

[ licrosoft Windows [Version 1¢.6.16240] a

IC: \Users\John>echo “Hello World" > ftpTransfer.txt

lc: \Users\John

¥v

**PDF s. 310:** 3 Inthe CMD use the command dir to verify that the file was created.

BH Command Prompt - a x

A

iC: \Users\John>dir

Volume in drive C has no label.

Volume Serial Number is CAC7-9E44

Directory of C:\Users\John

09/30/2026 @3:27 AM <DIR> =

09/30/2026 62:46 AM <DIR> Contacts

09/30/2026 62:46 AM <DIR> Documents

09/30/2026 62:46 AM <DIR> Downloads

69/30/2026 3:27 AM 16 ftptransfer.txt

09/30/2020 @2:46 AM <DIR> Music

09/30/2826 62:49 AM <DIR> OneDrive

09/30/2026 62:47 AM <DIR> Pictures

09/30/2026 @2:47 AM <DIR> Searches

09/30/2026 62:46 AM <DIR> Videos

1 File(s) 16 bytes

IC: \Users\John>

¥

4 Inthe CMD use the command ftp <Debian IP> to open the connection to the FTP

server. Specify your user name and password when requested.

es

A

Connected to 192.168.1.12.

Jser (192.168.1.12:(none)): john

331 Please specify the password.

238 Login successful.

Ft p> bs

**PDF s. 311:** 5 Use the command put ftpTransfer.txt to upload the file ftpTransfer.txt to the FTP

server.

[BH Command Prompt - ftp 192.168.1.12 + oO x

User (192.168.1.12:(none)): john A

331 Please specify the password.

Password:

23@ Login successful.

158 Ok to send data.

Ft p> oe

6 Inthe Debian machine, check if the file exists in your home directory by running

the command Is -I /home/[user].

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ls -l /home/john

total 48

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Desktop

drwxr-xr-x 3 john john 4096 Sep 29 01:37 Documents

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Downloads

-rw-rw-rw- 1 john john 45 Sep 29 02:40 file.txt

-fW------- 1 john john 16 Sep 30 06:33 ftpTransfer.txt

drwxr-xr-x 5 john john 4096 Sep 19 08:21 Music

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Pictures

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Public

drwxr-xr-x 2 john john 4096 Sep 19 06:50 Templates

drwxr-xr-x 2 john john 4096 Sep 29 03:14 test

-rw-r--r-- 1 john john 10 Sep 30 04:20 testFile

drwxr-xr-x 2 john john 4096 Sep 19 66:50 Videos

root@debian:~#

</details>
