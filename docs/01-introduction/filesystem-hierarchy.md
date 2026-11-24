# System Libraries & Linux Filesystem Hierarchy

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 14–15; Linux Security.pdf, s. 27–29.

## Mapa wiedzy

- Linux uses a single rooted filesystem beginning at `/`. Paths and filenames are case-sensitive.
- The course explains core directories such as `/root`, `/boot`, `/etc`, `/home`, `/mnt`, `/sbin`, `/bin`, `/dev`, `/lib`, `/tmp`, `/var`, `/usr`, `/proc` and `/sys`.
- Configuration is concentrated under `/etc`; logs and variable data under `/var`; devices are represented under `/dev`; process/system information is exposed through pseudo-filesystems such as `/proc` and `/sys`.
- Linux treats many resources as files or streams, which is important for administration and scripting.

## Komendy / pliki / składnia występujące w materiale

```text
cat /etc/ssh/ssh_config
grep -in Fire /var/log/dpkg.log --color
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
cp /etc/shadow
vim /etc/quality/pwquality.conf
chown root:adm /var/log/boot.log
chmod 640 /var/log/boot.log
chmod 644 /var/log/boot.log
chown root:root /var/log/boot.log
ls -la /usr/bin/passwd
sudo cat /etc/shadow
sudo vim /etc/pam.d/common-password
echo "piotr" > /etc/ssh/sshd.allow
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
sudo vim /etc/apache2/conf-available/security.conf
cd /etc/apache2/mods-enabled
sudo vim /etc/apache2/sites-available/default-ssl.conf
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/ssh/ssh_config`
- `grep -in Fire /var/log/dpkg.log --color`
- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `more /var/log/dpkg.log`
- `less /var/log/dpkg.log`
- `cp /etc/shadow`
- `vim /etc/quality/pwquality.conf`
- `chown root:adm /var/log/boot.log`
- `chmod 640 /var/log/boot.log`
- `chmod 644 /var/log/boot.log`
- `chown root:root /var/log/boot.log`
- `ls -la /usr/bin/passwd`
- `sudo cat /etc/shadow`
- `/etc/init.d/networking stop`
- `/etc/init.d/networking start`
- `/etc/vsftpd.conf`
- `1 #!/bin/bash`
- `#!/bin/bash`
- `file=/var/www/html/index.html`
- `/etc/grub.d/00_header`
- `sudo vim /etc/pam.d/common-password`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`
- `sudo vim /etc/apache2/conf-available/security.conf`
- `/etc/init.d/apache2 force-reload`
- `cd /etc/apache2/mods-enabled`
- `sudo vim /etc/apache2/sites-available/default-ssl.conf`
- `SSLCertificateFile /etc/ssl/certs/apache_selfsigned.crt`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 14:** Section 5: System Libraries

OS Root Directories

Files and directories are organized in a single-root inverted tree structure. The file

system begins at the root directory, represented by a forward slash (/). Names are case-

sensitive, and paths are delimited by a forward slash.

/

2 |@|@/|@/|@

(oat) Gore) Cm) Gm) an)

©

© ©

/root — super user home directory

/boot — kernel image

/etc — system configuration files

/home — user directories

/mnt— mount points

/sbin — executables

/dev — device files

/bin — executables

/lib - libraries

Some important directories include:

**Textbook s. 15:** e /root, /home/<username>

The home folder(s)

e /bin, /usr/bin, /usr/local/bin

/sbin, /usr/sbin, /usr/local/sbin

Binary program files

e /media and /mnt

External file system and mount points

Additional directories include:

« /etc - System config files

+ /tmp - Temporary files

* /boot - Kernel and bootloader

* /var and /srv - Server data

* /procand /sys - System information

* /lib - Library directories

For file and directory names, all characters are valid, except the forward slash. It is

important to be careful when using some special characters in file or directory names,

and some characters should appear in quotes when they are referenced.

Names are case-sensitive. For example, MAIL, Mail, mail, and mAiL are all different file

names, and while they can all be used, caution should be applied when doing so.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 27:** Introduction to Linux

System Libraries

**Slides s. 28:** Gc: System Libraries

Every directory has a

dedicated purpose.

Bin and sbin store

binaries.

Media and mnt are

| all used to mount drives.

Home stores personal

user files.

28

**Slides s. 29:** (Ac System Libraries

.

e /tmp—stores temporary files. Do not

save personal files in this directory.

e /etc—important folder in which

application settings are saved.

e /var—stores system logs.

Directory names are important in Linux

and are case-sensitive.

Q\ = ,

</details>
