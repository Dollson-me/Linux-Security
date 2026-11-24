# File Integrity Monitoring with Hashes

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 113–115; Linux Security.pdf, s. 247–250.

## Mapa wiedzy

- File-integrity monitoring stores a known-good hash and compares it with a newly generated hash to detect change.
- The course uses `md5sum` and `cmp` in a Bash script around Apache’s `index.html` as a concrete example.
- The security idea is change detection: a mismatch is an alert condition, not proof of the cause of modification.

## Komendy / pliki / składnia występujące w materiale

```text
echo -e "Backup finished! \nScript end time: ‘date“"
Md5sum
Md5sum uses an MD5 message digest. It generates an MD5 hash for almost any type of
Bash Scripting
echo "Tworze hash z pliku index.html"
md5sum $file > $temppath
```

## Notatki z zajęć (PadRiseup)

- `file=/var/www/html/index.html`
- `Stworz hash tymczasowy pliku index.html`
- `echo "Tworze hash z pliku index.html"`
- `md5sum $file > $temppath`
- `status="$(cmp --silent $hashpath $temppath; echo $?)"`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-06-L3 — File Integrity Monitoring](../labs/lnx-06-l3.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 113:** To backup files using the tar command, run:

“tar czfP Sdest/Sarchive_file Sbackup_files”

To print a message at the end of the process, run:

echo -e "Backup finished! \nScript end time: ‘date“"

Lab Assignment: LNX-06-L2 Compression & Backup

—_— Build a backup plan for a directory and write an automated script that

=| compresses the folder and backs it up.

Follow the instructions in lab document LNX-06-L2.

Section 6: File Integrity

In Linux, file integrity refers to whether or not files have been modified.

Hashing

Hashing is the process of generating a unique value from a string or text using a

mathematical algorithm. Hashes are used for almost any type of digital content,

including text, documents, images, and more. A hashing function will always output the

same results for the same given data.

Databases of known password hashes, called rainbow tables, contain data that

correspond with hashed values.

Hashing Tools

Linux has a built-in command called checksum generation that displays the outcome of

a cryptographic hash function. The most popular encryption utility in Linux is md5sum.

There are tools that make hashing easier and can create a hash for almost anything,

including files, words, and passwords.

The following are examples of hashing tools.

B2SUM

B2SUM is a BLAKE2 hashing tool. BLAKE2 is a cryptographic hash that works faster than

MDS5 and SHA1(3), and has the SHA-3 security standard.

**Textbook s. 114:** Cksum

Checksum is a well-known tool that uses the cksum command to count bytes in a file.

This allows you to compare two files, one that you created and the source file, to

ensure that data was not compromised.

Md5sum

Md5sum uses an MD5 message digest. It generates an MD5 hash for almost any type of

object, and is pre-installed in most Linux distributions.

Shalsum

Sha1sum works on SHA-1 message digests, which are no longer considered secure.

sum

The sum command performs a checksum and counts 512-byte blocks in a file.

Extra: /etc/shadow

Linux passwords are stored in /etc/shadow, which requires high level permissions to

access. The file consists of eight fields separated by colons.

**Textbook s. 115:** The password structure of the shadow file is as follows: SidSsaltShashed.

Sid is the algorithm used in Linux.

Other algorithms are indicated as follows:

$1$ is MDS

$2a$ is Blowfish

$2yS is Blowfish

S$5$ is SHA-256

S6$ is SHA-512

The last six fields in the file indicate password expiry and account lockout, as follows:

Last password change: Days since Jan 1, 1970, that a password was last changed.

Minimum: The minimum number of days required between password changes.

Maximum: The maximum number of days the password is valid.

Warn: Number of days before a password is set to expire, upon which the user will be

warned that the password needs to be changed.

Inactive: Number of days after a password expires, upon which the account will be

disabled.

Expire: Days since Jan 1, 1970, that the account was disabled.

Lab Assignment: LNX-06-L3 File Integrity Monitoring

—_— Practice Bash variables and operators while obtaining a better

mm =| understanding of the Apache protocol and its folders.

Follow the instructions in lab document LNX-06-L3.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 247:** Bash Scripting

File Integrity

**Slides s. 248:** (He File Integrity

e Hashing is the process of generating a value from a

11m)\10 string or text using a mathematical algorithm.

Oo 1 e Hashes are used for almost any type of digital content,

including text, documents, images, and more.

1c 0

e Linux has a built-in command for checksum generation.

110110 Li h built-i d for check. i

e Hashes are a cryptographically secure one-way

algorithm.

The most popular hashing utility in Linux is md5sum.

Note: MD5 is no longer a secure hashing algorithm.

Q\ = “

**Slides s. 249:** File Integrity

(Hashing Tools

Sg

c2l

cksum @) shalsum a

b2sum md5sum sum

**Slides s. 250:** File Integrity

a) . 5 . Practice using Bash variables and operators and obtain

F ile Integrity Monitoring | a better understanding of the Apache protocol and its

30-40 Min. I | folders.

a » = e¢ Compare www files.

~ 3 : e Print if there is no change.

. See oy e Print the changes if there are any.

LG 4 =

ra _ XQ { e ; d

| } 7 1 ) T e Apache e Lab document

=~ 8 & * Debian OS

) ps |

| id s > ae |

</details>
