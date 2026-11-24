# Terminal Emulators & Graphical Applications

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 18–19; Linux Security.pdf, s. 39–42.

## Mapa wiedzy

- A terminal emulator is the graphical program that hosts a shell/command interpreter and can also provide remote terminal access.
- The course differentiates terminal applications from programs that require a GUI and shows GNOME-based graphical tools.
- Automation remains centered on the CLI even when a graphical desktop is installed.

## Komendy / pliki / składnia występujące w materiale

```text
SS Experience the Gnome desktop environment
apt install gedit
```

## Notatki z zajęć (PadRiseup)

- https://itbiznes.pl/oprogramowanie/nowy-polski-gnome/
- `apt install gedit`
- `grep-in-the-terminal/`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-01-L4 — Graphical Apps](../labs/lnx-01-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 18:** Although GUI actions are the equivalent of commands, the CLI is still more commonly

used by IT professionals. CLI allows the user to run a variety of actions with a single

device (keyboard) from any directory. For example, if the CLI command execution

location is in the root folder, you can use a single command to create a new folder in

the Home folder. If you need to create multiple directories, one script can create as

many directories as needed, whereas in the GUI, it would be a much more manual

process. In addition, a GUI consumes more system resources.

Remembering commands may be challenging at first, especially if the command is

complex and works with several flags.

Installing GNOME as a Desktop Experience

In addition to the clean Linux-based OS installation process described above and the

features that can be added as part of the kernel, GNOME (GNU Network Object Model

Environment) installs tools and features in a graphical interface and presents them ina

desktop environment.

GNOME is one of many desktop experience interfaces that are referred to as windows

managers, and can be installed and uninstalled at any time.

Lab Assignment: GNOME DE Installation

— Create a more interactive virtual environment that includes graphical

m= | interfaces and tools.

Follow the instructions in lab document LNX-01-L3: GNOME DE Installation.

Section 8: Terminal Emulator

In Linux, the terminal emulator allows the user to run OS commands directly on the

machine. It is a tool that has a graphical interface and emulates shell or terminal text.

The terminal emulator also allows remote command execution through SSH or Telnet

protocols. For example, a network administrator who wants to connect from a

Microsoft Windows OS can run a simple command in Windows or Linux to create a

connection based in the terminal emulator.

**Textbook s. 19:** Graphical Usage & Applications

Some applications cannot be replaced with a terminal emulator, such as those that run

their own database. For example, Firefox can be opened using the terminal, but it

cannot run without using the graphical interface, since it is based on graphics.

Some applications, such as Wireshark, can be used as both GUI and non-GUI.

Lab Assignment: Graphical Applications

— Experience the GNOME desktop environment and Debian tools.

m=:

Follow the instructions in lab document LNX-01-L4: Graphical Applications.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 39:** Introduction to Linux

Terminal Emulator

**Slides s. 40:** Terminal Emulator

john@debian: ~ x

File Edit View Search Terminal Help

The terminal runs the shell

command interpreter.

It is used to invoke

commands and execute

programs.

Connection to the terminal

can be from a remote

workstation, via the SSH

protocol.

**Slides s. 41:** (Grapt Emulator

¢ Some applications must have a graphical

interface.

¢ Graphical interfaces are more intuitive for

new users.

e Some programs interact with CLI.

| The CLI is easier to use for automation purposes. &-

Q\ = “

**Slides s. 42:** Terminal Emulator

SS Experience the Gnome desktop environment

Graphical Apps and Debian tools.

20-30 Min ;

——" ec | e Install guest additions.

nisin > “4 : e Look for graphical-based applications.

= y L ~t. e Learn about graphical app configurations.

. : Ld bd e at

| . ® tT ¢ VirtualBox e Lab document

' %; e Debian

4 :

‘ |

</details>
