# firewalld

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 132–135; Linux Security.pdf, s. 308–314.

## Mapa wiedzy

- firewalld provides a higher-level firewall management model and organizes policy around zones/services rather than only raw rule chains.
- The course contrasts it with direct iptables management and emphasizes verifying active services/rules after configuration.

## Komendy / pliki / składnia występujące w materiale

```text
apt install firewall-applet -y. After installation, they can be run from the Applications
which other computers on the network are not to be trusted.
firewall-cmd --new-zone=zone-name —-permanent
firewall-cmd --get-zones
firewall-cmd --permanent --new-zone=Class
firewall-cmd --permanent --zone=Class --add-
firewall-cmd --panic-on
firewall-cmd -query-panic
firewall-cmd --panic-off Firewalld has an option to
```

## Powiązane laboratoria

- [LNX-08-L2 — Summary Exercise](../labs/lnx-08-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 132:** Section 2: Firewalld

Firewalld is an iptables wrapper, and zone and-service based system, that provides

enhanced capabilities, such as runtime and permanent configuration sets, and a

graphical interface.

Firewalld is installed by default on:

e CentOS 7 and higher

e Fedora 18 and higher

e Red Hat Enterprise Linux 7 and higher

e@ OpenSUSE Leap 15 and higher

e SUSE Linux Enterprise 15 and higher

It is also possible to install Firewalld on other Linux distributions, such as Debian

systems (Ubuntu and others).

To install Firewalld, use the apt command: sudo apt install firewalld -y.

The graphical interfaces need to be installed separately using the apt command:

apt install firewall-applet -y. After installation, they can be run from the Applications

menu.

**Textbook s. 133:** Applications ~ &) Terminal ~

Te pa 5

Boise. SRE Advanced Network Configuratt.

Accessories =

Games —

Graphics

Internet

Office

Programming

Sound & Video

System Tools

Utilities

Other 4

Activities Overview

Firewalld GUI

Firewall Configuration x

File Options View Help

© ActiveBingings Configuration: Runtime

Connections Zones Services PSets

Wired connection |, ———

iemp fiters and riehrules, The zone canbe bound tinterfaces and source aderesses

Sources

dma ——.

ed services are accessible from all hosts and networks that can reach the

external machine from connections, interfaces and sources bauind to this zone.

home a

intemal amanda-client

amanda-K5-clent

trusted ame

Pi

wor ane

apcusd

aut

bacula

bap

bitcoin

bitcoin-pe

bitcon-testnet

bitcoin-testnet-rpe

cep

Connection firewall established

Default Zone: public Log Denied off PanicMode: disabled Automatic Helpers: system off) Lockdown disabled

**Textbook s. 134:** Firewall zones are pre-defined sets of rules with varying degrees of trust based on

location or scenario. For example, the public zone is intended for an environment in

which other computers on the network are not to be trusted.

Each zone allows for traffic from its defined services and protocols only. Upon

installation, the default zone will be Public.

Zones can also be defined by interface type, whether internal or external, and have

services defined appropriately. For example, external interface services such as HTTPS

and DNS would be allowed, but DHCP would not.

Unless configured otherwise, interfaces are assigned to the default zone.

New zones can be created in one of two ways:

1. With the new zone command:

firewall-cmd --new-zone=zone-name —-permanent

The new zone will appear after the service is reloaded.

2. With an existing zone’s .xml file as a template.

The second method involves copying the .xml file of an existing zone from the

/usr/lib/firewalld/zones/ and /etc/firewalld/zones/ directories and changing its

configuration to suit your needs.

Firewalld employs runtime and permanent configuration sets, meaning you can change

rules without interrupting connections by adding them to the runtime configuration set.

The changes will be not be retained upon reboot unless added to the permanent

configuration set.

Firewalld has a feature called Panic Mode, which is intended for use in extreme cases.

Panic mode will sever all existing connections and drop all incoming and outgoing

packets. The mode can be turned on and off using firewall-cmd --panic-on and firewall-

cmd --panic-off. To check if Panic mode is on, use: firewall-cmd --query-panic.

**Textbook s. 135:** All Firewalld commands begin with firewall-cmd.

The following table lists some useful commands:

--list-all Lists all port services in the default zone.

Note: Firewalld commands need to be run with superuser permissions.

#) Lab Assignment: LNX-08-L1 Configure a Allow list

— Create firewall rules to block all SSH traffic. Create a allow list and add the

a host IP.

Follow the instructions in lab document LNX-08-L1.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 308:** Network Security

Firewalld

**Slides s. 309:** $ firewall-cmd --get-zones

Block dmz drop external home internal public trusted work

Some Linux distributions

have Firewalld installed by

default.

Firewalld uses zone

configurations to enable it

to be applied separately.

Zones can be associated

with more than one

network interface.

**Slides s. 310:** Firewalld

$ firewalld-cmd --list-all

Public

target: default

icmp-block-inversion: no

interfaces:

sources:

services: dhcpv6é-clisnt ssh

ports:

protocols:

masquerade:

forward-ports:

source-ports:

icmp-blocks:

rich rules:

If a zone is not specified, the “Public” zone summary will be displayed.

**Slides s. 311:** (Ne Firewalld

a Defines the network’s level of security.

$ firewall-cmd --permanent --new-zone=Class

Success

$ firewall-cmd --permanent --zone=Class --add-

interface=enpes3 Z

Success

y < | Newzonesare not configured by default.

New zones must be assigned a network interface.

12

**Slides s. 312:** $ firewall-cmd --panic-on

Success

$ firewall-cmd -query-panic

yes

$ firewall-cmd --panic-off Firewalld has an option to

Success terminate all existing

connections.

Panic mode is activated

using --panic-on (or off).

Query panic mode can be

set, for later review.

**Slides s. 313:** (Fir Firewalld

@ | Syntax Meaning

| --zone=<name> Creates a new zone with a specified name

| --add-service=<service> Adds a service to a zone

| --list-services Lists all services in the zone

| --reload Reloads Firewalld

| --permanent Creates persistent settings

| --add-port Adds a specific port i

14

**Slides s. 314:** Configu re a Whitelist | Create firewall rules to block all SSH traffic.

us 4+ Create a whitelist and add the host IP.

20-25 Min

oF é& ” ® Connect with SSH.

; = ®@ Install iptables.

— ; ;

ee a d - @ View rule list.

, rE, q yf, i @ Block all SSH traffic.

ia » yw hy | 8 2 yr

DB, m—~_NL.UlUlUlg . c nt]

4 “ge

| . n ® r ®@® Debian environment @ Lab document

> Bek Wy ® Windows 10 VM

| j a " ‘ ®@ iptables

f | s > % . = al

</details>
