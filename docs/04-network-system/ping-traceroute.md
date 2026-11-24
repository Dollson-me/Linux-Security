# Network Testing: ping & traceroute

[← 04 · Networking & System Management](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 70–70; Linux Security.pdf, s. 136–140.

## Mapa wiedzy

- `ping` tests reachability with ICMP Echo Request/Reply and reports round-trip time and packet loss.
- `traceroute` shows the hop-by-hop path toward a destination and is useful for finding where connectivity fails.
- The course also uses `ip address`, `ip route`, `ifconfig` and related tools to inspect interface and routing state.

## Komendy / pliki / składnia występujące w materiale

```text
Ping
Ping can be used with an IP address or DNS name and has advanced options that can be
Traceroute
Traceroute checks the path of a packet that is sent to its destination, and displays it in
IP Address
ip a command can also be used, and is included in Debian’s iproute package. The
Ping and Traceroute
traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets
traceroute counts and da ners
source to destination.
ip address
ip address is used to
ifconfig is part of a
target = input("Enter the IP address of the target: ")
ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'
```

## Notatki z zajęć (PadRiseup)

- `target = input("Enter the IP address of the target: ")`
- `ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'`

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

**Textbook s. 70:** | Chapter 4: Networking & System Management

Section 1: Network Testing using Ping & Traceroute

Ping

The ping command, which is based on the Internet Control Message Protocol (ICMP),

sends a network packet called ICMP echo request to a remote server, which replies with

the information about how long it took for the packet to get to the server and back to

the station. The response can also include an error message if the connection fails.

Ping can be used with an IP address or DNS name and has advanced options that can be

set with flags such as -c, which counts the number of pings, -f, which floods the server

with ping requests, and -i, which sets the interval in seconds between each packet it

sends.

Traceroute

Traceroute checks the path of a packet that is sent to its destination, and displays it in

the command line. Each device along the path is known as a hop. Not every hop will be

visible because some devices do not reply to ICMP requests even though they process

them. Such devices are marked with **. The final destination is the target IP address

and the source IP is linked to the sending station.

IP Address

When clean versions (without additional tools) of some Linux distributions are installed

(such as Debian), the ip address command will display the IP address of the station. The

ip a command can also be used, and is included in Debian’s iproute package. The

popular ifconfig command requires a newer version of the package called net-tools.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 136:** Linux Security

Network Testing Using

Ping and Traceroute

**Slides s. 137:** Network Testing Using Ping and Traceroute

File Edit View Search Terminal Help

The ping command tests 64 bytes from 8.8.8.8: icmp seq=1 ttl=54 time=53.9 ms

network communication 64 bytes from 8.8.8.8: icmp seq=2 ttl=54 time=53.9 ms

b di k h 64 bytes from 8.8.8.8: icmp seq=3 ttl=54 time=53.8 ms

y senaing pac ets to the 64 bytes from 8.8.8.8: icmp seq=4 ttl=54 time=54.2 ms

destination and receiving 64 bytes from 8.8.8.8: icmp seq=5 ttl=54 time=53.9 ms

li 64 bytes from 8.8.8.8: icmp_seq=6 ttl=54 time=55.1 ms

replies. 64 bytes from 8.8.8.8: icmp seq=7 ttl=54 time=53.8 ms

64 bytes from 8.8.8.8: icmp seq=8 ttl=54 time=53.9 ms

Unlike other OSs, regular 64 bytes from 8.8.8.8: icmp seq=9 ttl=54 time=54.5 ms

f pi in li d 64 bytes from 8.8.8.8: icmp seq=10 ttl=54 time=53.7 ms

use Of ping In Linux goes 64 bytes from 8.8.8.8: icmp seq=11 ttl=54 time=53.9 ms

not limit the number of 64 bytes from 8.8.8.8: icmp seq=12 ttl=54 time=54.3 ms

packets sent. [1]+ Stopped ping 8.8.8.8

“—h

The —c flag can be used to

limit the number of

packets sent.

**Slides s. 138:** Network Testing Using Ping and Traceroute

File Edit View Search Terminal Help

:/$ traceroute 8.8.8.8

traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets

1 gateway (10.0.2.2) 6.339 ms 0.149 ms 0.088 ms

2 gateway (10.0.2.2) 1.959 ms 1.899 ms 1.835 ms

traceroute counts and da ners

displays the hops from

source to destination.

All messages from hops

between the source

and destination are

included in the output.

This enables the paths

of packets sent over

the network to be

traced. |

**Slides s. 139:** john@Debian:/%$ ip address

john@Debian:/% ip route show

ip address is used to

obtain existing addresses

on the network.

Some distributions do

not include this binary.

The ip route show

command displays the

main routing table.

**Slides s. 140:** john@Debian:/% ifconfig

ifconfig is part of a

command package called

net-tools.

It displays the network

adapter, IP address,

netmask, and more.

Linux OS supports both

IPv4 and IPv6.

</details>
