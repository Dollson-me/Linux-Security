# SFTP vs FTP / FTPS

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 149–149; Linux Security.pdf, s. 344–348.

## Mapa wiedzy

- SFTP is the SSH File Transfer Protocol and uses SSH’s encrypted transport and authentication; the source explicitly notes port 22.
- FTP uses unencrypted control/data channels and port 21 for control, while SFTP tunnels file operations through SSH.
- FTPS is FTP protected with SSL/TLS and therefore uses certificates; the course distinguishes it from SFTP.

## Komendy / pliki / składnia występujące w materiale

```text
SFTP stands for SSH File Transfer Protocol. It is an extension of the SSH protocol, which
SFTP
ftp johnd@localhost
SFTP Vs. FIPS
ftp 192.168.1.68
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT
```

## Notatki z zajęć (PadRiseup)

- `ftp 192.168.1.68`
- `sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-05-L2 — Install and Configure Samba and FTP](../labs/lnx-05-l2.md)
- [LNX-05-L3 — Securing Services](../labs/lnx-05-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 149:** Section 9: SFTP

SFTP stands for SSH File Transfer Protocol. It is an extension of the SSH protocol, which

was included in SSH2 and uses the same port, 22. SFTP was designed to work with the

encrypted connection SSH establishes to securely transfer files between machines. SFTP

relies completely on SSH for encryption and authentication. SFTP also provides

enhanced file functionality, such as permission and attribute manipulation, file locking,

and more.

The following are some key differences between FTP and SFTP:

1. FTP uses a client-server architecture, meaning that a server holds files the client

downloads, as opposed to SFTP, which transfers files between any two nodes.

2. FTP uses two separate channels, one to transfer data and one to control the

connection; both are unencrypted. SFTP uses SSH, which establishes an

encrypted connection, then transmits all the data on a single secure channel.

3. FTP works on port 21, while SFTP uses port 22.

4. FTP directly transfers files, whereas SFTP uses a tunneling transfer method.

FTPS is another secure file transfer protocol that uses FTP with SSL/TLS for security, and

therefore requires a certificate. As opposed to SFTP, FTPS communication can be logged

and read by humans. SFTP communication cannot be logged, since SSH transfers data in

binary form and is unreadable to humans.

Lab Assignment: LNX-08-L4 SSL Encryption

— Generate an SSL certificate for the Apache web server and configure Apache

mm =| to use SSL.

Follow the instructions in lab document LNX-08-L4.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 344:** Network Security

SFTP

**Slides s. 345:** SFTP

(Secure File Transfer Protocol (SFTP)

.

// ip @ Secure FTP is based on the SSH protocol.

Pa @ SFTP files are exchanged in encrypted

(9) | ig format and are more secure than FTP files.

®@ The addition of SSH to FTP should not

mean dropping other security measures.

@ SFTP relies on SSH protocol authentication.

a,

**Slides s. 346:** $ ftp johnd@localhost

ftp: johnd@localhost: Name or service not known

ftp> exit

oh SUD inal Cetecl fn When SFTP is deployed, the

johnd@localhost’s password: FTP service will automatically

Connected to johnd@localhost be disabled.

sftp> cd docs/

sftp> put test.txt SFTP displays more detailed

Uploading test.txt to /docs/test.txt data, such as permissions,

test.txt 100% 61 206.6KB/s 0:00 date, time, and size.

ge SFTP operates via the SSH

bexte Ext protocol, while FTP is based

a on plain text authentication.

**Slides s. 347:** (SF SFTP

SFTP Vs. FIPS

@ SFTP was designed as a secure extension of SSH.

@ Most OpenSSH installations on servers support SFTP.

{hy @ FTPS is FTP with the addition of SSL for security.

an 8 It requires additional configuration during FTP

installation

| FTPS and SFTP are entirely different protocols.

Lp acai

**Slides s. 348:** SSL Encryption Generate an SSL certificate for the Apache web

tS ] server and configure Apache to use SSL.

40-45 Min

— g , @ Generate a self-signed key.

es * ® Configure Apache to use SSL.

a y = ' @ Redirect Apache requests to HTTPS.

—6hdL GOA

} e's —_. _

| : a @ Openssl @ Lab document

; ; @ Apache

la |

</details>
