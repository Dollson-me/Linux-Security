# Data Streams, Redirection & Text Editors

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 38–42; Linux Security.pdf, s. 72–78.

## Mapa wiedzy

- Linux defines standard input (`stdin`), standard output (`stdout`) and standard error (`stderr`).
- `>` overwrites redirected output and `>>` appends; redirection is a building block for logging, pipelines and scripts.
- `cat` displays/concatenates data. Nano, Vim and Gedit are introduced as editors with different interfaces and workflows.
- Vim uses modes; Nano emphasizes shortcut keys; Gedit is a graphical editor.

## Komendy / pliki / składnia występujące w materiale

```text
cat is short for “concatenate”. It combines two files and sends the output to
Nano
Nano is a text editor for UNIX-like operating environments that use a command-line
Vim
Vim is a built-in text editor based on the terminal. It is invoked by typing vi, uses colors,
Vim opens in command mode, whereby what you type is interpreted as commands
Gedit
Gedit is a text editor for UNIX-like operating environments. It is a third-party application
Gedit is invoked using the gedit command. Terminating the command without exiting
cat
echo “content” > filename - overwrites the content
echo “content” >> filename - appends the content
Vim is useful for programming
vim tutorials
apt install gedit
find / -name *.sh 2>/dev/null
cat /etc/passwd | cut -f 1 -d ':' > users
cat local_users.txt | sort > sorted_local_users.txt
vim /etc/quality/pwquality.conf
sudo vim ports.conf
echo "testowy plik" > plikzubuntu.txt
md5sum $file > $temppath
sudo vim /etc/pam.d/common-password
echo "piotr" > /etc/ssh/sshd.allow
vim /etc./pam.d./sshd
vim /etc/pam.d/sshd
echo "It works as $me" > /tmp/crontabout.txt
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
sudo vim /etc/apache2/conf-available/security.conf
sudo vim security2.conf
sudo vim /etc/apache2/sites-available/default-ssl.conf
sudo vim /etc/apache2/sites-available/000-default.conf
```

## Notatki z zajęć (PadRiseup)

- `vim tutorials`
- https://www.openvim.com/
- https://www.freecodecamp.org/news/vim-beginners-guide/
- https://danielmiessler.com/p/vim/
- `apt install gedit`
- `find / -name *.sh 2>/dev/null`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `cat local_users.txt | sort > sorted_local_users.txt`
- `vim /etc/quality/pwquality.conf`
- `sudo vim ports.conf`
- `echo "testowy plik" > plikzubuntu.txt`
- `md5sum $file > $temppath`
- `sudo vim /etc/pam.d/common-password`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `vim /etc./pam.d./sshd`
- `vim /etc/pam.d/sshd`
- `echo "It works as $me" > /tmp/crontabout.txt`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`
- `sudo vim /etc/apache2/conf-available/security.conf`
- `sudo vim security2.conf`
- `sudo vim /etc/apache2/sites-available/default-ssl.conf`
- `sudo vim /etc/apache2/sites-available/000-default.conf`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L3 — Editing Files](../labs/lnx-02-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 38:** Section 6: Data Streams

There are three standard streams in Linux:

Stdin - The standard input stream that reads data from the user.

Stdout - The standard output stream that, by default, sends data to the output

terminal.

Stderr - The standard error stream that sends error messages to stdout.

Writing & Reading Files

Different commands are used in Linux to view files. The cat [file name] command is

used to output a file’s content to the terminal.

john@debian: ~ x

File Edit View Search Terminal Help

1~$ ls

file.txt

2=o) Cat) fi lenox

This is a test document.

:~$ ff

® | Good to Know

cat is short for “concatenate”. It combines two files and sends the output to

stdout. A benefit of the command is displaying a single file via stdout.

Appending and writing text to a file can be done using the echo command, which

displays typed content on the same terminal interface.

If you add > or >> and a file name, it will add the content in the file without displaying it

on the terminal interface.

The > sign after echo will overwrite all existing content and insert the new content.

Using >> will append the existing content to the end of the file.

**Textbook s. 39:** john@debian: ~ x

File Edit View Search Terminal Help

79 (Gav) fi Vestxt

This is a test document.

:~$ echo "Hello World!" >> file.txt

'=$ cat file. txt

This is a test document.

Hello World!

:~$ echo "Overwrite" > file.txt

:~$ cat file.txt

Overwrite

a |

Nano

Nano is a text editor for UNIX-like operating environments that use a command-line

interface. It includes shortcut keys to exit a file, cut a file’s content, look for keywords in

a file, and more. The keys appear at the bottom of the command line when using Nano.

The command used to invoke Nano is nano [file name].

john@debian: ~ x

File Edit View Search Terminal Help

:~$ nano file.txt J |

**Textbook s. 40:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 filenwxt

Overwrite

mo Get Help @@ Write Out@l] Where Is @ Cut Text

@A Exit asi} Read Fileg Replace @J Uncut Text

Vim

Vim is a built-in text editor based on the terminal. It is invoked by typing vi, uses colors,

and displays line and character locations.

Messages displayed at the bottom of the terminal window can be set to appear in

yellow or red.

Writing code in Vim is made easier by its completion feature, which completes what

you type and helps minimize mistakes in the code.

Vim opens in command mode, whereby what you type is interpreted as commands

rather than regular strings. For example, if you type the letter u, the editor will interpret

it as the command to undo a previous action. Ctrl+r will be interpreted as the command

to redo the previous action.

When in a different mode, command mode can be activated by pressing Esc.

Pressing i will activate the insert mode, which will allow regular string input in a file,

rather than characters activating commands.

To run a command while a Vim file is open, use the colon (:). The colon can be used, for

example, to save the file, search for something in the code, or display information on

other commands. When you type a colon (:), a line will appear at the bottom of the

terminal, where you can enter a command.

**Textbook s. 41:** File Edit View Search Terminal Help

Look at the bottom Line

Gedit

Gedit is a text editor for UNIX-like operating environments. It is a third-party application

that works with an interface similar to Notepad.

Gedit is invoked using the gedit command. Terminating the command without exiting

the Gedit interface will close the Gedit window without saving the changes.

It supports syntax highlighting, printing, plugins, spell check, and more.

Text appears in monochrome (black), unless a different color scheme is chosen.

Shortcut keys can be used to perform actions, such as Ctrl+a which selects all text in a

file, or Ctrl+s which saves the file.

**Textbook s. 42:** Activities [) Text Editor ~ Tue 04:52 2 Or

Open > fA Untitled Document 1 Save = «x

PlainText ~ TabWidth:8 ~ Ln1,Col1 v INS

Lab Assignment: Editing Files

— Practice using text editors and output redirection to read from and write to

=== files.

Follow the instructions in lab document LNX-02-L3.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 72:** CLI Fundamentals

Data Streams

**Slides s. 73:** (Sti Data Streams

stdin is when the input (command)

is sent for execution. toa

stdout is the result returned from

the command.

stderr is an error that was sent due to

an issue with the execution.

aa

**Slides s. 74:** (wi Data Streams

cat

Prints all contents to the terminal.

M/ | echo

Prints the sent content as an output to the user.

echo “content” > filename - overwrites the content

echo “content” >> filename - appends the content

Lp

**Slides s. 75:** Data Streams

‘Activities [) Terminal + Tue 01:55 4, Or

johnd@debian: / x

File Edit View Search Terminal Help

Look at the bottom line

A terminal-based text editor.

Work with Vim can be in Insert

mode or Command mode.

Vim is useful for programming

| since it features colored lines

based on the type of code.

:wq

**Slides s. 76:** Data Streams

Activities &] Terminal + Tue 01:54 2a Or

johnd@debian: / x

File Edit View Search Terminal Help

This is a test a 5

Document only.. A text editor operated via

eee ea! the terminal.

Performing actions via the

terminal requires Ctrl key

combinations.

p Nano includes many special

i options.

a We Get Help @@ Write Out gl) Where Is MM Cut Text (@) Justify @e Cur Pos

is Exit fi Read File gi} Replace @@ Uncut Textggj To Spell jg Go To Line

**Slides s. 77:** (Ge Data Streams

Gedit

Open ¥ ic] *Untitled Document 1 Save = x

Write your data here

Similar to Notepad in

Windows OS.

Can be opened from the

CLI or an application

center.

Terminating the Gedit

process from CLI will close

it without saving data.

PlainText ~ Tab Width: 8 + Ln, Col21 . INS. J

34

**Slides s. 78:** Data Streams

—» — = "en, Practice working with text editors and their output

Editi ng Files | to read and write files.

— @ Copy random text to a file.

i , | ®@ Review the content in read-only mode.

’ er y . > ®@ Insert information without entering

a ® + ® VirtualBox ®@ Lab document

| @ Debian

| , ® Terminal

h od =~

</details>
