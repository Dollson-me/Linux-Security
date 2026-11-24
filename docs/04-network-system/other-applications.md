# Other System Applications: Logwatch, Nginx & Services

[← 04 · Networking & System Management](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 81–82; Linux Security.pdf, s. 166–171.

## Mapa wiedzy

- The course introduces Logwatch for log analysis/reporting and Nginx as a high-performance HTTP server that can also function as a proxy/mail server.
- The service-debugging lab intentionally creates a port conflict between Apache and Nginx, then identifies the listener and moves one service to another port.
- `dmesg` and other diagnostic commands are used to inspect system/kernel messages.

## Komendy / pliki / składnia występujące w materiale

```text
dmesg
which a device failure occurs. : [mem 9x900OeROOTeEEHNNNN-OxO0000000TeEOOTTT] reserved
Service Debugging a port conflict.
sudo apt install nginx
```

## Notatki z zajęć (PadRiseup)

- `sudo apt install nginx`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-04-L4 — Service Debugging](../labs/lnx-04-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 81:** Section 5: Other Applications

Logwatch

Logwatch is a system log analyzer and reporter. It generates periodic reports based on

criteria specified by the user, and can aggregate logs from multiple machines to a single

report. Even though Logwatch was written for the Linux OS, it can analyze logs from

multiple platforms. Some Logwatch versions are not supported by older versions of

system logs.

Logwatch is installed using the command: apt install logwatch -y

dmesg

dmesg is a diagnostic tool that generates messages from the kernel ring buffer during

the boot sequence. This is especially useful in cases of device failure. The kernel ring

buffer records messages related to the operation of the kernel.

Nginx

Nginx is another open-source web server that focuses on performance optimization.

Aside from being a web server, it is also used as a reverse proxy, HTTP cache, and load

balancer. The advanced capabilities of Nginx have often made it a preferrable choice

over Apache.

Other Servers

There are many other types of servers, of which the following are some examples:

Squid Cache Proxy - a proxy server, mainly used to resolve slow network connectivity.

Cups Print Server - a print server that runs in the background and transfers print

requests.

MongoDB - a type of server database that is document-oriented and unstructured

(NoSQL).

Gaming Server - servers that can be run on home PCs for multiple player video games.

Plex Media Server - can store entertainment services (similar to Netflix) for movies,

program series, music, and more.

**Textbook s. 82:** Lab Assignment: LNX-04-L4 Service Debugging

— Practice a basic level of service troubleshooting.

=m:

Follow the instructions in lab document LNX-04-L4.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 166:** Linux Security

Other Applications

**Slides s. 167:** (Lo Other Applications

@ Logwatch is a system log analyzer and reporter.

@ It generates periodic reports based on criteria

specified by the user.

@ Some Logwatch versions are not supported by

older versions of system logs.

When invoked, Logwatch collects logs from

every relevant system resource.

Cc % = .

**Slides s. 168:** Other Applications

File Edit View Search Terminal Help

root@debian:~# dmesg

Linux version 4.19.0-6-amd64 (debian-kernel@lists.debian.org) (gc

c version 8.3.0 (Debian 8.3.0-6)) #1 SMP Debian 4.19.67-2+deb1l0ul (2019-09-20)

The dmesg command displays : BOOT IMAGE=/boot/vmlinuz-4.19.6-6-amd64 root=UUID=2

: c5a2577-2b2f-40cc-8b48-dcb17b7a9b28 ro quiet

messages from the kernel ring : Supporting XSAVE feature 0x01: 'x87 floating point regi|

buffer. : Supporting XSAVE feature 0x002: 'SSE registers'

: Supporting XSAVE feature 0x004: 'AVX registers'

The messages are generated : xstate offset[2]: 576, xstate sizes[2]: 256

. : Enabled xstate features 8x7, context size is 832 bytes,

during the computer boot using 'standard' format.

BIOS-provided physical RAM map:

Process. : [mem @x8000900000000000 -OxQR0000000009TbTT] usable

: [mem O@xQQo0g0000009T cod -OxQon000000009T TTF] reserved

j j : [mem O0xOG0O9G00000TO0OO -Oxoo000000000TTTTT] reserved

dmesg Is an important : [Mem @x9000990000100000-Oxo0000000dTTeffTf] usable

diagnostic tool for cases in : [mem oxeoooe90edTffe000-axos0e0000dTTTfTtff] ACPI data

. ‘“ « : [mem @x909000000Tec 00000 -OxQn000000fecOOTTf] reserved

which a device failure occurs. : [mem 9x900OeROOTeEEHNNNN-OxO0000000TeEOOTTT] reserved

: [mem 8xQQ9000000TTfcO000 -OxQo000000TFTTTTTf] reserved

: [mem 0x9000000100000000-Ox000000011ffTTTTT] usable |

**Slides s. 169:** (Ngin: Applications

@ Nginx is a free HTTP server that can also operate as a

mail server.

@ It features high-level performance, reliability, and

simplicity.

@ Insome respects, Nginx is a better choice than Apache.

For example, it is known for more efficient resource

usage.

Cc % =

**Slides s. 170:** Other Applications

Additional Applications

= Cups Print Gaming

a Server Server

Squid Cache MongoDB Plex Media

Proxy Server

38

**Slides s. 171:** Other Applications

=e = Seri Install the Apache and Nginx services and resolve

Service Debugging a port conflict.

20-30 Min

oe : @ Install the Apache service.

er > : - @ Install Nginx.

i 4 - ~~ @ Reboot and debug.

Uf 4 0, a e) @ Change the listening port.

| . ma f ® Debian ®@ Lab document

= & ON .

; ® Apache

| 3 NY @ Nginx

{ 4 s

s Pi .

3; —a

</details>
