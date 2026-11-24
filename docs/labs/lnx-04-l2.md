# LNX-04-L2 — System Update and Upgrade

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 218–235.

## Cel, misja i środowisko

- G Lab Objective Understand how to use the package manager to update and install packages. bs Lab Mission Use the APT package manager to update the repository database, update
- bs Lab Mission Use the APT package manager to update the repository database, update repository links, and install the gitleaks binary. rN) "
- @ Lab Duration 10-20 minutes fe Requirements e Knowledge of APT package manager
- fe Requirements e Knowledge of APT package manager Lt [ea] Resources
- [ea] Resources e@ Environment and tools o VirtualBox =" Debian

## Zadania / etapy

1. Lab Task 1: Taking a Snapshot 1 Taking snapshots of a machine is important. Go to Machine > Take Snapshot. 2 Name the snapshot Fresh Debian Install. This allows you to know what the
2. Lab Task 2: Adding Kali Linux Apps Add Kali Linux applications by adding Kali repositories to the package manager. Note: To accomplish this lab, an active internet connection is required. 1 Open the terminal and use the command su — to switch to the root user.
3. Lab Task 3: Revert to the Snapshot 1. Torevert your VM, click the X in the top right corner. Then select Power off the machine and the check box to Restore current snapshot. Click OK. Page 6
4. Lab Task 1: Taking a Snapshot 1 Taking snapshots of a machine is important. Go to Machine > Take Snapshot. File Machine View Input Devices Help
5. Lab Task 3: Revert to the Snapshot 1. Torevert your VM, click the X in the top right corner. Then select Power off the machine and the check box to Restore current snapshot. Click OK. 2 Bako Twa ernment

## Komendy występujące w labie

```text
apt update. This should result in an error due to the requirement of a
su -
I
root@debians"# apt update
apt install gitleaks
nano /etc/apt/sources.list.d/kali.listl
Uf
apt update
ff
```

## Powiązana teoria

- [Apt Packages](../04-network-system/apt-packages.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 218:** Linux Security

Lab Assignment Networking

and System

Management

eo inn LNX-04-L2

oln JU System Update

and Upgrade

**PDF s. 219:** Linux Security

Lab Assignment Networking

and System

Management

eo inn LNX-04-L2

oln JU System Update

and Upgrade

**PDF s. 220:** G Lab Objective

Understand how to use the package manager to update and install packages.

bs Lab Mission

Use the APT package manager to update the repository database, update

repository links, and install the gitleaks binary.

rN) "

@ Lab Duration

10-20 minutes

fe Requirements

e Knowledge of APT package manager

Lt

[ea] Resources

e@ Environment and tools

o VirtualBox

=" Debian

**PDF s. 221:** Lab Task 1: Taking a Snapshot

1 Taking snapshots of a machine is important. Go to Machine > Take

Snapshot.

2 Name the snapshot Fresh Debian Install. This allows you to know what the

purpose of the snapshot is. You can also add notes in the description field.

Click OK. This snapshot will be of use later in the lab.

**PDF s. 222:** Lab Task 2: Adding Kali Linux Apps

Add Kali Linux applications by adding Kali repositories to the package manager.

Note: To accomplish this lab, an active internet connection is required.

1 Open the terminal and use the command su — to switch to the root user.

Use the command apt update to update the database of available packages.

2 Tryto install the package gitleaks with the command apt install gitleaks

If done correctly, this won't work, and you will get an error message stating

that the system cannot locate the package. This happens because Debian

does not have the required repository for this package.

3 Use the command nano /etc/apt/sources.|list.d/kali.list to create a file to

hold the required repository.

4 Add to the file the following Kali repository:

deb https://http.kali.org/kali kali-rolling main non-free contrib

Save the file and exit it. This will allow apt update to reach out to the

website to pull updates.

5 Try to update the database of available packages again using the command

apt update. This should result in an error due to the requirement of a

public key for this distribution.

6 Make sure you are in the root home directory. If not, use cd to navigate to

it.

**PDF s. 223:** 7 Use the command wget ‘https://archive.kali.org/archive-key.asc' to

download the required key. The key is required to interact with the Kali

Linux repository securely.

8 Use the command apt-key add archive-key.asc to import the downloaded

key to the operating system.

Note: If the import succeeded, you should get the message “OK.”

9 Use the command apt update again to update the database of available

packages.

10 Try to install the gitleaks application again using the command apt install

gitleaks -y

Note: The -y flag represents yes for the installation prompt. When asked to

restart services during installation, click Yes.

**PDF s. 224:** Lab Task 3: Revert to the Snapshot

1. Torevert your VM, click the X in the top right corner. Then select Power off

the machine and the check box to Restore current snapshot. Click OK.

**PDF s. 225:** Linux Security

Lab Assignment Networking

& Solution and System

Management

orn LNX-04-LS2

oln JU System Update

and Upgrade

**PDF s. 226:** Linux Security

Lab Assignment Networking

& Solution and System

Management

orn LNX-04-LS2

oln JU System Update

and Upgrade

**PDF s. 227:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Understand how to use the package manager to update and install packages.

ba) Lab Mission

Use the APT package manager to update the repository database, update

repository links, and install the gitleaks binary.

es .

©) Lab Duration

10-20 minutes

fe Requirements

e Knowledge of APT package manager

os

| Resources

¢ Environment and tools

o VirtualBox

=" Debian

**PDF s. 228:** Lab Task 1: Taking a Snapshot

1 Taking snapshots of a machine is important. Go to Machine > Take

Snapshot.

File Machine View Input Devices Help

GP Settings... Host+S

D session Information... Host+N.

==. File Manager...

Pause Host+P

© Reset Host+R

Y ACPI Shutdown Host+H

Take a snapshot of the virtual machine 2) (WiC? al? GS #) Right crt

2 Name the snapshot Fresh Debian Install. This allows you to know what the

purpose of the snapshot is. You can also add notes in the description field.

Click OK. This snapshot will be of use later in the lab.

[@ Take Snapshot of Virtual Machine 2 x

i@ ‘Snapshot Name

Fresh Debian Install] |

‘Snapshot Description

**PDF s. 229:** Lab Task 2: Adding Kali Linux Apps

Add Kali Linux applications by adding Kali repositories to the package manager.

Note: To accomplish this lab, an active internet connection is required.

1 Open the terminal and use the command su — to switch to the root user.

john@debian: ~ 4

john@debian:"$ su -

Passuord:

root@debian:"# I

2 Use the command apt update to update the database of available

packages.

john@debian: ~ x

root@debians"# apt update

Hits. http://security.debian.org/debian-security buster/updates InRelease

Hitt2 httpt//deb,debian,org/debian buster InRelease

Hit?3 http2//deb.debian.org/debian buster-updates InRelease

Reading package lists... Done

Building dependency tree

Reading state information... Done

All packages are up to date,

raot@debian:“# ff

**PDF s. 230:** 3 Tryto install the package gitleaks with the command apt install gitleaks

If done correctly, this won't work, and you will get an error message stating

that the system cannot locate the package. This happens because Debian

does not have the required repository for this package.

john@debian: ~ x

root@debian:”# apt install gitleaks

Reading package lists... Done

Building dependency tree

: Unable to locate package aitleaks

4 Use the command nano /etc/apt/sources.list.d/kali.list to create a file to

hold the required repository.

john@debian: ~ =

root@debian:# nano /etc/apt/sources.list.d/kali.listl

5 Add to the file the following Kali repository:

deb https://http.kali.org/kali kali-rolling main non-free contrib

Save the file and exit it. This will allow apt update to reach out to the

website to pull updates.

john@debian: ~ x

deb httpst/Anttp.kali.org/kali kali-rolling sain non-free contribl]

MR_Get Helo Where Is Cut Text Justify a Cur Pos

Wu Exit =] ahead Fite ms Replace i Uncut Text@ll To Spell Go To Line

**PDF s. 231:** 6 Try to update the database of available packages again using the command

apt update. This should result in an error due to the requirement of a

public key for this distribution.

john@debian: ~ x

rootl@debian?”# apt update

Hits1 https//deb.debian.org/debian buster InRelease

Hitz2 http3//security,debian,org/debian-security buster/updates InRelease

Hitz3 httpz//deb.debian.org/debian buster-updates InRelease

Setreyttps://kali.download/kali kali-rolling InRelease [30.6 kB]

Errz4 pttps://kali.dounload/kali kali-rolling InRelease

allowing signatures couldn't be verified because the public key is not av

jailable; NO_PUBKEY ED444FFO?D8DOBF5

Reading package lists... Done

i: GPG error: httpst//kali.download/kali kali-rolling InReleaset The following s

ignatures couldn't be verified because the public key is not available: NO_PUBKE

YY ED444FFO7DSDOBFE

E: The repository ‘https://http.kali.org/kali kali-rolling InRelease’ is not sig

ned,

IN: Updating from such a repository can't be done securely, and is therefore disa

bled by default,

IN; See apt-secure(8) manpage for repository creation and user configuration deta

ils.

root@debian:# Uf

7 Make sure you are in the root home directory. If not, use cd to navigate to

it.

**PDF s. 232:** 8 Use the command wget ‘https://archive.kali.org/archive-key.asc' to

download the required key. The key is required to interact with the Kali

Linux repository securely.

john@debian: ~ x

rootBdebian;"# wget ‘https://archive,kali.org/archive-key.asc'

—-2021-10-14 13:06:49-- https?//archive,kali.org/archive-key, asc

Resolving archive.kalisorg (archive.kali.org)... 192.99.45.140

Connecting to archive.kali.org (archive.kali.org) 1192.99.45.1401 2443... connecte

Sit request sent, awaiting response... 200 OK

Length: 3155 (3,1k) [application/octet-stream]

Saving to; ‘archive-key.asc”

archive-key, ase 1002[=sssssssssssss=s===>] 3,08K ——,-KB/s in 0s

2021-10-14 13:06:49 (184 MB/s) - ‘archive-key.ase” saved [3155/3155]

rootidebian:#

9 Use the command apt-key add archive-key.asc to import the downloaded

key to the operating system.

Note: If the import succeeded, you should get the message “OK.”

john@debian: ~ x

rootB@debian:”# apt-key add archive-key,asc

Pact ancl I

**PDF s. 233:** 10 Use the command apt update again to update the database of available

packages.

john@debian: ~ x

root@debian:"# apt update

Hite] httpt//security.debian,org/debian-security buster/updates InRelease

Hit:2 https//deb.debian.org/debian buster InRelease

Hit?3 httpt//deb,debian,org/debian buster-updates InRelease

Getz4 https://kali.download/kali kali-rolling InRelease [30.6 kB]

Get:5 httpst//kali.download/kali kali-rolling/main amd64 Packages [17.9 MB]

Get:6 https://kali.download/kali kali-rolling/non-free amd64 Packages [209 kB]

Get3? httpst//kali.download/kali kali-rolling/contrib amd64 Packages [111 kB]

Fetched 18.2 MB in Ss (3,526 kB/s)

Reading package lists... Done

Building dependency tree

Reading state information,,, Done

1359 packages can be upgraded. Run ‘apt list --upgradable' to see them.

root@debian:“# ff

**PDF s. 234:** 11 Try to install the gitleaks application again using the command apt install

gitleaks -y

Note: The -y flag represents yes for the installation prompt. When asked to

restart services during installation, click Yes.

john@debian: ~ x

Iroat@debiant”# apt install gitleaks -y

Reading package lists,,, Done

Building dependency tree

Reading state information,,, Done

The following NEW packages will be installed:

gitleaks

0 upgraded, 1 neuly installed, 0 to remove and 1359 not upgraded,

Need to get. 2,507 kB of archives,

After this operation, 8,350 kB of additional disk space will be used,

Gett1 httpst//kali,download/kali kali-rolling/main amd64 gitleaks amd64 7,5,0-0k

jalil (2,507 kB]

loz [1 gitleaks 0 B/2,507 kB Ox]§]

Note: Congratulations! You have installed a Kali distribution package in your

Debian Virtual Machine.

**PDF s. 235:** Lab Task 3: Revert to the Snapshot

1. Torevert your VM, click the X in the top right corner. Then select Power off

the machine and the check box to Restore current snapshot. Click OK.

2 Bako Twa ernment

FO Seve the shutdown sal

© © Power off the machine

[Restore current snapshot ‘Fresh Debian Install

ox Cancel Help

fe) aS PG iw) Rane on

</details>
