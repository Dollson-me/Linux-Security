# PAM Authentication Framework

[← 07 · Host Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 121–123; Linux Security.pdf, s. 274–280.

## Mapa wiedzy

- PAM (Pluggable Authentication Modules) centralizes authentication policy used by Linux services.
- The course uses PAM to enforce password complexity/history and to restrict SSH authentication behavior.
- Configuration under `/etc/pam.d` and password-quality modules such as `libpam-pwquality` are key practical elements.

## Komendy / pliki / składnia występujące w materiale

```text
vim /etc/quality/pwquality.conf
sudo apt install libpam-pwquality
sudo vim /etc/pam.d/common-password
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
```

## Notatki z zajęć (PadRiseup)

- `vim /etc/quality/pwquality.conf`
- `sudo apt install libpam-pwquality`
- `sudo vim /etc/pam.d/common-password`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-07-L2 — PAM Authentication Features](../labs/lnx-07-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 121:** dm-crypt is a disk encryption subsystem that uses the kernel’s crypto API framework.

dm-crypt can encrypt single files, logical volumes, partitions, or entire disks. Together

with LUKS, it allows different keys to access encrypted data.

Note: dm-crypt does not work solely with LUKS.

Lab Assignment: LNX-07-L1 Encrypt Grub & System

— Learn more about Linux host security, attacks hackers perform on machines

mm = after gaining access, and how the attacks are mitigated.

Follow the instructions in lab document LNX-07-L1.

Section 3: PAM

Pluggable Authentication Modules (PAM) reside between Linux applications and the

Linux native authentication system. Authentication in Linux is done by comparing a

password’s hash to the hash of the password in the /etc/shadow file, in which secure

user account information is stored.

johnd@debian: ~ x

File Edit View Search Terminal Help

_apt:* 99999:7

Systemd-timesync:* 10:99999:7

systemd-network:*: 19:99999:7:::

systemd-resolve:*: 99999:7

messagebus : * 99999:7:::

tes:*: 30:99999; 7255

dnsmasq:*: 0299999: 7:3:

usbmux: * 299999: 7

rtkit:*: :0:99999:7:::

sshd:*: S0:S9999!7 65:

pulse: * 199999:7

speech-dispatcher:! 99999:7:::

avahi:*: pR:909905755;

saned: * 99999:7

colord:* :99999:7

geoclue: *: :9:99999:7:::

hplip:*: 99999:7:

Debian-gdm: * 99999:7:::

jehnd:

99999:7

systemd-coredump:!!:18224 :B

38,31: Bot i

**Textbook s. 122:** Since many Linux programs and services require their own authentication mechanisms

and files, there is a potential for data to be inconsistent among the different types of

files.

With the introduction of PAM, one user database can be used for all services. PAM

integrates multiple low-level authentication modules into a high-level API that provides

dynamic authentication support for applications.

Using PAM, a system admin can deny or allow applications the right to authenticate

users or generate warnings when programs attempt to authenticate.

PAM has a modular design that provides complete control over how users are

authenticated simply by editing a configuration file, regardless of the authentication

scheme of a certain program or service. This is due to a library containing the functions

for the proper authentication scheme that is loaded with PAM.

PAM's features include:

- Prevents the use of old passwords based on their age.

- Provides uniform operation among system users.

- Is structured in modules that can interface with services, like SSH.

Packages PAM uses for its operation include:

- cracklib-runtime — a library that prevents users from configuring a weak password

that can easily be cracked.

- libpam-pwquality —a library that provides multiple options for password quality

checks, and rates the passwords based on their randomness.

**Textbook s. 123:** When PAM is configured, different tokens are available for use to control the created

policy:

Operator Meaning

Auth Checks if users are who they claim to be.

Required Control flag for modules.

on Module used to deny or allow services based on an

Pam_listfile.so : ‘

arbitrary file.

Onerr Set to ‘succeed’ (module argument).

Item User (specifies what is listed).

Sense Allow (specifies which action to take).

rifts /etc/ssh/sshd.allow (argument, specifies a file containing

one item per line, such as a user name).

The configuration of PAM can be done through a single file, located at /etc/pam.conf,

or spread across individual files per program or service, located in the /etc/pam.d

directory.

Note: /etc/pam.d takes precedence over /etc/pam.conf.

Lab Assignment: LNX-07-L2 PAM Authentication Features

— How to enforce strong user password policies in Linux.

=m

Follow the instructions in lab document LNX-07-L2.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 274:** Host Security

PAM

**Slides s. 275:** se 12

What Is PAM?

. .o8 @ Pluggable authentication module

wal @ Performs authentication, authorization, and modification

= @ Can control who can run su (switch user command)

@ Password policies can be configured using PAM.

Cc % =

**Slides s. 276:** we MV

@ Checks user accounts based on conditions, such as

cm. user expiration date

© @ Authenticates users to third-party password systems

us ®@ Enforces password policies

=— @ User sessions are created after users successfully

authenticate.

| OpenPAM is an alternative Linux-based PAM. &-

Cc % = .

**Slides s. 277:** we ss

fess | PAM can prevent the reuse of old passwords. “

Y Enforcing PAM ensures uniform operation

5.9 [> | among users.

= PAM is divided into modules that can interface

with services like SSH.

ee

**Slides s. 278:** we MV

r

: Cracklib-runtime is a library that prevents users from

ae---] choosing passwords that can easily be cracked.

Libpam-pwquality provides common functions

for password quality checks and rates

passwords based on their randomness.

Lp ala

**Slides s. 279:** (To ce

O | auth Checks if users are who they claim to be

| required Control flag for module usage

am listfile.so A module used to deny or allow services

Pam_ . based on arbitrary files

onerr Should be set to fail (module argument for various

system operations)

| item User (specifies what is listed)

| sense Allow (specifies which action to take)

file /etc/ssh/sshd.allow (argument; specifies a file é

containing one item per line, such as a username)

20

**Slides s. 280:** PAM

Lab: LNX-07-L2 [ees

e VIISSION

aan SS Learn how to enforce strong user password policies in

PAM Authentication Features Linux for new user creation and password resetting.

20-30 Min. —

a ; @ Set password complexity.

— = : ®@ Disable reuse of the 10 oldest passwords.

$i, ” E “elke @ Restrict PAM SSH authentication.

i b NN s e yr

| 2 ® tT - ® PAM @ Lab document

=} ON ® SSHD

; ‘ @ PuTTY

| { ; 4 . is

if ’ . |

Tr. —a

</details>
