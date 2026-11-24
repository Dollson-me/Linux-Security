# System Update, Upgrade & APT

[← 04 · Networking & System Management](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 75–77; Linux Security.pdf, s. 152–158.

## Mapa wiedzy

- Packages bundle application files and dependency information; APT is the Debian-family package-management workflow used throughout the course.
- `apt update` refreshes package indexes; `apt upgrade` upgrades installed packages; `apt install` and `apt purge` add/remove software.
- APT repository configuration lives under `/etc/apt`, especially `sources.list` and files in `sources.list.d`.
- Class notes include repository/key handling and package installation for tools used later in the course.

## Komendy / pliki / składnia występujące w materiale

```text
lsof
source lists can be configured freely in all distributions. For example, Kali tools can be
Apt Package Manager
apt install — installs packages
apt remove — removes packages
apt update — updates package lists for upgrades
apt upgrade — updates existing packages to the newest available version
which can then be retrieved and installed using the apt install command.
apt upgrade
apt update
apt install htop
apt install Linux-headers-$(uname-r)
apt install gedit
apt purge sudo
apt install sudo
apt install firefox
sudo apt install net-tools
sudo apt update
sudo apt upgrade
sudo apt install apache2
sudo apt install nginx
sudo apt install openssh-server
sudo apt install samba
sudo apt install vsftpd
apt update && apt upgrade
sudo apt install cracklib-runtime
sudo apt install libpam-pwquality
sudo apt install libapache2-mod-security2
sudo apt install git
```

## Notatki z zajęć (PadRiseup)

- `apt update`
- `apt install htop`
- `apt install Linux-headers-$(uname-r)`
- `apt install gedit`
- `apt purge sudo`
- `apt install sudo`
- `apt install firefox`
- `sudo apt install net-tools`
- `sudo apt update`
- `sudo apt upgrade`
- `sudo apt install apache2`
- `sudo apt install nginx`
- `sudo apt install openssh-server`
- `sudo apt install samba`
- `sudo apt install vsftpd`
- `apt update && apt upgrade`
- `sudo apt install cracklib-runtime`
- `sudo apt install libpam-pwquality`
- `sudo apt install libapache2-mod-security2`
- `sudo apt install git`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-04-L2 — System Update and Upgrade](../labs/lnx-04-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 75:** lsof

Another system indicator tool is Isof, which displays open files, local and network, from

the specific host in which the command is executed. The lsof command displays results

only from the directory it is executed from and if a user does not have permission to

view the file, the output will be readlink: permissions denied. Some files are not

accessible to users, such as system files that are located in the root directory, while

others are displayed with the directory path, process ID (PID), node, user, file type, and

device.

Section 3: Updating and Upgrading

During Linux installation, a file in the /etc/apt/ directory called sources.list is installed.

Many Debian based distributions make use of a directory of list files called

/etc/apt/sources.list.d/. The purpose of the files is to communicate with the sources

listed in the file for online updates. Since Linux is an open-source operating system,

source lists can be configured freely in all distributions. For example, Kali tools can be

distributed in the Debian environment by adding a Kali distribution source list.

Package

A package is a type of archive that contains all files required for a binary to be installed

and operate properly. In some cases, a package may also list other packages required

for the specific binary.

Packages are typically installed by software called "Package Manager", which is a simple

and highly efficient utility for installing, updating, and removing binaries. The package

manager is operated via commands and does not require the use of browsers and

download websites.

Apt Package Manager

Debian uses a package manager called "apt" that provides a wide selection of options to

handle packages.

The options include:

apt install — installs packages

**Textbook s. 76:** apt remove — removes packages

apt update — updates package lists for upgrades

apt upgrade — updates existing packages to the newest available version

Updating the system does not mean it installs the packages. Instead it saves a list of the

newest versions of the available packages in the /var/cache/apt/archives directory,

which can then be retrieved and installed using the apt install command.

Repositories

The paths listed in the sources.list directory are called repositories, which are storage

locations that Linux designates for all packages (a remote server). The file can be

located in the /etc/apt/ directory and there are also several files in the

/etc/apt/sources.list.d/ directory.

When an update or installation command is initiated, the system must have internet

connection to access the repository. Without the connection, the system will not be

able to view the information in the repository.

Changes can be made in the sources.list file to change the accessed repositories, but

such changes require root access.

**Textbook s. 77:** jehn@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 jetc/apt/sources.list

ke

# deb cdrom: [Debian GNU/Linux 10.3.0 Buster_ - Official amd64 NETINST 20200208$|

deb cdrom: [Debian GNU/Linux 10.3.0 Buster_ - Official amd64 NETINST 20200208-$

rt main

1 re main

1 main

/ main

# buster-updates, previously known as ‘volatile’

: : main

l# This system was installed using small removable media

i (e.g. netinst, live or single CD). The matching “deb cdrom”

# entries were disabled at the end of the installation process

# For information about how to configure apt package sources

# see the sources.list(5) manual

ig Set Help GM) write out MM] where Is MM cut Text fB) justify 9 cur Pos

ie Exit i Read File MN Replace aU Uncut Textgay To Spell gj Go To Line

Lab Assignment: LNX-04-L2 System Update & Upgrade

— Obtain a more comprehensive understanding of how Linux repositories

mm | work and practice using the repositories of other distributions.

Follow the instructions in lab document LNX-04-L2.

Debian package (Dpkg) files (.deb) allow for the easy installation and removal of

applications, and provide information about the package. Dpkg is a common way to

install and remove applications in a Linux environment.

® | Good to Know

Dpkg stores and saves information about .deb files.

' :

x ¢ | Tip

a © * | To install a Debian package, use the command: dpkg -i file.deb

=

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 152:** Linux Security

Updating and

Upgrading

**Slides s. 153:** (Pa Updating and Upgrading

@ A package is an archive file that contains all

the files of an application.

®@ Italso lists the installations for other packages

+ + that are dependencies of the application.

—_— @ Packages are usually installed via a package

manager, such as APT or YUM.

Cc % =

**Slides s. 154:** (AF Updating and Upgrading

; @ APTis a Debian package manager.

®@ It can download, install, and remove packages.

- @ apt install is used for installation.

s ® apt remove is used for installation removal.

i

Cc % =

**Slides s. 155:** (sy Updating and Upgrading

O

, apt update

Updates package lists for upgrades.

Installation packages are downloaded

7 to /var/cache/apt/archives.

apt upgrade

Installs all available package updates.

Lp ala

**Slides s. 156:** (So Updating and Upgrading

®@ Located in the /etc/apt directory

ely a Fs °

@ The file name is sources.list or can be a number

of files in /etc/apt/sources.list.d/.

®@ \t points to available packages and available

package versions.

®@ \t also discloses the distributor.

Cc % =

**Slides s. 157:** Updating and Upgrading

File Edit View Search Terminal Help

GNU nano 3.2 fetc/apt/sources. List

#

A user must have root

permissions to change the # deb cdrom:[Debian GNU/Linux 10.1.0 Buster_ - Official amd64 NETINST 20190908%

repositories in the source #deb cdrom: [Debian GNU/Linux 10.1.0 Buster_ - Official amd64 NETINST 20190908-$

list.

main

‘ : main

Software repositories

contain software main

mair

packages. ae

# buster-updates, previously known as ‘volatile'

Communication with a main

: = main

repository requires the

network to be open to # This system was installed using small removable media

th t | t k # (e.g. netinst, Live or single CD). The matching “deb cdrom"

OMMEPeXte (nal DELWOMKS: # entries were disabled at the end of the installation process.

Me Get Help me) Write i, Where Ts ex eel Justify me Cur Pos

**Slides s. 158:** Updating and Upgrading

2 eee Use the APT package manager to update the repository

System U pdate and U pgrade | brane update repository links, and install the WPScan

10-20 Min A

- ee SS @ Update the repository database.

, @ Adda Kali repository.

il — S. . ‘ = I ® Install WPScan.

(w ("/ r i ® Work with WPScan.

Nae? ff f 04 j

a | i | : ey ®@ Install gitleaks

ad _ = ® 8 da

a | .) A s ~~ ELEiVibiWVitiiitiit CA IV INSIGtCOU Piito

| i) re ®@ Debian @ Lab document

& @ Package manager

| :

: 4

| ) |

{ \ % ia. >. “=

</details>
