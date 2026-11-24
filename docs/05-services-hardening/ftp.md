# FTP & vsftpd

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 87–88; Linux Security.pdf, s. 186–190.

## Mapa wiedzy

- FTP is a client/server file-transfer protocol. The course uses the `ftp` client and `vsftpd` server.
- FTP credentials and data are not encrypted; project screenshots explicitly demonstrate that login/password information can be observed in traffic.
- `vsftpd.conf` controls service behavior and the lab changes the listening port as part of hardening before restoring the default.
- SFTP/FTPS are introduced as safer alternatives later in the course.

## Komendy / pliki / składnia występujące w materiale

```text
FTP works with two sides: one is the client and the other is the server.
FTP Installation
FTP Commands Meaning
cd Changes the directory
delete Deletes a file
which is located in /etc/.
FTP
apt-get install ~ Ai Connection is over
sudo apt install vsftpd
systemctl restart vsftpd.service
ftp 192.168.1.68
```

## Notatki z zajęć (PadRiseup)

- `sudo apt install vsftpd`
- `/etc/vsftpd.conf`
- `systemctl restart vsftpd.service`
- `ftp 192.168.1.68`
- `listen_port=201`

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

**Textbook s. 87:** Section 3: FTP

FTP works with two sides: one is the client and the other is the server.

The client application is called ftp and the server application is called vsftpd.

The client and server applications may not be pre-installed in the Linux distribution by

default.

FTP Installation

The installation process for the client is simple and requires the execution of a single

command: apt install ftp

After the installation, a connection can be established to a server simply by providing

the name of the application and the target IP address, for example: ftp 10.0.0.1

Upon connection, the CLI of the ftp server will appear and allow command execution.

FTP Commands Meaning

append Appends a file

bye Terminates the connection

cd Changes the directory

cdup Goes to the parent directory

close Ends the session

delete Deletes a file

get Receives a file

A browser can also be an ftp client, as long as the protocol is specified in the target URL.

**Textbook s. 88:** Si Index of ftp://localhost/ x tS

< ee ® fp://localhost ~~ OW IO =

Index of ftp://localhost/

4 Up to higher level directory

Name Size Last Modified

B Desktop 11/5/19 2:17:00 AM EST

©) Documents 11/5/19 1:59:00 AM EST.

[5 Downloads 11/5/19 1:59:00 AM EST

Music 11/5/19 1:59:00 AM EST.

[Pictures 11/5/19 1:59:00 AM EST.

(Public 11/5/19 1:59:00 AM EST

© Templates 11/5/19 1:59:00 AM EST

Access to FTP server via a browser

File Sharing

The protocol allows file sharing among parties, and can also be used to deploy a file

storage server that users can access via CLI or a browser and download files from it. The

server's access permissions can be controlled via its configuration file, vsftpd.conf,

which is located in /etc/.

The default installation of an FTP server is considered unsecure, since all the data is

transferred in plain text.

vsftpd

This is the server side of the FTP communication. The server is responsible for running

the FTP daemon and stores all information regarding the service and its configurations.

Installation of the vsftpd service is done using the command: apt install vsftpd

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 186:** Services and Hardening

FTP

**Slides s. 187:** FTP

(FTP Installation

Users are from

the local OS.

apt-get install ~ Ai Connection is over

the internet or CLI.

a service vsftpd start Y :

**Slides s. 188:** Fil FTP

File Sharing

O @ Index of ftp:/flocalhost!) x | +

a

)37 Ca @ ftp://localhost —~ OW IO =

Files can be shared

using the FTP protocol.

Files are stored in a single Index of ftp://localhost/

station and publicly

shared. & Up to higher level directory

A default FTP installation Name aie LastModified

is notiseaure. since the J Desktop 15/19 2:17:00 AM EST

Is oe , i Pl Documents 11/5/19 1:59:00 AM EST

THAHIG 38 NGRENERE AUER. © Downloads 1/5/19 1:59:00 AM EST

© Music 15/19 1:59:00 AM EST

[Pictures 11/5/19 1:59:00 AM EST

© Public 11/5/19 1:59:00 AM EST

[Templates 11/5/19 1:59:00 AMEST

16

**Slides s. 189:** (FT FTP

O

* append: to append a file ° close: end session

° bye: terminate connection ° delete: delete a file

° cd: change directory ° get: receive a file

° cdup: go to parent directory

| There are many more commands and flags for advanced FTP usage.

17,

**Slides s. 190:** we t

® There are two sides of FTP: client and server.

® Theserver runs the FTP daemon and contains

the information.

® The configurations are set from a server that

hosts the FTP server.

| To install the FTP server, run apt install vsftpd &-

Cc % = if

</details>
