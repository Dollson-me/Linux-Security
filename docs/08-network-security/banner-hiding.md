# Banner Hiding for SSH & Apache

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 144–145; Linux Security.pdf, s. 334–338.

## Mapa wiedzy

- Service banners can disclose product/version/OS information useful to reconnaissance.
- The course demonstrates observing SSH/HTTP banners and then reducing information disclosure through service configuration.
- Banner hiding is defense-in-depth: it does not fix vulnerabilities but removes easy fingerprinting data.

## Komendy / pliki / składnia występujące w materiale

```text
curl -v 10.71.0.103:22
SSH & Apache
systemctl restart sshd
echo "piotr" > /etc/ssh/sshd.allow
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
```

## Notatki z zajęć (PadRiseup)

- `systemctl restart sshd`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-05-L3 — Securing Services](../labs/lnx-05-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 144:** Lab Assignment: LNX-08-L2 IP Lockout

— Create a Bash script that blocks IP addresses listed in iptables when they

mmm | exceed the limit of 404 error login attempts.

Follow the instructions in lab document LNX-08-L2.

Section 7: Banner Hiding for SSH & Apache

When an Apache server receives a request, by default it sends back potentially sensitive

information, including the server version, operating system, installed modules, and

more. Banners can also include such information.

This seemingly harmless information, means more potential attack vectors for a hacker.

Banners should be hidden, not only for Apache, but also for SSL and other services that

have external access.

The curl command can be used to view a banner. The following example demonstrates

how an SSH banner provides information regarding the OS.

curl -v 10.71.0.103:22

* Rebuilt URL to: 10.71.0.103:22/

* TCP_NODELAY set

* Connected to 10.71.6.103 (10.71.6.103) port 22 (#0)

> GET / HTTP/1.1

> Host: 10.71.0.103:22

> User-Agent: curl/7.55.1

SSH-2.0-OpenSSH_7.9p1 |Debian-10+deb1i6u1

Protocol mismatch.

* Recv failure: Connection was reset

* Closing connection @

curl: (56) Recv failure: Connection was reset

**Textbook s. 145:** As a best practice, banners should be disabled to prevent leakage of information that

an attacker may use against the system. When Apache encounters an error, it displays

output with the error code. In some cases, the code may include server-related

information that should be hidden. Custom error messages can be defined and

configured for the service.

403 Forbidden - Mozilla Firefox

403 Forbidden % EE

€ eo ® tocathost:443/test —~ Or In &

Forbidden

You don't have permission to access this resource.

ModSecurity

ModSecurity is an open-source web application firewall (WAF) used for data monitoring

over HTTP traffic. It allows filtration of data received by a web server, and in response it

detects and blocks malicious content. Its installation and integration are fairly easy with

the Apache web server.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 334:** Network Security

Banner Hiding for

SSH & Apache

**Slides s. 335:** (Ba Banner Hiding for SSH & Apache

@ More information for an attacker means more

attack possibilities.

® Server details can encourage attackers to use

known exploits.

@ Removing error messages and banners is a

recommended security measure.

=

**Slides s. 336:** (Hi Banner Hiding for SSH & Apache

Hide Apache Banner

OC fs Activities €) FirefoxESR + Mon 09:35 2, wh

OF 403 Forbidden - Mozilla Firefox

403 Forbidden * |

< Cn @ localhost:443/test/ — Ow IN @

Forbidden The Apache service

You don't have permission to access this resource. returns answers with

error codes.

Hide error banners that

include server-related

information.

Customize error messages

that are returned.

37

**Slides s. 337:** Banner Hiding for SSH & Apache

curl -v 10.71.0.103:22

* Rebuilt URL to: 16.71.0.103:22/

* Trying 10.71.0.103...

* TCP_NODELAY set

* Connected to 10.71.6.103 (10.71.6.163) port 22 (#@)

> GET / HTTP/1.1

> Host: 160.71.0.163:22

> User-Agent: curl/7.55.1

STAGCEDE: 6*/>

>

SSH-2.0-OpenSSH_7.9p1|Debian-16+debi6u1

Protocol mismatch.

* Recv failure: Connection was reset

* Closing connection @

curl: (56) Recv failure: Connection was reset

Connecting via SSH displays operating system information.

**Slides s. 338:** (ivi Banner Hiding for SSH & Apache

O

@ ModSecurity is an open-source WAF (Web

¥ Application Firewall).

®@ Its job is to filter data received by a web

server and detect and block malicious

. content.

: @ \Itcan be easily installed and integrated with

an Apache web server.

=

</details>
