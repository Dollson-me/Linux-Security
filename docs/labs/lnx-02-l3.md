# LNX-02-L3 — Editing Files

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 99–127.

## Cel, misja i środowisko

- G Lab Objective This lab introduces text manipulation commands and teaches how to work with terminal-based text editors. s Lab Mission
- s Lab Mission Practice using text editors and output redirection to read from and write to files. ea . ©) Lab Duration
- ©) Lab Duration 20-30 minutes fe Requirements e Working knowledge of the CLI interface
- fe Requirements e Working knowledge of the CLI interface e Working knowledge of Vim and other text editors on
- | Resources Environment and tools: © Debian environment from LNX-01-L3 ¢ Terminal

## Zadania / etapy

1. Lab Task 1: Explore Nano Editor Modes Explore the use of various modes in the Nano text editor. 1 From the terminal, navigate to your home directory and create a file named test by using the command touch test. Verify its creation with the command Is.
2. Lab Task 2: Edit Files Using Various Editors Create and edit files in the Debian environment by using the built-in GUI text editor and the terminal. 1 Open Firefox in the VM.
3. Lab Task 3: Vim Editor In this task, you will become familiar with the Vim text editor and search for a word. 1 Open Firefox in the VM and browse to Debian’s Wikipedia page: https://en.wikipedia.org/wiki/Debian.

## Komendy występujące w labie

```text
which lines by using the command :/swirl. Press n to navigate through the
nano is simple to learn.
nano is simple to learn.ff
nano is simple to learn.f
nano is to learn.
cat lorem |
cat lorem > lorem _copy
1s
cat lorem_copy |
Source model Open source
```

## Powiązana teoria

- [Data Streams Editors](../02-cli/data-streams-editors.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 99:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L3

5cnae Editing Files

olf

Ee

**PDF s. 100:** Linux Security

Lab Assignment CLI Fundamentals

LNX-02-L3

5cnae Editing Files

olf

Ee

**PDF s. 101:** G Lab Objective

This lab introduces text manipulation commands and teaches how to work with

terminal-based text editors.

s Lab Mission

Practice using text editors and output redirection to read from and write to files.

ea .

©) Lab Duration

20-30 minutes

fe Requirements

e Working knowledge of the CLI interface

e Working knowledge of Vim and other text editors

on

| Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

© Text editors:

o Nano

o Gedit

o Vim

**PDF s. 102:** Lab Task 1: Explore Nano Editor Modes

Explore the use of various modes in the Nano text editor.

1 From the terminal, navigate to your home directory and create a file named test

by using the command touch test. Verify its creation with the command Is.

2 Open the test file with the Nano text editor by using the command nano test.

Click Y when the message File _ is being edited... appears.

3 Type nano is simple to learn.

4 Press Ctrl+0 to save the changes in the file. Then, press Enter when asked for a

name.

5 Press Ctrl+G to display the help content and review the provided support and

guidance.

6 Exit the help page by pressing Ctrl+X.

7 Press Ctrl+W and search for the word simple. Note that it marks the first letter of

the word.

8 Press Ctrl+\ to replace a word in the document. Replace the word simple with the

word easy. When Search (to replace) appears, enter the word simple and when

Replace with appears, enter easy. Press Y when asked to replace the instance.

Note that the word changed.

9 Save the changes with Ctrl+0 and exit the editor with Ctrl+X.

**PDF s. 103:** Lab Task 2: Edit Files Using Various Editors

Create and edit files in the Debian environment by using the built-in GUI text editor and

the terminal.

1 Open Firefox in the VM.

2 Browse to https://loremipsum.io and create three paragraphs of text.

3 Open the terminal and make sure you are in your home directory. Run the

command gedit to open the gedit text editor.

4 Copy the generated paragraphs and paste them into the text editor by right-

clicking in it and selecting Paste.

5 Save the file by clicking Save. Name the file lorem and click Save again.

6 Print the contents of the file lorem to the terminal by using the command cat

lorem.

7 Use the command cat lorem > lorem_copy to copy the contents of the file and

paste them into a new file that was created automatically. Verify the creation of

the file by using Is.

8 Display the contents of the file by using the command cat lorem_copy and note

that it’s the same as the original.

9 Erase the entire content of the copy file in the fastest way possible and replace it

with your own sentence; use the command echo “erasing file’s content” >

lorem_copy.

10 Use the command cat lorem_copy to verify that the content was replaced.

**PDF s. 104:** Lab Task 3: Vim Editor

In this task, you will become familiar with the Vim text editor and search for a word.

1 Open Firefox in the VM and browse to Debian’s Wikipedia page:

https://en.wikipedia.org/wiki/Debian.

2 Right-click on the page, select Select All, right-click again in the content, and

select Copy.

3 Inthe terminal, make sure you are in your home directory, then execute the

command vi Debian_Wiki to create a new file and open it in the Vim editor.

4 Press Ctrl+Shift+V to paste the copied content from Debian’s Wikipedia page.

5 Press Esc and type :w to write the file. Press Enter, and then press Enter again to

continue.

6 Navigate to the beginning of the file by pressing Esc and typing :1.

7 Press Esc and type :set number to place line numbers.

8 Find out how many times the word swirl is repeated in the document and on

which lines by using the command :/swirl. Press n to navigate through the

results.

9 Let’s remove the line numbers and learn how to close the editor. Press Esc to run

the command -set nonumber. Now let’s close out of the editor and save the

document; press Esc, then type :wa!.

**PDF s. 105:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS3

5cnae Editing Files

itl

**PDF s. 106:** Linux Security

Lab Assignment CLI Fundamentals

& Solution

LNX-02-LS3

5cnae Editing Files

itl

**PDF s. 107:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

This lab introduces text manipulation commands and teaches how to work with

terminal-based text editors.

5 Lab Mission

Practice using text editors and output redirection to read from and write to files.

rN) .

@ Lab Duration

20-30 minutes

fe Requirements

e Working knowledge of the CLI interface

e Working knowledge of Vim and other text editors

Lt

| Resources

Environment and tools:

© Debian environment from LNX-01-L3

¢ Terminal

¢ Text editors:

o Nano

o Gedit

o Vim

**PDF s. 108:** Explore the use of various modes in the Nano text editor.

1 From the terminal, navigate to your home directory and create a file named test

by using the command touch test. Verify its creation with the command Is.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ touch test

eS)

Desktop Downloads Pictures Templates Videos

Documents Music Public test

:~$ ff

2 Open the test file with the Nano text editor by using the command nano test.

Click Y when the message File _ is being edited... appears.

john@debian: ~ x

File Edit View Search Terminal Help

an:~$ nano testff |

GNU nano_3.2 test

a

BE Get Help Write Out Where Is i Cut Text E Justify Cur Pos Undo

Mis Exit WB Reed File Replace M Uncut Text To Spell Go To Line Gi Redo

**PDF s. 109:** 3 Type nano is simple to learn.

john@debian: ~ x

File Edt View Search Terminal Help

GNU nano 3.2 test Modified

nano is simple to learn.

me Get Help ie Write Out @i) Where Is @N Cut Text

es Exit ii Read File @\ Replace gy Uncut Text

4 Press Ctrl+0 to save the changes in the file. Then, press Enter when asked for a

name.

john@debian: ~ x

File Eoit View Search Terminat Help

GNU nano 3.2 test Modified

nano is simple to learn.ff

Mc Get Help @ Write Out i) Where Is la Cut Text

sy Exit x Read File @y Replace We) Uncut Text

**PDF s. 110:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 test Modified

nano is simple to learn.

File Name to Write: test

ce Get Help (fi) DOS FormatZB@A Append Backup File

me Cancel Mew Mac Formatigiy Prepend Noy Eutes

5 Press Ctrl+G to display the help content and review the provided support and

guidance.

eee S

File Edit View Search Terminal Help ;

GNU nano 3.2 test

nano is simple to learn.

@g Get Help @@ Write Out (i Where Is “< Cut Text

@y Exit ix; Read File (iN Replace @!) Uncut Text

**PDF s. 111:** 6 Exit the help page by pressing Ctrl+X.

john@debian:~ =

File Edit View Search Terminal Help

Main nano help text

The nano editor is designed to emulate the functionality

and ease-of-use of the UW Pico text editor. There are

four main sections of the editor. The top line shows the

program version, the current filename being edited, and

whether or not the file has been modified. Next is the

main editor window showing the file being edited. The

status line is the third line from the bottom and shows

important messages. The bottom two lines show the most

commonly used shortcuts in the editor.

@® Refresh Where Is Previous jm Prev Line

® Close ()] Where Was Next i) Next Line

7 Press Ctrl+W and search for the word simple. Note that it marks the first letter of

the word.

john@debian: ~ x

File Edit_View Search Terminal _Help

GNU nano 3.2 EEE Modified

nano is simple to learn.ff

[ Cancelled ]

Me Get Help write Out QM where Is) QM cut Text

es Exit Mx Read File 4 Replace @) Uncut Text

**PDF s. 112:** john@debian: ~ x

File Edit View Search Terminal Help

GNU nano 3.2 test Modified

nano is simple to learn.

Search:| simple

me Get Help (Bf@ Case Sens is} Backwards @ig Older

me Cancel Mes Regexp is Replace @i) Newer

8 Press Ctrl+\ to replace a word in the document. Replace the word simple with the

word easy. When Search (to replace) appears, enter the word simple and when

Replace with appears, enter easy. Press Y when asked to replace the instance.

Note that the word changed.

john@debian: ~ x

Flle Edit View Search Terminal. Help

GNU nano 3.2 test

nano is simple to learn.f

[ Cancelled ]

@¢ Get Help ® Write Out @lj Where Is la Cut Text

Oy Exit i Read File [IN Replace gj) Uncut Text

**PDF s. 113:** eee =

File E9it View Search Terminal Help

GNU nano 3.2 test

nano is simple to learn.

Search (to replace) [hello]:|simple

@¢ Get Help (Ble Case Sens |B} Backwards @my Older

@@ Cancel Mex Regexp aii No Replace @) Newer

john@debian: ~ x

File Eoit View Search Terminal Helo

GNU nano 3.2 test

nano is simple to learn.

Replace with: | easy

ic Get Help Qe Older @i First Line

me Cancel @i) Newer @ Last Line

**PDF s. 114:** john@debian: ~ x

File Ecit View Search Terminal Help

GNU nano 3.2 ESE

nano is to learn.

Replace this instance?

Ii Yes N ALL

i} No me Cancel

9 Save the changes with Ctrl+0 and exit the editor with Ctrl+X.

**PDF s. 115:** Lab Task 2: Edit Files Using Various Editors

Create and edit files in the Debian environment by using the built-in GUI text editor and

the terminal.

1 Open Firefox in the VM.

fetivities Mon 03:03 Ad Or

Q firefox! a

**PDF s. 116:** 2 Browse to https://loremipsum.io and create three paragraphs of text.

Activities) FirefoxESR ~ Mon 03:05 WM Or

= Lorem Ipsum — Generar. x | x

©)? X @ [© af repsinoreripsume] a eS

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do

ciusmod tempor incididunt ut labore et dolore magna aliqua. Ut

enim ad minim veniam, quis nostrud exercitation ullamco laboris

nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in

reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla

pariatur. Excepteur sint oceaccat cupidatat non proident, sunt in

culpa qui officia deserunt mollit anim id est laborum.

Til] ] [ rarscrarne

close x

a PPA 4d

Transfering cata from ade googlesynication.com..

3 Open the terminal and make sure you are in your home directory. Run the

command gedit to open the gedit text editor.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cd ~

:~$ gedit

**PDF s. 117:** 4 Copy the generated paragraphs and paste them into the text editor by right-

clicking in it and selecting Paste.

Activities &) FirefoxESR + Mon 03:09 aM Or

$ Lorem Ipsum Generator x | x

427 e¢ © @ https://loremipsum.iolgenerator/?n=38t=p a-Or Woe =

placeholder text. Select the

number of characters, |

words, sentences or

paragraphs, and hit

generate!

Activitie: Text Editor ~ Mon 03:10 4 Ov

Opn y Untitled Document 1 Save 5 x

**PDF s. 118:** 5 Save the file by clicking Save. Name the file lorem and click Save again.

Activities (2) Text Editor ¥ Mon 03:12 2a Or

oma a *Untitied Document 1 = x

Loren ipsun dolor sit anet, consectetur adipiscing elit, sed do elusmod teapor incididunt ut

habore et dotore magna sliqua, Posuere ac ut consequat semper viverra. velit scelerisque in

consectetur adipiscing elit pellentesque habitant morbi. pretium viverra suspendisse potenti

Inutian ac. ALiquan purus sit anet luctus venenatis lectus magna Tringitta urna. Nec Teugist

Iragna ac placerat vestibulun lectus mauris ultrices eros in.

lst etiam sit anet nist purus in notlis nunc sed. Td nibh tortor id aliquet. Malesuada bibendum

arcu vitae elenentum curabitur vitae. ultricies mi eget mauris pharetra. sem fringitta ut norbi

feinesdunt augue. Aliquan faucibus purus in nassa tempor nec. Lobortis feugiat vivanus at augue

Inon. Sed velit dignissim sodales ut eu sem integer. 1d interdun velit laoreet id donec. sed

R'ibero enin sed Taucibus. Odio tempor orci dapibus ultrices in iaculis. Favcibus ornare

freugiat vivonus at augue eget arcu, Mattis molestie a iaculis at erat pellentesque adipiscing

vulputate. Massa placerat duis ultricies lacus. Donec pretium vulputate sapien nec sagittis

atiquan matesuada babendun arcu. scelerisque viverra mauris in aliquan sem tringitta ut. At

luctus accunsan tortor posuere. id senper risus in hendrerit. Justo laoreet sit anet cursus

at. Natesuada Tanes ac turpis egestas sed, Nisi vitae suscipit tellus mauris. Venenatis urna

frenpus iaculis urna id. ut morbi tincidunt augue interdum velit euismod in pellentesque nassa

PlainText TebWidtne > __Ln5\Col834_ > INS

Activities (2) Text Editor ~ Mon 03:14 4“ Or

@ Home 4 @john > GQ

© Documents od

omen 5 Desktop Thu

ON Documents Tho

dd Music ™ Downloads Thu

. = Music Thu

seat Pictures 02:36

vm Videos Public Thu

Templates Tho

OVEx6. 2 test 2Bbytes 02:47

= Videos Thu

+ Other Locations

Character Encosing: CurrentLocale (UTF-8) * Line Ending: Unix/tinx = Ailes ~

**PDF s. 119:** 6 Print the contents of the file lorem to the terminal by using the command cat

lorem.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ cat lorem |

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do

eiusmod tempor incididunt ut labore et dolore magna aliqua. Posu

ere ac ut consequat semper viverra. Velit scelerisque in dictum

non consectetur a. Justo donec enim diam vulputate ut pharetra.

Dolor sit amet consectetur adipiscing elit pellentesque habitant

morbi. Pretium viverra suspendisse potenti nullam ac. Aliquam p|

urus sit amet luctus venenatis lectus magna fringilla urna. Nec

7 Use the command cat lorem > lorem_copy to copy the contents of the file and

paste them into a new file that was created automatically. Verify the creation of

the file by using Is.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ cat lorem > lorem _copy

john@debian:~$ 1s

Desktop Downloads lorem_copy Pictures Templates Videos

Documents lorem Music Public test

john@debian:~$

8 Display the contents of the file by using the command cat lorem_copy and note

that it’s the same as the original.

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ cat lorem_copy |

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do

eiusmod tempor incididunt ut labore et dolore magna aliqua. Posu

ere ac ut consequat semper viverra. Velit scelerisque in dictum

non consectetur a. Justo donec enim diam vulputate ut pharetra.

Dolor sit amet consectetur adipiscing elit pellentesque habitant

morbi. Pretium viverra suspendisse potenti nullam ac. Aliquam p|

urus sit amet luctus venenatis lectus magna fringilla urna. Nec

**PDF s. 120:** 9 Erase the entire content of the copy file in the fastest way possible and replace it

with your own sentence; use the command echo “erasing file’s content” >

lorem_copy.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ echo “erasing file's content" > lorem_copy

:-$ Il

10 Use the command cat lorem_copy to verify that the content was replaced.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat lorem_copy

erasing file's content

$f

**PDF s. 121:** Lab Task 3: Vim Editor

In this task, you will become familiar with the Vim text editor and search for a word.

1 Open Firefox in the VM and browse to Debian’s Wikipedia page:

https://en.wikipedia.org/wiki/Debian.

Activities © FirefoxESR Mon 03:41 4“ Or

Ww Debian - Wikipedia a [=F x

oreo © a@ [ips/enwikipedia.orghuin/Debion] B-On NOS =

ge |

Po y Atide Talk Read Edit Viewhistory |Seafch Wikipedia Q

WIKIPEDIA Debian :

The Pace Eneyelopesia From Wikipedia, the free encyclopedia

sis pepe Debian (/‘dcbion/),5%l also known as Debian Debian

contents GNU/Linux, is a Linux distribution composed of

anton free and open-source software, developed by

Random article the community-supported Debian Project,

Shorey einars which was established by lan Murdock on

oe ‘August 16, 1993. The first version of Debian

{0.01} was released on September 15, 1993,'7! ‘

oo ands et stable version C1) wes releosed on debian

Help June 17, 1996.!8/ The Debian Stable branch is

Community portal the most popular edition for personal » a

Recent changes computers and servers. Debian is also the basis ——

Anos Ne: for many other distributions, most notably '

Tools: Ubuntu. i

what links here Debian is one of the oldest operating systems ir

Special pages coordinated over the Internet by a team of ee

Permanent link volunteers guided by the Debian Project Debian 10 (buster) with the GNOME desktop

**PDF s. 122:** 2 Right-click on the page, select Select All, right-click again in the content, and

select Copy.

Activities © Firefox ESR + ‘Mon 03:43 a Or

‘w Debian - Wikipedia x | + x

69 e¢ ® @ hitps://en.wikipedia.org/wiki/Debian B-or Noe =

Q = ‘h Wikipedi Qa

eS Z Artcle Talk Read Edit View histor Search Wikipedia

oom vv |

ee Debian ®

WrerpeprA | SE

‘The Free Emeyelopestin From Wikipedia, the free encyclopedia

iia pope eet arts © > © f pepian

Current events free and open-source software, deve ve Bage As

Random article the community-supported Debian py} Save Pageto Pocket

fetes which was established by lan Murdo¢ Send Page toDevice >

cor AAUgUSE 16, 1993. The first version of, Vey, Background mave

(0.01} was released on September seta gf bi

contribute and its first stable version (1.1) 0s Mo ebian

Help June 17, 1996.!8/The Debian Stable| View Page Source .

Community ports! | the most popular edition for persond View Page Info oa

Recent changes computers and servers. Debian is ali inspect Element (@)

upoat ale for many other distributions, Most Nts rake a Screenshot

oa ubuntu. ;

What links here Debian is one of the oldest operating systems. q ia |

spacial pages coordinated over the Internet by a team of —

Permanent link Golirastirs gilded bn she eabian froiaet Debian 10 (buster) with the GNOME desktop

Activities FirefoxESR > Mon 03:44 a Or

‘Ww Debian- Wikipedia x |+ x

erx-¢n ® @ hittps://enwikipedia.orgiwiki/Debian 5B -On Noe =

Ae a |

(eg m= EEE ME [sewer witineia

*

ome Debian ®

WikipepiIA = ee L.

arsed Deviant

FenU/Linux. sa Linux distribution composed ot =

= \

(Ge

Co

Selectall idl

a

Hepse Bereta)

Foot $8 Take a Screenshot

Sana

Volunteers guided by the Debian Prolect

**PDF s. 123:** 3 Inthe terminal, make sure you are in your home directory, then execute the

command vi Debian_Wiki to create a new file and open it in the Vim editor.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ vi Debian Wiki

4 Press Ctrl+Shift+V to paste the copied content from Debian’s Wikipedia page.

Activities GJ Terminal + Mon 04:00 2“ Or

john@debian: ~ x

File Edit View Search Terminal Help

This is a good article. Click here for more information.

Debian

From Wikipedia, the free encyclopedia

Jump to navigation

Jump to search

DebianDebian OpenLogo

Screenshot of Debian 10 (buster) with the GNOME desktop e|

nvironment

Debian 10 (buster) with the GNOME desktop environment

Developer The Debian Project

oS family Unix-like

Working state Current

Source model Open source

Initial release September 1993; 27 years ago

Latest release 10.5 (Buster)[1] (August 1, 2020; 51 days

ago) [+]

Latest preview 11 (Bullseye) [2]

**PDF s. 124:** 5 Press Esc and type :w to write the file. Press Enter, and then press Enter again to

continue.

john@debian: ~ x

File Edit View Search Terminal Helo

This is a good article. Click here for more information.

Debian

From Wikipedia, the free encyclopedia

Jump to navigation

Jump to search

DebianDebian OpenLogo

Screenshot of Debian 10 (buster) with the GNOME desktop e|

Invironment

Debian 10 (buster) with the GNOME desktop environment

Developer The Debian Project

oS family Unix-like

Norking state Current

Source model Open source

Initial release September 1993; 27 years ago

Latest release 10.5 (Buster)[1] (August 1, 2020; 51 days

ago) [+]

Latest preview 11 (Bullseye) [2]

a |

6 Navigate to the beginning of the file by pressing Esc and typing :1.

john@debian: ~ x

File Edit View Search Terminal Help

8.3 Embedded systems

9 Organization

9.1 Developers

10 Development

10.1 Release cycle

10.2 Security

10.2.1 2008 OpenSSL vulnerability

10.3 Value

11 Forks and derivatives

12 See also

13 References

14 Further reading

15 External Links

Features

Debian 10 installation menu (BIOS Mode)

Text version of the Debian Installer

Graphical version of the Debian Installer

21

**PDF s. 125:** 7 Press Esc and type :set number to place line numbers.

Activities _ &) Terminal + Mon 04:05 24) Or

john@debian: ~ x

File Edit View Search Terminal Help

This is a good article. Click here for more information.

Debian

From Wikipedia, the free encyclopedia

Jump to navigation

Jump to search

DebianDebian OpenLogo

Screenshot of Debian 10 (buster) with the GNOME desktop e|

nvironment

Debian 10 (buster) with the GNOME desktop environment

Developer The Debian Project

os family Unix-like

Working state Current

Source model Open source

Initial release September 1993; 27 years ago

Latest release 10.5 (Buster)[1] (August 1, 2020; 51 days

ago) [+]

Latest preview 11 (Bullseye) [2]

8 Find out how many times the word swirl is repeated in the document and on

which lines by using the command :/swirl. Press n to navigate through the

results.

Activities _ &) Terminal + Mon 04:07 24 O

john@debian: ~ x

File Edit View Search Terminal Help

1

This is a good article. Click here for more infor|

mation.

Debian

From Wikipedia, the free encyclopedia

5 Jump to navigation

6 Jump to search

7 DebianDebian OpenLogo

Screenshot of Debian 10 (buster) with the GNOME d

esktop environment

) Debian 10 (buster) with the GNOME desktop environ

ment

10 Developer The Debian Project

1 OS family Unix-like

12 Working state Current

Source model Open source

14 Initial release September 1993; 27 years ago

**PDF s. 126:** Activities GJ Terminal + Mon 04:08 4 Or

john@debian: ~ x

File Edit View Search Terminal Help

259 Logo

262 The Debian "swirl" logo was designed by Raul Silv

a[152][153] in 1999 as part of a contest to replace the s

emi-official logo that had been used.[154] The winner of

the contest received an @debian.org email address, and a

set of Debian 2.1 install CDs for the architecture of the|

ir choice. There has been no official statement from the

Debian project on the logo's meaning, but at the time of

the logo's selection, it was suggested that the logo repr

esented the magic smoke ( or the genie ) that made comput

ers work. [155] [156] [157]

€

Activities _ &) Terminal + Mon 04:08 24 Or

john@debian: ~ x

File Edit View Search Terminal Helo

259 Logo

160 The "swirl" logo represents the magic smoke.

61

262 The Debian "Bwirl" logo was designed by Raul Silv

a[152][153] in 1999 as part of a contest to replace the s

emi-official logo that had been used.[154] The winner of

the contest received an @debian.org email address, and a

set of Debian 2.1 install CDs for the architecture of the|

ir choice. There has been no official statement from the

Debian project on the logo's meaning, but at the time of

the logo's selection, it was suggested that the logo repr

esented the magic smoke ( or the genie ) that made comput

ers work. [155] [156] [157]

/swirl

The word swirl should appear five times.

**PDF s. 127:** 9 Let’s remove the line numbers and learn how to close the editor. Press Esc to run

the command :set nonumber. Now let’s close out of the editor and save the

document; press Esc, then type :wq!.

fhe Debian “swirl logo was designed by Raul Silva[160][161] in 1999 as part of

lOne theory about the origin of the Debian logo is that Buzz Lightyear, the chose

In character for the first named Debian release, has a swirl in his chin. [166][16|

7] Stefano Zacchiroli also suggested that this swirl is the Debian one.[168] Bu2|

Branding

In character for the first named Debian release, ha wirl in his chin. [166] [16

lz Lightyear's swirl is a more likely candidate as the codenames fi Debian are ni

</details>
