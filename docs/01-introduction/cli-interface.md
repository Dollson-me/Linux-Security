# CLI Interface, Prompts & Command Syntax

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 17–17; Linux Security.pdf, s. 33–38.

## Mapa wiedzy

- The CLI accepts textual commands in the general form `command [options] [arguments]`.
- The prompt indicates privilege: the material uses `$` for a regular user and `#` for root.
- CLI is emphasized for administration and automation because it is fast, flexible, scriptable and consistent across many Linux distributions.
- The GNOME desktop is presented as an optional graphical layer that does not replace the underlying CLI.

## Komendy / pliki / składnia występujące w materiale

```text
SS Create a more interactive virtual environment that
cat sorted_local_users.txt | grep -v root
chown root:adm /var/log/boot.log
chown root:root /var/log/boot.log
```

## Notatki z zajęć (PadRiseup)

- `oh my zsh https://ohmyz.sh/`
- `root`
- `$ zwykły user`
- `grep-in-the-terminal/`
- `cat sorted_local_users.txt | grep -v root`
- `chown root:adm /var/log/boot.log`
- `chown root:root /var/log/boot.log`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-01-L3 — GNOME DE Installation](../labs/lnx-01-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 17:** Section 7: Command Line Interface

The terminal allows the user to enter commands for the operating system. The

command interface depends on the distribution.

In the terminal prompt, the dollar sign ($) typically means "logged in as regular user.”

The hash sign (#) means "logged in as root user."

Commands have the following syntax:

Command [options] [arguments]

A command can be a representation of existing data in the system, but can also

configure the system itself, create new files, and run programs. Options are properties

of commands that expand the command’s capabilities. They are typically represented

by hyphens and one or more letters.

File Edit View Search Terminal Help

:~$ ping -c 3 192.168.1.1

command

option

arguments

CLI Vs. GUI

While Microsoft Windows OS is developed for regular end users and includes an easy-

to-use and well-designed interface, Linux is designed more for technical purposes, such

as servers, devices, hacking tools, and forensics. The Linux OS is mainly based on the

command-line interface (CLI), but most Linux operating systems are designed and

installed with a graphical user interface (GUI) as well.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 33:** Introduction to Linux

CLI Interface

**Slides s. 34:** root:~# command

Many commands are the

same across all distributions.

Regular users are denoted by

the dollar sign ($). Root users

are denoted by the hash sign

(#).

The syntax is:

[command] [option] [argument]

**Slides s. 35:** (CL CLI Interface

O

a CLI GUI

Only a keyboard is required | | Requires additional components, |

such as a mouse

Difficult to work with | | Easy to work with |

Faster performance | PV | Slower performance |

Flexible | | Less flexible |

The same for most distributions Depends an whieh deshiep

applications are installed

35

**Slides s. 36:** CLI Interface

es cI

Bk ©

4 —

#5 AisleR... Calcul... Calen... Cheese Chess Clocks

@ @oe@n = A

x Conta... Docu... Docu... Evolut... Files Firefo...

my Ei 6° -<_ -.»

S 7 Pee tt “ i

Five o... Four-i... Hitori lagno jEdit Klotski

s5] Q 7 ~a

a. EF ya: je ha

av Libre... Libre... Libre... Libre... ibre... Lights .

Working with Gnome is similar to working with Windows Manager.

**Slides s. 37:** CLI Interface

Gnome Applications

.

Gnome has several built-in apps:

e Firefox

e File explorer

e Terminal

Additional tools and features can be installed

via their package names.

(\ «a

**Slides s. 38:** CLI Interface

SS Create a more interactive virtual environment that

Gnome DE Installation includes graphical interfaces and tools.

20-30 Min J

A r Os FF ° Install Gnome.

= ; e Experience DE.

~ a - | .

a PP ’ a

’ ° inet : ™= f

b . Ny ® yr

| “By +9 iY ® er ¢ VirtualBox e Lab document

{ BX ¢ Debian

f . a” :

.) |

</details>
