# Working with Files & Directories

[← 02 · CLI Fundamentals](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 33–37; Linux Security.pdf, s. 65–71.

## Mapa wiedzy

- Core file operations are `touch`, `mkdir`, `rm`, `rmdir`, `cp` and `mv`.
- `rm -r` recursively deletes directory trees and `rm -f` forces deletion; the textbook explicitly warns against destructive recursive deletion in production.
- `mv` is also used to rename files. Linux filenames are case-sensitive, so `file` and `File` can coexist.

## Komendy / pliki / składnia występujące w materiale

```text
1s
cd test _folder/
ls
rm *
rm -rf *
rmdir test _folder/
Jj
1s Desktop/
mv file.txt Desktop/
ls Desktop/
Jf
mv file.txt ./renamed_file.txt
fj
touch <file name>
rm does not remove directories by default, and the -r flag is required.
SS 4 ! ~~ various directories in the file system.
cp /etc/shadow
sudo rm kali.list
scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT
mv modsecurity.conf-recommended modsecurity.conf
sudo mv modsecurity-crs/ modsecurity-crs_bak
sudo mv owasp-modsecurity-crs/ modsecurity-crs
sudo mv crs-setup.conf.example crs-setup.conf
```

## Notatki z zajęć (PadRiseup)

- `cp /etc/shadow`
- `sudo rm kali.list`
- `scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop`
- `sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT`
- `mv modsecurity.conf-recommended modsecurity.conf`
- `sudo mv modsecurity-crs/ modsecurity-crs_bak`
- `sudo mv owasp-modsecurity-crs/ modsecurity-crs`
- `sudo mv crs-setup.conf.example crs-setup.conf`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-02-L2 — Moving Files in the File System](../labs/lnx-02-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 33:** Section 5: Working with Files & Folders

Files in Linux can include more than text, images, and compiled programs. They can also

contain partitions, hardware device drivers, and directories.

Linux files are case-sensitive. Two files can share the same name, but their names may

have different letter cases. For example, File.txt and file.txt are two different files.

There are three basic file types:

Ordinary Files: Files that contain data, text, or program instructions.

Directories: Store both special and ordinary files. For users familiar with Windows,

UNIX-based directories are similar to folders.

Special Files: Special files may provide access to hardware, such as hard drives, CD-

ROM drives, modems, and Ethernet adapters. Other special files are similar to aliases

or shortcuts that open or activate the files they represent.

Creating Files & Directories

Files and directories can be created using terminal commands, and the process is easier

and more flexible than via the GUI.

To create a file, use the command touch [option] [file name].

J john@debian: ~ x 1

File Edit View Search Terminal Help

: :~$ touch test.txt

:~$ ls

J TEST. EXE

i-$

**Textbook s. 34:** To create a directory, use the command mkdir [option] [directory name].

john@debian: ~ x

File Edit View Search Terminal Help

:~$ mkdir test folder

i=$ US

LESTE EXT

:<§$ |

Deleting Files & Dirctories

Several commands can be used to delete files and directories. Since directories may

include additional content, a recursive flag is required in the command to delete it (-r).

To delete files, use the command rm [option] [file name].

john@debian: ~ x

File Edit View Search Terminal Help

:~$ rm test.txt

1~$ ls

i~$

Additional flags can be added to the rm command. For example, to force file deletion,

you can use the -f flag, and the syntax would be rm -rf *, which would recursively delete

all files in the the current directory, including directories within that directory.

Note that the -r causes the deletion to be recursive, and the asterisk (*), which is also

known as a wildcard, represents “everything”.

The following example shows how the r and f flags are used in the command to delete

directories and their content.

**Textbook s. 35:** john@debian: ~/test_folder x

File Edit View Search Terminal Help

john@debian:~$ 1s

Desktop Music Templates

Documents Pictures test_folder

Downloads Public Videos

john@debian:~$ cd test _folder/

john@debian:~/test_folder$ ls

files games movies

john@debian:~/test_folder$ rm *

rm: cannot remove 'files': Is a directory

rm: cannot remove 'games': Is a directory

rm: cannot remove 'movies': Is a directory

john@debian:~/test_folder$ rm -rf *

john@debian:~/test_folder$ ls

john@debian:~/test_ folders Jj

The following example shows how rmdir is used to delete a directory.

I john@debian: ~ =

File Edit View Search Terminal Help

john@debian:~$ 1s

Desktop Music Templates

Documents Pictures test_folder

Downloads Public Videos

john@debian:~$ rmdir test _folder/

john@debian:~$ ls

Desktop Downloads Pictures Templates

Documents Music Public Videos

john@debian:~$ Jj

@ More Information

) 1d Ubuntu and many other Linux distributions protect the root directory.

Some, however, do not, and you should NEVER runrm -rf /* ona

production system!

**Textbook s. 36:** Copying Files & Folders

The command to copy files from one location to another is cp <filename>

<destination>, whereby filename and destination can be absolute or relative paths. The

destination parameter can include a file name, and also enables the user to define a

new name for the file that was copied.

john@debian: ~ x

File Edit View Search Terminal Help

==$uls

Tite. txt

:~$ cp file.txt Desktop/

:~$ Ls Desktop/

file. txt

2

Moving Files

The command to move a file from one location to another is mv <filename>

<destination>. The original location is referenced first, and then the new location. Note

that using the CLI to move a file executes the command immediately with no message

asking to confirm the operation (as would appear in Windows and other GUI

interfaces). The command will also overwrite any files in the destination with the same

specified name.

**Textbook s. 37:** john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ 1s

Desktop file.txt Public

Documents Music Templates

Downloads Pictures Videos

john@debian:~$ 1s Desktop/

john@debian:~$ mv file.txt Desktop/

john@debian:~$ 1s

Desktop Downloads Pictures Templates

Documents Music Public Videos

john@debian:~$ ls Desktop/

Tile txt

john@debian:~$ Jf

The mv command can also be used to rename files in the system. To change a file’s

name and leave it in the same directory, the destination should be the current working

directory (./).

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ 1s

Desktop Downloads Music Public Videos

Documents file.txt Pictures Templates

john@debian:~$ mv file.txt ./renamed_file.txt

john@debian:~$ 1s

Desktop Music renamed file. txt

Documents Pictures Templates

john@debian:~$ fj

Lab Assignment: Moving Files in the File System

eS Create files and folders, and move and copy them within the file system.

=m

Follow the instructions in lab document LNX-02-L2.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 65:** CLI Fundamentals

Working With

Files & Folders

**Slides s. 66:** (Fil Working With Files & Folders

| Ordinary files contain data, text, or

program instructions. toa

Directories store both special

and ordinary files.

Some special files provide access

to hardware.

aa

**Slides s. 67:** john@debian:~/¢$ touch <file name>

john@debian:~/¢ mkdir <directory name>

The touch command is used to create files and mkdir is used to create

directories and folders.

**Slides s. 68:** john@debian:~/¢ rm <file name>

john@debian:~/¢ rmdir <directory name>

Files, folders, and directories can be deleted using various commands.

rm does not remove directories by default, and the -r flag is required.

**Slides s. 69:** john@debian:~/¢ cp <file name> <destination>

When copying a file or folder, first the original location is specified, and

then the destination. During this operation, the file can also be renamed.

**Slides s. 70:** john@debian:~/¢ mv <file name> <destination>

When moving a file or folder, first the original location is specified, and

then the destination. During this operation, the file can also be renamed.

**Slides s. 71:** Working With Files & Folders

es Create files and folders and move and copy them

Moving Files in the File System | to different directories in the file system.

15-20Min — .

— ® Create files and folders.

ee , } ® Move and copy files and folders to

SS 4 ! ~~ various directories in the file system.

> Se * 8 -

= ® ® al ®@ VirtualBox @ Lab document

| ® Debian

| , ® Terminal

h % ye. ~<

</details>
