# LNX-08-L2 — Summary Exercise

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 482–497.

## Cel, misja i środowisko

- G Lab Objective Learn how to automate the management of security by writing a Bash script that will check logs for malicious users and ban them. s Lab Mission
- s Lab Mission Create a Bash script that blocks IP addresses through Iptables, when the limit of 404 error login attempts is exceeded. ea .
- © Lab Duration 60-75 minutes tC) Requirements e Proficiency with Bash scripting
- tC) Requirements e Proficiency with Bash scripting e Proficiency with Linux system commands. LT
- [ea] Resources e¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Prepare the Lab Set up the Debian environment with requisite log files and directories that replicate a web server that was attacked. 1 Loginto the Debian VM and change to the root user with the command su -.
2. Lab Task 2: Create the Script In this task, you will write a script to check if an IP address is trying to execute a brute- force attack through standard directories and web pages. If an IP has more than three 404 status codes (page not found) in the access.log, block it using Iptables.
3. Lab Task 3: Run the Script and Check the Results Run the script and check the results to verify that the IPs attacking the web server were blocked. If no IPs were blocked, troubleshoot each part of the script to ensure it was written properly.
4. Lab Task 1: Prepare the Lab Set up the Debian environment with requisite log files and directories that replicate a web server that was attacked. 1 Login to the Debian VM and change to the root user with the command su -.

## Komendy występujące w labie

```text
nano IPCheck.sh
ip nf D
iptables -A INPUT /32 -d 0/0 -j DROP
| . /IPCheck. sh
|cat /var/log/badIP
[]
man iptables .
/iptables -L
```

## Powiązana teoria

- [Log Monitoring](../08-network-security/log-monitoring.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 482:** Linux Security

Lab Assignment Network Security

5 LNX-08-L2

onan 5 .

olf ummary Exercise

Ea

All Rights Reserved.

**PDF s. 483:** Linux Security

Lab Assignment Network Security

5 LNX-08-L2

onan 5 .

olf ummary Exercise

Ea

All Rights Reserved.

**PDF s. 484:** G Lab Objective

Learn how to automate the management of security by writing a Bash script that will

check logs for malicious users and ban them.

s Lab Mission

Create a Bash script that blocks IP addresses through Iptables, when the limit of 404

error login attempts is exceeded.

ea .

© Lab Duration

60-75 minutes

tC) Requirements

e Proficiency with Bash scripting

e Proficiency with Linux system commands.

LT

[ea] Resources

e¢ Environment & Tools

o VirtualBox

= Debian

o Iptables

e Extra Lab Files

o ApzEEpi6

**PDF s. 485:** Lab Task 1: Prepare the Lab

Set up the Debian environment with requisite log files and directories that replicate a

web server that was attacked.

1 Loginto the Debian VM and change to the root user with the command su -.

Then download or transfer the provided log file named ApzEEpi6 to the Debian

VM.

2 Move the downloaded file to /var/log/apache2/access.log and rename it.

To move and rename the file, use a single mv command, as follows:

3 Open /var/log/apache2/access.log with a text editor and find the IP and status

code columns. The IP address will be in the first column, and the status code will

be in the ninth column.

**PDF s. 486:** Lab Task 2: Create the Script

In this task, you will write a script to check if an IP address is trying to execute a brute-

force attack through standard directories and web pages. If an IP has more than three

404 status codes (page not found) in the access.log, block it using Iptables.

1 Create a file named IPCheck.sh and open it with a text editor.

2 Start the script with the shebang line, then define a variable to a new log file,

bad IP, in the directory /var/log/.

3 Use the previously-defined variable to write an if-then statement that will create

the log, if it does not already exist, in the /var/log/ directory.

4 Filter the IP addresses (using piping) for the number of 404 errors, as follows:

Use the awk command to extract only the status code and IP of each line.

Use the grep command to filter only lines with 404 status codes

Use the cut command to extract only the IP address

Use the unig -c command to count the IP address.

Use output redirection (>) to save the results in the file in /tmp/hosts.

Notes:

The ‘awk’ command refers to the input from the 'cat' command as a table.

Therefore, the 1st and 9th columns refer to IP addresses and status codes.

Using the -f flag in the ‘cut’ command will parse the IP address and remove the

status code from the output of the ‘awk’ command.

The ‘unig -c’ command will count the number of times each IP appears from the

results filtered by the previous commands and output as a table with two

columns (count and IP address).

5 Adda ‘while’ loop that reads each line from the /tmp/hosts file used in the

previous step (do not close the loop, it will continue to run in the next step).

The ‘line’ within the while loop will read each line of the file appended in the

previous step.

6 Create a variable in the loop that will use the piping and cut commands to count

and include only the number of attempts made by each IP address in the

/tmp/hosts file.

**PDF s. 487:** The variable will take a line from the appended file (/tmp/hosts) defined as ‘line’

and cut out the first column of text (the number of times an IP was rejected).

7 Create another variable in the loop that uses the piping and cut commands to

include all IPs in the /tmp/host file.

The variable will cut out the second column of text (the list of rejected IPs).

8 Inthe previous loop, write an if-then statement to check if the number of

attempts is greater than or equal to three. Leave the if statement open for now.

9 Insert the date of the blocked IP and the IP in the file /var/log/badIP.

10 Print information about the blocked IP address.

11 Insert the IP addresses with a /32 CDIR in the Iptables list, to drop the

connection. Then end with ‘fi’ and close the loop.

The ‘iptables’ command is the IPv4 netfilter firewall included in the Linux kernel.

This command is used to make a rule dropping packets coming from a defined

IP/CIDR.

-A is used to append a rule.

-s refers to the source address.

-d refers to the destination address.

-j specifies what to do with the packets.

When combined, this iptables command determines that future packets from the

specified IP will be dropped.

12 Make the script executable using the chmod command.

**PDF s. 488:** Lab Task 3: Run the Script and Check the Results

Run the script and check the results to verify that the IPs attacking the web server were

blocked. If no IPs were blocked, troubleshoot each part of the script to ensure it was

written properly.

1 Run the IPCheck.sh script from the terminal and check /var/log/badIP for the

results.

2 Use iptables -L to check if the IPs were blocked.

**PDF s. 489:** Linux Security

Lab Assignment Network Security

& Solution

5 LNX-08-LS2

onan 5 .

olf ummary Exercise

El

All Rights Reserved.

**PDF s. 490:** Linux Security

Lab Assignment Network Security

& Solution

5 LNX-08-LS2

onan 5 .

olf ummary Exercise

El

All Rights Reserved.

**PDF s. 491:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Learn how to automate the management of security by writing a Bash script that will

check logs for malicious users and ban them.

5 Lab Mission

Create a Bash script that blocks IP addresses through Iptables, when the limit of 404

error login attempts is exceeded.

oe 2

@ Lab Duration

60-75 minutes

fe Requirements

e Proficiency with Bash scripting

e Proficiency with Linux system commands.

Lt

| Resources

e Environment & Tools

o VirtualBox

=" Debian

o Iptables

e Extra Lab Files

o ApzEEpi6

**PDF s. 492:** Lab Task 1: Prepare the Lab

Set up the Debian environment with requisite log files and directories that replicate a

web server that was attacked.

1 Login to the Debian VM and change to the root user with the command su -.

Then download or transfer the provided log file named ApzEEpi6 to the Debian

VM.

2 Move the downloaded file to /var/log/apache2/access.log and rename it.

To move and rename the file, use a single mv command, as follows:

| reot@debian: /etc/apache2# my ApzEEp16 /var/log/apache2/access. log

3 Open /var/log/apache2/access.log with a text editor and find the IP and status

code columns. The IP address will be in the first column, and the status code will

be in the ninth column.

GNU nano 3.2 7war/ log/apache2/access. log

46.72.21.13)- - [12/Dec/2015:18:39:27 +0100] "POST /administrator/index.php HTTP/1.1" 200|/4494 “http: //exa$

17.20.11.13|- - [12/Dec/2615:18:40:58 +0160] "GET /administrator/ HTTP/1.1" 2060/4263 "-" "Mozilla/5.0 (Wing

17.20.11.13)- - [12/Dec/2015:18:40:58 +0100] "POST /administrator/index.php HTTP/1.1" 200 |4494 “http: //exa$

17.35.10.41)- - [12/Dec/2015:18:44:48 +0100] "GET /administrator/ HTTP/1.1" 200 4263 "-" "Mozilla/5.@ (Wing$

17.35.10.41)- - [12/Dec/2015:18:44:48 +0100] "POST /administrator/index.php HTTP/1.1"| 200 4494 "http: //exa$

92.25.16.97|- - [12/Dec/2015:18:44:53 +0166] "GET /administrator/ HTTP/1.1" 206 4263 "-""Mozilla/5.0 (Win$

92.25.16.97|- - [12/Dec/2015:18:44:53 +0100] "POST /administrator/ index.php HITP/1. 1g) 200 4494 "http: //exa$

31.20.23.21 - - [12/Dec/2015:18:46:21 +0100] "GET /administrator/ HTTP/1.1"/200|4263 *= Mozilla/5.0 (wing

31.20.23.21 - - [12/Dec/2015:18:46:21 +0100] "POST /administrator/index.php HTTP/1.1"|200 4494 "http: //exa$

83.21.15.23|- - [12/Dec/2015:18:46:25 +0100] "GET /administrator/ HTTP/1.1" 200 4263 “= Mozilla/5.0 (Wing

83.21.15.23|- - [12/Dec/2015:18:46:25 +0100] "POST /administrator/index.php HITP/1.1"| 200 4494 “http: //exa$

46.72.18.17|- - [12/Dec/2015:18:51:08 +0100] "GET /administrator/ HTTP/1.1" 200 4263 ‘= Mozilla/5.0 (wing

46.72.18.17)- - [12/Dec/2015:18:51:08 +0100] "POST /administrator/index.php HTTP/1.1" 200 4494 “http: //exa$

17.11.13.82|- - [12/Dec/2615:18:51:25 +0160] "GET /administrator/ HTTP/1.1" 200 4263 "-" "Mozilla/5.6 (Wing

17.11.13.82)- - [12/Dec/2015:18:51:25 +0100] "POST /administrator/index.php HTTP/1.1" 200 4494 “http: //exa$

17.47,18.16|}- - [12/Dec/2015:18:53:10 +0100] "GET /administrator/ HTTP/1.1" 200 4263 "-" "Mozilla/5.@ (Win$

17.47.18.16|- - [12/Dec/2015:18:53:11 +0100] "POST /administrator/index.php HTTP/1.1" 200 4494 “http: //exa$

17.44.14.23)- - [12/Dec/2015:18:57:24 +0160] "GET /administrator/ HTTP/1.1" 200 4263 "-" "Mozilla/5.6 (Win$

17.44.14.23)- - [12/Dec/2015:18:57:24 +0100] "POST /administrator/index.php HTTP/1.1" 200 4494 “http: //exa$

**PDF s. 493:** Lab Task 2: Create the Script

In this task, you will write a script to check if an IP address is trying to execute a brute-

force attack through standard directories and web pages. If an IP has more than three

404 status codes (page not found) in the access.log, block it using Iptables.

1 Create a file named IPCheck.sh and open it with a text editor.

See

root@debian:~# nano IPCheck.sh

2 — Start the script with the shebang line, then define a variable to a new log file,

badIP, in the directory /var/log/.

GNU nano 3.2 TPcheck.sh

3 Use the previously-defined variable to write an if-then statement that will create

the log, if it does not already exist, in the /var/log/ directory.

4 Filter the IP addresses (using piping) for the number of 404 errors, as follows:

Use the awk command to extract only the status code and IP of each line.

Use the grep command to filter only lines with 404 status codes

Use the cut command to extract only the IP address

Use the unig -c command to count the IP address.

Use output redirection (>) to save the results in the file in /tmp/hosts.

eer en rae Pera od orem eee

**PDF s. 494:** Notes:

The ‘awk’ command refers to the input from the ‘cat’ command as a table.

Therefore, the 1st and 9th columns refer to IP addresses and status codes.

Using the -f flag in the ‘cut’ command will parse the IP address and remove the

status code from the output of the ‘awk’ command.

The ‘unig -c’ command will count the number of times each IP appears from the

results filtered by the previous commands and output as a table with two

columns (count and IP address).

5 Adda ‘while’ loop that reads each line from the /tmp/hosts file used in the

previous step (do not close the loop, it will continue to run in the next step).

The ‘line’ within the while loop will read each line of the file appended in the

previous step.

6 Create a variable in the loop that will use the piping and cut commands to count

and include only the number of attempts made by each IP address in the

/tmp/hosts file.

line

count i 1

The variable will take a line from the appended file (/tmp/hosts) defined as ‘line’

and cut out the first column of text (the number of times an IP was rejected).

**PDF s. 495:** 7 Create another variable in the loop that uses the piping and cut commands to

include all IPs in the /tmp/host file.

count bald i

ip nf D

The variable will cut out the second column of text (the list of rejected IPs).

8 Inthe previous loop, write an if-then statement to check if the number of

attempts is greater than or equal to three. Leave the if statement open for now.

9 Insert the date of the blocked IP and the IP in the file /var/log/badIP.

10 Print information about the blocked IP address.

**PDF s. 496:** 11 Insert the IP addresses with a /32 CDIR in the Iptables list, to drop the

connection. Then end with ‘fi’ and close the loop.

(date) gFil : . —

iptables -A INPUT /32 -d 0/0 -j DROP

/tmp/hosts

The ‘iptables’ command is the IPv4 netfilter firewall included in the Linux kernel.

This command is used to make a rule dropping packets coming from a defined

IP/CIDR.

-A is used to append a rule.

-s refers to the source address.

-d refers to the destination address.

-j specifies what to do with the packets.

When combined, this iptables command determines that future packets from the

specified IP will be dropped.

12 Make the script executable using the chmod command.

root@debian:~#

**PDF s. 497:** Lab Task 3: Run the Script and Check the Results

Run the script and check the results to verify that the IPs attacking the web server were

blocked. If no IPs were blocked, troubleshoot each part of the script to ensure it was

written properly.

1 Run the IPCheck.sh script from the terminal and check /var/log/badIP for the

results.

root@debian:~#| . /IPCheck. sh

The IP was succesfully added to /var/log/badIP

The following IP has been blocked 6 times by the webserver: 19.12.19.16

The IP was succesfully added to /var/log/badIP

The following IP has been blocked 4 times by the webserver: 95.83.17.23

root@debian:~#|cat /var/log/badIP

Fri 08 May 2020 03:41:57 PM EDT 19.12.19.16

Fri 08 May 2020 03:41:58 PM EDT 95.83.17.23

root@debian:~# []

2 Use iptables -L to check if the IPs were blocked.

root@debian:~# man iptables .

root@debian:~#/iptables -L

Chain INPUT (policy ACCEPT)

taroet prot opt_source destination

IDROP all -- 19.12.19.16 anywhere

IDROP all -- | 95-83-17-23.¢aransk.ru anywhere

</details>
