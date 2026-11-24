# LNX-04-L1 — Static and Dynamic IP Configuration

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 204–217.

## Cel, misja i środowisko

- G Lab Objective Understand how to make an IP address static via the command line and use various tools to complete the lab. bs) Lab Mission
- bs) Lab Mission Become familiar with manual, static IP address configuration and learn about system network services. Ca .
- ©) Lab Duration 20-30 minutes {© Requirements e Knowledge of networking concepts
- {© Requirements e Knowledge of networking concepts e Working knowledge of text editors oo
- | Resources ¢ Environment & Tools o VirtualBox =" Debian

## Komendy występujące w labie

```text
IP Configuration
nano /etc/network/interfaces.d/enpOs3
ff
ip address
fj
ip route
Jf
touch /etc/network/interfaces.d/enp0s3
nano /etc/network/interfaces.d/enp0s3
/etc/init.d/networking stop
|
/etc/init.d/network-manager restart
/etc/init.d/networking start
ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
systemctl reboot
```

## Powiązana teoria

- [Network Configuration](../04-network-system/network-configuration.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 204:** Linux Security

and System

Management

eo inn LNX-04-L1

io) JU Static and Dynamic

yes) . .

IP Configuration

All Rights Reserved.

**PDF s. 205:** Linux Security

and System

Management

eo inn LNX-04-L1

io) JU Static and Dynamic

yes) . .

IP Configuration

All Rights Reserved.

**PDF s. 206:** G Lab Objective

Understand how to make an IP address static via the command line and use various

tools to complete the lab.

bs) Lab Mission

Become familiar with manual, static IP address configuration and learn about system

network services.

Ca .

©) Lab Duration

20-30 minutes

{© Requirements

e Knowledge of networking concepts

e Working knowledge of text editors

oo

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

© Text editors

o CLI

**PDF s. 207:** Lab Task: Make an IP Address Static

In this lab, we will change an IP address to a static IP. The first step is to gather

information about the current environment. Then, we will set a static IP that is different

from the current one. The final step will be to verify that the new IP is in place and that

there is network connectivity.

Note: In this exercise, you will change the settings of important network files. It is highly

recommended to back up each file (cp file /NewFileLocation/NewFileName) to your

home directory before working on it or using VirtualBox snapshot capabilities.

1 Open the terminal and use the su — command to switch to the user root.

2 Use the ip address command to identify the name of the NIC and the IP address

allocated to it.

3. Use the ip route command to find the address of the default gateway.

4 Use the touch /etc/network/interfaces.d/enp0s3 command to create a file

named enpOs3 in the directory /etc/network/interfaces.d/.

5 Open the file you created using the following command:

nano /etc/network/interfaces.d/enpOs3

6 Insert the following data to set up a static IP:

Important: The static IP address must be on the same subnet as the current IP

address.

auto [Nic name]

iface [NIC name] inet static

address [another IP address from the same subnet]

netmask 255.255.255.0

gateway [the default gateway]

7 Save and exit the file.

8 Use the /etc/init.d/networking stop command to stop the networking service.

**PDF s. 208:** 9 Use the /etc/init.d/network-manager restart command to restart the network-

manager service.

10 Use the /etc/init.d/networking start command to start the networking service.

11. Use the ip address command to check if the new IP address you assigned is

different than the previous IP address. Note that the IP address was changed.

12 Use the command ping 8.8.8.8 to ping IP 8.8.8.8 and check the communication

from the host to the world.

Note: Use Ctrl + c to terminate the ping.

13 Inthe terminal, run the command rm /etc/network/interfaces.d/enp0s3 to

remove the file and reset the machine to receive a DHCP IP.

14 Repeat Steps 8-10 and then restart the machine with systemctl reboot

15 After the machine has rebooted, open the terminal to run ping 8.8.8.8 and test

connectivity again.

**PDF s. 209:** Linux Security

& Solution and System

Management

eo inn LNX-04-LS1

io) JU Static and Dynamic

yes) . .

IP Configuration

All Rights Reserved.

**PDF s. 210:** Linux Security

& Solution and System

Management

eo inn LNX-04-LS1

io) JU Static and Dynamic

yes) . .

IP Configuration

All Rights Reserved.

**PDF s. 211:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to make an IP address static via the command line and use various

tools to complete the lab.

5 Lab Mission

Become familiar with manual, static IP address configuration and learn about system

network services.

Ca q

©) Lab Duration

20-30 minutes

{© Requirements

e Knowledge of networking concepts

e Working knowledge of text editors

oo

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

© Text editors

o CLI

**PDF s. 212:** Lab Task: Make an IP Address Static

In this lab, we will change an IP address to a static IP. The first step is to gather

information about the current environment. Then, we will set a static IP that is different

from the current one. The final step will be to verify that the new IP is in place and that

there is network connectivity.

Note: In this exercise, you will change the settings of important network files. It is highly

recommended to back up each file (cp file /NewFileLocation/NewFileName) to your

home directory before working on it or using VirtualBox snapshot capabilities.

1 Open the terminal and use the su — command to switch to the user root.

john@debian: ~ x

File Edit View Search Terminal Help

i~$ su -

Password:

root@debian:~# ff

2 Use the ip address command to identify the name of the NIC and the IP address

allocated to it.

Note: The IP address may be different than the one shown in the example below.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ip address

1; lo: <LOOPBACK,UP,LOWER UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1600

link/Loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

inet 127.0.9.1/8 scope host lo

valid lft forever preferred 1ft forever

inet6 ::1/128 scope host

valid_lft forever preferred_lft forever

2: enpOs3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdise pfifo fast state UP group default qlen 1000

Link/ether 08:00:27:6d:00:ff brd ff:ffiff:tf:ffitt

inet 10.0,2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enpds3

valid lft 72354sec preferred lft 72354sec

inet6 fe80::a00:27ff:fe6d:ff/64 scope Link noprefixroute

valid lft forever preferred lft forever

root@debian:~# fj

**PDF s. 213:** 3 Use the ip route command to find the address of the default gateway.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ip route

default via 10.0.2.2 dev enp@s3 proto dhcp metric 100

10.0.2.0/24 dev enp@s3 proto kernel scope link src 10.@.2.15 metric 100

root@debian:~# Jf

4 Use the touch /etc/network/interfaces.d/enp0s3 command to create a file

named enpOs3 in the directory /etc/network/interfaces.d/.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# touch /etc/network/interfaces.d/enp0s3

root@debian:~#

5 Open the file you created using the following command:

nano /etc/network/interfaces.d/enpOs3

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano /etc/network/interfaces.d/enp0s3

**PDF s. 214:** 6 Insert the following data to set up a static IP:

Important: The static IP address must be on the same subnet as the current IP

address.

auto [Nic name]

iface [NIC name] inet static

address [another IP address from the same subnet]

netmask 255.255.255.0

gateway [the default gateway]

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/network/interfaces.d/enp0s3 Modified

auto enp0s3

iface enp0s3 inet static

address 10.0.2.250

netmask 255.255.255.0

gateway 10.0.2.2

Me Get Help @f) Write Out @M] Where Is @{ cut Text (MJ Justify

ys Exit fi Read File gy Replace @ Uncut Textggy To Spell

7 Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/network/interfaces.d/enp0s3 Modified

auto enp0s3

iface enp0s3 inet static

address 10.0.2.250

netmask 255.255.255.0

gateway 10.0.2.2

@ Get Help @ write out fy Where Is QM cut Text @M] Justify

i Exit fi Read File gy Replace i Uncut Textggy To Spell

Page5

**PDF s. 215:** 8 Use the /etc/init.d/networking stop command to stop the networking service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# /etc/init.d/networking stop

[ ] Stopping networking (via systemctl): networking.service.

root@debian:~# |

9 Use the /etc/init.d/network-manager restart command to restart the network-

manager service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~-# /etc/init.d/network-manager restart

[....] Restarting network-manager (via systemctl): network-manager.

[ ce.

root@debian:-#

10 Use the /etc/init.d/networking start command to start the networking service.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# /etc/init.d/networking start

[ ] Starting networking (via systemctl): networking.service.

root@debian:~#

11. Use the ip address command to check if the new IP address you assigned is

different than the previous IP address. Note that the IP address was changed.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ip address

1: lo: <LOOPBACK,UP,LOWER UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000

link/ loopback 60:00:00:00:00:60 brd 60:00:00:00:60:00

inet 127.0.0.1/8 scope host lo

valid lft forever preferred ft forever

inet6 ::1/128 scope host

valid lft forever preferred lft forever

2: enp@s3: <BROADCAST, MULTICAST, UP, LOWER UP> mtu 1500 qdisc pfifo fast state UP group default qlen 1960

link/ether 68:00:27:6d:00:tf brd ff :ff:ff:ff:ff:ff

“inet 10.0.2.256/24 brd 10.0.2.255 scope global enpds3

valid lft forever preferred lft forever

inet6 fe80::a00:27ff:fe6d:ff/64 scope Link

valid lft forever preferred Ift forever

**PDF s. 216:** 12 Use the command ping 8.8.8.8 to ping IP 8.8.8.8 and check the communication

from the host to the world.

Note: Use Ctrl + c to terminate the ping.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# ping 8.8.8.8

PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.

64 bytes from 8.8.8.8: icmp_seq=1 ttl=106 time=50.10 ms

64 bytes from 8.8.8.8: icmp_seq=2 ttl=106 time=49.3 ms

64 bytes from 8.8.8.8: icmp_seq=3 ttl=106 time=51.9 ms

64 bytes from 8.8.8.8: icmp_seq=4 ttl=106 time=51.2 ms

--- 8.8.8.8 ping statistics ---

4 packets transmitted, 4 received, 0% packet loss, time 14ms

rtt min/avg/max/mdev = 49.343/50.866/51.943/0.989 ms

root@debian:~#

13 Inthe terminal, run the command rm /etc/network/interfaces.d/enpOs3 to

remove the file and reset the machine to receive a DHCP IP.

14 Repeat Steps 8-10 and then restart the machine with systemctl reboot

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# systemctl reboot

**PDF s. 217:** sa.¢ | Debian

o © * | Another way to reboot the machine is with the systemctl reboot command.

= You can also use the systemctl poweroff command to shut down the

computer.

15 After the machine has rebooted, open the terminal to run ping 8.8.8.8 and test

connectivity again.

</details>
