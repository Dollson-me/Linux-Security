# Learning Path — Linux Security

Rekomendowana kolejność przejścia materiału. Każdy etap łączy teorię z laboratoriami.

## 1. Introduction to Linux

- [Linux History, Kernel & Linux vs. Windows](01-introduction/linux-history.md)
- [Linux Distributions & Dedicated Environments](01-introduction/distributions.md)
- [Open-Source Philosophy & Licenses](01-introduction/open-source.md)
- [Linux Installation & Virtual Machines](01-introduction/installation.md)
- [System Libraries & Linux Filesystem Hierarchy](01-introduction/filesystem-hierarchy.md)
- [Linux User Types & Privilege Model](01-introduction/users-basics.md)
- [CLI Interface, Prompts & Command Syntax](01-introduction/cli-interface.md)
- [Terminal Emulators & Graphical Applications](01-introduction/terminal-emulators.md)

**Laby:** [LNX-01-L1 — Distribution Research](labs/lnx-01-l1.md), [LNX-01-L2 — Debian Installation](labs/lnx-01-l2.md), [LNX-01-L3 — GNOME DE Installation](labs/lnx-01-l3.md), [LNX-01-L4 — Graphical Apps](labs/lnx-01-l4.md)

## 2. CLI Fundamentals

- [Shell Types & System Awareness](02-cli/shells-system-awareness.md)
- [Command Structure, Help & Manuals](02-cli/command-structure.md)
- [File System Structure & Navigation](02-cli/file-system-structure.md)
- [Listing Files, Hidden Files & File Types](02-cli/listing-files.md)
- [Working with Files & Directories](02-cli/files-directories.md)
- [Data Streams, Redirection & Text Editors](02-cli/data-streams-editors.md)
- [Grep Basics](02-cli/grep-basics.md)
- [Find & Locate](02-cli/find-locate.md)
- [Command History](02-cli/history.md)

**Laby:** [LNX-02-L1 — System Information](labs/lnx-02-l1.md), [LNX-02-L2 — Moving Files in the File System](labs/lnx-02-l2.md), [LNX-02-L3 — Editing Files](labs/lnx-02-l3.md), [LNX-02-L4 — Search](labs/lnx-02-l4.md)

## 3. Users & Permissions

- [Pipes, Redirection & Compound CLI Workflows](03-users-permissions/piping-redirection.md)
- [Advanced Grep & AWK](03-users-permissions/advanced-grep-awk.md)
- [Additional CLI Commands & Environment](03-users-permissions/additional-commands.md)
- [User Management](03-users-permissions/users.md)
- [Password Management & Policy](03-users-permissions/password-management.md)
- [Groups & Membership](03-users-permissions/groups.md)
- [Linux File Permissions & Ownership](03-users-permissions/permissions.md)
- [SUID, SGID & PATH Security](03-users-permissions/suid-sgid-path.md)

**Laby:** [LNX-03-L1 — Advanced Piping](labs/lnx-03-l1.md), [LNX-03-L2 — Creating Users](labs/lnx-03-l2.md), [LNX-03-L3 — Group Management](labs/lnx-03-l3.md), [LNX-03-L4 — The Power of SUID](labs/lnx-03-l4.md)

## 4. Networking & System Management

- [Network Testing: ping & traceroute](04-network-system/ping-traceroute.md)
- [Linux Network Files & Configuration](04-network-system/network-configuration.md)
- [System Update, Upgrade & APT](04-network-system/apt-packages.md)
- [Apache HTTP Server](04-network-system/apache.md)
- [Other System Applications: Logwatch, Nginx & Services](04-network-system/other-applications.md)

**Laby:** [LNX-04-L1 — Static and Dynamic IP Configuration](labs/lnx-04-l1.md), [LNX-04-L2 — System Update and Upgrade](labs/lnx-04-l2.md), [LNX-04-L3 — Install and Configure Apache](labs/lnx-04-l3.md), [LNX-04-L4 — Service Debugging](labs/lnx-04-l4.md)

## 5. Services & Hardening

- [Common Linux Services & Protocols](05-services-hardening/common-services.md)
- [SSH & SCP](05-services-hardening/ssh-scp.md)
- [FTP & vsftpd](05-services-hardening/ftp.md)
- [Samba / SMB File Sharing](05-services-hardening/samba.md)
- [Service Hardening Principles](05-services-hardening/service-hardening.md)
- [Bash Scripting for Administration](05-services-hardening/bash-admin.md)

**Laby:** [LNX-05-L1 — Install and Configure SSH](labs/lnx-05-l1.md), [LNX-05-L2 — Install and Configure Samba and FTP](labs/lnx-05-l2.md), [LNX-05-L3 — Securing Services](labs/lnx-05-l3.md)

## 6. Bash Scripting

- [Bash Scripting Introduction](06-bash/bash-introduction.md)
- [Script Input, Output, Variables & Arguments](06-bash/script-io.md)
- [Conditions & Control Flow](06-bash/conditions.md)
- [Arithmetic Operators](06-bash/arithmetic.md)
- [Archives, tar, gzip & Backups](06-bash/archives-backups.md)
- [File Integrity Monitoring with Hashes](06-bash/file-integrity.md)
- [Crontab / Cron Automation](06-bash/cron.md)

**Laby:** [LNX-06-L1 — Basic Scripting](labs/lnx-06-l1.md), [LNX-06-L2 — Compression and Backup](labs/lnx-06-l2.md), [LNX-06-L3 — File Integrity Monitoring](labs/lnx-06-l3.md), [LNX-06-L4 — Scripting for Security](labs/lnx-06-l4.md)

## 7. Host Security

- [Linux External Mounting & Removable Media](07-host-security/external-mounting.md)
- [GRUB, Boot Protection & Disk Encryption](07-host-security/boot-protection.md)
- [PAM Authentication Framework](07-host-security/pam.md)
- [SELinux & AppArmor](07-host-security/selinux-apparmor.md)
- [Privilege Escalation](07-host-security/privilege-escalation.md)
- [Cron Security & Scheduled-Task Abuse](07-host-security/cron-security.md)

**Laby:** [LNX-07-L1 — Encrypt GRUB & System](labs/lnx-07-l1.md), [LNX-07-L2 — PAM Authentication Features](labs/lnx-07-l2.md), [LNX-07-L3 — Cron Security Vulnerability](labs/lnx-07-l3.md)

## 8. Network Security

- [iptables Firewall](08-network-security/iptables.md)
- [firewalld](08-network-security/firewalld.md)
- [Fail2Ban](08-network-security/fail2ban.md)
- [Log Monitoring & Security Analysis](08-network-security/log-monitoring.md)
- [Detecting / Countering Apache Enumeration](08-network-security/apache-enumeration.md)
- [Secure Apache & ModSecurity](08-network-security/secure-apache.md)
- [Banner Hiding for SSH & Apache](08-network-security/banner-hiding.md)
- [SSL/TLS Encryption for Web Services](08-network-security/ssl-tls.md)
- [SFTP vs FTP / FTPS](08-network-security/sftp.md)

**Laby:** [LNX-08-L1 — Configure a Whitelist](labs/lnx-08-l1.md), [LNX-08-L2 — Summary Exercise](labs/lnx-08-l2.md), [LNX-08-L3 — Configure ModSecurity](labs/lnx-08-l3.md), [LNX-08-L4 — SSL Encryption](labs/lnx-08-l4.md)

## Final Project

- [Linux Fundamentals — Final Project](projects/linux-final-project.md)
