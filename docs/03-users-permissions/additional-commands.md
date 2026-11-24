# Additional CLI Commands & Environment

[← 03 · Users & Permissions](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 50–54; Linux Security.pdf, s. 98–103.

## Mapa wiedzy

- This section extends day-to-day command-line administration with text viewing, process/system information and environment control.
- The course uses `more`, `less`, `env`, PATH manipulation and other utilities as building blocks for troubleshooting and automation.
- Knowing where privileged binaries live (`/usr/sbin`, for example) matters when PATH differs between regular and root sessions.

## Komendy / pliki / składnia występujące w materiale

```text
Tail & Head
Tail and head commands are typically used in content with large amounts of text. They
Cat
cat - concatenate files and print on the standard output
cat [OPTION]... [FILE]..
man :x:6:12:man:/var/cache/man: /usr/sbin/nologin
Sort reorders the output of a file by
Cut is a text delimiter that cuts strings with a
export PATH=/usr/sbin:$PATH
env
```

## Notatki z zajęć (PadRiseup)

- https://www.openvim.com/
- `more /var/log/dpkg.log`
- `less /var/log/dpkg.log`
- `export PATH=/usr/sbin:$PATH`
- `env`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-03-L1 — Advanced Piping](../labs/lnx-03-l1.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 50:** Section 3: Additional Commands

Tail & Head

Tail and head commands are typically used in content with large amounts of text. They

do not filter for strings. Tail displays the last 10 lines of the document while head

displays the first 10 lines. You can change the number of lines displayed using the -n

flag.

For example, for a file that contains numbers in order from 1 to 20, head will display

numbers 1 to 10, while tail will display numbers 11 to 20.

Additional Useful Commands

Some additional commands can be useful regarding ordering items in text.

For example, the sort command sorts content line by line. If the sort command is used

with numbers, the output will display the numbers from lowest to highest without

taking into consideration the number value. For example, if the numbers 1, 2, and 10

are sorted, the order will be 1, 10, and 2. If the sort command is executed on letters,

the results will be sorted in alphabetical order in which uppercase letters precede

lowercase.

Some additional flags can be combined with this command, such as -o, which places the

sorted output in a new file; -r, which sorts content in reverse order; and -n, which takes

numeric values into consideration. To combine flags, use a single hyphen with each flag

and place flags one after the other.

**Textbook s. 51:** john@debian: ~ x“

File Edit View Search Terminal Help

:~$ head animals.txt

Cat

Dog

Guinea pig

Donkey

Horse

Pig

:~$ sort -o reverse order animals.txt

:~$ head reverse order

Cat

Dog

Donkey

Guinea pig

Horse

Pig

-$ ff

Another command that customizes alphabetic output is cut. This command “cuts”

letters and presents several parts of the word or words. The text can be arranged by

bytes using the -b flag, by column with -c, by field with -f, and -d is used as a delimiter.

A file’s word count, number of letters, bytes, and more can be displayed with we. Flags

determine the content that will be displayed. For example, -l lists the line numbers in

the file, -w displays the number of words in the file, -c shows the number of bytes, and -

L displays the longest line in the file.

**Textbook s. 52:** john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat example.txt

CAT(1) User Commands CAT(1)

NAME

cat - concatenate files and print on the standard output

SYNOPSIS

cat [OPTION]... [FILE]..

DESCRIPTION

Concatenate FILE(s) to standard output.

:~$ we -1l example.txt

10 example.txt

i~$ we -w example. txt

25 example.txt

:~$ we example.txt

10 25 237 example. txt

More

When working with large files, cat displays all content so you can search the file without

opening it. To avoid scrolling endlessly to find something in the file, it can be viewed

page by page using the more command. In the output of a command using more, you

can use the spacebar to scroll down a page, or press Enter to read the next line. The

bottom line of the terminal displays the percentage of content read.

**Textbook s. 53:** john@debian: ~ ae

File Edit View Search Terminal Help

root:x:0:0:root:/root:/bin/bash

daemon: x:1:1:daemon:/usr/sbin: /usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:X:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man :x:6:12:man:/var/cache/man: /usr/sbin/nologin

1Up:x:7:7:lp:/var/spool/tpd: /usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news :x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

lwww-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup: x:34:34: backup: /var/backups: /usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin) :/var/lib/gnats: /|

--More- - (35%)

Less

The less command opens one page of the file at a time (more loads the entire file).

During command execution, a search option provides the ability to search the file for

keywords using ?.

The following is an example of a search for logs performed in December:

**Textbook s. 54:** john@debian: ~ ae

File Edit View Search Terminal Help

root:x:0:0:root:/root:/bin/bash

daemon: x:1:1:daemon:/usr/sbin: /usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:X:3:3:sys:/dev:/usr/sbin/nologin

sync:x:4:65534:sync:/bin:/bin/sync

games:x:5:60:games:/usr/games:/usr/sbin/nologin

man :x:6:12:man:/var/cache/man: /usr/sbin/nologin

1Up:x:7:7:lp:/var/spool/tpd: /usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

news :x:9:9:news:/var/spool/news:/usr/sbin/nologin

uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

lwww-data:x:33:33:www-data:/var/www:/usr/sbin/nologin

backup: x:34:34: backup: /var/backups: /usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin

gnats:x:41:41:Gnats Bug-Reporting System (admin) :/var/lib/gnats:/|

Lab Assignment: LNX-03-L1 Advanced Piping

ae Use stream redirection and piping to filter the output of commands and

= =| obtain a more accurate output.

Follow the instructions in lab document LNX-03-L1.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 98:** Users & Permissions

Additional Commands

**Slides s. 99:** (He Additional Commands

e

iS

A=) Head, by default, outputs the first

7 4 10 lines ina file.

Tail, by default, outputs the last 10

lines of a file.

Lp ala

**Slides s. 100:** (ot Additional Commands

Sort reorders the output of a file by

number, date, text, etc. “

Cut is a text delimiter that cuts strings with a

specified character and prints the delimited

text based on selected fields.

WC displays the number of lines, words,

bytes, and characters in a file.

ee

**Slides s. 101:** Additional Commands

“y more access.log.1

127.0.0.1 - - [@7/JuL/2022:19:09:33 -@400] "-" 408 @ "-" "-"

127.0.0.1 - - [@7/Jul/2022:19:10:27 -@400] "\x16\x03\x@1\x02" 400 6 "-" "-"

tio - - [@7/Jul/2022:19:11:67 -@400] "GET / HTTP/1.1" 20@ 3586 "-" "Mozilla/5.0

inux x86_64; rv:83.0) Gecko/20100101 Firefox/83.0"

1 - - [07/Jul/2022:19:11:07 -0400] "GET /bundles/jqueryval1681?v=k0952jRLUEVNZ

hsJ@t@ngQHk32HeNdumCbRM1 HTTP/1.1" 200 28486 “http: //localhost/" "Mozilla/5.@ (Xx

ux x86_64; rv:83.0) Gecko/20100101 Firefox/83.0"

1 - - [07/Jul/2022:19:11:07 -0400] "GET /bundles/bootstrap53b9?v=NE-C7tK4A7Qr2 j

5926HQS1t1ZdBjgam_8c3101 HTTP/1.1" 200 28623 “http: //Localhost/" “Mozilla/5.@ (Xx More displays the data of

ux x86_64; rv:83.0) Gecko/20100101 Firefox/s3.0" a file.

tl - — [@7/JuL/2022:19:11:607 -@400] "GET /bundles/jqueryc2b0?v-yMmPM1TxecYcowtc

@fr9kiAasOfb-W51Q01A1 HTTP/1.1" 200 84458 "http://LocaLhost/" "Mozilla/5.@ (X11;

x86_64; rv:83.0) Gecko/20100101 Firefox/83.0" j

rd - — [07/Jul/2022:19:11:07 -8400] "GET /bundles/bootstrap-carouselfc13?v=rUr3 Using enter and space,

cIo1RwL-7U9bu6em4uigphbGo7qxh4YE1 HTTP/1.1" 200 3351 “http://localhost/” “Mozill you can scroll down the

X11; Linux x86_64; rv:83.0) Gecko/20100101 Firefox/83.0"

gd - — [@7/Ju1L/2022:19:11:07 -0400] "GET /Content/sitebfd2.css?v=16KScg LOON-Kqj text.

9wjGBaJWegpUYS6A7q1S101 HTTP/1.1" 20@ 21430 "“http://Localhost/" "Mozilla/5.@ (X1

x x86_64; rv:83.9) Gecko/20100101 Firefox/s3.0"

m1 - - [07/Jul/2022:19:11:07 -0400] "GET /Images/troyhuntcom.png HTTP/1.1" 200 The text can only be

ttp://localhost/" "Mozilla/5.@ (X11; Linux x86_64; rv:83.@) Gecko/20100101 Firef

5 scrolled forward, not

na o- - [@7/Jul/2@22:19:11:07 -@400] "GET /Images/Makes/2.png HTTP/1.1" 200 8536

//localhost/" "Mozilla/5.@ (X11; Linux x86_64; rv:83.0) Gecko/20100101 Firefox/8 backward.

m1 - -— [07/Jul/2022:19:11:07 -@400] "GET /Images/Makes/3.png HTTP/1.1" 200 1388

://localhost/" "Mozilla/5.@ (X11; Linux x86_64; rv:83.0) Gecko/20100101 Firefox/

1 - - [@7/Jul/2@22:19:11:07 -@400] "GET /Images/Makes/1.png HTTP/1.1" 200 6993

//localhost/" "Mozilla/5.@ (X11; Linux x86_64; rv:83.0) Gecko/20100101 Firefox/8

From: ThriveDX

**Slides s. 102:** Additional Commands

Activities LE) Terminal + Tue 03:54. 3 4, Or

johnd@debian: fete x

File Edit View Search Terminal Help

- - [05/Nov/2019:00:29:59 -0500] “POST / HTTP/1.1" 200 349 Create-Prin

ter-Subscriptions successful-ok

- ~ [05/Nov/2019:00:29:59 -0500] "POST / HTTP/1.1" 200 176 Create-Prin|

ter-Subscriptions successful-ok

- ~ [05/Nov/2019:00:31:28 -0500] "POST / HTTP/1.1" 200 184 Renew-Subsc| Less is similar to More

ription client-error-not-found !

- ~ [05/Nov/2019:61:29:48 -8500] “POST / HTTP/1.1" 200 184 Renew-Subsc| but the output can be

ription client-error-not- found

- - [05/Nov/2019:01:58:50 -9500] "POST / HTTP/1.1" 200 153 Cancel-Subs| scrolled up and down

cription client-error-not-found .

- ~ [05/Nov/2019:01:58:50 -0500] "POST / HTTP/1.1" 200 153 Cancel-Subs| using the arrow keys.

cription client-error-not-found

- - [05/Nov/2019:01:58:50 -0500] “POST / HTTP/1.1" 401 123 Cancel-Subs|

cription successful-ok “7

- root [05/Nov/2019:01:58:50 -0500] "POST / HTTP/1.1" 206 123 Cancel-s ?’ enables a search for

ubscription successful-ok keywords.

- - [@5/Nov/2019:01:58:50 -0500] “POST / HTTP/1.1" 200 152 Cancel-Subs

cription successTul-ok

- - [05/Nov/2019:01:59:09 -9500] “POST / HTTP/1.1" 200 349 Create-Prin

ter-Subscriptions successful-ok

- - [05/Nov/2019:61:59:10 -0500] “POST / HTTP/1.1" 200 176 Create-Prin

ter-Subscriptions successful-ok

} : - - [05/Nov/2019:01:59:36 -0500] "POST / HTTP/1.1" 200 361 Create-Prin|

J :

From: ThriveDX

**Slides s. 103:** Additional Commands

SO ae Use stream direction and piping to filter and obtain a

Advanced Piping | more accurate output of commands.

20-25 Min. A

en @ yA : @ Use the commands you have learned

4 up to this point.

il aes: 7 = I | ®@ Use piping commands.

. ~~ ® 8 di

J ap, yr

a | .) A s ~~ ELEiVibiWVitiiitiit CA IV INSIGtCOU Piito

| ®,.° @ VirtualBox @ Lab document

~~=, | ® Debian

. ® Desktop experience

j ‘. | (Gnome)

{ << “=

</details>
