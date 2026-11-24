# Linux History, Kernel & Linux vs. Windows

[← 01 · Introduction to Linux](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 6–8; Linux Security.pdf, s. 4–10.

## Mapa wiedzy

- Linux is a family of UNIX-like operating systems; the course distinguishes the Linux kernel from a complete Linux distribution.
- The kernel is the intermediary between applications/users and hardware. The material assigns it device/hardware management, memory management, process management and handling system calls.
- Linux is presented as open-source and highly customizable; the course contrasts this with the closed-source Windows ecosystem.
- The layered model in the material is hardware → kernel → shell → application; separating layers helps protect hardware and system resources.

## Komendy / pliki / składnia występujące w materiale

```text
SS The Linux Kernel Archi
chmod +x VBoxLinuxAdditions.run
sh ./VBoxLinuxAdditions.run
apt install Linux-headers-$(uname-r)
```

## Notatki z zajęć (PadRiseup)

- `Linux Security`
- `Ch1 & Ch2 - Intro to Linux & CLI Fundamentals`
- https://github.com/torvalds/linux
- `Przykładowe distro Linux red teamingowe:`
- `chmod +x VBoxLinuxAdditions.run`
- `sh ./VBoxLinuxAdditions.run`
- `linux manual pages - help https://linux.die.net/man/`
- `#Podstawowe komendy Linuxa:`
- https://pixelozaa.wordpress.com/podstawowe-komendy-linuxa/
- `apt install Linux-headers-$(uname-r)`
- https://arstechnica.com/gadgets/2021/08/linux-bsd-command-line-101-using-awk-sed-and-

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 6:** | Chapter 1: Introduction to Linux

Section 1: Linux History

Linux is a family of operating systems (OS) intended to provide a UNIX-like experience.

Linux uses the GNU General Public License version 2 (GPLv2), in contrast to UNIX, which

has a proprietary license.

Linux was created in the early 1990s by Finnish student Linus Torvalds as a private

project that began with the development of the Linux kernel.

Linux primarily uses a terminal (CLI), and most Linux distributions have a graphical user

interface (GUI) as well, which makes the environment more user friendly. It is important

to remember that Linux itself is only the kernel, which manages communication

between applications and hardware.

Linux Vs. Windows

Some points of comparison between Linux and MS Windows include:

e Windows is a closed-source system, Linux is an open-source system.

e Windows is purchased, Linux is mostly free.

e Windows is not customizable, Linux is highly customizable.

Many Linux distributions include GUI systems, GNU utilities, installation and

management tools, and various applications, such as OpenOffice, Firefox, and others.

Linux also comes with the open-source Netfilter, an iptables-based firewall tool.

© | Good to Know

) As the course continues, you will become familiar with iptables, its purpose,

and how to use it.

Some Linux distributions require additional applications to create a complete and

usable OS. Most Linux systems, however, are considered complete operating systems,

and come with A-Z programs, such as an editor, compilers, etc.

**Textbook s. 7:** Linux is considered one of the most user-friendly UNIX-like operating systems.

Installation of sound cards, flash players, and other desktop applications and software is

simple and straightforward. The fact that it is an open-source software enables many

organizations to create customized Linux distributions.

Linux Kernel

Today there are many distributions based on the Linux kernel, and most are free.

Due to its scalability, Linux-based operating systems can be used for a variety of

products, ranging from wristwatches and refrigerators to supercomputers.

Although the applications and use cases of each OS will be different, the kernel is the

same in all of them, with only slight changes in each distribution. The kernel establishes

communication between the hardware and software components, and manages the

system’s resources.

APPLICATION

SHELL

Linux Kernel

Linux OS is composed mainly of the layers shown above, which provide crucial

separation for stable functionality and data security. The kernel is an abstraction layer

that serves as a buffer between users/apps and hardware. Separating those elements

prevents an application or user from obtaining access to the hardware, and damaging

the system.

**Textbook s. 8:** Due to the layered architecture, applications cannot directly access the hardware

without the right permissions. Applications that require access to hardware resources

will have to communicate with them through the kernel.

The kernel has four primary responsibilities:

1. Hardware management

2. Memory management

3. Process management

4. System call management

Hardware Management

Systems can include a variety of hardware components, such as CPUs, memory devices,

sound cards, graphics cards, etc. The kernel stores all data related to the device drivers

and how to interact with them. Without a kernel, the components could not be

controlled.

Memory Management

The kernel is responsible for OS memory management. It keeps track of memory usage

for the purpose of enhancing performance, and uses virtual memory addresses to

ensure that one process does not manipulate the data of another process.

Process Management

The kernel assigns resources to individual processes and prioritizes them. It also

manages process security and ownership information.

Handling System Calls

The kernel can receive requests from programs to perform certain tasks.

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 4:** Introduction to Linux

Linux History

**Slides s. 5:** (Th Linux History

rs e Started as a private project by Linus Torvalds.

: e Evolved from UNIX.

e The OS developed as an open-source system.

Q\ =

**Slides s. 6:** Cw Linux History

e

e UNIX alternative.

e Supports all hardware types.

e Linux is a family of OS’s.

e Many home-based loT devices use Linux.

**Slides s. 7:** Linux History

L_J

SS The Linux Kernel Archi

€ LINUX Kernel Archives

ze omer

Linux is a kernel, which is

the core of an operating iit 2 me (ew

bi S.221(EOL] 2019-10-11 [rarbali) [pgp] [patch] [in ch) (view diff] [browse] [chan: 1

system. tongterm 41929, 20D 10M1 Lortll fp fat nc patel sew ait] browse {hangelol

longterm: 414.149 2019-10-11 [tarball] [pgp] [patch] [inc. patch} [view diff] [browse] [changelog)

longterm 49.196 2099-10-07 [tarball] [pgp] [patch Linc. patch] [view diff] [browse} [changetog)

longterm 4.4196 2019-10-07 [tarball] [pgpl [patchl Linc. patch] [view diff] [browse] [changelog]

H longterr 316.75 2019-10-05 [tarball] [pgp] [patchy Linc. patch] [view ditf] [browse} [changelog]

The kernel establishes a ee me a Ee

communication

Other resources Social

between software and

hardware. as esis pene ag =

Ome” packet fastly Google

[Vv] CONSTELLIX ( Carrevaie:

me

**Slides s. 8:** Linux History

(The Kernel’s Responsibilities

.

e Device management

e Memory management

(®) e Process management

e Handling system calls

**Slides s. 9:** (Lir Linux History

APPLICATION |

The Linux OS consists of SHELL |

several layers. |

The kernel is an |

abstraction layer that

acts as an intermediary

between users and |

apps, and the |

hardware. |

The architecture |

provides system data |

and functionality |

protection. |

9

**Slides s. 10:** (Lir Linux History

S

= Linux Windows

Open-source OS | | Closed-source OS |

Has multiple branches and versions HesiTew Supperted Yersions (7, 8. 10,11)

and corresponding server versions

Free to use | PV | Pay to use |

Highly customizable | | Minimal customization |

Supports a large variety of hardware | | Mainly for PCs and servers |

10

</details>
