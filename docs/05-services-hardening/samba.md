# Samba / SMB File Sharing

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 89–91; Linux Security.pdf, s. 191–195.

## Mapa wiedzy

- Samba provides SMB/CIFS-based sharing between Linux and Windows systems.
- The course installs Samba, configures shares/users and tests access from a Windows client.
- Hardening focuses on limiting who can access shares, controlling permissions and avoiding unnecessary exposure.

## Komendy / pliki / składnia występujące w materiale

```text
sudo apt install samba
systemctl restart samba
net use
net use \192.168.1.68\tempuser /d
```

## Notatki z zajęć (PadRiseup)

- `sudo apt install samba`
- `systemctl restart samba`
- `net use`
- `net use \192.168.1.68\tempuser /d`

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

**Textbook s. 89:** Section 4: Samba

Samba is a service that operates via the SMB protocol, which is responsible for file

sharing in a network. The shared directory that it opens is specified in the smb.conf

configuration file located in /etc/samba. The configuration file allows selection of

different access permissions, such as allowing write operations to the directory,

permitting browsing in other directories, and more.

Samba Installation

The installation process is straightforward, and the service is installed via the apt

package manger.

Before installing Samba, it is recommended to have a fixed IP address to avoid

unnecessary changes to the configuration file.

johnd@debian: ~ x

File Edit View Search Terminal Help

Package configuration

Samba server and utilities

If your computer gets IP address information from a DHCP server on the

network, the DHCP server may also provide information about WINS servers

("NetBIOS name servers") present on the network. This requires a change

to your smb.conf file so that DHCP-provided WINS settings will

automatically be read from /var/lib/samba/dhcp.conf.

The dhcp-client package must be installed to take advantage of this

feature.

Modify smb.conf to use WINS settings from DHCP?

<Yes> iNo>}

Aconfiguration change in the smb.conf file

**Textbook s. 90:** Smb.conf

Samba's configuration file is used to manage all the options regarding data sharing. The

file contains comments that explain the different options and assists in the

configuration process.

The process includes the following steps:

e The first configuration option in the file specifies the service's work environment,

meaning whether or not it is a workgroup of a domain.

e To share a folder, its name and path must be specified.

e The folder’s read and access permissions must be set. For example, allow writing to

the share, and provide guest access to it.

e Any change in the configuration file requires a system restart.

aii _________~si

john@debian: /etc/samba x

File Edit View Search Terminal Help

[global]

workgroup = WORKGROUP

ime Get Help @@ Write Out @]) Where Is iN Cut Text @@] Justify fe cur Pos

ma Exit i Read File gy Replace @ Uncut Textgj To Spell @ Go To Line

Part of the smb.conf configuration file

**Textbook s. 91:** SMB Vs. NFS

NSF (Network File System) is a protocol used to access files from a remote network.

SMB NFS

Supports Windows Supports some Windows versions

More complex than NFS Setting up a connection is fast and easy

Meant for multiple users Meant for downloading documents only

R b d fi

FSSISLESISS (6} A) I51S ABE AeeP AEETAD Can be run from a single machine

other resources

Lab Assignment: Install and Configure Samba & FTP

— Perform basic configuration of Samba, provide access via MS Windows

=m = client, and create an FTP server to transfer files from another machine.

Follow the instructions in lab document LNX-05-L2.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 191:** Services and Hardening

Samba

**Slides s. 192:** Samba

ivities ] Terminal + Thu 06:33 > «, ©

johnd@debian: ~ x

File Edit View Search Terminal Help |

Package configuration

Samba is a tool used for file

eee eres sharing among workstations

: ; via the SMB protocol.

If your computer gets IP address information from a DHCP server on the

network, the DHCP server may also provide information about WINS servers

("NetBIOS name servers") present on the network. This requires a change . . .

to your smb.conf file so that DHCP-provided WINS settings will Samba installation requires

automatically be read from /var/lib/samba/dhcp.conf. additional configuration

The dhcp-client package must be installed to take advantage of this

feature.

When you set up a Samba

Modify smb.conf to use WINS settings from DHCP? ege

server, it is recommended to

“ have a fixed IP address.

20

**Slides s. 193:** Samba

smb.conf

-

TEE Specify the work environment (workgroup or

2ROd domain) for the Samba server to be recognized. “

r 7 Set the sharing of the folder name and path,

= | set reading permissions, and specify if a guest

L| co connection is permitted.

© Restart Samba to apply the changes. ee

ee

**Slides s. 194:** (SN Samba

SMB vs. NFS

O

= SMB NFS

Supports Windows Supports some

PP Windows versions

More complex than NFS | | Fast and easy to set up

Meant for multiple users Meanitier downloading

documents only

Resources can be managed Can be run from a single

from other resources machine

22

**Slides s. 195:** Samba

Lab: LNX-05-L2 Jee

Perform a basic configuration of Samba, provide

Install and Configure Samba and FTP access via MS Windows client, and create an FTP

30-40 Min | server to transfer files from another machine.

& | @ ®@ Install Samba.

sn :

. , a «€ ® Configure a shared file.

= ‘ cm oss L , <p eA

; “~~ ® Access from the host computer.

LG ; 0, @) @ Set up FTP and use it for a file transfer.

| a @ ft ®@ Debian ® Lab document

|| ® Windows

| |

4

.

} i % ia =~

</details>
