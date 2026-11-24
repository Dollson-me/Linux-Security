# LNX-06-L1 — Basic Scripting

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 349–359.

## Cel, misja i środowisko

- G Lab Objective Practice using common Linux commands, Bash scripting, and Bash operators. La Lab Mission Design a script for penetration testing that uses the ping command to obtain
- La Lab Mission Design a script for penetration testing that uses the ping command to obtain information on network endpoints. ea 7
- ©) Lab Duration 15-20 minutes £e Requirements e Knowledge of Bash commands and script syntax
- £e Requirements e Knowledge of Bash commands and script syntax Lt | Resources
- | Resources ¢ Environment & Tools o VirtualBox = Debian OS

## Komendy występujące w labie

```text
ip a command.
ip a
fj
ping 5 10.0.2.$iff
echo "" liveHosts
echo “[+] pinging 10.0.2.$i"
ping -c 5 10.0.2. | grep “bytes from" liveHosts
echo "Done!"
cat LiveHosts; {if
chmod +x pingsweep.sh
./pingsweep.sh
```

## Powiązana teoria

- [Bash Introduction](../06-bash/bash-introduction.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 349:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L1

A isis! Basic Scripting

Ooln

EI

All Rights Reserved.

**PDF s. 350:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L1

A isis! Basic Scripting

Ooln

EI

All Rights Reserved.

**PDF s. 351:** G Lab Objective

Practice using common Linux commands, Bash scripting, and Bash operators.

La Lab Mission

Design a script for penetration testing that uses the ping command to obtain

information on network endpoints.

ea 7

©) Lab Duration

15-20 minutes

£e Requirements

e Knowledge of Bash commands and script syntax

Lt

| Resources

¢ Environment & Tools

o VirtualBox

= Debian OS

o Text editor

**PDF s. 352:** Lab Task: Design a Penetration Testing Script

Conduct penetration testing in your client’s company and scan for live hosts on the

network to gain a better understanding of the network’s activities.

1 Log into Debian and switch users to root using the su - root command.

Use Linux commands to write a script that will check for live hosts.

First, determine the current subnet of your workstation using the

ip a command.

In the example above, you can see the workstation IP is 10.0.2.15/24, which

means the network name is 10.0.2.0 and there are 254 hosts on the network.

2 Create and access a Bash script file using nano to create the file pingsweep.sh.

3 Write a for loop in the Bash script that uses ping to find live hosts on the subnet.

The script may need to be altered based on the environment.

4 Using echo, cat, and grep, overwrite the liveHosts file so it does not contain any

data. Note: The file liveHosts will be created by the echo command if one does

not exist.

5 Create a for loop that will ping all hosts on the network (1..255) and print the

results to the terminal. Make the loop append the results to the /iveHosts file so

only the relevant information is appended. To do so, search the results of the

loop for bytes from and append it to the latest version of the liveHosts file.

6 Save the script, make the script file executable, and run it. To do so in Nano, use

Ctrl + O to save, and exit the file using Ctrl + X.

After you exit Nano, use the chmod +x <file name> command to make the script

executable, and use ./ to run the file.

Note: To stop the script, press Ctrl + Z.

**PDF s. 353:** Linux Security

Lab Assignment Bash Scripting

& Solution

LNX-06-LS1

A isis! Basic Scripting

Ooln

EJ

All Rights Reserved.

**PDF s. 354:** Linux Security

Lab Assignment Bash Scripting

& Solution

LNX-06-LS1

A isis! Basic Scripting

Ooln

EJ

All Rights Reserved.

**PDF s. 355:** Note: Solutions for the instructor are shown in the green box.

G Lab Objective

Practice using common Linux commands, Bash scripting, and Bash operators.

5 Lab Mission

Design a script for penetration testing that uses the ping command to obtain

information on network endpoints.

of :

@ Lab Duration

15-20 minutes

fe Requirements

e Knowledge of Bash commands and script syntax

LT

[ra] Resources

¢ Environment & Tools

o VirtualBox

= Debian OS

o Text editor

**PDF s. 356:** Lab Task: Design a Penetration Testing Script

Conduct penetration testing in your client’s company and scan for live hosts on the

network to gain a better understanding of the network’s activities.

1 Log into Debian and switch users to root using the su - root command.

Use Linux commands to write a script that will check for live hosts.

First, determine the current subnet of your workstation using the

ip a command.

johnd@debian: ~ x

File Edit View Search Terminal Help

:~$ su - root

Password:

root@debian:~# ip a

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group defaul

t qlen 1000

link/lLoopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

inet 127.0.0.1/8 scope host lo

valid lft forever preferred lft forever

inet6 1/128 scope host

valid lft forever preferred lft forever

2: enp@s3: <BROADCAST,MULTICAST,UP,LOWER UP> mtu 1500 qdisc pfifo fast state UP

group default qlen 1000

link/ether 08:00:27:0f:8b:a0 brd ff:ff:ff:ff:tf: ff

inet 10.0.2.250/24 brd 10.0.2.255 scope global enp0s3

valid lft forever preferred lft forever

inet 10.0.2.15/24 brd 10.0.2.255 scope global secondary dynamic enpds3

valid_lft 86313sec preferred_lft 86313sec

inet6 fe80::a00:27ff:feOf:8ba0/64 scope Link

valid lft forever preferred lft forever

root@debian:~# fj

In the example above, you can see the workstation IP is 10.0.2.15/24, which

means the network name is 10.0.2.0 and there are 254 hosts on the network.

**PDF s. 357:** 2 Create and access a Bash script file using nano to create the file pingsweep.sh.

3 Write a for loop in the Bash script that uses ping to find live hosts on the subnet.

The script may need to be altered based on the environment.

GNU nano 3.2 pingsweep.sh

i ie. 25)

ping 5 10.0.2.$iff

4 Using echo, cat, and grep, overwrite the liveHosts file so it does not contain any

data. Note: The file /iveHosts will be created by the echo command if one does

not exist.

user@debian: ~

File Edit View Search Terminal Help

GNU nano 3.2 pingsweep.sh

**PDF s. 358:** 5 Create a for loop that will ping all hosts on the network (1..255) and print the

results to the terminal. Make the loop append the results to the /iveHosts file so

only the relevant information is appended. To do so, search the results of the

loop for bytes from and append it to the latest version of the liveHosts file.

user@debian: ~ %

File Edit View Search Terminal Help

GNU nano 3.2 pingsweep.sh Modified |f

echo "" liveHosts

# | e Je | |

f din’ €1...255}

echo “[+] pinging 10.0.2.$i"

ping -c 5 10.0.2. | grep “bytes from" liveHosts

echo "Done!"

cat LiveHosts; {if

We Get Help @@ Write Out gi) Where Is iM cut Text MJ Justify me Cur Pos

Wi Exit Mii Read File ga} Replace @Y Uncut Textggy To Spell gi Go To Line

6 Save the script, make the script file executable, and run it. To do so in Nano, use

Ctrl + O to save, and exit the file using Ctrl + X.

Get Help @ Write Out gi) Where Is Cut Text (@) Justify me Cur Pos

Exit fii Read File @@) Replace Uncut Text@™j To Spell (@™™ Go To Line

**PDF s. 359:** After you exit Nano, use the chmod +x <file name> command to make the script

executable, and use ./ to run the file.

root@debian:~# chmod +x pingsweep.sh

root@debian:~# ./pingsweep.sh

[+] pinging 10.0.2.1

[+] pinging 10.0.2.2

[+] pinging 10.0.2.3

[+] pinging 10.0.2.4

[+] pinging 10.0.2.5

[+] pinging 10.0.2.6

[+] pinging 10.0.2.7

[+] pinging 10.0.2.8

[+] pinging 10.0.2.9

[+4] pinging 10.0.2.10

Note: To stop the script, press Ctrl + Z.

</details>
