# Script Input, Output, Variables & Arguments

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 100–101; Linux Security.pdf, s. 216–220.

## Mapa wiedzy

- Scripts communicate through standard input/output/error and can consume positional arguments or interactive user input.
- Variables are expanded with `$`; quoting rules matter when values contain spaces or special characters.
- `read`, `echo` and redirection are used to build interactive and file-producing scripts.

## Komendy / pliki / składnia występujące w materiale

```text
Read & Echo
echo What is your name?
read name
echo Hello $name nice to meet you.
echo $Time
Bash Scripting
echo <text to show on screen>
echo “What is your favorite dish?”
read dish
echo “I like $dish also!”
echo "testowy plik" > plikzubuntu.txt
echo "Tworze hash z pliku index.html"
echo "Porownuje ze soba oryginalny hash z nowostworzonym"
echo "Hashe sie nie zgadzaja!"
echo "Hashe sie zgadzaja!"
echo "piotr" > /etc/ssh/sshd.allow
echo "It works as $me" > /tmp/crontabout.txt
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
```

## Notatki z zajęć (PadRiseup)

- `echo "testowy plik" > plikzubuntu.txt`
- `18 echo "Rozpoczynamy proces backupu"`
- `23 echo "Zakonczono tworzenie backupu"`
- `echo "Tworze hash z pliku index.html"`
- `echo "Porownuje ze soba oryginalny hash z nowostworzonym"`
- `status="$(cmp --silent $hashpath $temppath; echo $?)"`
- `echo "Hashe sie nie zgadzaja!"`
- `echo "Hashe sie zgadzaja!"`
- `echo "piotr" > /etc/ssh/sshd.allow`
- `echo "It works as $me" > /tmp/crontabout.txt`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`

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

**Textbook s. 100:** Section 2: Script Input & Output

Read & Echo

When learning a new language, a good way to start is to learn how to print and read

data. The read command waits for input from the user and assigns it to a variable. The

command can be used in a script to collect information from the user and use it as a

variable.

For example:

#!/bin/bash

echo What is your name?

read name

echo Hello $name nice to meet you.

The example will produce the following output:

johnd@debian: ~

File Edit View Search Terminal Help

r~$ . /new

Nhat is your name?

ohn

ello John nice to meet you.

By using the -ep flag with the read command, the first echo can be replaced by read.

The flag creates a message for the user instead of the echo requirement.

**Textbook s. 101:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 script

-ep "What is your name?" name

"Hello $name, nice to meet you"

mo Get Help @@ Write Out gi] Where Is gi Cut Text

Wd Exit Mi Read File gy Replace gj Uncut Text

Command Separators

Variable=$ (command) runs the command in the parentheses and saves the output in

the variable (like the back tick sign mentioned earlier). A good test would be to assign

the command date to a variable and run it a few times in succession. You will get the

same result even when time has passed.

johnd@debian: ~

File Edit View Search Terminal Help

johnd@debian: ~$ Time=$(date)

johnd@debian:~$ echo $Time

Wed 11 Dec 2019 08:58:20 AM EST

johnd@debian:~$ echo $Time

Wed 11 Dec 2019 08:58:20 AM EST

johnd@debian:~$ echo $Time

Wed 11 Dec 2019 08:58:20 AM EST

johnd@debian:~$ echo $Time

Wed 11 Dec 2019 08:58:20 AM EST

johnd@debian:~$ fj

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 216:** Bash Scripting

Script Input

& Output

**Slides s. 217:** (re Script Input & Output

O

| Gets user input and assigns it to a variable @

echo <text to show on screen>

| Prints the text after the word echo

10

**Slides s. 218:** $ echo “What is your favorite dish?”

$ read dish

$ echo “I like $dish also!”

The read command

reads a single line from

user input.

It adds a new line

character at the end of

the line.

Using the -ep option, read creates a message for the user

without requiring the first echo.

**Slides s. 219:** #!/bin/bash

WHO_AM_I=%(whoami

$(command) saves the LIST="1ls -a

variable as the command echo $WHO_AM I; echo $LIST

output.

Use a backtick (*) when

combining commands.

Commands can be

separated using

semicolons (,).

The output of the script will be the current username and a

list of all items in the directory.

**Slides s. 220:** $ Is || echo “Failed to list directory”

$ 1s && echo “Directory Successfully listed”

# find / | grep “file.sh”

&& will execute the

second command if the

first succeeds.

|| will execute the

second command if the

first fails.

| will send the stdout of

the first command to the

second command.

Other command separators can be used as well.

</details>
