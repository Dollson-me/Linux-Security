# Pipes, Redirection & Compound CLI Workflows

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 46–47; Linux Security.pdf, s. 91–93.

## Mapa wiedzy

- The pipe `|` sends the output of one command to the input of the next, enabling small tools to be combined into larger workflows.
- The course combines commands such as `ls`, `cat`, `grep`, `sort`, `head`, `tail` and `cut` to filter and transform text.
- Output redirection writes results to files, which is repeatedly used in user enumeration, log analysis and scripts.

## Komendy / pliki / składnia występujące w materiale

```text
cat <file name> | grep <word>
cat file.txt
cat file.txt | grep file
sort the contents by redirecting its output to the sort command:
cat <file name> | sort
Cat
cat file.txt | sort
fj
cat /etc/passwd | head -n3 | tail -n 1
cat /etc/passwd | cut -f 1 -d ':' > users
cat local_users.txt | sort > sorted_local_users.txt
cat sorted_local_users.txt | grep -v root
ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
cat ips | cut -d " " -f 1
```

## Notatki z zajęć (PadRiseup)

- `cat /etc/passwd | head -n3 | tail -n 1`
- `cat /etc/passwd | cut -f 1 -d ':' > users`
- `cat local_users.txt | sort > sorted_local_users.txt`
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

**Textbook s. 46:** ] Chapter 3: Users & Permissions

Section 1: Piping

The pipe character (|) redirects the output of one command through the input of

another command. Piping is a type of redirection from a stdout to a stdin. It is used

mainly in command form and can also be used in programs and processes.

The pipe character divides the command into two inter-dependent parts. Since

commands flow from left to right, the second part of a piped command must be

associated with the first part.

The grep command is used to search for strings within text. Concatenating the Is

command with grep using a pipe will filter the search to obtain a more accurate output:

Is -I | grep <file name>

In the example, the output of Is -I flows through grep, which displays all directories and

files that contain the tmp string.

I john@debian: ~ =|

File Edit View Search Terminal Help

i~$ ls -l / |grep tmp

drwxrwxrwt 13 root root 4096 Sep 24 09:33 tmp

:=$

Another example is to use the cat command to display a file's contents and search for

specific words or sentences within the contents using grep:

cat <file name> | grep <word>

In the example, the output of the file flows through grep, which displays the line

containing the specified word.

**Textbook s. 47:** john@debian: ~ x 7

File Edit View Search Terminal Help

john@debian:~$ cat file.txt

This is a test file.

It is used to test commands in the system.

john@debian:~$ cat file.txt | grep file

This is a test file.

john@debian: ~$

As another example, you can display the contents of a file using the cat command and

sort the contents by redirecting its output to the sort command:

cat <file name> | sort

In the example, the output is sorted in alphabetical order.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ cat file.txt

Hello

Dog

Cat

Oven

Bread

Human

Plant

Speaker

john@debian:~$ cat file.txt | sort

Bread

Cat

Dog

Hello

Human

Oven

Plant

Speaker

john@debian:~$ fj

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 91:** Users & Permissions

Piping

**Slides s. 92:** john:~# ls -1 | grep <file name>

john:~# cat <file name> | grep <word>

Piping is the redirection

of stdout to stdin. john:~# cat <file name> | sort

It is used to pass outputs

to another program or john:~# find <path> -name ‘<file name>' | we -1

utility.

john:~# ls -1 | awk ‘{print $1}?

The output of the first J | {P =)

command becomes the

input of the second

command.

**Slides s. 93:** Piping

(Output Redirection & Operators

.

@ Redirect passes output to a file or stream.

® > outputs and overwrites a file.

@ >> appends the output to a file.

| The direction cab (<) is also used as an input. &- me

</details>
