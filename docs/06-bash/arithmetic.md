# Arithmetic Operators

[← 06 · Bash Scripting](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 108–109; Linux Security.pdf, s. 233–238.

## Mapa wiedzy

- Bash supports arithmetic operations and comparisons for counters, thresholds and calculations inside scripts.
- The material covers addition, subtraction, multiplication, division/modulo and ways to evaluate arithmetic expressions.

## Komendy / pliki / składnia występujące w materiale

```text
Bash Scripting
echo $surm
echo Y
echo |
echo :
```

## Powiązane laboratoria

- [LNX-06-L1 — Basic Scripting](../labs/lnx-06-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 108:** Section 4: Arithmetic Operators

Arithmetic operators are mathematical functions that can calculate two or more

operands, or objects that can be manipulated. For example, in 2 - 1 = 1, the 2 and 1 are

operands and the minus sign is the operator.

Arithmetic operators are used in equations in computer language scripts, to perform

various types of calculations.

‘let' Command

The let command is used to calculate arithmetic expressions. It converts a variable to an

arithmetic expression.

The command does not require spaces, but if one is needed in the expression, it must

appear in quotation marks.

sum=24+2

Mathematical Equations

Mathematical equations can be used for calculations:

+= Addition

- = Subtraction

* = Multiplication

/ = Division

Notes for Variables and Calculations:

e Using a double plus sign (++) before or after a variable increases the value by 1.

¢ Variables are calculated relative to their locations within the command flow.

¢ The last variable that is calculated will be the final value.

**Textbook s. 109:** Example:

number=3

sum.

In the following script, the output will be 4 because it solves the NUM (number)

variable in each of the equations.

=7

NUM-=3 #7 -3=4

NUM+=2 #4+2=6

NUM*=2 #6 * 2 = 12

NUM/=3 #12 /3=4

In arithmetic operators, there is an option to use the escape character (\), which

indicates the removal of the special meaning of a character.

Expr

The expr command evaluates a given sequence. For example, in the following script,

the output will be 6:

File Edit View Search Terminal Help

jhond@debian:~$ sum=$(expr 2 \* 3)

lsum (PED jonc@debian:~$ echo $sum

6

jhond@debian:~$

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 233:** Bash Scripting

Arithmetic Operators

**Slides s. 234:** #!/bin/bash

sum=2+2

echo $surm

¢ letis a built-in command used to evaluate

arithmetic expressions.

e |t converts a variable to an arithmetic expression.

¢ The let command does not require spaces. y

¢ If aspace is needed in the expression, it should ~~]

be placed within quotation marks. y

**Slides s. 235:** #!/bin/bash

; ; number=3

Arithmetic can be used to sum

express calculations:

echo Y

+: addition echo .

-: subtraction

*: multiplication

/. division

Using a double plus sign

before or after the variable

increments the value by 1.

Variables are remembered by their place in the flow.

The last variable that is calculated will be the final value.

**Slides s. 236:** #!/bin/bash

=7

NUM-=3 #7 = 3 = 4

NUM+=2 #44+2=6

NUM*=2 tte) we G2 i aly

NUM/=3 #12 /3 = 4

echo |

In the example above, the output will be 4 because it solves the NUM variable

in each of the equations.

**Slides s. 237:** (expr Operators

O

expr 7 +7

sum=$(expr 2 \* 3

A simple expression will calculate the sum and

Bel print the stdout. Pn

~~ -

=a Ssum is saved as a variable and can be reused - ™

SEBGI . . 4

Core in the script. ~

**Slides s. 238:** #!/bin/bash

a=2

b=3

sum= a+b

echo :

In the example above, the output ($sum) will be 5.

Note that double parentheses can be used for variables that include two expressions.

</details>
