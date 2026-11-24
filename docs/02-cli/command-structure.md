# Command Structure, Help & Manuals

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 23–24; Linux Security.pdf, s. 50–54.

## Mapa wiedzy

- Linux commands combine the command name with optional flags/options and arguments.
- `man`, `--help` and `whatis` are used to understand syntax and purpose; `whereis` and `which` locate binaries and related files.
- The prompt itself carries context: user, machine, current path and privilege level.

## Komendy / pliki / składnia występujące w materiale

```text
Command [option] [argument]
represents the logged user, the machine’s name, the current
whoami - returns the current user name.
pwd — prints the current working directory.
uname - returns information regarding the operating system.
uname
```

## Notatki z zajęć (PadRiseup)

- `Bardzo dziękujemy za trzymanie się zasad :-)`
- `linux manual pages - help https://linux.die.net/man/`
- https://arstechnica.com/gadgets/2021/08/linux-bsd-command-line-101-using-awk-sed-and-

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

**Textbook s. 23:** Section 2: Command Structure

The terminal and commands run through it are used to configure system settings and

display existing data. System operations and management can be faster and more

efficient via the terminal, and process automation is simpler.

Commands run via the terminal have unique structures that include letters, numbers,

and characters.

Command Breakdown

Machine name Root user Data used by the command

root@debian:/etc# Command [option] [argument]

Username Current path Optional extension

Every command has a similar structure that includes several sections.

The first section represents data regarding the user and the system.

root@debian:/etc# represents the logged user, the machine’s name, the current

directory, and a sign representing the user, which in the example above is the pound

sign (#) that represents a root user (super user). The dollar sign ($) would represent a

simple user.

The second section is the command itself with an option part for flags, and arguments

passed to the command.

Ne Tip

= © * | The default prompt in many Linux distributions will show

= username @host:/current/path for a quick orientation of where you are in

the file system.

**Textbook s. 24:** System Commands

System commands provide data regarding the system and its content.

System command examples include:

whoami - returns the current user name.

pwd — prints the current working directory.

uname - returns information regarding the operating system.

) Lab Assignment: System Information

— Use the command line to obtain information about the Linux

—_! operating system.

Follow the instructions in lab document LNX-02-L1.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 50:** CLI Fundamentals

Command Structure

**Slides s. 51:** (Co Command Structure

® Commands are used to configure the system and

represent existing data.

® Commands include letters, numbers, and characters.

@ They automate processes in the operating system.

**Slides s. 52:** (Co Command Structure

O

root@debian:/etc# Command [option] [argument]

1. The user name is root 5. Command is the execution string

2. The machine’s name is Debian 6. Option represents extensions

3. ‘Jetc’ is the current path 7. Argument is the “what and where”

4. ‘#’ stands for root user of the command

| A dollar sign (S$) represents a regular user.

A hash sign (#) represents the root.

iS]

**Slides s. 53:** (sy Command Structure

@ whoami

dim Returns the current user name. toa

° pwd

Ba Finds the current system location.

uname

Gets information about the operating system.

aa

**Slides s. 54:** Command Structure

eS — Use the command line to obtain information

System Information about the Linux operating system.

10-15Min Us

— g ) @ Try out the commands.

' a : : a : ®@ Search the internet for more

-—-- 4 1 . command flags.

|GZa.

} vc

| : a= " @ VirtualBox @ Lab document

; : y ®@ Debian

‘ ta ae |

</details>
