# LNX-02-L2 — Moving Files in the File System

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 88–98.

## Cel, misja i środowisko

- G Lab Objective In this lab, you will learn about the basic commands for creating, copying and moving files and folders. La Lab Mission
- La Lab Mission Practice using basic Linux CLI commands. of . © Lab Duration
- © Lab Duration 15-20 minutes fe Requirements e Working knowledge of the CLI interface
- fe Requirements e Working knowledge of the CLI interface Lt [ea] Resources
- [ea] Resources Environment and tools: © Debian environment from LNX-01-L3 ¢ Terminal

## Komendy występujące w labie

```text
cd dir3
|cp file*.txt /etc
cp file*.txt /tmp
cd ..
cp -r dir* /tmp/
|1s /tmp/dir*
cp -x dir* /etc
mv file*.txt /var/
ls /var/file*
/mv dir* /var/
1s
1s /var/dir*
```

## Powiązana teoria

- [Files Directories](../02-cli/files-directories.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 88:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L2 Moving Files in

oonRe the File System

olf

E-

**PDF s. 89:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L2 Moving Files in

oonRe the File System

olf

E-

**PDF s. 90:** G Lab Objective

In this lab, you will learn about the basic commands for creating, copying and moving

files and folders.

La Lab Mission

Practice using basic Linux CLI commands.

of .

© Lab Duration

15-20 minutes

fe Requirements

e Working knowledge of the CLI interface

Lt

[ea] Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

¢ Web browser

**PDF s. 91:** Lab Task

This task focuses on basic commands associated with managing folders and files.

1 Create anew directory.

2 Navigate to the newly created directory, and create a four directories, “dir 1” to

“dira”

3 Navigate to “dir3” folder, and create two text files using the appropriate

command.

4 Copy files and folders to the various directories in the file system.

5 Move files and folders to the various directories in the file system.

**PDF s. 92:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-LS2 Moving Files in

oonRe the File System

olf

E-

**PDF s. 93:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-LS2 Moving Files in

oonRe the File System

olf

E-

**PDF s. 94:** G Lab Objective

In this lab, you will learn about the basic commands for creating, copying and moving

files and folders.

La Lab Mission

Practice using basic Linux CLI commands.

of .

© Lab Duration

15-20 minutes

fe Requirements

e Working knowledge of the CLI interface

Lt

[ea] Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

¢ Web browser

**PDF s. 95:** Lab Task

This task focuses on basic commands associated with managing folders and files.

1 Create anew directory.

To create a new directory (folder), use <mkdir>.

: $ mkdir folderl

: $ 1s | grep folder1

folder1

at 2

2 Navigate to the newly created directory, and create a four directories, “dir 1” to

“dira”

To navigate to the new folder, use <cd [folder1 path]>.

To create multiple folders, use <mkdir dir{1..4}>.

: $ cd folderi/

: $ mkdir dir{1..4}

: $ Is

: sf

**PDF s. 96:** 3 Navigate to “dir3” folder, and create two text files using the appropriate

command.

To navigate to the new folder use <cd [folder1 path]>.

To create two text files, use <touch file1.txt file2.txt>.

: $ cd dir3

- $ touch filel.txt file2.txt

: $ 1s

file1.txt file2.txt

sil

4 Copy files and folders to the various directories in the file system.

To copy files to various directories use <cp file name [folder path]>:

root@debian: /home/john/folder1l# cd dir3

root@debian: /home/john/folder1/dir3#|cp file*.txt /etc

iroot@debian: /home/john/folder1/dir3#|1s /etc/file*

fetc/filel.txt /etc/file2.txt

root@debian: /home/john/folderi/dir3# cp file*.txt /tmp

lroot@debian: /home/john/folder1/dir3# |ls /tmp/file*

/tmp/filel.txt /tmp/file2.txt

To copy folders to various directories use <cp -r folder name [folder path]>:

iroot@debian: /home/john/folder1/dir3# cd ..

iroot@debian: /home/john/folder1l# cp -r dir* /tmp/

root@debian: /home/john/folderi#|1s /tmp/dir*

/tmp/dirti:

étmp/dir2:

/tmp/dir3:

filel.txt file2.txt

/tmp/dir4:

iroot@debian: /home/ john/folder1#

**PDF s. 97:** root@debian: /home/john/folderl# cp -x dir* /etc

lroot@debian: /home/ john/folderl# 1s /etc/dir*

fetec/dirl:

fetc/dir2:

fetc/dir3:

filel.txt file2.txt

fete/dir4:

iroot@debian: /home/ john/folderi#

5 Move files and folders to the various directories in the file system.

To move files to various directories use <mv file name [folder path]>:

iroot@debian: /home/ john/folder1# cd dir3

iroot@debian: /home/ john/folder1/dir3# 1s

Filel.txt file2.txt

root@debian: /home/john/folder1/dir3# mv file*.txt /var/

iroot@debian: /home/ john/folder1/dir3# 1s

iroot@debian: /home/john/folderi/dir3# ls /var/file*

/var/filei.txt /var/file2.txt

iroot@debian: /home/ john/folder1/dir3#

To move folders to various directories use <mv folder name [folder path]>:

lroot@debian: /home/john/Tolderi# 1s

idizl dir2 dizr3 dir4

root@debian: /home/john/folderi#/mv dir* /var/

root@debian: /home/john/folderi# 1s

root@debian: /home/john/folderl# 1s /var/dir*

/var/dirl:

/var/dir2:

/var/dir3:

/var/dir4:

root@debian: /home/ john/folder1#

</details>
