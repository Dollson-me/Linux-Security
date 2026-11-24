# LNX-05-L3 — Securing Services

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 312–348.

## Cel, misja i środowisko

- G Lab Objective Understand how to harden and secure SSH and FTP, and how to back up the Samba configuration file. be Lab Mission
- be Lab Mission Make existing installed services more secure and less vulnerable, and learn about Windows tools. ea rl
- ©) Lab Duration 40-50 minutes tC) Requirements e General knowledge of commands.
- tC) Requirements e General knowledge of commands. e Knowledge of system-related commands. oo
- | Resources ¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: SSH Hardening Enhance and secure SSH by setting connection limitations and port configuration. Before starting, make sure the Windows host and Debian VMs are turned on, and have connectivity with each other and the internet.
2. Lab Task 2: FTP Hardening Change the port number for the FTP connection, and connect using FileZilla. 1 Copy the FileZilla installation file to your Windows machine and double-click it. 2 Click Yes when asked to allow changes.
3. Lab Task 3: Samba Hardening Back up the Samba configuration file. 1 Inthe Debian VM use the command nano /etc/ samba/smb.conf to open the service's configuration file.
4. Lab Task 2: FTP Hardening Change the port number for the FTP connection, and connect using FileZilla. 1 Copy the FileZilla installation file to your Windows machine and double-click it. ga

## Komendy występujące w labie

```text
service vsftpd status to verify that the service is active.
locate it, add it in the file.
IP Network
fj
service ssh start |
service ssh status
ip a
Jf
SSH
nano /etc/ssh/sshd_confiof |
service ssh restart |
nano /etc/ssh/sshd_configff |
service vsftpd start |
service vsftpd status
nano /etc/vsftpd. conf I |
service vsftpd restart
nano /etc/samba/smb. conf |
read only = no
service smbd restart
service smbd status
read only = yes
```

## Powiązana teoria

- [Service Hardening](../05-services-hardening/service-hardening.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 312:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-L3

Roi tsts, Securing Services

oOln

EI

All Rights Reserved.

**PDF s. 313:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-L3

Roi tsts, Securing Services

oOln

EI

All Rights Reserved.

**PDF s. 314:** G Lab Objective

Understand how to harden and secure SSH and FTP, and how to back up the Samba

configuration file.

be Lab Mission

Make existing installed services more secure and less vulnerable, and learn about

Windows tools.

ea rl

©) Lab Duration

40-50 minutes

tC) Requirements

e General knowledge of commands.

e Knowledge of system-related commands.

oo

| Resources

¢ Environment & Tools

o VirtualBox

= Debian

o Windows

e Extra Lab Files

o Putty.zip

o FileZilla_3.50.0_win64_sponsored-setup.zip

**PDF s. 315:** Lab Task 1: SSH Hardening

Enhance and secure SSH by setting connection limitations and port configuration.

Before starting, make sure the Windows host and Debian VMs are turned on, and have

connectivity with each other and the internet.

1 Follow the "Installing Guest Additions” section in the Windows 10 installation

guide to install guest additions in your Windows VM.

2. Make sure the NIC in both the Debian and Windows machines is set to Bridged

Adapter.

3. Open the terminal in Debian and use the command su — to switch to the root

user.

4 Use the command service ssh start to start SSH service. Verify that it is active

using the command service ssh status.

5 Copy the provided Putty.exe file to the Windows machine.

6 Check the IP address in your Debian machine using the command ip a.

7 Inthe Windows machine double-click putty to start it. Insert Debian's IP address

on port 22, and click Open to open a connection via SSH.

8 Click Yes in the Security Alert window.

9 Provide the name and password of your Debian user, and verify that the

connection is established.

10 Close the SSH connection.

11 Inthe Debian machine use the command nano /etc/ssh/sshd_config to open the

service's configuration file.

12 Use Ctrl + wto search for the word “port”. Uncomment it and change the

number to 4567. This will change the connection port to the service.

**PDF s. 316:** Save and exit the file.

13 Use the command service ssh restart, and then use service ssh status to verify

that the service is active.

14 Open Putty again and connect this time to port 4567.

15 Click Yes in the alert window.

16 Provide your user name, but then insert an incorrect password six times and

note the error message.

17 Inthe Debian machine use the command nano /etc/ssh/sshd_config to open

the service's configuration file.

18 Use Ctrl + wto search for the word "MaxAuthTries". Uncomment it and change

the number to 3. This will change number of permitted login attempts.

Save and exit the file.

19 Use the command service ssh restart, and then use service ssh status to verify

that the service is active.

20 Connect again to the SSH service via Putty and verify that the login failure count

was updated.

21 Setting back to default port 22 from 4567. Type nano /etc/ssh/sshd_config and

change the port number to 22 with a hashtag to have the default value.

Important: Read the blue text.

**PDF s. 317:** Lab Task 2: FTP Hardening

Change the port number for the FTP connection, and connect using FileZilla.

1 Copy the FileZilla installation file to your Windows machine and double-click it.

2 Click Yes when asked to allow changes.

3 Click | Agree for the license agreement.

4 Make sure "Anyone who uses this computer (all users)" is selected and click Next.

5 Check all the component boxes for installation, and click Next.

6 Set the destination for the installation, and click Next.

7 Click Next in the Start Menu Folder selection window.

8 Select "Start FileZilla now" and click Finish.

9 Use the command service vsftpd start to start the FTP server, and then use

service vsftpd status to verify that the service is active.

10 Inthe FileZilla host field, enter the IP address of the Debian machine, and then

enter your user name and password. Leave the port area empty and click

Quickconnect.

11 Inthe “Remember passwords?” window, select Save passwords and click OK.

12 Inthe “Insecure FTP connection” window, click OK.

Note: The right side of FileZilla is for Debian files, the left side is the Windows

host.

13 In the Debian VM use the command nano /etc/vsftpd.conf to open the service's

configuration file.

**PDF s. 318:** 14 Use Ctrl + wto search for "listen_port=21" and change it to 201. If you can’t

locate it, add it in the file.

Save and exit the file.

15 Use the command service vsftpd restart to restart the vsftpd service and verify

that it is running using the command service vsftpd status.

16 Establish a new connection via FileZilla on port 201.

17 Setting back to default port 21 from 201, nano /etc/vsftpd. Remove the

Listen_port=201 to set vsftpd back to default. Important: Read the blue text.

**PDF s. 319:** Lab Task 3: Samba Hardening

Back up the Samba configuration file.

1 Inthe Debian VM use the command nano /etc/ samba/smb.conf to open the

service's configuration file.

2 At the bottom of the file, change the option guest ok to no. This will prevent

anyone from connecting to the share without providing credentials.

Save and exit the file.

3 Use the command service smbd restart, and then use service smbd status to

verify that the service is active.

4 Open the File Explorer in your Windows machine and try to access the Files share

again via \\[Debian IP]\Files.

In the window that appears requesting credentials, enter the required data and

click OK.

5 Right-click in the share and create a new folder named "Hello". Note that you can

write inside the share.

6 Inthe Debian machine, open smb's configuration file again using nano /etc/

samba/smb.conf. Go to the bottom of the page and change read only to yes.

Save and exit the file.

7 Use the command service smbd restart, and then use service smbd status to

verify that the service is active.

8 Try again to create a folder in the share from File Explorer. Note the alert saying

you need the correct permission to perform the action.

**PDF s. 320:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS3

Roi tsts, Securing Services

oOln

EI

All Rights Reserved.

**PDF s. 321:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS3

Roi tsts, Securing Services

oOln

EI

All Rights Reserved.

**PDF s. 322:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to harden and secure SSH and FTP, and how to back up the Samba

configuration file.

5 Lab Mission

Make existing installed services more secure and less vulnerable, and learn about

Windows tools.

ea 7

O) Lab Duration

40-50 minutes

fe Requirements

e General knowledge of commands.

e Knowledge of system-related commands.

Lt

| Resources

e¢ Environment & Tools

o VirtualBox

=" Debian

o Windows

e Extra Lab Files

o Putty.zip

o FileZilla_3.50.0_win64_sponsored-setup.zip

**PDF s. 323:** Lab Task 1: SSH Hardening

Enhance and secure SSH by setting connection limitations and port configuration.

Before starting, make sure the Windows host and Debian VMs are turned on, and have

connectivity with each other and the internet.

1 Follow the "Installing Guest Additions” section in the Windows 10 installation

guide to install guest additions in your Windows VM.

2. Make sure the NIC in both the Debian and Windows machines is set to Bridged

Adapter.

[BB General Network

[=| System Adapter 1 Adapter 2 Adapter 3 Adapter 4

I disptay Enable Network Adapter

Name: Realtek Gaming GbE Family Controller od

p Audio D Advanced

IP Network

£39 serie! Ponts

s USB

[7 Shared Folders

i User Interface

or

**PDF s. 324:** 3. Open the terminal in Debian and use the command su — to switch to the root

user.

john@debian: ~ x

File Edit View Search Terminal Help

:-$ su -

Password:

root@debian:~# fj

4 Use the command service ssh start to start SSH service. Verify that it is active

using the command service ssh status.

jehn@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service ssh start |

root@debian:~# service ssh status

ssh.service - OpenBSD Secure Shell server

Loaded: loaded (/lib/systemd/system/ssh.service; ena

Active: since Wed 2020-09-30 06:05:

**PDF s. 325:** 5 Copy the provided Putty.exe file to the Windows machine.

a,

g

S=

Pr o era Flo) gaya

**PDF s. 326:** 6 Check the IP address in your Debian machine using the command ip a.

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

inet 192.168.1.12/24 brd 192.168.1.255 scope global dynamic noprefi

xroute enpOs3

valid_lft 3593sec preferred_lft 3593sec

inet6 2a00:a040:19c:a2e7:e8fe:ede2:be0:a25f/64 scope global tempora

ry dynamic

valid lft 599987sec preferred lft 81441sec

inet6 2a00:a040:19c:a2e7:a00:27ff:fe6d:ff/64 scope global dynamic m

ngtmpaddr noprefixroute

valid lft 808164sec preferred lft 330574sec

inet6 fe80::a00:27ff:fe6d:ff/64 scope link noprefixroute

valid lft forever preferred lft forever

root@debian:~# Jf

**PDF s. 327:** 7 Inthe Windows machine double-click putty to start it. Insert Debian's IP address

on port 22, and click Open to open a connection via SSH.

$88 PUTTY Configuration ? x

Category

Session | Basic options for your PUTTY session |

Legging Specify the destination you want to connect to

© Teminal

abel Host Name (or IP address! Port

Ball 192.168.1.12) lz]

Features Connection type:

Window ORaw OTeinet ORlogn|@ ssh] © Serial

ala Load, save or delete a stored session

aviour

‘Traraeaioi Saved Sessions

Selection Ld

Colours

Default Set

-Connection a nes ae

Data Save

Proxy

Telnet Delete

Rlogin

SSH

Sa Close window on exit:

Oalways QNever @ Only on clean ext

**PDF s. 328:** 8 Click Yes in the Security Alert window.

PuTTY Security Alert 4

The server's host key is not cached in the registry. You

have no guarantee that the server is the computer you

think itis,

The server's ssh-ed25519 key fingerprint is:

ssh-ed25519 255 b Scr] d:2S:fesd3:7bib2:4c:aTsbbefS:22:04:48:81

If you trust this host, hit Yes to add the key ta

PuTTV's cache and carry on connecting,

If you want to carry on connecting just once, without

adding the key to the cache, hit No.

If you do not trust this host, hit Cancel to abandon the

connection.

i ay

9 Provide the name and password of your Debian user, and verify that the

connection is established.

&P john@debian: ~ - a x

Linux debian 4-19. U-T0-amded FI SMP Debian 4.19.132-1 (2020-07-24) x86 64

The programs included with the Debian GNU/Linux system are free software;

the exact distribution terms for each program are described in the

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

lpermitted by applicable law.

**PDF s. 329:** 10 Close the SSH connection.

8 «|

g@? login as: john

Linux debian 4.19.0-10-amdé4 #1 SMP Debian 4.19.132-1 (2020-07-24) x86_64

The programs included with the Debian GNU/Linux system are free software;

‘the exact distribution terms for each program are described in the

[Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent

11 Inthe Debian machine use the command nano /etc/ssh/sshd_config to open

the service's configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/ssh/sshd_confiof |

**PDF s. 330:** 12 Use Ctrl + w to search for the word “port”. Uncomment it and change the

number to 4567. This will change the connection port to the service.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/ssh/sshd_config Modified

$

Include fetc/ssh/sshd_config.d/*.conf

Port 4567

Get Help Wl write out J Where Is @M Cut Text (J Justify

Exit i Read File gy) Replace gj Uncut Text To Spell

13 Use the command service ssh restart, and then use service ssh status to verify

that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service ssh restart |

root@debian:~-# service ssh status

l@ ssh.service - OpenBSD Secure Shell server

Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vend

Active: active (running) since Wed 2020-09-30 07:37:36 EDT; 3s

**PDF s. 331:** 14 Open Putty again and connect this time to port 4567.

&& PuTTY Configuration ? x

Category:

3 Session | Basic options for your PuTTY session

i loom Specify the destination you want to connect to

Terminal ee Sl Coal :

eccrine Host Name for IP addres ort

a EX i co

H Features Connection type:

Window ORaw ©Telnet © Rlogin }@)SSH | © Serial

i =e Load, save or delete a stored session

|= Behaviour

: Translation Saved Sessions

Selection CO

Colours : 1

i Default Settings

[Connection Ek

Dis Save

Proxy =

Telnet Delete

Rlogin

f- SSH

aa Close window on exit:

OAways ©)Never @) Only on clean ext

About Halp [Open |} ances

**PDF s. 332:** 15 Click Yes in the alert window.

PuTTY Security Alert x»

The server's hast key is not cached in the registry. You

have no guarantee that the server is the computer you

think itis.

The server's ssh-ed25519 key fingerprint is:

ssh-ed25519 255 b1:9c:1d:25:ferd3:7bxb24ciaT:bb:f5:22:a4:48:81

if you trust this host, hit Ves to add the key to

PUTTY's cache and carry on connecting.

if you want to carry on connecting just once, without

adding the key to the cache, hit No.

if you do not trust this host, hit Cancel to abandon the

connection.

16 Provide your user name, but then insert an incorrect password six times and

note the error message.

g@ login as: john

@ john@192.168.1.12's password:

@ Access denied

@ Access denied

Fa Access denied

@ Access denied

@ Access denied

yf jonnG@192.168.1.12's password: [RAI x

Remote side sent disconnect message

type 2 (protocol error):

“Too many authentication failures"

OK

**PDF s. 333:** 17 Inthe Debian machine use the command nano /etc/ssh/sshd_config to open

the service's configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/ssh/sshd_configff |

18 Use Ctrl + w to search for the word "MaxAuthTries". Uncomment it and change

the number to 3. This will change number of permitted login attempts.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/ssh/sshd_config Modified

MaxAuthTries 3

$

$

mg Get Help gi Write Out @i) Where Is @ Cut Text ga) Justify

ey Exit i) Read File @y Replace gg Uncut Textggy To Spell

**PDF s. 334:** 19 Use the command service ssh restart, and then use service ssh status to verify

that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service ssh restart |

root@debian:~# service ssh status

ssh.service - OpenBSD Secure Shell server

Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vend

Active: ( since Wed 2020-09-30 07:37:36 EDT; 3s

20 Connect again to the SSH service via Putty and verify that the login failure count

was updated.

&

PuTTY Fatal Error x

Remote side sent disconnect message

type 2 (protocol error):

“Too many authentication failures"

21 Setting back to default port 22 from 4567. Type nano /etc/ssh/sshd_config and

change the port number to 22 with a hashtag to have the default value.

Important: Read the blue text.

**PDF s. 335:** File Edit View Search Terminal Help

GNU nano 3.2 /etc/ssh/sshd config Modified

Port 22

imo Get Help ff Write Out MM] Where Is [iN Cut Text @&] Justify me Cur Pos

ie Exit i Read File @\ Replace ey Uncut Text To Spell Go To Line

**PDF s. 336:** Lab Task 2: FTP Hardening

Change the port number for the FTP connection, and connect using FileZilla.

1 Copy the FileZilla installation file to your Windows machine and double-click it.

ga

Gg

at

|

" oenma BO) onan

2 Click Yes when asked to allow changes.

@& User Account Control x |

@ Do you want to allow this app to make changes to your

o Pc?

| Program name: FileZilla FTP Client

Verified publishen Tim Kosse

File origin: Hard drive on this computer

~) Show details No | |

**PDF s. 337:** 3 Click | Agree for the license agreement.

A FiteZilla Client 3.50.0 Setup = x

License agreement and privacy policy

Please review these terms before installing FileZilla Client 3.50.0. a

Press Page Down to see the rest of the agreement.

Table Contents: n

1A: License agreement

B: Privacy policy

ISECTION A License agreement

GNU GENERAL PUBLIC LICENSE -

If you accept the terms of this agreement and the privacy policy, dick I Agree to continue.

You must accept the agreement and privacy policy to install FileZilla Client 3.50.0.

" . ii: 2

4 Make sure "Anyone who uses this computer (all users)" is selected and click Next.

FileZilla Client 3.90.0 Setup = x

(Choose Installation Options

Who should this application be installed for? FI

Please select whether you wish to make this software available to all users or just yourself.

@ Anyone who uses this computer (all users)

© Only for me Gohn)

Installation for all users requires Administrator privileges.

oe —e| Cones

**PDF s. 338:** 5 Check all the component boxes for installation, and click Next.

FileZilla Client 3.90.0 Setup: = x

‘Choose Components

Choose which features of FileZilla Client 3.50.0 you want to install. a

Check the components you want to install and uncheck the components you don't want to

install, Click Next to continue.

Select components to install Fiezila Clent ee

Icon sets :

Language files st escri

Shell Extension

Space required: 36.5 MB.

ane ae

6 Set the destination for the installation, and click Next.

FileZilla Client 3.50.0 Setup - x

‘Choose Install Location

Choose the folder in which to install FileZilla Client 3.50.0. @

Setup will install FileZilla Client 3.50.0 in the following folder. To install in a different folder,

dick Browse and select another folder. Click Next to continue.

Destination Folder

C:\Program Files\FileZilla FTP Client | Browse...

Space required: 36.5 MB

Space available: 32.7 GB

<Back cancel

**PDF s. 339:** 7 Click Next in the Start Menu Folder selection window.

FileZilla Client 3.50.0 Setup im x

‘Choose Start Menu Folder

Choose a Start Menu folder for the FileZilla Client 3.50.0 shortcuts. Fz)

Select the Start Menu folder in which you would like to create the program's shortcuts. You

can also enter a name to create anew folder.

Accessibility

Accessories

Administrative Tools

‘Maintenance

Oracle VM VirtualBox Guest Additions

StartUp

System Tools

Windows PowerShell

(100 not create shortcuts

(Mulls Trestle 3 4 tt $$

" — " a pees,

8 Select "Start FileZilla now" and click Finish.

FileZilla Client 3.50.0 Setup =

Completing FileZilla Client 3.50.0

& Setup

FileZilla Client 3.50.0 has been installed on your computer.

Click Finish to close Setup.

**PDF s. 340:** 9 Use the command service vsftpd start to start the FTP server, and then use

service vsftpd status to verify that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service vsftpd start |

root@debian:~# service vsftpd status

vsftpd.service - vsftpd FTP server

Loaded: loaded (/lib/systemd/system/vsftpd.service; enabled; v

Active: since Wed 2020-09-30 06:22:55 EDT; lh

10 Inthe FileZilla host field, enter the IP address of the Debian machine, and then

enter your user name and password. Leave the port area empty and click

Quickconnect.

FileZilla = o x

File Edit View Transfer Server Bookmarks Help

HEP TTSIORORTIFACA

11 Inthe “Remember passwords?” window, select Save passwords and click OK.

Remember passwords? x

Would you like FileZilla to remember passwords?

When allowing FileZilla to remember passwords, you can reconnect without having to

re-enter a password after restarting FileZilla.

©)Do not save passwords

© Save passwords protected by a master password

Master password:

Repeat password:

A lost master password cannot be recovered! Please thoroughly memorize your password.

**PDF s. 341:** 12 Inthe “Insecure FTP connection” window, click OK.

Note: The right side of FileZilla is for Debian files, the left side is the Windows

host.

Insecure FTP connection x

This server does not support FTP over TLS.

If you continue, your password and files will be sent in clear over the

internet.

Host: 192.168.1.12

Port 21

(Always allow insecure plain FTP for this server.

13 In the Debian VM use the command nano /etc/vsftpd.conf to open the service's

configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/vsftpd. conf I |

**PDF s. 342:** 14 Use Ctrl + wto search for "listen_port=21" and change it to 201. If you can’t

locate it, add it in the file.

Save and exit the file.

jehn@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/vsftpd. conf Modified

$

$

Llisten_port=201

$

$

$

$

me Get Help (@ write out fi) Where Is gia Cut Text ga) Justify

el Exit ii Read File @§ Replace lj Uncut Textggj To Spell

15 Use the command service vsftpd restart to restart the vsftpd service and verify

that it is running using the command service vsftpd status.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service vsftpd restart

root@debian:~# service vsftpd status

e vsftpd.service - vsftpd FTP server

Loaded: loaded (/lib/systemd/system/vsftpd.service; enabled; v

Active: active (running) since Wed 2020-09-30 08:44:02 EDT; 3s

**PDF s. 343:** 16 Establish a new connection via FileZilla on port 201.

fips//john@'192.168.1.12:201 - FileZilla - a x

File Edit View Transfer Server Bookmarks Help:

#- (SPR Oko. Tiz=aoe

Status: Server does not support non-ASCII characters. a

Status: Logged in

Status: Retrieving directory listing.

Status: Calculating timezone offset of server...

Status: Timezone offset of server is 0 seconds.

Status: Directory listing of "/" successful v

john@192.168.1.12 x | ftp://john@192.168.1.12:201 x iti

| | Users ales a

| ieeL | All Users -/2| Desktop

© oa-| | Default Documents

© bs( | Default User Downloads

© John Music

Ete) Public v “Pictures ¥

17 Setting back to default port 21 from 201, nano /etc/vsftpd. Remove the

Listen_port=201 to set vsftpd back to default. Important: Read the blue text.

jehn@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/vsftpd.conf Modified

$

$

listen=NO

listen_port=201

$

$

$

$

Get Help Write Out @f] Where Is QM cut Text [MJ Justify

Exit @@ Read File @¥ Replace gj Uncut Textggj To Spell

**PDF s. 344:** Lab Task 3: Samba Hardening

Back up the Samba configuration file.

1 Inthe Debian VM use the command nano /etc/ samba/smb.conf to open the

service's configuration file.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/samba/smb. conf |

2 At the bottom of the file, change the option guest ok to no. This will prevent

anyone from connecting to the share without providing credentials.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/samba/smb. conf Modified

$

$

; write list = root, @lpadmin

[Files]

comment = my files

path = /home/john

browsable = yes

read only = no

guest ok = no

Get Help Write Out @J Where Is QM cut Text MJ Justify

Exit Read File gi Replace J Uncut Textgyy To Spell

**PDF s. 345:** 3 Use the command service smbd restart, and then use service smbd status to

verify that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service smbd restart

root@debian:~# service smbd status

smbd.service - Samba SMB Daemon

Loaded: loaded (/lib/systemd/system/smbd.service; enabled; ven

Active: since Wed 2020-09-30 08:57:22 EDT; 37

4 Open the File Explorer in your Windows machine and try to access the Files share

again via \\[Debian IP]\Files.

In the window that appears requesting credentials, enter the required data and

click OK.

w = | File Explorer = x

GE Home = Share = View 2)

* ~ > | Search Quick access Pp

3 Quick access ~ Freq] Windows Security * .

MM Desktop Ps

Pdounloads — ¢ Enter network credentials

zs Enter your credentials to connect to: 192.168.1.12

[B Documents ¢

=| Pictures a

D Music lien sid

iB Videos

[This Pc Domain: DESKTOP-GODDBKE

- (J Remember my credentials

o> Network ~ Rec

**PDF s. 346:** - op " u

5. Right-click in the share and create a new folder named "Hello". Note that you can

write inside the share.

2) & Oh =| Fites = Oo «x

BPM tome Share View e

€ » A Lb > Network > 192.168.1.12 > Files » ¥ & | Search Files Pp

BREA access, Name Date modified Type Size

[Ml Desktop [| Desktop 9/19/2020 3:50AM File folder

‘Downloads Documents 6/28/2020 1037 PM Filefolder

B Docs Py a Downloads: 9/19/2020 3:50 AM. File folder

ep G Music 9/19/2020 5:21 AM File folder

EI Pict *

copia (1) Pictures ‘ew. > Ber

Joe (7) Public Sorby 5 per

IB Videos (]] Templates Suny > pe

@ OneDrive : ‘a Refresh -

ideos ler

[This Pc Biftite Customize this folder... Hela 1B

a om 5] ftpTransfer Paste cument 1 KB

- Oi testrte Paste shortcut KB

1B B= | Fites - Oo x“

PPR ome Share View e

© ~ 7 Lb > Network > 192.168.1.12 > Files > ¥ ® | Search Files P

Pn Name Date modified Type Size «

[bj Desktop y/1¥/2v20 3:50 AM File folder

Hh Desktop * |) Documents 9/28/2020 10:37PM File folder

& Downloads * || Downloads 9/19/2020 3:50 AM File folder

B Documents ¢ — | | Music 9/19/20205:21 AM File folder

—— »| Bia 9/19/2020350 AM File Folder

dD Music 1) Public 9/19/2020 3:50AM File folder

Bi Viseos (1 Templates 9/19/2020 3:50 AM File folder

(test 9/29/2020 12:14AM File folder

@ OneDrive (1 Videos 9/19/20203:50 AM File folder

eis B file 9/28/2020 11-40 PM Text Document 1 KB

thie

~ (5 fptransfer 9/30/20203:33 AM Text Document 1kB

a Network oa testFile 9/30/2020 1:20 AM File 1KB

oO Hello 9/30/2020 6:03 AM File folder v

13items 1 item selected f=

**PDF s. 347:** 6 Inthe Debian machine, open smb's configuration file again using nano /etc/

samba/smb.conf. Go to the bottom of the page and change read only to yes.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/samba/smb. conf Modified

$

; write list = root, @lpadmin

[Files]

comment = my files

path = /home/john

browsable = yes

read only = yes

guest ok = no

imc Get Help (@ Write Out @ij Where Is (iN Cut Text pa] Justify

led Exit i} Read File gy Replace @! Uncut Textgyj To Spell

7 Use the command service smbd restart, and then use service smbd status to

verify that the service is active.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service smbd restart

root@debian:~# service smbd status

smbd.service - Samba SMB Daemon

Loaded: loaded (/lib/systemd/system/smbd.service; enabled; ven

Active: since Wed 2020-09-30 08:57:22 EDT; 37

**PDF s. 348:** 8 Try again to create a folder in the share from File Explorer. Note the alert saying

you need the correct permission to perform the action.

BB Ds | Fits - o Xx

GEM Home Share View e

€ » A Lb > Network > 192.168.1.12 > Files v © Search Files 2

a Quick access é x ps a

I Desktop *

& Downloads - A You need permission to perform this action

[B Documents -# ae

Pictures *

Dd Music

{B Videos

@ OneDrive -

This PC Try Again Cancel

= 1KB

& Network Pl apranter 9/30/0050333 AM Tea Document KB

i testFile 9/30/2020 1:20 AM File 1KB y

13 items eG

</details>
