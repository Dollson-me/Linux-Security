# Grep Basics

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 43–43; Linux Security.pdf, s. 79–80.

## Mapa wiedzy

- `grep` searches text and is commonly combined with other commands and redirection.
- The output is line-oriented: matching lines are returned, which makes grep useful for logs, configuration files and pipelines.
- Later material extends grep with recursive search, case-insensitive matching, line numbers, inverted matches and combinations with `awk`, `cut`, `head`, `tail`, `sort` and `sed`.

## Komendy / pliki / składnia występujące w materiale

```text
Grep outputs the result. If you want to find a word in a large file, you can specify the
Grep Basics
grep sed awk
grep -in Fire /var/log/dpkg.log --color
cat sorted_local_users.txt | grep -v root
ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
```

## Notatki z zajęć (PadRiseup)

- `grep sed awk`
- `grep -in Fire /var/log/dpkg.log --color`
- `cat sorted_local_users.txt | grep -v root`
- `ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L4 — Search](../labs/lnx-02-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 43:** Section 7: Grep Basics

The grep command in Linux is often used to filter text for a more specific search. It can

be combined with other functions and commands to improve search results.

Grep outputs the result. If you want to find a word in a large file, you can specify the

word in the command and the output will include the specified word. Although it does

not, by default, indicate the word’s location within the file’s content, you can combine

the basic command with additional commands to obtain that information.

The grep command shows the entire line in the result.

john@debian: ~ x

File Edit View Search Terminal Help

i~$ cat file.txt

Hello

World

Hello

Team

'~$ grep Hello file.txt

Hello

Hello

=o) |

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 79:** CLI Fundamentals

Grep Basics

**Slides s. 80:** Grep Basics

Activities [) Terminal + Tue 02:17 54, Or

johnd@debian: ~/Desktop x

File Edit View Search Terminal Help

:~/Desktop$ cat test

Hello

World

tee Grep is typically used to

Hello filter text.

Everyone

Hello

eg The output is a displayed

aaa :~/Desktop$ grep Hello test word (if it exists in the

oe specified document).

Hello

Hello ~ as «

Hello Grep can filter data in

:~/Desktop$ iq 4 i

cae multiple files.

</details>
