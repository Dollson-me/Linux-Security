# LNX-07-L1 — Encrypt GRUB & System

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 399–420.

## Cel, misja i środowisko

- G Lab Objective Acquire a better understanding of Linux host security, what types of attacks hackers can perform on machines once they gain physical access, and how to mitigate those attacks. ba) Lab Mission
- ba) Lab Mission Learn how to use Grub to password-protect your bootloader and prevent malicious users from obtaining information about your Linux environment. es .
- ©) Lab Duration 30-40 minutes tC) Requirements e Knowledge of the Grub boot process.
- tC) Requirements e Knowledge of the Grub boot process. LT [ea] Resources
- [ea] Resources e¢ Environment & Tools o VirtualBox =" Debian

## Zadania / etapy

1. Lab Task 1: Password-Protect Your Bootloader Conduct a privilege escalation attack that displays the output of a shadow file, and mitigate the vulnerability by installing Grub encryption functionality, and encrypting Grub with a password.
2. Lab Task 2: VM Restoration In this task you will return your Debian machine to its previous state, prior to password protection. 1 Close your virtual machine.

## Komendy występujące w labie

```text
cat <<EOF
password_pbkdf2 [user] [paste the generated code copied above here]
apt #2 1852430:99999:73::
su -
grub-mkpasswd-pbkdf2
fj
| | ;
nano Grub Pass |
id Exit i Read File gy Replace gl! Uncut Text
| |
nano /etc/grub.d/00_header fj |
update-grub
done
reboot] |
```

## Powiązana teoria

- [Boot Protection](../07-host-security/boot-protection.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 399:** Linux Security

Lab Assignment Host Security

LNX-07-L1

Encrypt Grub & System

oon

Ooln

ES

All Rights Reserved.

**PDF s. 400:** Linux Security

Lab Assignment Host Security

LNX-07-L1

Encrypt Grub & System

oon

Ooln

ES

All Rights Reserved.

**PDF s. 401:** G Lab Objective

Acquire a better understanding of Linux host security, what types of attacks hackers can

perform on machines once they gain physical access, and how to mitigate those attacks.

ba) Lab Mission

Learn how to use Grub to password-protect your bootloader and prevent malicious

users from obtaining information about your Linux environment.

es .

©) Lab Duration

30-40 minutes

tC) Requirements

e Knowledge of the Grub boot process.

LT

[ea] Resources

e¢ Environment & Tools

o VirtualBox

=" Debian

o Grub

o CLI

**PDF s. 402:** Lab Task 1: Password-Protect Your Bootloader

Conduct a privilege escalation attack that displays the output of a shadow file, and

mitigate the vulnerability by installing Grub encryption functionality, and encrypting Grub

with a password.

1 Click the menu icon of your Debian VM and select Snapshots.

2 Click Take to create a new snapshot for the VM.

3 Name the snapshot and click OK.

4 Start the Debian VM and press C as soon as the splash screen appears.

5 When the command-line loads, use the command cat /etc/shadow to read the

contents of the shadow file. Note that the command was executed with high

level permissions and the content of the file can be viewed.

6 Press Esc to exit the Grub console, press Enter to boot Debian normally, and log

in to your user.

7 Open the terminal and use the command su — to switch to the root user.

8 Use the command grub-mkpasswd-pbkdf2 to generate a Grub password. Enter a

password and make sure you remember it.

9 Copy the password as follows: select it using the cursor, right-click it, and select

Copy.

10 Use the command nano Grub_Pass to create a new file and open it.

11. Right-click in the file and paste the password. Save and exit the file.

12. Right-click the terminal, and click New Tab to open another terminal tab.

13 Inthe new tab, use the command su — to switch to the root user.

14 Use the command nano /etc/grub.d/00_header to open the file 00_header.

**PDF s. 403:** Note: This is a Grub configuration file.

15. Scroll to the end of the file and insert the following lines:

cat <<EOF

set superusers="[user]"

password_pbkdf2 [user] [paste the generated code copied above here]

EOF

Set the user as "student" and use the code generated earlier.

Save and exit the file.

16 Run the command update-grub.

17 Use the command reboot to reboot the workstation, and enter the Grub

console by pressing C when the splash screen appears. Note that this time Grub

requests a user name and password.

Note: This method prevents malicious users from obtaining information, such as

reading sensitive files, searching for plain text passwords, and reading

workstation settings.

**PDF s. 404:** Lab Task 2: VM Restoration

In this task you will return your Debian machine to its previous state, prior to password

protection.

1 Close your virtual machine.

2 Click the menu icon of your Debian VM and select Snapshots.

3. Right-click the name of the VM's previous state and click Restore.

4 Deselect Create a snapshot of the current machine state, and click Restore.

5 Run the machine and note that it returned to its previous state.

**PDF s. 405:** Linux Security

Lab Assignment Host Security

& Solution inane

Encrypt Grub & System

oon

Ooln

ES

All Rights Reserved.

**PDF s. 406:** Linux Security

Lab Assignment Host Security

& Solution inane

Encrypt Grub & System

oon

Ooln

ES

All Rights Reserved.

**PDF s. 407:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Acquire a better understanding of Linux host security, what types of attacks hackers can

perform on machines once they gain physical access, and how to mitigate those attacks.

ey Lab Mission

Learn how to use Grub to password-protect your bootloader and prevent malicious

users from obtaining information about your Linux environment.

ea 7

©@ Lab Duration

30-40 minutes

rt ) Requirements

e Knowledge of the Grub boot process.

os

| Resources

¢ Environment & Tools

o VirtualBox

=" Debian

o Grub

o CL

**PDF s. 408:** Lab Task 1: Password-Protect Your Bootloader

Conduct a privilege escalation attack that displays the output of a shadow file, and

mitigate the vulnerability by installing Grub encryption functionality, and encrypting Grub

with a password.

1 Click the menu icon of your Debian VM and select Snapshots.

& Orecle VIM VirtualBox Manager - Oo x

Fle Machine Snapshot Help

bhi = a2 Sieic es.

ize) > Coa |

sree Gil srersto.

=

(=) Ubuntu ———

= Atubutes | Informaten

Sisto nune: [tr arane or te tew napa,

=n Ee

**PDF s. 409:** 2 Click Take to create a new snapshot for the VM.

@ Oracle VM VirtualBox Manager - ao x

File Machine Snapshot |Help

US 2a Blo @ oe.

sake _peete neste |propees| Gone _Setings oscad stat

= Name Takes

® © Gurrent state

[ea] ‘CentOS (Snapshot 1)

vbunte

CZ) windows 10 hibies nema

= west

3 Name the snapshot and click OK.

8% Take Snapshot of Virtual Machine ? x

Snapshot Name

Snapshot Description

a

**PDF s. 410:** 4 Start the Debian VM and press C as soon as the splash screen appears.

GNU GRUB version 2.02+dfs¢1-20

Debian GNU/Linux

Advanced options for Debian GNU/Linux

Use the 7 and | keys to select which entry is highlighted.

Press enter to boot the selected 05, “e' to edit the commands

before booting or “c' for a command-line.

**PDF s. 411:** 5 When the command-line loads, use the command cat /etc/shadow to read the

contents of the shadow file. Note that the command was executed with high

level permissions and the content of the file can be viewed.

gnatsix:18524:9:99999r7i i:

nobody: «:18524:6:99999: 7:2:

apt #2 1852430:99999:73::

systemed-t imesync:%:18524:9:99999:7:::

systemd-network:*:18524:6:99999:7:::

systemd-resolve:«: 18524:9:99999:7:::

messagebus:*:18524:9:99999:7:::

dnsmasg:*:18524:9:99999: 7:2:

usbmux::18524:9:99999: 72:2

ptkit:#:18524:@:99999:7:::

pulse:x:19524:0:99999:7:::

speech-dispatcher: |:18524:6:99999:7:::

avahdt:18524:6:99999:7it:

Saned:#:18524:@:99999:7:::

colord:#:18524:4:99999: 7:2:

geoclue:*:18524:9:99999: 7:2:

Deblan-gdm:%:18524:9:99999: 722:

John: $629x85ve5F 1 l20GKIP$aHU8 Ic Ftu. SPO3VYIKHIGSP¥nmnSHHFeg2kWoxOSFstEVTItJa.B

chGoxbfboyVil L2ppSHJHRO Jk. SiwEK4F@:18524:6:99999: 7:2:

systemd-coredump:!!:18524:i:i::

Vboxadd: !:18524:iii::

Jane: $6$kPAng/k42kpURBSDS5AT sOcadpo02NVSPBk 1GhodVoOPbsRePyoUBog5Sp7ATaGIIRKbGX

SpuzM2IcvIjJeqFeRHMCISOZK IMGawvPATOL: 18534:6:99999: 7: i:

sshdi#:18535:0:99999:7:::

Ftpik: 18595:0:99999:7it:

**PDF s. 412:** 6 Press Esc to exit the Grub console, press Enter to boot Debian normally, and log

in to your user.

GNU GRUB version 2.02+dfs¢1-2@+debleuz

Debian GNU/Linux

Advanced options for Debian GNU/Linux

Use the 7 and | keys to select which entry is highlighted.

Press enter to boot the selected 05, “e' to edit the commands

before booting or “c' for a command-line.

7 Open the terminal and use the command su — to switch to the root user.

john@debian: ~ *

File Edit View Search Terminal Help

john@debian:~$ su -

Password:

root@debian:~#

**PDF s. 413:** 8 Use the command grub-mkpasswd-pbkdf2 to generate a Grub password. Enter a

password and make sure you remember it.

I john@debian: ~ x |

File Edit View Search Terminal Help

root@debian:~# grub-mkpasswd-pbkdf2

Enter password:

Reenter password:

PBKDF2 hash of your password is grub.pbkdf2.sha512.1000

©. 16B69B174E8720BD088F 7E4848003DF8FEE9DE58E1B152932B533

AC3B6ADAC30A9E3242CCC5C37B84414D0461DE549C77ACOF8AE69CO

16ED99A93DCB4A76AA86. BB3CB0550C9A233B0668004C4FC9E57EC6

BCOQBOED72A9A66FE65C96B6385D5878AE5B35031E74AFDBFDEDO74

54F2D3CE3077EB15A47B603D8719C65AAD8FBOE

root@debian:~# fj

9 Copy the password as follows: select it using the cursor, right-click it, and select

Copy.

j john@debian: ~ x j

File Edit View Search Terminal Help

root@debian:~# grub-mkpasswd-pbkdf2

Enter password:

Reenter password:

PBKDF2 hash of your password iS (efgille@pels) <oheam-int-lon Warm Role]¢)

Ce a |

B602C33B7EB13FE5125AFB873F18C32E296267342) = copyasutm. =—98

93FF2669EE62534C8558.8FDASCODBF2157D3BEE1| _ ..... FBI

(0O4BCBC770665E00A9762750E8791CA23469B48F9| © Read-Only Pal

21242AFF525FECF90AB482E2F183F9105226270

7 Preferences

root@debian: ~# | | ;

New Window

**PDF s. 414:** 10 Use the command nano Grub_Pass to create a new file and open it.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# nano Grub Pass |

11. Right-click in the file and paste the password. Save and exit the file.

j john@debian: ~ x |

File Edit View Search Terminal Help

GNU nano 3.2 Grub Pass

|

O Read-Only

Preferences

New Window

New Tab

(4 Show Menubar

[ New File ]

ime Get Help @@ Write Out @i] Where Is (iq Cut Text

id Exit i Read File gy Replace gl! Uncut Text

john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 Grub Pass Modified

Rjrub. pbkdf2.sha512.10000.42B510E29FF2D54FA113164DAEDD6$

Get Help Write Out @] Where Is MW Cut Text

Exit @@ Read File @N Replace J Uncut Text

**PDF s. 415:** 12. Right-click the terminal, and click New Tab to open another terminal tab.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:~# | |

© Read-Only

Preferences

New Window

New Tab

13 Inthe new tab, use the command su — to switch to the root user.

john@debian: ~ x

File Edit View Search Terminal Tabs Help

i~$ SU -

Password:

root@debian:~#

14 Use the command nano /etc/grub.d/00_header to open the file 00_header.

Note: This is a Grub configuration file.

john@debian: ~ x

File Edit View Search Terminal Tabs Help

john@debian: ~ john@debian: ~ A +

root@debian:~# nano /etc/grub.d/00_header fj |

**PDF s. 416:** 15. Scroll to the end of the file and insert the following lines:

cat <<EOF

set superusers="[user]"

password_pbkdf2 [user] [paste the generated code copied above here]

EOF

Set the user as "student" and use the code generated earlier.

Save and exit the file.

john@debian: ~ x

File Edit View Search Terminal Tabs Help

john@debian: ~ jehn@debian: ~ fH +

GNU nano 3.2 /etc/grub.d/00 header Modified

EOF

superusers t t

password pbkdf2 student grub.pbkdf2.sha512.10000.744BF$

EOF

Get Help Write Out MJ] Where Is f@ Cut Text

Exit ls; Read File @N Replace @y Uncut Text

16 Run the command update-grub.

john@debian: ~ x

File Edit View Search Terminal Tabs Help

john@debian: john@debian: ~ SZ

root@debian:~# update-grub

Generating grub configuration file ...

Found background image: /usr/share/images/desktop-base/desktop-grub.png

Found linux image: /boot/vmlinuz-4.19.0-10-amd64

Found initrd image: /boot/initrd.img-4.19.0-10-amd64

Found linux image: /boot/vmlinuz-4.19.0-8-amd64

Found initrd image: /boot/initrd.img-4.19.0-8-amd64

done

root@debian:~# fj

**PDF s. 417:** 17 Use the command reboot to reboot the workstation, and enter the Grub

console by pressing C when the splash screen appears. Note that this time Grub

requests a user name and password.

Note: This method prevents malicious users from obtaining information, such as

reading sensitive files, searching for plain text passwords, and reading

workstation settings.

john@debian: ~ o

File Edit View Search Terminal Tabs Help

john@debian: ~ john@debian: ~ & +

root@debian:~# reboot] |

Enter username:

student

Enter password:

**PDF s. 418:** Lab Task 2: VM Restoration

In this task you will return your Debian machine to its previous state, prior to password

protection.

1 Close your virtual machine.

ia You want to:

(B O save the machine state

F CO send the shutdown signal

© Poner off the machine |

(CJ Restore current snapshot ‘Before Grub Encryption’

Coe] been ae

BO so DEH GwWrortcn

**PDF s. 419:** 2 Click the menu icon of your Debian VM and select Snapshots.

Oracle VM VirtualBox Manager - a x

File Machine Snapshot |Help

Uf Boas gaged.

‘ake _Oekte Rese | propetes| Gone _Setings Oscad stat

a De ves |. sal

3 ‘Centos (Snapshot 1) ol a

© Povered oF =

=

vbunte

ee Atwbuies fermaton

= west

3 Right-click the name of the VM's previous state and click Restore.

& Orecle VM VirtualBox Manager -— oOo x

File Machine Snapshot Help

ces 14383 8% :

Take _DeleteRestre properties, Gone Setings Uscard_ start

= Name Tien

GS cretsen eens ®B dete... Ctrl ShitteD

ie] Centos (Snapshot 1)

Sireseor Properties Ctrl= Shifts P-

{39 ubuntu G Gee. Certs Shite

Are Atbies Ifermaton

EE] © roveres ont name: fare Gab raypion SS

Apply ‘Reset

**PDF s. 420:** 4 Deselect Create a snapshot of the current machine state, and click Restore.

iy ley

Take_veete_nesbre [moperses| cone setings Dscard_ stat

Name Taken

(WB Before Grab Enenption 1/10/2020 929 7 minutesage)

© Current State (changed)

3 Centos (Snapshot 1) VirtualBox - Question 7 x

© Ponered OFF

)) You are about to restore snapshot

— @ sxe:

Soe eae

spe rete te fe cree eae

[=] windows 10 permanently lost. Do you wish to proceec?

Orrcator

feriy | | Reset

5 Run the machine and note that it returned to its previous state.

</details>
