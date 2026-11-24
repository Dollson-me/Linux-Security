# Advanced Grep & AWK

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 48–49; Linux Security.pdf, s. 94–97.

## Mapa wiedzy

- Advanced `grep` flags cover case-insensitive matching, line numbers, filenames, recursive search, counting and inverted matches.
- `awk` extracts fields/columns and can use custom separators; it is especially useful for structured text such as `/etc/passwd` and logs.
- Class notes also combine grep/awk with `cut`, `uniq`, `sed` and redirection to build small analysis pipelines.

## Komendy / pliki / składnia występujące w materiale

```text
Grep and AWK are tools used to find words, characters, lines, and text patterns in files.
AWK is a data extraction tool commonly used in Linux systems. It can extract specific
awk '{print $6 $8}' access_log
grep sed awk
grep -in Fire /var/log/dpkg.log --color
cat /etc/passwd | cut -f 1 -d ':' > users
cat sorted_local_users.txt | grep -v root
ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
cat ips | cut -d " " -f 1
```

## Notatki z zajęć (PadRiseup)

- `grep sed awk`
- `grep -in Fire /var/log/dpkg.log --color`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `cat sorted_local_users.txt | grep -v root`
- `ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`
- `cat ips | cut -d " " -f 1`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L1 — Advanced Piping](../labs/lnx-03-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 48:** Output Redirection & Operators

The pipe is one example of a two-part command in which the first part affects the

second part. Other redirection operators include > and >>.

Using > overwrites data in a file with the text that follows the character. Using >>

appends data to the end of the specified file. Neither redirection displays output on the

command line, but they do generate records in the history log.

Because Is displays the list of items in the current directory, adding > after Is followed

by a file name places the Is output in a file but does not show it in the terminal. If the

name of the file does not exist, it is created and contains the executed command: Is >

<file name>

john@debian: ~ x

File Edit View Search Terminal Help

i~$ Ls > file. txt

=

Section 2: Advanced Grep & AWK

Grep and AWK are tools used to find words, characters, lines, and text patterns in files.

Their primary use is for quickly finding specific words and patterns that match the

search in all specified files and folders.

Additional flags that can be used with grep are:

-i- Ignores case sensitivity

-v— Outputs the unmatched typed filter

-c— Counts the number of lines that were found with a match

-I - Displays the file name of input files

-n— Shows the number of the line the word was found in

-r — Represents recursive, and processes all files in the directory

An example of the grep command for a recursive search from the directory it is running

on is to find the word “success” in all files and subdirectories. For each result, it will

print every line containing the word.

**Textbook s. 49:** john@debian: ~ x

File Edit View Search Terminal Help

:~$ grep -r success |

Binary file Documents/Guest Addition/NT3x/VBoxControl.exe matches

Binary file Documents/Guest Addition/NT3x/VBoxService.exe matches

Binary file Documents/Guest Addition/cert/VBoxCertUtil.exe matche

AWK is a data extraction tool commonly used in Linux systems. It can extract specific

data from texts and output the results to the screen.

Following is an example of AWK that shows how to retrieve the third and fourth

columns of each line in a file.

$3 is the third word (third field of each line in the file).

$4 is the fourth word (fourth field of line in the file).

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat file

first second third forth fifth

first second third forth fifth

first second third forth fifth

first second third forth fifth

:~$ awk ‘{print $3,$4}' file

third forth

third forth

third forth

third forth

i$

By default AWK uses white space to separate between fields, but you can set a custom

separator using the -F flag. For example -F “:” will set the colon character as a

separator.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 94:** Users & Permissions

Advanced Grep & AWK

**Slides s. 95:** (Gr Advanced Grep & AWK

0

@ Grep is an application that filters data.

®@ It can use stdin as an input.

@ Advanced grep commands can search for more

complex patterns.

®@ Grep can ignore patterns such as space, upper,

and lower. ;

**Slides s. 96:** (Ac Advanced Grep & AWK

= | Flag Meaning

| -i Ignores case sensitivity

| -V Outputs non-matching lines

| -C Counts the number of lines found

| -| Displays the file names of input files

| -n Shows the line number of the word

| +r Recursive; processes all files in the directory é

9

**Slides s. 97:** (AV Advanced Grep & AWK

O

johnd@debian:/var/log/cups# awk '{print $6 $8}' access_log

e The location of the directory is ° $8 means print the words in

/var/log/cups the eighth field of each line.

e Print means display on screen. ° Access_log is the name of

* $6 means print the words in the the file for which the

sixth field of each line. command is executed.

| By default, AWK uses white space to separate fields. You can set a custom separator

using the -F flag. For example, -F “:” will set the colon character (:) as a separator.

10

</details>
