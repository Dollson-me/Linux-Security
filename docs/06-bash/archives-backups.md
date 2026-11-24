# Archives, tar, gzip & Backups

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 110–112; Linux Security.pdf, s. 239–246.

## Mapa wiedzy

- `tar` groups files into an archive; compression such as gzip reduces archive size. Combined `.tar.gz`/`.tgz` files are common for backup and transfer.
- The course builds a dated backup script that archives a selected directory into a destination path.
- Archive workflows include create/extract/list operations and should be paired with sensible permissions and storage locations.

## Komendy / pliki / składnia występujące w materiale

```text
Gzip compresses data to reduce its size. The original data can be recovered by
Tar Archive
Tar is typically used by Linux system administrators to back up data. It creates archive
tar -zcvf backupSettings.tar.gz /etc/
echo “Script start time: date"
tar czfP, $dest/$archive file $baskup files
echo -e "Backing up Sbackup_files to Sdest/Sarchive_file \nprocess
echo “Script start time: ‘date’”
Bash Scripting
gzip bzip2 XZ tar
tar -zPvf backupSettings.tar /etc/
tar czfPf $ t/$archive_f t up
echo -e
```

## Notatki z zajęć (PadRiseup)

- `5 backup_path="/home/piotr/Desktop"`
- `9 dest_path="/tmp"`
- `21 tar -czvf dest ath/filename $backup_path`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-06-L2 — Compression and Backup](../labs/lnx-06-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 110:** Double Parentheses

The starting point of a calculation can be indicated using double parentheses.

For example, in the following script, the calculation will begin with 2 + 3, whereby the

internal set of parentheses is used for the arithmetic operation.

a=2

b=3

sum= a+b

Section 5: Archives

An archive is a group of files that are bundled into a single file. Many archives are

compressed to reduce the file’s size.

Transmission of data and program distribution can also be performed using archives.

Software available online is typically distributed in archived files that include all

associated files and documentation.

Zip & Unzip

The zip command is located in the /bin Linux directory. Options can be added to the

command, such as the -d flag, which deletes the file during the unzipping process, and -

u, which updates the compression.

zip [options] <file_name.zip> <file.txt> [<file2> [<file3>]..]

Zipping Files

The zip command compresses specified files. A list of files that were added will be

displayed at the end of the command.

$ zip compress.zip file1.txt file2.txt file3.txt file4.txt

**Textbook s. 111:** Zip is not installed by default in the Debian distribution

Unzipping Files

For a zipped file to be unzipped, the file must be specified in the unzip command.

The -d flag can be used to export the zipped content to a different folder.

$ unzip compress.zip -d /tmp/

Compression

Gzip compresses data to reduce its size. The original data can be recovered by

unzipping the compressed file. This application is essential for web apps and websites

because the HTTP protocol uses Gzip for output, enabling smaller files to be

downloaded by visitors.

BZip2 is an open-source file compression program. It can only compress individual files

and is not a file archiver.

Tar Archive

Tar is typically used by Linux system administrators to back up data. It creates archive

files that can be moved easily from disk to disk. A tar archive is created using tar -zevf

<archive_name> <directory>.

The -zevf flags have the following meanings:

z—Compress using Gzip

c— Create a new archive

v— Show a list of processed files

f—Specify the archive name

For example:

$ tar -zcvf backupSettings.tar.gz /etc/

**Textbook s. 112:** Creating Backups

Creating file backups is crucial for any organization, regardless of its size.

Backups should be created every 24 hours to prevent data loss.

Important data should be backed up a minimum of once per week.

backup_files="/home/"

dest="/tmp”

currentDate= date +%Y-%m-%d

hostname=$% (hostname -s

archive file="$hostname-$currentDate.tgz”

"Backing up $backup files to $dest/$archive file \nprecess."

echo “Script start time: date"

tar czfP, $dest/$archive file $baskup files

"Backup finished! \nScript end time: ‘date "

The following script creates a backup of the home folder and puts it in the temp folder:

backup_files=”/home/”

“[home/” is the location you choose to back up.

dest is the destination of the backup files.

The archived file name consists of the following:

currentDate= ‘date +%Y-%m-%d~

hostname=S(hostnames)

archive_file="Shostname-ScurrentDate.tgz

A message to the user regarding the process can be sent using:

echo -e "Backing up Sbackup_files to Sdest/Sarchive_file \nprocess

To print the start date:

echo “Script start time: ‘date’”

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 239:** Bash Scripting

Archives

**Slides s. 240:** Archives

zip & unzip

Zip [options] <file_name.zip> <file.txt> [<file2> [<file3>]..]

e After installation, the zip binary is in the Debian /bin a

directory and can be called using the zip command.

e Options can be added to the command.

e The -d flag deletes the file during the unzip process.

e The -u flag updates the archive.

33

**Slides s. 241:** (Zippir

O

$ zip compress.zip file1.txt file2.txt file3.txt file4.txt

¢ Zip is not installed by default in the Debian distribution. =)

e The zip command will compress the specified files. T =

e Alist of files that were added will be displayed at the i \

end of the command. a

34

**Slides s. 242:** (ur Archives

O

$ unzip compress.zip -d /tmp/

e Unzipping compressed archives is done the same way as zipping

them.

e The zipped folder must be specified.

e¢ To export the zipped content to a different folder, use the -d flag.

| By default, files will be decompressed to the same directory unless

otherwise specified using the -d flag.

35

**Slides s. 243:** Archives

(Compression Tools

gzip bzip2 XZ tar

**Slides s. 244:** (Ta Archives

O |

mS $ tar -cvf backupSettings.tar /etc/

$ tar -zPvf backupSettings.tar /etc/

e Tar is typically used by Linux system administrators to back up data.

e |t creates archive files that can be moved easily from disk to disk.

e Adding az will create a Gzip compressed tar archive.

e -czPvf means the following:

c: Create a new archive

z: Compress using Gzip TAR _}

P: Preserve path names

v: Show a list of processed files

f: Specify the archive name

37

**Slides s. 245:** #!/bin/bash

# The path of the folder to back up

backup_files

# Backup destination path

dest

# Create archive file name

currentDate= date +%Y-%m-%d

hostname=% (hostname -s

The result of the example Reni CS Leils

script on the right is . .

. # Let the user know the process is starting

creating a compressed echo -e

archive of the /home/ # Print the start date

directory in the /tmp/ echo

directory. # Break line

# Back up the files using the tar command

tar czfPf $ t/$archive_f t up

# Print the end status message

echo -e

**Slides s. 246:** Archives

Compression & Backup Build a backup plan for a directory and write an automated

_ 1 script that compresses the folder and backs it up.

20-30 Min.

. © » j ¢ Compress an important directory.

= a / e Back it up to a different directory.

" ra ’ Ps XQ ® e yr

i ~ pe! yr oa _ z —

| : . a t e Text editor e Lab document

' eet } % * Linux OS

| eS Sy e Tar

& <

4 TY = |

</details>
