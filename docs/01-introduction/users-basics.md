# Linux User Types & Privilege Model

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 16–16; Linux Security.pdf, s. 30–32.

## Mapa wiedzy

- The material distinguishes service users, regular users and root/superusers.
- Root can access and modify all system resources, so compromise or careless use of root has system-wide impact.
- `/etc/passwd` is introduced as a quick way to inspect user accounts; later chapters expand this with `/etc/shadow`, groups, sudo and permissions.

## Komendy / pliki / składnia występujące w materiale

```text
Service Users
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
cat sorted_local_users.txt | grep -v root
chown root:adm /var/log/boot.log
chown root:root /var/log/boot.log
visudo
apt purge sudo
apt install sudo
sudo whoami
usermod -a -G sudo piotr
sudo su
sudo cat /etc/shadow
sudo ip addr del 10.0.2.15/24 dev enp0s3
sudo apt install net-tools
sudo apt update
sudo apt upgrade
sudo apt-key add archive-key.asc
sudo rm kali.list
sudo apt install apache2
sudo vim ports.conf
sudo systemctl restart apache2
sudo apt install nginx
sudo netstat -tulpn
sudo apt install openssh-server
sudo apt install samba
sudo apt install vsftpd
sudo update-grub
sudo apt install cracklib-runtime
sudo apt install libpam-pwquality
```

## Notatki z zajęć (PadRiseup)

- `root`
- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `cat sorted_local_users.txt | grep -v root`
- `chown root:adm /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `visudo`
- `apt purge sudo`
- `apt install sudo`
- `sudo whoami`
- `usermod -a -G sudo piotr`
- `sudo su`
- `sudo cat /etc/shadow`
- `sudo ip addr del 10.0.2.15/24 dev enp0s3`
- `sudo apt install net-tools`
- `sudo apt update`
- `sudo apt upgrade`
- `sudo apt-key add archive-key.asc`
- `sudo rm kali.list`
- `sudo apt install apache2`
- `sudo vim ports.conf`
- `sudo systemctl restart apache2`
- `sudo apt install nginx`
- `sudo netstat -tulpn`
- `sudo apt install openssh-server`
- `sudo apt install samba`
- `sudo apt install vsftpd`
- `sudo update-grub`
- `sudo apt install cracklib-runtime`
- `sudo apt install libpam-pwquality`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 16:** Section 6: Users

In Linux, there are three user types:

e Service users

e Regular users

© Root user or superuser

A simple way to view all users in the system is to read the contents of the /etc/passwd

file. Each line in that file contains information about a single user.

Service Users

Generally, service users run non-interactive or background processes on a system, while

regular users can log in and run interactive processes.

Regular Users

A regular user is added by the root user and has low-level permissions. This user cannot

perform high-level actions in the system. Also known as super-do, a sudo is a normal

user added to sudo groups by the root user. This user may be assigned permissions to

access and execute some root commands.

Root Users

A root user, or superuser, is the highest-level user in the system. Each system has its

own root admin user. Root users can access all files in the system and execute all

commands.

A root user can override any file ownership, permissions, or restrictions. In addition,

their ability to perform system-wide changes means their accounts must be kept

secure.

An unsecure superuser account means a hacker can assume superuser privileges and

make changes to other user accounts in the system.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 30:** Introduction to Linux

Users

**Slides s. 31:** (Us Users

e System (root) users

e Super users

cu} e Sudo users

A e Regular users

System users have the highest privileges

in the Linux environment.

<p

**Slides s. 32:** (Pr Users

Root users can perform any task in

the system. ial

Super users can perform only what

they are permitted to do in the system.

Regular users can perform only basic

tasks in the system

i

</details>
