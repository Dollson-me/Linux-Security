# Secure Apache & ModSecurity

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 143–143; Linux Security.pdf, s. 329–333.

## Mapa wiedzy

- Apache hardening includes restricting methods/resources, reducing exposed information, applying appropriate permissions and using a web-application firewall layer.
- The class installs `libapache2-mod-security2`, enables ModSecurity configuration and imports OWASP Core Rule Set resources.
- The lab `LNX-08-L3` focuses on configuring ModSecurity.

## Komendy / pliki / składnia występujące w materiale

```text
Curl Vs. Wget
Wget is useful when downloading multiple files or mirroring an entire website.
Curl is better suited to downloading several files from the same address, since it
sudo vim /etc/apache2/conf-available/security.conf
mv modsecurity.conf-recommended modsecurity.conf
sudo mv modsecurity-crs/ modsecurity-crs_bak
git clone https://github.com/SpiderLabs/owasp-modsecurity-crs
sudo mv owasp-modsecurity-crs/ modsecurity-crs
sudo vim security2.conf
IncludeOptional /usr/share/modsecurity-crs/*.conf
IncludeOptional /usr/share/modsecurity-crs/rules/*.conf
```

## Notatki z zajęć (PadRiseup)

- `sudo vim /etc/apache2/conf-available/security.conf`
- `mv modsecurity.conf-recommended modsecurity.conf`
- https://github.com/SpiderLabs/owasp-modsecurity-crs
- `sudo mv modsecurity-crs/ modsecurity-crs_bak`
- `git clone https://github.com/SpiderLabs/owasp-modsecurity-crs`
- `sudo mv owasp-modsecurity-crs/ modsecurity-crs`
- `sudo vim security2.conf`
- `IncludeOptional /usr/share/modsecurity-crs/*.conf`
- `IncludeOptional /usr/share/modsecurity-crs/rules/*.conf`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-08-L3 — Configure ModSecurity](../labs/lnx-08-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 143:** Curl Vs. Wget

Wget is useful when downloading multiple files or mirroring an entire website.

Curl is better suited to downloading several files from the same address, since it

supports wildcards. Curl supports more protocols across several platforms and uses

more efficient authentication methods.

Wéget can resume interrupted downloads automatically, while curl cannot.

The tools are similar, but each can be suitable for a different purpose.

Section 6: Secure Apache Configuration

The following are some methods of hardening and securing an Apache server:

1. Use only necessary HTTP methods: Some HTTP methods, such as PUT, DEL,

TRACE, and CONNECT are known to be vulnerable to exploitation and privilege

escalation, and are not recommended to be used.

2. Work with ‘weak’ users for services: Services can be exploited for privilege

escalation, so it is a best practice to have them run with regular user permissions

rather than special permissions.

3. Reduce or remove server headers: Server headers contain version information

about Apache servers. Attackers can look up known vulnerabilities for specific

versions and exploit them.

4. Disable banners: Banners also divulge important information for hackers to

exploit.

5. Set access controls: Such controls restrict access to your server.

6. Use only TLS 1.2 or 1.3 and disable older versions: Older versions of SSL and TLS

have been cracked and are not recommended for use. Some websites still use TLS

1.0, 1.1, and SSL2.0.

7. Disable directory listings: To prevent enumeration attacks.

8. Update services as needed: New vulnerabilities are discovered all the time and it

is an essential company practice to have the latest security patches installed.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 329:** Network Security

Secure Apache

Configuration

**Slides s. 330:** (Se Secure Apache Configuration

OG

Use only necessary HTTP

Set access controls

methods

Work with ‘weak’ users for Use only TLS 1.2, disable

services older versions

Reduce nr remove server Disable directory listing

headers

(4) Disable banners Update services as needed

31

**Slides s. 331:** (Di Secure Apache Configuration

L_]

OC 403 Forbidden x | +

en

(€)/7 co @® localhost/test/ oe w In O =

Forbidden

Web pages have root You don't have permission to access this resource.

folders that include

subfolders. Apache/2.4.38 (Debian) Server at localhost Port 80

Directory listing is enabled

by default.

Sensitive information may

be revealed when listing

all web directories.

32

**Slides s. 332:** Secure Apache Configuration

Remove Version Information

.

ServerSignature off - Removes version

information from the header response

and error codes.

ServerTokens Prod - Removes the server’s

OS version and displays “Apache” instead.

a

**Slides s. 333:** Sum mary Exercise | Create a Bash script that blocks IP addresses in Iptables

iby = | when they exceed the limit of 404 error login attempts.

60-75 Min ,

en nl Lf ” ® Download a log file.

4 ® Create a script that reads records

—_,,, =] ta in the file.

; "fe a ®@ Block IPs that violate the policy.

ay [= | 7,

a | ant —

| . » @ i @ CL @ Lab document

~. "\* ® ®@ Debian environment @ ApzEEpi6

i Y *

| s.

ih <<

</details>
