# LNX-05-L1 — Install and Configure SSH

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 268–285.

## Cel, misja i środowisko

- G Lab Objective Understand how to configure a new virtual machine in VirtualBox and how to transfer a file via SCP. * Lab Mission
- * Lab Mission Install the SSH service for remote connection, use Secure Copy Protocol (SCP) to transfer files, and work with the Ubuntu Linux distribution. ea rl
- ©) Lab Duration 40-50 minutes fe Requirements e Practical experience with the APT package manager
- fe Requirements e Practical experience with the APT package manager e Knowledge of networking configuration e Knowledge of SSH commands
- | Resources ¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Install SSH and Work with SSH and SCP Facilitate communication between two Linux clients using Secure Shell (SSH). 1 Open the terminal and use the command su - to switch to the root user. 2 Use the command apt update
2. Lab Task 2: Debian Network Configuration In this task, you will verify that Debian is in bridged mode and is connected to the internet. 1 Click Devices in the VM menu, select Network, and click Network Settings... to
3. Lab Task 3: Ubuntu Installation Use the Ubuntu 20.04 installation guide to create a new Ubuntu machine for use throughout the course. Note: When you reach step 15 in the installation guide, click Try Ubuntu instead of
4. Lab Task 4: File Creation and Transfer In this task, you will create a file on the Ubuntu machine and transfer it to the Debian machine. 1 Open the terminal in the same way you open it in Debian. Use the command
5. Lab Task 1: Install SSH and Work with SSH and SCP Facilitate communication between two Linux clients using Secure Shell (SSH). 1 Open the terminal and use the command su - to switch to the root user. john@debian: ~ x
6. Lab Task 4: File Creation and Transfer In this task, you will create a file on the Ubuntu machine and transfer it to the Debian machine. 1. Open the terminal in the same way you open it in Debian. Use the command

## Komendy występujące w labie

```text
echo "test text" > testFile to create a new file with the text test text.
apt update |
apt install ssh -y |
service ssh start |
service ssh status
rm /etc/network/interfaces.d/enp0s3
dhclient -r
dhclient
ip a
```

## Powiązana teoria

- [Ssh Scp](../05-services-hardening/ssh-scp.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 268:** Linux Security

Lab Assignment Services and

Hardening

LNX-05-L1

AO iets Install and Configure SSH

Olin

El

All Rights Reserved.

**PDF s. 269:** Linux Security

Lab Assignment Services and

Hardening

LNX-05-L1

AO iets Install and Configure SSH

Olin

El

All Rights Reserved.

**PDF s. 270:** G Lab Objective

Understand how to configure a new virtual machine in VirtualBox and how to transfer a

file via SCP.

* Lab Mission

Install the SSH service for remote connection, use Secure Copy Protocol (SCP) to

transfer files, and work with the Ubuntu Linux distribution.

ea rl

©) Lab Duration

40-50 minutes

fe Requirements

e Practical experience with the APT package manager

e Knowledge of networking configuration

e Knowledge of SSH commands

Lt

| Resources

¢ Environment & Tools

o VirtualBox

= Debian

= Ubuntu 20.04

o SSH

**PDF s. 271:** Lab Task 1: Install SSH and Work with SSH and SCP

Facilitate communication between two Linux clients using Secure Shell (SSH).

1 Open the terminal and use the command su - to switch to the root user.

2 Use the command apt update

3 Use the command apt install ssh -y to install the SSH service.

4 Use the command service ssh start to start the SSH service. Verify that SSH is

running and active using the command service ssh status

**PDF s. 272:** Lab Task 2: Debian Network Configuration

In this task, you will verify that Debian is in bridged mode and is connected to the

internet.

1 Click Devices in the VM menu, select Network, and click Network Settings... to

open the network configuration window.

2 Select the Bridged Adapter option and click OK.

3 Use the command rm /etc/network/interfaces.d/enpOs3 to remove the static IP

address configuration file created in a previous lab.

4 Inthe terminal, use the command dhclient -r to release the machine's current IP

address.

5 Use the command dhclient to request a new IP address.

6 Use the command ip a to verify the IP address of your local machine. Verify that

the Debian machine received an appropriate IP address on the local network.

**PDF s. 273:** Lab Task 3: Ubuntu Installation

Use the Ubuntu 20.04 installation guide to create a new Ubuntu machine for use

throughout the course.

Note: When you reach step 15 in the installation guide, click Try Ubuntu instead of

Install Ubuntu.

**PDF s. 274:** Lab Task 4: File Creation and Transfer

In this task, you will create a file on the Ubuntu machine and transfer it to the Debian

machine.

1 Open the terminal in the same way you open it in Debian. Use the command

echo "test text" > testFile to create a new file with the text test text.

2 Use the command sep testFile <user>@<ip address>:~/ to transfer the file from

Ubuntu to your home directory on the Debian machine via SCP (use the IP

address from step 4 above). Type yes when asked to connect and provide your

password.

3. Onthe Debian machine, navigate to your home directory and verify that the file

was transferred using the command Is

**PDF s. 275:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS1

AO iets Install and Configure SSH

Olin

El

All Rights Reserved.

**PDF s. 276:** Linux Security

Lab Assignment Services and

& Solution Hardening

LNX-05-LS1

AO iets Install and Configure SSH

Olin

El

All Rights Reserved.

**PDF s. 277:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to configure a new virtual machine in VirtualBox and how to transfer a

file via SCP.

5 Lab Mission

Install the SSH service for remote connection, use Secure Copy Protocol (SCP) to

transfer files, and work with the Ubuntu Linux distribution.

ea 7

©) Lab Duration

40-50 minutes

tC) Requirements

e Practical experience with the APT package manager

e Knowledge of networking configuration

e Knowledge of SSH commands

oo

| Resources

e¢ Environment & Tools

o VirtualBox

= Debian

= Ubuntu 20.04

o SSH

**PDF s. 278:** Lab Task 1: Install SSH and Work with SSH and SCP

Facilitate communication between two Linux clients using Secure Shell (SSH).

1 Open the terminal and use the command su - to switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Help

i~$ su -

Password:

root@debian: ~#

2 Use the command apt update

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt update |

3. Use the command apt install ssh -y to install the SSH service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# apt install ssh -y |

Reading package lists... Done

Building dependency tree

Reading state information... Done

The following packages were automatically installed and are no lo

nger required:

enn 8 hunhan anc Tihacan& lihe daw hin liharcr & daw

**PDF s. 279:** 4 Use the command service ssh start to start the SSH service. Verify that SSH is

running and active using the command service ssh status

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# service ssh start |

root@debian:~# service ssh status

ssh.service - OpenBSD Secure Shell server

Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vend

Active: since Wed 2020-09-30 03:11:02 EDT; 1m

Docs: man:sshd(8)

man:sshd_config(5)

(heels lel Se ae

**PDF s. 280:** Lab Task 2: Debian Network Configuration

In this task, you will verify that Debian is in bridged mode and is connected to the

internet.

1 Click Devices in the VM menu, select Network, and click Network Settings... to

open the network configuration window.

§@ Debian [Running] - Oracle VM VirtualBox - ia x

File Machine View Input Devices | Help

@ Optical Drives » a 0) Or

1B Audio »

EP Network » Network Settings...

OC use p=

Connect Network Adapter

[7 Shared Folders >

[1 Shared Clipboard rs

[4 Drag and Drop >

A Insert Guest Additions CD image...

e

cs)

Wednesday, September 30

5) CFiles.

Display virtual machine settings window to configure network adapters OUST GEMS Broncn

**PDF s. 281:** 2 Select the Bridged Adapter option and click OK.

[ cenerai Network

[=] System Adapter 1 Adapter2 © Adapter3 Adapter 4

[_} Display Enable Network Adapter

Name: Realtek Gaming GbE Family Controller =

Dp Audio D Advanced

[Ee Network

S Serial Ports

e USB

[7 Shared Folders

FF] user interface

3 Use the command rm /etc/network/interfaces.d/enpOs3 to remove the static IP

address configuration file created in a previous lab.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# rm /etc/network/interfaces.d/enp0s3

root@debian:-~#

**PDF s. 282:** 4 Inthe terminal, use the command dhclient -r to release the machine's current IP

address.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# dhclient -r

root@debian:~#

5 Use the command dhclient to request a new IP address.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# dhclient

root@debian: ~#

6 Use the command ip a to verify the IP address of your local machine. Verify that

the Debian machine received an appropriate IP address on the local network.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:-# ip a

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN gro

up default qlen 1000

link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

inet 127.0.0.1/8 scope host lo

valid lft forever preferred lft forever

inet6 ::1/128 scope host

valid_lft forever preferred_lft forever

2: enpOs3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast

state UP group default qlen 1000

link/ether 08:00:27:6d:00:ff brd ff:ff:ff:ff: ff: ff

inet 192.168.1.12/24 brd 192.168.1.255 scope global dynamic enp0s3

valid lft 3598sec preferred lft 3598sec

inet6 2a00:a040;19c:a2e7:a00:27ff:fe6d:ff/64 scope global dynamic m

ngtmpaddr

valid_lft 808166sec preferred lft 330576sec

inet6 fe80::a00:27ff:fe6d:ff/64 scope link

valid lft forever preferred lft forever

root@debian:~#

**PDF s. 283:** Lab Task 3: Ubuntu Installation

Use the Ubuntu 20.04 installation guide to create a new Ubuntu machine for use

throughout the course.

Note: When you reach step 15 in the installation guide, click Try Ubuntu instead of

Install Ubuntu.

‘ura te Auto captre keyboard soto ted. Tesi he ral Macune aonatalycapturetelayooadevey sree (3°) |

> Oe 7

“Le uO at OS ppt wee yor titration’ Tins Pujol de teed apnoea aE)

Welcome

Espanol =

Esperanto

Euskara

Gaeilge

Galego

Hrvatski ZZ

fslenska

Italiano Install Ubuntu

Kurd

heres You can try Ubuntu without making any changes to your computer, directly From

Lietuviskai this CD.

aca Orif you're ready, you can install Ubuntu alongside (or instead of) your current

Nederlands operating system. This shouldn't take too tong

No localization (UTF-8)

Norsk bokmal

BeueoreH#oowunn

**PDF s. 284:** Lab Task 4: File Creation and Transfer

In this task, you will create a file on the Ubuntu machine and transfer it to the Debian

machine.

1. Open the terminal in the same way you open it in Debian. Use the command

echo "test text" > testFile to create a new file with the text test text.

seal ubuntu@ubuntu: ~ ol = = oO Pe

t~$ echo "test text" > testFile

i~$

2 Use the command sep testFile <user>@<ip address>:~/ to transfer the file from

Ubuntu to your home directory on the Debian machine via SCP (use the IP

address from step 4 above). Type yes when asked to connect and provide your

password.

Bl ubuntu@ubuntu: ~ au f= = Oo x

:~§ scp testFile john@192.168.1.12:~/

The authenticity of host '192.168.1.12 (192.168.1.12)' can't be estab

lished.

ECDSA key fingerprint is SHA256:oSPIxfWmHOOhr 2EDfujq&Qy9oucF2WmgmL/CS

Um4N40.

Are you sure you want to continue connecting (yes/no/[fingerprint])?

yes

Warning: Permanently added '192.168.1.12' (ECDSA) to the list of know

n hosts.

john@192.168.1.12's password:

testFile 100% 16 16.3KB/s 00:00

Sf

**PDF s. 285:** 3. Onthe Debian machine, navigate to your home directory and verify that the file

was transferred using the command Is

john@debian: ~ x

File Edit View Search Terminal Help

i~$ 1s

file.txt testFile

i~$

</details>
