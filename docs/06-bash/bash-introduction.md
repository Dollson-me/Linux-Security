# Bash Scripting Introduction

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 97–99; Linux Security.pdf, s. 211–215.

## Mapa wiedzy

- A shell script is a file containing commands interpreted by a shell. The hashbang selects the interpreter path.
- Anything runnable as a shell command can be incorporated into a script. Scripts can be executed in a new process or sourced into the current shell.
- Variables use `name=value`; aliases can simplify commands and persistent aliases can be stored in shell startup files such as `~/.bashrc`.

## Komendy / pliki / składnia występujące w materiale

```text
Bash Scripting
case $- in
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT
```

## Notatki z zajęć (PadRiseup)

- `/home/[nazwa uzytkownika]/.bashrc`
- `1 #!/bin/bash`
- `#!/bin/bash`
- `sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-06-L1 — Basic Scripting](../labs/lnx-06-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 97:** | Chapter 6: Bash Scripting

Section 1: Bash Scripting Introduction

Bash, also known as the Bourne-again shell, is a type of interpreter that processes shell

commands. An interpreter is a program that executes instructions written in a high-

level language.

Running a high-level language program can be done via an interpreter or compiler. The

difference between them is that the interpreter translates the code into an

intermediate form and then runs it, while compilers translate the code into machine

language before running it. Although compiled programs run faster, they first need to

go through the compilation process, which is time-consuming.

Interpreters run high-level programs immediately. A shell interpreter links commands

written in CLI to OS services and binaries, and runs them.

Bash Scripting

Anything that can be run as a command can be included in a script. For example, you

can write a script to run simple commands such as tar and crontab to schedule a

backup.

A shell script is a complete language, with variables, functions, and conditional

executions. When you execute a script, a terminal window opens to run the commands.

Since the commands are run in plain text, they are typically logged and can be viewed

using the history command.

Similar to processes, scripts can run and perform tasks in the background.

Shebang

#!/bin/bash

A script is indicated by the shebang at the start of the document. In a UNIX-like

Operating system, a shebang is interpreted as an executable file. It consists of a hashtag

(#) and an exclamation mark (!) followed by a path for the interpreter, and no spaces.

To execute a script file, simply run ./ and the name of the script with no spaces, or bash

<script path and name>.

**Textbook s. 98:** Alias

When working with a shell interpreter, aliases can help write scripts faster and more

efficiently. An alias is a combination of commands that are piped together.

The commands can be sequenced in .bashrc files, which are located in the user’s home

directory. The file is hidden (as indicated by the dot before the file name) and can be

viewed using Is -Ia (the -a flag shows hidden files) or opened using a text editor (for

example, vim ~/.bashrc). The file can also be viewed using the GUI file explorer, and

Ctrl + H allows you to see hidden files in a folder.

johnd@debian: ~ ry

File Edit View Search Terminal Help

# for examples

i# If not running interactively, don't do anything

case $- in

*) return:

l# don’t put duplicate Lines or Lines starting with space in the history

i See bash(1) for more options

lurstcontRoL=ignoreboth

l# append to the history file, don't overwrite it

shopt -s histappend

lé for setting history Length see HISTSIZE and HISTEILESIZE in bash(1)

Inrstsize=

WESTFILESIZE=

\# check the window size after each command and, if necessary

1# update the values of LINES and COLUMNS

shopt -s checkwinsize

Hatch all tiles and zero or more directories and subdirectories

#[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

lif [ -z "${debian chroot:-}" && [ -r fetc/debian chroot ]; then

debian_chroot=$(cat /etc/debian_chroot)

1,54 Top

If an alias does not exist, the shell interpreter will go to the PATH and look for

executable files that correspond to the given command. PATH is an environment

variable that points the shell to directories where the executable files (such as binaries

and scripts) reside.

Variables

**Textbook s. 99:** A variable is a character string to which a value can be assigned. Since a variable is a

pointer to actual data, it can represent anything from a character to a device. Variables

are indicated by the dollar sign ($).

To assign a variable, simply write the reference, followed by an equals sign (=), and the

value of the variable with a number, or a word in quotes. For example, num=3 or

str=”Hello World”.

To assign a command output to a variable, you can use back ticks ("): myIP=‘ip a | grep -

A 1 enp0s3°. Using that example, you can obtain the IP address by running echo $myIP

after the grep command.

' A

x. ¢ | Tip

a © * ) When setting variables in Bash, don’t place spaces between the variable and

= the value.

johnd@debian: ~ x

File Edit View Search Terminal Help

:~$ myIP="ip a | grep -A 1 enp@s3

:~$ echo $myIP

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER UP> mtu 1500 qdisc pfifo fast state UP

group default qlen 1000 link/ether 08:00:27:0e:8d:a6 brd ff:ff:ff:ff:ff:ff inet

10.71.0.121/24 brd 10.71.0.255 scope global dynamic noprefixroute enp@s3 valid 1

ft 588079sec preferred 1Lft 588079sec

inh

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 211:** Bash Scripting

Bash Scripting

Introduction

**Slides s. 212:** (Ba Bash Scripting Introduction

e Anything that can be run as a command can be inserted

in a shell script.

e The terminal opens a new session or sources the script

into the current session for the script to run.

© Commands are usually written in plain text.

Q\ =

**Slides s. 213:** (He Bash Scripting Introduction

Hashbang

:

e Also known as shabang, shebang, pound-bang, or hash-pling

e Announces the interpreter path

e Must be added to the first line of the script

e No spaces are used in shebang.

e Script execution is done with ./<script name>, .<script

name>, path/<script name>, or bash <script name>.

e Ascript must have executable permissions to run.

| An interpreter is an application or program that can &- me

translate and execute code written in a high-level

programming language.

**Slides s. 214:** (ali Bash Scripting Introduction

p : e The shell interpreter checks for an alias when a

command is used.

e To set upa persistent alias, edit the ~/.bashrc file.

The Linux system has a hierarchy of commands:

e If there is no alias, it will look for a function.

e If there is no function, it will look for a built-in

command.

e If there is no built-in command, it will search

for an executable file in the PATH.

<p aia

**Slides s. 215:** (Va Bash Scripting Introduction

OC) $ myName=“John Doe”

= $ echo “Hello “ $myName

= ° Variables are created with value

md) 6 assignments (variable=value). all

A ° No spaces are used in the command. tS ~

e Variables do not have data types. -

° To call a variable in the script, use é _ 4

the prefix S<variable>. ~~

</details>
