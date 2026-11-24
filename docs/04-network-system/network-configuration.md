# Linux Network Files & Configuration

[← 04 · Networking & System Management](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 71–74; Linux Security.pdf, s. 141–151.

## Mapa wiedzy

- Linux may operate as a DHCP client/server or use static addressing. The course demonstrates both CLI configuration and persistent configuration files.
- Important tools/files include `ip address`, `ip route`, `ifconfig`, `route`, `dhclient`, `/etc/network/interfaces` and `/etc/resolv.conf`.
- `nslookup` resolves names/IPs; `netstat`, `ss` and `lsof` inspect listening sockets and network connections.
- The lab configures static/dynamic IP information and verifies connectivity.

## Komendy / pliki / składnia występujące w materiale

```text
ifconfig
dhclient
IP addresses can be changed, released, renewed, or removed from the server side and
ifconfig <interface> <ip_address> netmask <mask> up
source /etc/network/interfaces.d/*
Route Display
nslookup
netstat command shows network statistics about the workstation and displays the port
nano /etc/network/interfaces
ifconfig adds IP addresses
route
ip route add <IP> via <gateway> dev <interface>.
netstat displays TCP/UDP connections
Netstat is part of the net-tools package and
find specific processes. rcu_gp a ; root cwd unknown
sudo netstat -tulpn
target = input("Enter the IP address of the target: ")
```

## Notatki z zajęć (PadRiseup)

- `less /var/log/dpkg.log`
- `sudo netstat -tulpn`
- `target = input("Enter the IP address of the target: ")`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-04-L1 — Static and Dynamic IP Configuration](../labs/lnx-04-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 71:** ifconfig

Like the ip address command, ifconfig displays information such as the IP address,

network card name, protocol support (IPv4/IPv6), subnet mask, and more. The ifconfig

command is also used to turn the network interface on or off with the following

command syntax: ifconfig up and ifconfig down.

Section 2: Networking Files & Configuration

The Linux environment can be used as a client for different needs and it can be used as

a server to manage stations and users. Either way, the host obtains the IP address from

a DHCP server or acts as the server that distributes IP addresses.

dhclient

IP addresses can be changed, released, renewed, or removed from the server side and

can be configured on a client station using the dhclient command. The dhclient

command requests a new IP address, dhclient -r releases an IP address received from a

DHCP server, and dhclient -p allows configuration of a custom port (the default port is

68 UDP).

Static IP Address

A static IP address can be configured through server configuration or from the client.

However, setting a fixed IP address via the client configuration file can cause a collision

between IP addresses on the same network if the DHCP server distributes the address

when the host is down and the address is available for use. In most cases, the address is

reserved on the server.

There are two ways to set static IP addresses for a client. The first is via aa command line

with the following syntax:

ifconfig <interface> <ip_address> netmask <mask> up

All the information about an address can be gathered by a simple ifconfig or ip address

command. To apply the changes, the interface needs to be restarted and in some cases

a reboot is required as well.

**Textbook s. 72:** The other method is to configure the interface configuration file with the address,

netmask, and gateway in the /etc/network/interfaces file directory (in Debian). Each

Linux distribution has a different location for the network configuration file.

siciiieaiaaaas .

File Edit View Search Terminal Help

|

|

source /etc/network/interfaces.d/*

auto lo

iface lo inet loopback

allow-hotplug enp®s3

iface enpuss inet static

address 10.0.2.14

mask 255.255.255.0

gateway 10.4.7.1

|

[ Read 15 lines ]

Route Display

The route command displays the routing host tables that show the possible ways to

forward network traffic. For example, if a host is listed under VLAN 10.0.0.x and needs

to transfer information to a 192.168.0.x VLAN network, adding the VLAN to the routing

table will allow communication through the gateway. Setting the IP address as one of

the sides (outgoing or incoming traffic) allows communication between all traffic

segments. Displaying the table is done with the route command and is listed as a table

showing columns for the destination, gateway, genmask, flags, metric, Ref, and Iface.

¢ Destination — the routed network.

e Gateway — the gateway address that points to the network.

¢ Genmask — the network mask of the destination network.

e Flags — additional data that describes the routes (U = up, G = gateway).

e Metric —a value that specifies the preferred route when there are several routes

to the same destination. A lower number indicates a higher preference.

**Textbook s. 73:** e Ref—references to the specified route.

e Use — route lookups (decision-making process to determine how to route packets

to their destinations).

e face — the interface used for the route.

Lab Assignment: LNX-04-L1 Static & Dynamic IP Configuration

—_— Practice static and dynamic IP address configuration and learn more about

a routing.

Follow the instructions in lab document LNX-04-L1.

nslookup

A package called dnsutils contains the nslookup tool that resolves IP addresses. Each

domain has information about the owner, main servers, and fully qualified domain

name (FQDN). Dnsutils allows you to run the DNS check from the CLI, although it can

also be found online. Flags can be added to the command to obtain more accurate

results, such as NS records that point to management sources like msft, Cloudflare, and

Google. The flag -type=ns. -type=any will display additional information about the

domain, such as NS records, mailing address, expiration date, and other records,

including SPF and TXT.

DNS Configuration

The service in Linux systems responsible for address name resolution is called system-

resolved.

Name resolution is performed by DNS servers specified in the resolve.conf file located

in /etc/.

**Textbook s. 74:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 /etc/resolv.cont

InMameserver 8.8.8.8

nameserver 1.1.1.1

lm Get Help @@ Write Out @] Where Is i Cut Text @@] Justify We Cur Pos

i Exit ii Read File @\ Replace mm!) Uncut Textgay To Spell ii Go To Line

Windows stores resolved local IP addresses in the host file under the system32

directory and Linux stores them in the /etc/hosts configuration file. This file serves the

same purpose in Linux and Windows: when a host tries to reach an IP address, it first

refers to the local file and then checks with other resolving sources like DNS servers.

john@debian: ~ x

File Edit View Search Terminal Help

127.0.0.1 localhost

a27.8.1.1 debian

1 localhost ip6-localhost ip6-loopback

ff02::1 ip6-allnodes

ff2::2 ip6-allrouters

Be Set Help QM write out J} where rs Mi cut Text fH] Justify Q@ cur Pos

i Exit Mii Read File Qi} Replace a Uncut Textgy To Spell ( Go To Line

Network Statistics

Another networking perspective is checking the connection from the local host. The

netstat command shows network statistics about the workstation and displays the port

number, incoming and outgoing connections, if the connection is active or inactive, and

if the port is listening. Some tools using these commands display the information in a

graphical view.

Netsat returns results with information about the online state and live connections,

similar to the ss command, which dumps socket statistics. The ss command is installed

by default in Linux distributions and is easier to use than netstat.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 141:** Linux Security

Networking Files

and Configuration

**Slides s. 142:** (dh Networking Files and Configuration

dhclient

—_ @ Linux can operate as a Dynamic Host

{ IP Configuration Protocol (DHCP) server or client.

a @ The dhclient command will request an IP from

.~ a DHCP server.

—- @ Some cases require the -r flag, which releases

the client’s current lease from the host.

Cc % =

**Slides s. 143:** john@Debian:/# ifconfig <interface> <ip_address> netmask <mask> up

john@Debian:/# nano /etc/network/interfaces

Configuring a static IP

address can be done via a

command or a change in

the configuration file.

ifconfig adds IP addresses

to an interface with the

specified mask.

In some cases, an

interface reset or full

reboot is required to

obtain an IP address.

**Slides s. 144:** Networking Files and Configuration

File Edit View Search Terminal Help

GNU nano 3.2 /etc/network/interfaces

Another way to configure

a static IP address is to edit source f/etc/network/interfaces.d/*

the interface file

(/etc/network/interfaces). auto lo

iface lo inet Loopback

The file can be edited with

root permissions. allow-hotplug enp0s3

iface enpOs3 inet static

After configuring the file, a mask 255.255.255.0

reboot may be required. gateway 10.0.2.1

i [ Read 15 lines ]

**Slides s. 145:** Networking Files and Configuration

johnd@Debian:/# route

ctivities &) Terminal ~ Tue 09:13 34, O

. . . johnd@debian: / x

Displays the routing table and is also used to Sh oS Eas om

define a static path in the table Kerra ae rity eb ;

Destination Gateway Genmask Flags Metric Ref Use Iface

# z P ¥ default gateway 0.0.0.0 UG 0 Cy © enpos3

The destination is typically the general address a 0.2.0 , 0.0.0.0 255.255.255.0 U ° ° © enpos3

of the subnet, which is determined by the

gateway.

Genmask must be applied to the destination.

There are two flags:

U = Route is up

G = The specified gateway is in use.

**Slides s. 146:** (Ro Networking Files and Configuration

® Aroute can be configured via the CLI.

@ The command syntax is

ip route add <IP> via <gateway> dev <interface>.

®@ The configuration is not persistent and must be

saved to a configuration file.

Cc % =

**Slides s. 147:** Networking Files and Configuration

ee == ’ Become familiar with manual static IP address configuration

Static and Dynamic IP Configuration in the system and learn about system network services.

20-30 Min |

i ; ® Practice networking commands.

_— = ; ® Create files using a text editor.

$s S, 4 , ~ ® Configure network files.

" b Ny ® e di

>, a oll I yr

| : ' n @ e a a ® Debian ® Lab document

~: W @ Text editor

{ ‘ ‘,

sy

Tr. —a

**Slides s. 148:** (ns Networking Files and Configuration

@ nslookup is part of the dnsutils package.

®@ \Itresolves IP addresses to names and names

to IP addresses.

@ The output of the command displays the IP

address of the DNS server and other related

information.

Advanced flags can be added to nslookup for

more accurate results.

Cc % = .

**Slides s. 149:** Networking Files and Configuration

File Edit View Search Terminal Help

GNU nano 3.2 /fetc/resolv.cont

nameserver 10.21.0.210

The system service nameserver 8.8.8.8

responsible for name

resolution is called

systemd-resolved (local).

resolv.conf is a DNS

configuration file that

contains nameservers.

Configuration of local DNS F

files can be done using

/etc/hosts.

[ Read 2 lines ]

ie Gat tin Br Writs ut Whos Tle s “4 Pomme Be Cu Dan za

**Slides s. 150:** (Ne Networking Files and Configuration

netstat displays TCP/UDP connections

and listening ports on workstations.

--S ®@ The ss command dumps socket statistics.

( ull ) ®@ Itis similar to netstat but is faster and easier.

4-4 @ Itincludes fewer functions than netstat.

Netstat is part of the net-tools package and

is not installed by default, unlike ss.

Lp

**Slides s. 151:** Networking Files and Configuration

File Edit View Search Terminal Help

joh ii :/$ Lsot

COMMAND PID TID TASKCMD USER FD TYPE DEVICE

The Isof command SIZE/OFF NODE NAME

. . systemd 1 root cwd unknown

displays a list of open /proc/1l/cwd (readlink: Permission denied)

files. systemd 1 root rtd unknown

/proc/1/root (readlink: Permission denied)

systemd 1 root txt unknown

It can be useful when /proc/lfexe (readlink: Permission denied)

trying to find out which systemd 1 ; root _NOFD —

. . /proc/1/fd (opendir: Permission denied)

file runs which process. kthreadd 2 root cwd unknown

/proc/2/cwd (readlink: Permission denied)

Isof runsona specific kthreadd 2 _ : root rtd unknown

. /proc/2/root (readlink: Permission denied)

directory. It can be kthreadd 2 root txt unknown

j /proc/2/exe (readlink: Permission denied)

executed by different user hey " 5 + NOED

” hreadd Z roo NC

accounts and filtered to /proc/2/fd (opendir: Permission denied)

find specific processes. rcu_gp a ; root cwd unknown

/proc/3/cwd (readlink: Permission denied)

rcu_gp =| root rtd unknown

</details>
