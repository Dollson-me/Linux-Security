# Bash Scripting for Administration

[← 05 · Services & Hardening](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 94–96; Linux Security.pdf, s. 201–206.

## Mapa wiedzy

- Bash scripts group commands into repeatable workflows and support variables, arguments, comments and text-processing tools.
- Scripts need appropriate execute permissions and normally begin with a hashbang selecting the interpreter.
- The section bridges service administration to the dedicated Bash chapter and uses tools such as `sed` for scripted text replacement.

## Komendy / pliki / składnia występujące w materiale

```text
Bash scripts allow multiple commands in a single file to be executed, which makes
Bash features make it ideal for administrative task automation. Script files have the
Bash
service apache2 start
echo “you can start using Apache”
sed
Bash Scripting
echo “You can start using Apache”
chmod +x VBoxLinuxAdditions.run
grep sed awk
ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'
chmod +x ping_sweep.sh
chmod +x backup.sh
```

## Notatki z zajęć (PadRiseup)

- `chmod +x VBoxLinuxAdditions.run`
- `grep sed awk`
- `/home/[nazwa uzytkownika]/.bashrc`
- `ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'`
- `chmod +x ping_sweep.sh`
- `chmod +x backup.sh`
- `1 #!/bin/bash`
- `#!/bin/bash`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-06-L1 — Basic Scripting](../labs/lnx-06-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 94:** Section 6: Bash Scripting

This aim of this section is to prepare for the next module, which covers Bash scripting in

more detail.

Why Use Bash?

Bash scripts allow multiple commands in a single file to be executed, which makes

command execution easier. It also allows system commands in the script, which are

otherwise typically executed from the terminal.

Bash features make it ideal for administrative task automation. Script files have the

extension .sh, and start with the line #!/bin/bash, which tells the system where to pass

the data for execution.

Bash

The characters ./ are placed before the name of a script, for it to be executed.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ ./script.sh |

When a script file is created, it is not assigned execution permissions, which must be

added manually to allow its execution.

When scripts are written in text editors, the editors recognize the code and provide

different colors for their various sections.

**Textbook s. 95:** Variables and Arguments

The following signs are used in Bash scripts to define different types of information and

perform actions.

Character Function

S Invokes a variable

| # Starts a comment

| -_ Defines textual content

Sl Completes the last command

Automation

Automation is a crucial aspect of Linux system management and operation. Bash

scripting is ideal for that purpose and can significantly reduce the time and effort of

administrator and user tasks.

When an automated task is performed, it is recommended to have the script print

messages about the execution for informational and possibly debugging purposes.

#!/bin/bash

service apache2 start

echo “you can start using Apache”

sed

The sed command is typically used for word replacement. It runs a search on the

specified item, deletes the desired word, and replaces it with another specified word.

After its execution, it displays an output of the result.

The command includes flags that can be used to enhance the search and replace

operation.

**Textbook s. 96:** As an example, the following command replaces the word “words” with the word

“replaces”: sed ‘s/words/replaces/’ filename

johnd@debian: ~ x

File Edit View Search Terminal Help

:~$ cat filename

This file contains an example for 'sed' command

Try to locate the differences

It is actually a text streamer

:+$ sed ‘s/words/replaces/* filename

This file contains an example for ‘sed‘ command

Try to locate the differences

It is actually a text streamer

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 201:** Services and Hardening

Bash Scripting

**Slides s. 202:** (Ww Bash Scripting

Why Use Bash?

@ Having multiple commands in a file simplifies

their execution.

®@ Bash scripting includes system commands.

@ The file extension is .sh.

\ @ It can be used to automate tasks.

The first line is the path, so every script starts with:

#!/bin/bash

Cc % = -

**Slides s. 203:** (Ba Bash Scripting

®@ Executed with the combination of ./<filename>

\ ® New.sh files must have execute (x) permission.

® Create and edit scripts in text editors.

® Color-coded commands

Cc % =

**Slides s. 204:** Bash Scripting

Variables and Arguments

| Character —_ Functionality

| S Variable

| # Comment ™ e

| a Text

| S! Complete the last command

32

**Slides s. 205:** #!/bin/bash

service apache2 start

echo “You can start using Apache”

When writing Bash scripts, you can print the output for debugging purposes.

**Slides s. 206:** Bash Scripting

ctivities &] Terminal ~ Thu 09:08 % 4,0

johnae@detian: 5

The sed command typically is used to replace [ppremeepereecereree

The command can be useful when scripting. _

Flags are added after specified words.

After the command executes, it is displayed

on the terminal window as an output.

|

</details>
