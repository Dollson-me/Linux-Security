# LNX-06-L3 — File Integrity Monitoring

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 373–384.

## Cel, misja i środowisko

- G Lab Objective Practice Bash variables and operators, while obtaining a better understanding of the Apache protocol and its folders. bs Lab Mission
- bs Lab Mission Write a script that will create and check the hashes for an Apache server. ea . © Lab Duration
- © Lab Duration 30-40 minutes tC) Requirements e Knowledge of Linux file system directories.
- tC) Requirements e Knowledge of Linux file system directories. e Knowledge of Apache directories. e Knowledge of Linux system commands.
- | Resources ¢ Environment & Tools o VirtualBox = Debian OS

## Komendy występujące w labie

```text
cd /var/www/html
touch filel.html file2.html file3.html
cd ~
nano WebsiteIntegrity.shf
chmod +x WebsiteIntegrity.sh
./WebsiteIntegrity.sh
cd /var/www/htmL
1s
cd /root
ff
```

## Powiązana teoria

- [File Integrity](../06-bash/file-integrity.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 373:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L3

File Integrity Monitoring

oo ina

Ooln

Ea

All Rights Reserved.

**PDF s. 374:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L3

File Integrity Monitoring

oo ina

Ooln

Ea

All Rights Reserved.

**PDF s. 375:** G Lab Objective

Practice Bash variables and operators, while obtaining a better understanding of the

Apache protocol and its folders.

bs Lab Mission

Write a script that will create and check the hashes for an Apache server.

ea .

© Lab Duration

30-40 minutes

tC) Requirements

e Knowledge of Linux file system directories.

e Knowledge of Apache directories.

e Knowledge of Linux system commands.

e Knowledge of Bash scripting concepts.

Lt

| Resources

¢ Environment & Tools

o VirtualBox

= Debian OS

o Apache

**PDF s. 376:** Lab Task: Write a Script to Check File Integrity

A scheduled task runs daily to check file integrity in the www/htnl folder. Use Linux

system commands to write a script that performs the integrity check for the scheduled

task.

The script should compare the hash of all current files in the folder with the previous

hash that was examined.

1 In Debian, switch to the root user with the command su — and make sure the

/var/www/html directory has files in it (if not, create some with the touch

command for the purpose of this lab).

2. Change the working directory to the /root directory. Create a text file named

Websitelntegrity.sh using the nano command that will check whether the files in

the /var/www/html have changed.

Important: The first time that you will run the script it will show that there is a

change, since it does not have anything to compare with.

3 Start the script with the shebang interpreter and create a variable that points to

all files in /var/www/html.

The “*” at the end is a wildcard that points to all files in the html directory.

4 Create a variable that points to /var/log/wwwHash that will contain new hashes.

5 Create a variable that points to /tmp/wwwHash that will contain the older

hashes.

6 Write an if-then statement that uses the previously-created variables to copy

previously-checked hashes from /var/log/wwwHash to /tmp/wwwHash and

store them for later comparison.

Note: -f in the condition will check if there is a file in the path that is tored in the

SvarPath variable.

**PDF s. 377:** 7 Write a line that will create the file /var/log/wwwHash the first time the script is

run.

8 Write an if-then statement in a for loop that will make new hashes for files in the

/var/www/HTML/* directory, and append them to /var/log/wwwHash.

Note: The for loop will iterate through the items in the path stored in the Sfiles

variable. For each item, it will check if it’s not a directory, and if it is not, it will

create an md5 hash for that file and save the hash in the file /var/log/wwwHash.

9 Write an if-then statement that compares the hashes located in the

/var/log/wwwhash and /tmp/wwwuHash files. If a change was made, the if-then

will report whether or not the file changed, and which files were changed.

10 Save the changes and exit the script file by pressing Ctrl + x.

Type Y and press Enter to save the script.

11 Grant the script file execution permissions with the command chmod +x

Websitelntegrity.sh, and run the file for the first time with the command

./Websitelntegrity.sh.

It should generate a baseline for further checking.

12 Modify any file at /var/www/html/ and run the script again.

13 Does the script recognize which file changed?

The terminal should appear as follows after you run the script again:

Note: The hash values of your files will most likely be different than those shown

in the screenshot above.

**PDF s. 378:** Linux Security

Lab Assignment Bash Scripting

& Solution ineaeaes

File Integrity Monitoring

oo ina

Ooln

El

All Rights Reserved.

**PDF s. 379:** Linux Security

Lab Assignment Bash Scripting

& Solution ineaeaes

File Integrity Monitoring

oo ina

Ooln

El

All Rights Reserved.

**PDF s. 380:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Practice Bash variables and operators, while obtaining a better understanding of the

Apache protocol and its folders.

2 Lab Mission

Write a script that will create and check the hashes for an Apache server.

of :

@ Lab Duration

30-40 minutes

fe Requirements

e Knowledge of Linux file system directories.

e Knowledge of Apache directories.

e Knowledge of Linux system commands.

e Knowledge of Bash scripting concepts.

oo

| Resources

¢ Environment & Tools

o VirtualBox

= Debian OS

o Apache

**PDF s. 381:** Lab Task: Write a Script to Check File Integrity

A scheduled task runs daily to check file integrity in the www/htnl folder. Use Linux

system commands to write a script that performs the integrity check for the scheduled

task.

The script should compare the hash of all current files in the folder with the previous

hash that was examined.

1 In Debian, switch to the root user with the command su — and make sure the

/var/www/html directory has files in it (if not, create some with the touch

command for the purpose of this lab).

root@debian:~# cd /var/www/html

root@debian: /var/www/html# touch filel.html file2.html file3.html

root@debian:/var/www/html#

2 Change the working directory to the /root directory. Create a text file named

Websitelntegrity.sh using the nano command that will check whether the files in

the /var/www/html have changed.

root@debian: /var/www/html# cd ~

root@debian:~# nano WebsiteIntegrity.shf

Important: The first time that you will run the script it will show that there is a

change, since it does not have anything to compare with.

3 Start the script with the shebang interpreter and create a variable that points to

all files in /var/www/html.

The “*” at the end is a wildcard that points to all files in the html directory.

4 Create a variable that points to /var/log/wwwHash that will contain new hashes.

varPath-"/var/log/wwwHash

**PDF s. 382:** 5 Create a variable that points to /tmp/wwwHash that will contain the older

hashes.

6 Write an if-then statement that uses the previously-created variables to copy

previously-checked hashes from /var/log/wwwHash to /tmp/wwwHash and

store them for later comparison.

Note: -f in the condition will check if there is a file in the path that is tored in the

SvarPath variable.

7 Write a line that will create the file /var/log/wwwHash the first time the script is

run.

8 Write an if-then statement in a for loop that will make new hashes for files in the

/var/www/HTML/* directory, and append them to /var/log/wwwHash.

f

Note: The for loop will iterate through the items in the path stored in the Sfiles

variable. For each item, it will check if it’s not a directory, and if it is not, it will

create an md5 hash for that file and save the hash in the file /var/log/wwwHash.

**PDF s. 383:** 9 Write an if-then statement that compares the hashes located in the

/var/log/wwwiash and /tmp/wwwuHash files. If a change was made, the if-then

will report whether or not the file changed, and which files were changed.

diff “$varPath" “$tmpPath" | we -< 2

“The files in the WWW/html folder have not changed."

“The Files in the WhW/html folder have changed."

“The following are the files that have changed:"

diff $varPath $tmpPath

10 Save the changes and exit the script file by pressing Ctrl + x.

ME cet Help MJ write out MJ where Is Cut Text @@) Justify %@ cur Pos

We Exit | fii Read File gi) Replace Uncut Text™j To Spell jj Go To Line

Type Y and press Enter to save the script.

Save modified buffer? (Answering "No" will DISCARD changes. )

Hi Yes |

lM No cancel

11 Grant the script file execution permissions with the command chmod +x

Websitelntegrity.sh, and run the file for the first time with the command

./Websitelntegrity.sh.

It should generate a baseline for further checking.

root@debian:-# chmod +x WebsiteIntegrity.sh

root@debian:~# ./WebsiteIntegrity.sh

The Files in the www/html folder have changed

The following are the files that have changed:

1,4d0

< d4ld8cd98foob204e9800998ecfa427e /var/wmww/html/filel. html

root@debian:~# chmod +x WebsiteIntegrity.sh

root@debian:~# ./WebsiteIntegrity.sh

The Files in the www/html folder have changed

The following are the files that have changed:

1,4d0

< d4ld8cd98foob204e9800998ecfa427e /var/www/html/filel. html

**PDF s. 384:** 12 Modify any file at /var/www/html/ and run the script again.

root@debian:~# cd /var/www/htmL

root@debian: /var/www/html# 1s

filel.html file2.html file3.html index.html

| root@debian: /var/www/html# nano file2.html

| root@debian: /var/www/html#

13 Does the script recognize which file changed?

The terminal should appear as follows after you run the script again:

root@debian:/var/www/html# cd /root

root@debian:~# ./WebsiteIntegrity.sh

The files in the WWW/html folder have changed.

The following are the files that have changed:

2c2

< ab99c7daeo19e2e448dbc3f309C9f943 /var/www/html/file2.html

> d41d8cd98foob204e9800998ecf8427e /var/www/html/file2.html

root@debian:~# ff

Note: The hash values of your files will most likely be different than those shown

in the screenshot above.

</details>
