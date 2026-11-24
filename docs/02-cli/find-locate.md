# Find & Locate

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 44–44; Linux Security.pdf, s. 81–82.

## Mapa wiedzy

- `find` performs flexible filesystem searches by path, name, type, size and other criteria; `locate` is faster but relies on a database.
- Examples in the material include `find / -name *.sh 2>/dev/null`, case-insensitive name matching and size filters.
- Redirecting errors to `/dev/null` is used to suppress permission-denied noise during broad searches.

## Komendy / pliki / składnia występujące w materiale

```text
Locate can find files in the Linux system, but relies on a database that must be updated
Locate has an advantage over find in its speed.
Find yields more accurate results and uses more complex syntax.
Find command example: find /root/Desktop -name *.sh
Find and Locate
find / -name *.sh 2>/dev/null
```

## Notatki z zajęć (PadRiseup)

- `find / -name *.sh 2>/dev/null`

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

**Textbook s. 44:** Section 8: Find & Locate

Finding files in Linux can be done with the locate or find command.

Locate can find files in the Linux system, but relies on a database that must be updated

to provide more accurate results.

Flags such as filetype and file name can be added to the find command to further filter

the results.

Locate has an advantage over find in its speed.

Find yields more accurate results and uses more complex syntax.

Find command example: find /root/Desktop -name *.sh

The command will find a file with the .sh extension in the /root/Desktop directory. The

asterisk (*) is used as a wildcard that represents “anything”.

Additional example: find —iname test

This command will find a file named test, with the results being non-case-sensitive.

Using —not in the command will return the opposite (only files that do not match the

exact case).

To find a file by size, you would use find / -size 50M

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 81:** CLI Fundamentals

Find and Locate

**Slides s. 82:** Gi Find and Locate

O @ ‘find’ is the most accurate search

command.

@ ‘find’ searches the entire directory

structure versus the file system

database

®@ ‘locate’ is older than ‘find’.

@ Update the database index using the

‘updatedb’ command.

®@ ‘locate’ finds results faster than ‘find’.

Each command has its advantages and

disadvantages. Try them on your own.

Lp

</details>
