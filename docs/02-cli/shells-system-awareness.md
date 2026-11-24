# Shell Types & System Awareness

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 20–22; Linux Security.pdf, s. 47–49.

## Mapa wiedzy

- The course introduces `sh`, Bash, Zsh and C shell as command interpreters with different convenience features and scripting capabilities.
- Commands such as `whoami`, `pwd` and `uname` are used to establish who is logged in, the current working directory and OS/kernel details.
- Executable lookup is influenced by the `$PATH` environment variable.

## Komendy / pliki / składnia występujące w materiale

```text
Sh
BASH
whoami outputs the user currently logged in to the CLI.
pwd (Present/Print Working Directory) indicates the current location. For example, if
uname -r displays information about the system and its version. The command can also
SH is a command line interpreter. aa
Bash is an improved version of SH. (
apt install Linux-headers-$(uname-r)
export PATH=/usr/sbin:$PATH
sudo whoami
md5sum $file > $temppath
```

## Notatki z zajęć (PadRiseup)

- `oh my zsh https://ohmyz.sh/`
- `apt install Linux-headers-$(uname-r)`
- `export PATH=/usr/sbin:$PATH`
- `sudo whoami`
- `5 backup_path="/home/piotr/Desktop"`
- `9 dest_path="/tmp"`
- `21 tar -czvf dest ath/filename $backup_path`
- `hashpath=/tmp/wwwhash`
- `temppath=/tmp/temphash`
- `md5sum $file > $temppath`
- `Sprawdz czy dwa hashe temppath oraz hashpath`
- `status="$(cmp --silent $hashpath $temppath; echo $?)"`
- `me=$(whoami)`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L1 — System Information](../labs/lnx-02-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 20:** | Chapter 2: CLI Fundamentals

Section 1: CLI & Terminal Emulators

As a core component of the operating system, the terminal allows users to run

commands on the system. The CLI accepts text commands, but each operating system

has its own variations of command syntax.

There are many types of terminals. Some operate without a GUI when the computer is

booted, while others, such as Gnome, work with an emulated GUI.

CLI terminals can run remotely via processes such as SSH and Telnet, and are known as

a Remote Terminals.

Many devices and operating systems support terminal emulators which can be

downloaded and executed as third-party applications on operating systems such as

Windows, Linux, Android, and OSX (Apple). Terminal emulator are basically applications

that enable connection to the system’s shell, and can run commands from within the

shell.

Shell Types

A shell is an application that executes commands in text form within an operating

system. Application commands run from shells are checked against the SPATH variable.

Some commands execute binary files often located in the /bin or /sbin directories.

However, each shell has its own slightly different built-in commands (such as cd) that

can be run regardless of the SPATH variable.

C Shell

Utilizing the C Shell is done by running the csh command from a terminal. C shell

commands provide programming features, such as keyboard shortcuts, automation by

scripting, displaying a history of commands, and more. The C Shell lends itself to ease of

extension and expansion using a C-syntax development language (similar to the C

Programming language). The C shell is common for developers who would like to

maintain consistency in syntax to the operating system itself.

**Textbook s. 21:** Sh

Also known as the Bourne shell, sh is a simple shell interface that works with the OS. In

some cases, sh is used as a scripting language and contains many features that are

designed for programming.

BASH

BASH, or the Bourne Again Shell, was designed as an improved version of the sh shell

and therefore has similar command syntax. BASH shell scripts are commonly run on

Linux distributions.

Z Shell (Zsh)

The Z shell is an extension of the sh shell and shares common features with it. The

features include automatic directory movement, recursive directory expansion (for

example, /et/ap will navigate to /etc/apt), spell check, correction, and more.

System Awareness

Commands like whoami, pwd, and uname -r can indicate details about the user,

directory position, and operating system.

whoami outputs the user currently logged in to the CLI.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ whoami

john

BAA

pwd (Present/Print Working Directory) indicates the current location. For example, if

the command execution was printed from /usr/bin, that will be the output of the

command.

**Textbook s. 22:** i john@debian: ~ x

File Edit View Search Terminal Help

:~$ pwd

/home/ john

in$

uname -r displays information about the system and its version. The command can also

be used with different flags to present additional information, such as the kernel

version.

I john@debian: ~ x 1

File Edit View Search Terminal Help

:~$ uname

Linux

:~$ uname -r

4.19.0-10-amd64

:~$ uname -a

Linux debian 4.19.0-10-amd64 #1 SMP Debian 4.19.132-1

(2020-07-24) x86 64 GNU/Linux

:~$ J

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 47:** CLI Fundamentals

CLI & Terminal Emulators

**Slides s. 48:** CLI & Terminal Emulators

Command Line Interface

.

® CLI accepts textual commands.

® Scripts are executed via the terminal.

@ Terminal is an application.

=

**Slides s. 49:** (Sh CLI & Terminal Emulators

SH is a command line interpreter. aa

Bash is an improved version of SH. (

7 4]

o Zsh has extensions, and simplifies SH usage.

. )) »

</details>
