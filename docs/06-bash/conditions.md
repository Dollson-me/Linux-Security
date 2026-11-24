# Conditions & Control Flow

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 102–107; Linux Security.pdf, s. 221–232.

## Mapa wiedzy

- Conditional logic uses tests/comparisons and `if`/`elif`/`else` blocks; the course applies conditions to host checks and security automation.
- Loops (`for`, `while`) enable repeated operations such as user cleanup, host scanning and processing files.
- Boolean/string/numeric tests and exit status form the decision layer of scripts.

## Komendy / pliki / składnia występujące w materiale

```text
if [ SuserNum == $num J; then echo "The variables are equal"; else echo "The variables are not equal"; fi
fi
While loop: Performs a block of code, as long as the condition is true.
echo “Execution times count: $x”
ping -c 1 10.71.0.$i | grep "bytes from" liveHost
ping -c 1 10.71.0@.$i | grep “bytes from" liveHost.
Bash Scripting
echo
cd ~/Desktop
echo “test”
echo $?
echo $? and is run from 127
cat /etc/ssh/ssh_config
find / -name *.sh 2>/dev/null
grep -in Fire /var/log/dpkg.log --color
for i in {5..7}; do deluser tempuser$i;done
apt install firefox
while True:
md5sum $file > $temppath
if $status -ne 0; then
else
```

## Notatki z zajęć (PadRiseup)

- `5. Używanie imienia i nazwiska na Zoomie ułatwia weryfikowanie obecności.`
- `Course book for [ID grupy]) - egzaminy, Final Projecty, Cywar itp.`
- `cat /etc/ssh/ssh_config`
- `find / -name *.sh 2>/dev/null`
- `grep -in Fire /var/log/dpkg.log --color`
- `for i in {5..7}; do deluser tempuser$i;done`
- `apt install firefox`
- `while True:`
- `finally:`
- `if "exit" in port:`
- `print("For port: {} Service is: {}".format(port, ret))`
- `16 filename=${data}_backup`
- `21 tar -czvf dest ath/filename $backup_path`
- `file=/var/www/html/index.html`
- `md5sum $file > $temppath`
- `if $status -ne 0; then`
- `else`
- `fi`
- `SSLCertificateFile /etc/ssl/certs/apache_selfsigned.crt`
- `SSLCertificateKeyFile /etc/ssl/private/apache_selfsigned.key`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-06-L1 — Basic Scripting](../labs/lnx-06-l1.md)
- [LNX-06-L4 — Scripting for Security](../labs/lnx-06-l4.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 102:** Logical Operators

Several commands can be written on a single line by separating them with a semi-colon

(;). This allows you to combine several commands in a single variable. Other command

separators can be used as well, such as | | which will run the second command if the

first fails, and && which will run the second command if the first succeeds.

r~# echo "Hello World"; pwd

Hello World

/root

i~# &f

The exit status syntax is echo $? and can only be run from the terminal window.

Section 3: Conditions

Conditional Operators

Conditional operators perform actions based on whether a statement is true or false.

They consist of if...then statements, whereby if the response is true, then an action will

be performed or a message will be issued. There can also be an else clause for a false

response, which will perform a different action or issue a different message.

Conditional operators can be logical operators, such as and or or, which can check as

many things as needed in one statement. Logical operators are indicated by a double

ampersand (&&) or double pipe (||). For ampersands, both conditions must be true.

For pipes, only one condition must be true.

**Textbook s. 103:** Operators

= Equals

I= Does not equal

-lt Less than |

le Less than or equal to

-gt Greater than

ge Greater than or equal to

-eq Equals (number)

< Less than

| > Greater than

If, Else, Then

The if structure includes if followed by open brackets, with the condition appearing in

the brackets. The word then follows, and what should happen if the statement is true.

The structure ends with fi.

Note: /f statements must include the following to work:

- They must end with fi.

- They must have spaces before and after an option in brackets.

For example:

num=3

userNum

**Textbook s. 104:** There is an option to write all of the code in one line.

For example:

if [ SuserNum == $num J; then echo "The variables are equal"; else echo "The variables are not equal"; fi

Elif

Elif is a combination of else and if. While if will always be checked and else only runs

when ff returns false, elif provides the ability to check multiple if statements, because

else considers only the last if statement.

For example:

#!/bin/bash

i

Y=

T=

[[ $X > $Y ]]

then “) “ I an ¥

elif [[$X < $Z]] ; then "x is less than z'

fi

Loops

Loop statements simplify repetitious tasks by continuously repeating an action until a

condition is met. Repetitive tasks are used in programming, as well as in malicious

brute-force attacks, the aim of which is to log in to a system by guessing a user’s

password.

In malicious usage of a loop, an attacker can create a script featuring a loop that tries to

enter a website by going through many possible passwords one at a time.

**Textbook s. 105:** There are three kinds of loops:

While loop: Performs a block of code, as long as the condition is true.

X=1

#A loop that will run as long as the value of $x is less than 5

$x 5

echo “Execution times count: $x”

x $x +1

For loop: Performs a block of code with a range, as long as the condition is true.

# Clear file at the beginning of the process

~/Desktop

"" > liveHost

# Loop in the range 1 to 255

i 1..255};

“[+] pinging 10.71.0.$i"

ping -c 1 10.71.0.$i | grep "bytes from" liveHost

"Done!"

**Textbook s. 106:** Until loop: Runs a block of code until a specific condition is met.

john@debian: ~ x!

File Edit View Search Terminal Help

GNU nano 3.2 script Modified

counter = 0

$counter 10

“$counter™

counter++

ime Get Help @e Write Out gi) Where Is @i Cut Text

i Exit i) Read File gy Replace @l Uncut Text

‘Do' Parameter

The do parameter defines the action to perform if the condition is true. The do action

follows for, and done closes the loop.

Note: done is necessary to let the script know when to end the loop actions.

For example:

z 1255);

"[+] pinging 10.71.0.$i"

ping -c 1 10.71.0@.$i | grep “bytes from" liveHost.

**Textbook s. 107:** Exit Status

Exit status is code that triggers a verification process. It checks if the last command

executed was a success or failure. The standard exit code is 0 for success, and any

number between 1 and 255 for failure.

froot/file.txt

Diff

Diff is a command that compares two files line-by-line and displays the differences.

The command uses specific symbols, and special instructions are required to create two

identical files.

Lab Assignment: LNX-06-L1 Basic Scripting

— Practice common Linux commands, Bash scripting, and Bash operators.

m=:

Follow the instructions in lab document LNX-06-L1.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 221:** Bash Scripting

Conditions

**Slides s. 222:** (Co Conditions

O

¢ Conditions ask the question /f..., and the

response will be true or false.

e Logical operators can be included ina single

qd: -P line using &&, which represents AND.

0 ea e |] is used for OR.

Q\ =

**Slides s. 223:** (Of Conditions

@ | Operator | Meaning

| = | Equals

| l= | Does not equal

| -It | Less than (number) e

| -gt | Greater than (number)

| -eq | Equals (number)

| <> | Less than and greater than (string) é

16

**Slides s. 224:** #!/bin/bash

num=3

userNum

if must have fi at the end a 4

of the statement.

echo

Use a semicolon when if

and else are in the same -e

line.

Use square brackets for mathematical expressions or string comparisons.

**Slides s. 225:** (elif

eli

O

e elif is a combination of else and if.

e To use elif, you must check for a condition.

e elif tries to run when ff fails.

e If else exists, it will be the last condition checked.

Q\ =

**Slides s. 226:** #!/bin/bash

# Clear file at the beginning of the process

cd ~/Desktop

A loop statement repeats a echo liveHost

task.

The jin the loop command is : mere GE seca

F ah ye 2553-5

a variable that represents

values in a range, like {1..255}. echo

After the for parameter in a ping -c 1 10.71.0. | grep liveHost

loop is defined, the action is

za echo

specified.

A loop can be created either with for or while.

**Slides s. 227:** (da Conditions

O

e The do parameter defines the action to

perform if the condition is true.

e The do action follows the for parameter.

e done closes the action’s specification.

Q\ =

**Slides s. 228:** #!/bin/bash

#Seting

A loop statement repeats a er

task.

#A loop that will run as long as the value of $x is less than 5

In the example on the right,

each iteration will print the 5

value of x and then add 1 to

the value. echo

x ar dl

Each time an iteration begins,

the condition will be checked

to see if it is true.

A loop can be created either with for or while.

**Slides s. 229:** $ echo “test”

test

$ echo $?

Every command has an 2 . -

exit status code. eee

-bash: ipconfig:

The exit status syntax is $ echo $?

echo $? and is run from 127

the terminal window.

A successful command

output would be 0.

**Slides s. 230:** #!/bin/bash

/root/file.txt

al

The exit code can be

tested by adding itasa Py

line in the script or as a

CLI command.

echo

In the example in red, the

S$? represents the exit

code.

Ois the response code for a successful statement.

If a statement fails, the status code will vary in accordance with the error code.

**Slides s. 231:** (dij Conditions

diff

O

$ diff file1 file2

e diff stands for difference. O Oj

e The function compares two files and outputs the

differences.

e If the files are identical, diff does not produce an output. We

24

**Slides s. 232:** Conditions

Basic Scripting | Practice using common Linux commands,

; 1 Bash scripting, and Bash operators.

15-20 Min.

wer r wf j e Write a script that checks for live hosts.

i \ )

| ‘ i= ® ~ e Text editor e Lab document

H ~ % - «

a é

4 TY = |

</details>
