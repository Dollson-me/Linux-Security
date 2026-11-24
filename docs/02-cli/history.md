# Command History

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 45–45; Linux Security.pdf, s. 83–86.

## Mapa wiedzy

- `history` records commands entered in the shell, including commands that returned errors.
- History can accelerate repeat work but can also expose sensitive commands or credentials if used carelessly.
- The material demonstrates recalling previous commands with history expansion.

## Komendy / pliki / składnia występujące w materiale

```text
history
History Command
history : saved in a log in the OS.
```

## Powiązane laboratoria

- [LNX-02-L4 — Search](../labs/lnx-02-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 45:** Section 9: History Command

Linux maintains a list of commands used in the terminal. The list can be useful when

you want to repeat a command and view the order in which commands were executed.

It does not display content that was not executed, such as if you began typing grep

Class but did not send the command.

All commands that were sent, even if they produced an error message with no output,

will be retained in the history.

To repeat a command, the history command is used together with an exclamation mark

(!) and the number of the command in the list output. This will complete the command

when part of the syntax is inserted after the sign. For example, !apt will complete the

syntax based on the last apt command. Important: Working this way may lead to

system issues, if not performed with caution.

john@debian: ~ x

File Edit View Search Terminal Help

'=$ Thi |

history

1 whoami

2 clear

3 pwd

4 clear

5 uname

6 clear

7 uname -r

8 clear

Lab Assignment: Search & Locate

—_— Use search commands to locate files and find specific text within them.

=_:

Follow the instructions in lab document LNX-02-L4.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 83:** CLI Fundamentals

History Command

**Slides s. 84:** History Command

john@debian: ~ x

‘ * es

File Edt View Search Terminal Help History’ is a command that

La :~$ history lists commands that were

Cc mk

2 ca = run.

3 cde,

a ‘Bash_history’ is a hidd

5 clear ash_history’ is a hidden

6 Is -la file that stores commands

? clear

Sts run by users.

9 rm Debian Wiki lorem lorem copy test

10 clear Bash hi

11 ls -la ash_history saves

12 clear commands run during each

13 history ‘i

7 :-$ I session, and runs

continuously until the shell

is terminated.

**Slides s. 85:** History Command

john@debian: ~ x

File Edit View Search Terminal Help Commands that are run are

=$ Uhi P ;

history : saved in a log in the OS.

Ica y-

: a 7 An exclamation mark (!) can

acd be used to complete

5 clear

5 te aie commands that were run,

; irae instead of showing the exact

s

9 rm Debian Wiki lorem lorem copy test commands.

10 clear

11 ls -la : ,

ipelear The History command will

13 history display the exact commands

14 clear

15 history that were run.

i$

**Slides s. 86:** History Command

Se Use search commands to locate files and

Search data within files.

15-20Min ys

—. - > @ Run the History command to look for

~ = : : commands that were executed.

eS 4 1 . @ Work with the Find command to

= F ; search for data in files.

|GZa.

we e 3 wd

} os _, in

| - a ft f ® VirtualBox ®@ Lab document

| ~ & Ne)

F : f ®@ Debian

: ta e~

</details>
