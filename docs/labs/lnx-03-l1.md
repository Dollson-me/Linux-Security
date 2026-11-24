# LNX-03-L1 — Advanced Piping

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 141–153.

## Cel, misja i środowisko

- G Lab Objective Learn how to work with the pipe command. La Lab Mission Use stream redirection and piping to filter the output of commands and obtain a more
- La Lab Mission Use stream redirection and piping to filter the output of commands and obtain a more accurate output. ea rl
- ©) Lab Duration 20-25 minutes tC) Requirements e Understanding of stream redirection
- tC) Requirements e Understanding of stream redirection e Working knowledge of piping commands oo
- | Resources e¢ Environment & Tools o VirtualBox o Debian environment from LNX-01-L3

## Zadania / etapy

1. Lab Task 1: Use Pipe to Explore Files Solve the following tasks using output redirection and pipe commands. 1 Find all .page files in /usr/share/help with the command find /usr/share/help/ -name *.page

## Komendy występujące w labie

```text
find /usr/share/help/ -name *.page
which each file is written.
cat /var/log/dpkg.log | grep “status installed”
cat /var/log/dpkg.log | grep “status installed” | awk {print $5}
find /usr/share/help/ -name *.page |
find /usr/share/help/ -name *.page | we -l
fj
9
ls -UhR / |
1s -lhR / | awk ‘{print $5}' | grep M | sort -n | tail -n 1
I |
exit
awk '{print $5}'
```

## Powiązana teoria

- [Piping Redirection](../03-users-permissions/piping-redirection.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 141:** Linux Security

Lab Assignment Users and

Permissions

ofan LNX-03-L1

Fo U Advanced Piping

All Rights Reserved.

**PDF s. 142:** Linux Security

Lab Assignment Users and

Permissions

ofan LNX-03-L1

Fo U Advanced Piping

All Rights Reserved.

**PDF s. 143:** G Lab Objective

Learn how to work with the pipe command.

La Lab Mission

Use stream redirection and piping to filter the output of commands and obtain a more

accurate output.

ea rl

©) Lab Duration

20-25 minutes

tC) Requirements

e Understanding of stream redirection

e Working knowledge of piping commands

oo

| Resources

e¢ Environment & Tools

o VirtualBox

o Debian environment from LNX-01-L3

oO Terminal

**PDF s. 144:** Lab Task 1: Use Pipe to Explore Files

Solve the following tasks using output redirection and pipe commands.

1 Find all .page files in /usr/share/help with the command

find /usr/share/help/ -name *.page

2 List the total number of lines in all the .page files within the /usr/share/help/

directory using the command find /usr/share/help/ -name *.page | wc -!

3 Determine the number of .page files and in which languages they are written

using the command Is /usr/share/help | we -I

Tip: Run Is /usr/share/help/ to determine how you can find the language in

which each file is written.

4 Switch to the root user with the command su to get additional permissions in the

Os.

5 Runthe command Is -IhR / to print a list of all files and their sizes.

6 Determine the size of the largest file in the system with the command

Is -IhR / | awk {print $5} | grep M | sort -n | tail -n 1

Scroll down to the bottom of the output and note the size.

Note: Some permission errors will occur during the search, but you will see the

largest number at the end of the output.

Tip: Since the fifth column contains the size, you can use the awk {print $5’

command. The output will contain many lines that end with K, M, or G (kilobytes,

megabytes, or gigabytes), so you can use grep M (because no files are larger than

1 GB). Use tail -n 1 to print the last result.

7 Switch back to your user account using the exit command.

8 Find all Gnome packages that were installed and print their names and versions

using the cat /var/log/dpkg.log | grep gnome command.

**PDF s. 145:** Note: There are multiple lines for each package, and some lines contain

irrelevant configuration records.

9 Use a similar command to display only lines with the installed status:

cat /var/log/dpkg.log | grep “status installed”

10 Filter the output of cat /var/log/dpkg.log | grep “status installed” to display

only the name of the installed package using the command

cat /var/log/dpkg.log | grep “status installed” | awk {print $5}

**PDF s. 146:** Linux Security

Lab Assignment Users and

& Solution Permissions

o am LNX-03-LS1

Fo U Advanced Piping

All Rights Reserved.

**PDF s. 147:** Linux Security

Lab Assignment Users and

& Solution Permissions

o am LNX-03-LS1

Fo U Advanced Piping

All Rights Reserved.

**PDF s. 148:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Learn how to work with the pipe command.

5 Lab Mission

Use stream redirection and piping to filter the output of commands and obtain a more

accurate output.

x) .

© Lab Duration

20-25 minutes

tC) Requirements

e Understanding of stream redirection

e Working knowledge of piping commands

Lt

| Resources

e¢ Environment & Tools

o VirtualBox

o Debian environment from LNX-01-L3

oO Terminal

**PDF s. 149:** Lab Task 1: Use Pipe to Explore Files

Solve the following tasks using output redirection and pipe commands.

1 Find all .page files in /usr/share/help with the command

find /usr/share/help/ -name *.page

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ find /usr/share/help/ -name *.page |

/usr/share/help/de/cheese/pref -fullscreen.page

/usr/share/help/de/cheese/effects-apply. page

/usr/share/help/de/cheese/photo-view. page

/usr/share/help/de/cheese/pref -resolution.page

/usr/share/help/de/cheese/video-record.page

/usr/share/help/de/cheese/burst-mode. page

/usr/share/help/de/cheese/photo-save. page

/usr/share/help/de/cheese/pref -image- properties .page

/usr/share/help/de/cheese/pref - countdown .page

/usr/share/help/de/cheese/photo-take. page

/usr/share/help/de/cheese/introduction. page

/usr/share/help/de/cheese/index.page

/usr/share/help/de/cheese/photo-delete. page

/usr/share/help/de/cheese/pref - flash. page

/usr/share/help/de/gnome-clocks/alarm-snooze-stop. page

/usr/share/help/de/gnome-clocks/alarm-edit. page

/usr/share/help/de/gnome-clocks/world-add.page

/usr/share/help/de/gnome-clocks/world-remove. page

/usr/share/help/de/gnome-clocks/stopwatch.page

2 List the total number of lines in all the .page files within the /usr/share/help/

directory using the command find /usr/share/help/ -name *.page | wc -!

john@debian: ~ x

File Edit View Search Terminal Help

john@debian:~$ find /usr/share/help/ -name *.page | we -l

28939

john@debian:~$ fj

There are approximately 29,000 lines.

**PDF s. 150:** 3. Determine the number of .page files and in which languages they are written

using the command Is /usr/share/help | we -I

Tip: Run Is /usr/share/help/ to determine how you can find the language in

which each file is written.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ Ls /usr/share/help

i~$ ls /usr/share/help | we -l

57

1=$

As a result, you should get a list of 57 languages.

4 Switch to the root user with the command su to get additional permissions in the

Os.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ su

Password:

root@debian:/home/john# 9

**PDF s. 151:** 5 Runthe command Is -IhR / to print a list of all files and their sizes.

john@debian: ~ x

File Edit View Search Terminal Help

root@debian:/home/john# ls -UhR / |

Ae

total 60K

Lrwxrwxrwx 1 root root 7 Sep 16 10:42 bin -> usr/bin

drwxr-xr-x 3 root root 4.0K Sep 17 03:49 boot

drwxr-xr-x 17 root root 3.2K Sep 23 01:21 dev

drwxr-xr-x 118 root root 4.0K Sep 23 01:35 etc

drwxr-xr-x 4 root root 4.0K Sep 23 01:35 home

Lrwxrwxrwx 1 root root 31 Sep 16 10:51 initrd.img -> boot/initrd.img-

4.19.0-10-amd64

Lrwxrwx rwx 1 root root 30 Sep 16 10:43 initrd.img.old -> boot/initrd

img-4.19.0-8-amd64

Lrwxrwx rwXx 1 root root 7 Sep 16 10:42 lib -> usr/lib

Lrwxrwx rwx. 1 root root 9 Sep 16 10:42 1lib32 -> usr/lib32

Lrwxrwxrwx 1 root root 9 Sep 16 10:42 1lib64 -> usr/lib64

Lrwxrwx rwXx 1 root root 10 Sep 16 10:42 Libx32 -> usr/libx32

drwx------ 2 root root 16K Sep 16 10:42 lost+found

drwxr-xr-x 3 root root 4.0K Sep 16 10:42 media

drwxr-xr-x 2 root root 4.0K Sep 16 10:42 mnt

drwxr-xr-x 3 root root 4.0K Sep 17 03:49 opt

6 Determine the size of the largest file in the system with the command

Is -IhR / | awk {print $5}’ | grep M | sort -n | tail-n 1

Scroll down to the bottom of the output and note the size.

Note: Some permission errors will occur during the search, but you will see the

largest number at the end of the output.

Tip: Since the fifth column contains the size, you can use the awk {print $5’

command. The output will contain many lines that end with K, M, or G (kilobytes,

megabytes, or gigabytes), so you can use grep M (because no files are larger than

1 GB). Use tail -n 1 to print the last result.

john@debian: ~ x

File Edit View Search Terminal Hel

root@debian:/home/john# 1s -lhR / | awk ‘{print $5}' | grep M | sort -n | tail -n 1

ls: cannot read symbolic link '/proc/10/exe': No such file or directory

ls: cannot read symbolic link ‘/proc/10/task/10/exe': No such file or directory

ls; cannot access '/run/user/1000/qvfs': Permission denied

ls: cannot open directory '/run/user/1000/gvfs': Permission denied

101M

root@debian: /home/john# I |

Page5

**PDF s. 152:** 7 Switch back to your user account using the exit command.

john@debian: ~ x

File Edit Wiew Search Terminal Help

root@debian: /home/john# exit

exit

[=¢

8 Find all Gnome packages that were installed and print their names and versions

using the cat /var/log/dpkg.log | grep gnome command.

Note: There are multiple lines for each package, and some lines contain

irrelevant configuration records.

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat /var/log/dpkg.log | grep gnome |

2020-09-17 01:56:55 install libsoup-gnome2.4-1:amd64 <none> 2.64.2-2

2020-09-17 01:56:55 status half-installed libsoup-gnome2.4-1:amd64 2

-64.2-2

2020-09-17 01:56:55 status unpacked Libsoup-gnome2.4-1:amd64 2.64.2-

2

9 Use a similar command to display only lines with the installed status:

cat /var/log/dpkg.log | grep “status installed”

john@debian: ~ x

File Edit View Search Terminal Help

:~$ cat /var/log/dpkg.log | grep -w "status installed" |

2020-09-16 14:42:30 status installed base-passwd:amd64 3.5.46

2020-09-16 14:42:30 status installed base-files:amd64 10.3+deb1l0u3

2020-09-16 14:42:31 status installed dpkg:amd64 1.19.7

2020-09-16 14:42:32 status installed libc6:amd64 2.28-10

2020-09-16 14:42:33 status installed perl-base:amd64 5.28.1-6

2020-09-16 14:42:33 status installed mawk:amd64 1.3.3-17+b3

2020-09-16 14:42:33 status installed debconf:all 1.5.71

**PDF s. 153:** 10 Filter the output of cat /var/log/dpkg.log | grep “status installed” to display

only the name of the installed package using the command

cat /var/log/dpkg.log | grep “status installed” | awk {print $5}

john@debian: ~ x

FARES EGE Views) Seaieh Terminal Help

:~$ cat /var/log/dpkg.log | grep -w "status installed" | |

awk '{print $5}'

base-passwd:amd64

base-files:amd64

dpkg: amd64

</details>
