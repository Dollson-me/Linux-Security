# LNX-06-L2 — Compression and Backup

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 360–372.

## Cel, misja i środowisko

- G Lab Objective Become familiar with how the tar command is used to back up and archive files through scripting. » Lab Mission
- » Lab Mission Build a backup plan for a directory and write an automated script that compresses the folder and backs it up. Cs .
- @ Lab Duration 20-30 minutes tC) Requirements e Knowledge of the Linux file system
- tC) Requirements e Knowledge of the Linux file system e Knowledge of Linux system commands e Knowldege of Bash scripting
- | Resources e¢ Environment & Tools © Text editor o Virtualbox

## Komendy występujące w labie

```text
fj
chmod +x backupScript.sh |
./backupScript.sh
nano backupScript.sh
I
cd /tmp
1s
```

## Powiązana teoria

- [Archives Backups](../06-bash/archives-backups.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 360:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L2

soAae Compression and Backup

olf

El

**PDF s. 361:** Linux Security

Lab Assignment Bash Scripting

LNX-06-L2

soAae Compression and Backup

olf

El

**PDF s. 362:** G Lab Objective

Become familiar with how the tar command is used to back up and archive files through

scripting.

» Lab Mission

Build a backup plan for a directory and write an automated script that compresses the

folder and backs it up.

Cs .

@ Lab Duration

20-30 minutes

tC) Requirements

e Knowledge of the Linux file system

e Knowledge of Linux system commands

e Knowldege of Bash scripting

Lt

| Resources

e¢ Environment & Tools

© Text editor

o Virtualbox

= Debian

o Tar

**PDF s. 363:** Lab Task: Write a Bash Script That Backs up Data

You hacked into an organization and reached the CEO’s computer. You created a

scheduled task that runs a script to generate a daily copy of all files and subfolders in

the user’s home directory. Write a script that compresses the /home/ directory and

saves the compressed file to the /tmp folder. Since we need to make sure the code

works properly during development, print the status of each step of the process on the

screen.

Note: Since the script will run daily, you must use unique file names to avoid conflicts

(you can use a date as part of the file name).

1 Log into the root user with the su— command and use the nano command to

create a file named backupScript.sh.

2 Begin the script by calling the shebang interpreter and defining the /home/

directory as a variable called backup_files, which is the directory that will be

backed up. #!/bin/bash must remain at the top of the script so that the

interpreter knows to run the script in Bash.

3 Create a variable named dest pointing to the /tmp directory as the backup file

destination path.

4 Define a variable named now that will contain the start and end times of the

script when it is run as an executeable.

Note:

¢ The date command will take the current time when the now variable is called.

e %H will format the output to show the hour when the variable is called.

e %Mwill format the output to show the minutes when the variable is called.

e %S will format the output to show the seconds when the variable is called.

5 Create two variables and assign the current date and the hostname to them.

Combine the two variables to a single unique file name and save it to a third

variable in combined form.

**PDF s. 364:** Note: Combine the hostname and currentDate variables to an archive_file

variable.

6 Use echo commands and the previously defined variables to show which

directory is being backed up and where the archive will be saved. Write a

separate echo command to show that the backup process began.

Note: Because the script is still being written, it is important to check that the

script is running properly. To do so, save the script, use chmod +x

backupScript.sh, and run it with ./backupScript.sh.

7 Add another echo command that will print the start time.

8 Use the tar command and previously defined variables to write a script that will

compress and back up the /home/ directory to the /tmp directory. Use the

archive file name.

Note: For more information on all the switches available to the tar command,

please visit this link: https://www.computerhope.com/unix/utar.htm.

9 Print a message saying the script is done and its end time.

10 Save the script file and make it executeable. To do so, use the chmod +x

command.

11. Run the script using ./backupScript.sh.

Check the /tmp directory for a .tgz file.

Extra: To decompress the archive, you can use tar -zxvf filename.tgz.

**PDF s. 365:** Linux Security

Lab Assignment Bash Scripting

& Solution ineaeie

soAae Compression and Backup

olf

ES

**PDF s. 366:** Linux Security

Lab Assignment Bash Scripting

& Solution ineaeie

soAae Compression and Backup

olf

ES

**PDF s. 367:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Become familiar with how the tar command is used to back up and archive files through

scripting.

» Lab Mission

Build a backup plan for a directory and write an automated script that compresses the

folder and backs it up.

x) .

e) Lab Duration

20-30 minutes

fe Requirements

e Knowledge of the Linux file system

e Knowledge of Linux system commands

e Knowldege of Bash scripting

**PDF s. 368:** oo

| Resources

e¢ Environment & Tools

© Text editor

o Virtualbox

= Debian

o Tar

**PDF s. 369:** Lab Task: Write a Bash Script That Backs up Data

You hacked into an organization and reached the CEO’s computer. You created a

scheduled task that runs a script to generate a daily copy of all files and subfolders in

the user’s home directory. Write a script that compresses the /home/ directory and

saves the compressed file to the /tmp folder. Since we need to make sure the code

works properly during development, print the status of each step of the process on the

screen.

Note: Since the script will run daily, you must use unique file names to avoid conflicts

(you can use a date as part of the file name).

1 Log into the root user with the su— command and use the nano command to

create a file named backupScript.sh.

:~$ su -

root@debian:~# fj

2 Begin the script by calling the shebang interpreter and defining the /home/

directory as a variable called backup_files, which is the directory that will be

backed up. #!/bin/bash must remain at the top of the script so that the

interpreter knows to run the script in Bash.

backup _files="/home/"fj

3 Create a variable named dest pointing to the /tmp directory as the backup file

destination path.

**PDF s. 370:** 4 Define a variable named now that will contain the start and end times of the

script when it is run as an executeable.

Note:

¢ The date command will take the current time when the now variable is called.

e %Hwill format the output to show the hour when the variable is called.

e %Mwill format the output to show the minutes when the variable is called.

e %Swill format the output to show the seconds when the variable is called.

5 Create two variables and assign the current date and the hostname to them.

Combine the two variables to a single unique file name and save it to a third

variable in combined form.

Note: Combine the hostname and currentDate variables to an archive_file

variable.

currentDate date +"%y

hostname hostname

archive file S .

6 Use echo commands and the previously defined variables to show which

directory is being backed up and where the archive will be saved. Write a

separate echo command to show that the backup process began.

Note: Because the script is still being written, it is important to check that the

script is running properly. To do so, save the script, use chmod +x

backupScript.sh, and run it with ./backupScript.sh.

**PDF s. 371:** 7 Add another echo command that will print the start time.

8 Use the tar command and previously defined variables to write a script that will

compress and back up the /home/ directory to the /tmp directory. Use the

archive file name.

Note: For more information on all the switches available to the tar command,

please visit this link: https://www.computerhope.com/unix/utar.htm.

9 Print a message saying the script is done and its end time.

Script end .

10 Save the script file and make it executeable. To do so, use the chmod +x

command.

root@debian:~-# chmod +x backupScript.sh |

root@debian:~-#

11. Run the script using ./backupScript.sh.

root@debian:-# ./backupScript.sh

Backing up /home/ to /tmp/debian-20-04-23.tgz

Process is starting.

Script start time: 12:32:03

tar: Removing Leading ~/' from member names

Backup finished

Script end time: 12:32:03

root@debian:~# nano backupScript.sh

root@debian:~# I

Check the /tmp directory for a .tgz file.

**PDF s. 372:** root@debian:~# cd /tmp

root@debian: /tmp# 1s

debian-20-04-23.tgz

Extra: To decompress the archive, you can use tar -zxvf filename.tgz.

Entire script:

backup files="/home/"

dest="/tmp"

now date +"%H:%M:%S"

currentDate date +"%y-%sm-%d"

hostname hostname -

archive file="$hostname-$currentDate.tgz”

“Backing up $backup_files to $dest/$archive_file"

"Process is starting."

Script start “$now"

-czPvf $dest/$archive file $backup_ files

“backup finished"

now date +"%H:%M:%S"

Script end “$now"

</details>
