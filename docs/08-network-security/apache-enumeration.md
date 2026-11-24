# Detecting / Countering Apache Enumeration

[← 08 · Network Security](index.md)  ·  [🏠 Wiki](../index.md)

> **Źródła:** Linux Security Textbook.pdf, s. 140–142; Linux Security.pdf, s. 324–328.

## Mapa wiedzy

- Web enumeration probes for directories/pages and often produces repeated 404 responses. The course links server logs to detection of scanning behavior.
- `curl` and `wget` are used to request/download web content; Bash pipelines extract IPs and response codes from logs.
- The objective is to identify enumeration patterns and feed that information into blocking/hardening decisions.

## Komendy / pliki / składnia występujące w materiale

```text
Wget is a tool created by the GNU project to retrieve files from web servers. It is an
Wget is a non-interactive tool, which means that the user does not have to be logged in
Wget has the capacity to pause and resume downloads, whether manually by the user
Curl stands for client URL and is used to transfer data to, or from a server with URL
curl https ‘www . facebook. com,
Curl enables multiple page requests in the same command, using brackets. For
FTP server, you can use the following syntax: ftp://ftp. yourserver.com/file[1-50].txt.
Curl can display a detailed progress meter of the download or upload using the -o
Curl syntax varies depending on the protocol in use:
Bash Scripting to Counter
Curl supports numerous protocols, such as FTP,
Bash Scripting to Counter Apache Enumeration
wget https://archive.kali.org/archive-key.asc
cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips
curl -v http://localhost
```

## Notatki z zajęć (PadRiseup)

- `wget https://archive.kali.org/archive-key.asc`
- `cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips`
- `curl -v http://localhost`

Pełny zapis zajęć: [Class Notes](../reference/class-notes.md).

## Powiązane laboratoria

- [LNX-08-L2 — Summary Exercise](../labs/lnx-08-l2.md)

## Powiązane strony

- [Indeks działu](index.md)
- [Command Reference](../reference/commands.md)
- [Files & Directories](../reference/files-directories.md)
- [Hardening Checklist](../reference/hardening-checklist.md)

<details>
<summary>Pełne notatki źródłowe — textbook (OCR, strona po stronie)</summary>

**Textbook s. 140:** Section 5: Bash Scripting to Counter Apache Enumeration

Enumeration is the process of establishing an active connection to a system and

extracting information that can be exploited later. The information can include user

names, machine names and addresses, kernel or installed application versions, network

interfaces and resources, and even running services. Information gathered can later be

used to identify vulnerabilities to achieve privilege escalation or lateral movement in

the network.

Enumeration is a crucial step in penetration testing. It can directly affect the outcome of

a penetration test (pentest) since the more information gathered about a target, the

more potential attack vectors will be available for exploitation.

There are different types of information that can be enumerated by an attacker or a

pentester, and various tools that acquire specific types of information.

Examples of enumeration tools include:

Nmap: Scans a network and looks for hosts, the OS version, and open ports.

Nikto: A scanner for web servers that looks for server versions and potentially

dangerous files and HTTP methods.

DirBuster, Gobuster & Dirsearch: Applications that enumerate directories and file

names on web application servers.

WPScan: WordPress vulnerability scanner.

Dnsenum: A script written in Perl to enumerate DNS information on a domain.

All-in-one (AIO) or “smart” tools were developed to enumerate several types of

information in one convenient interface.

Wget is a tool created by the GNU project to retrieve files from web servers. It is an

amalgamation of World Wide Web and get. The tool can download files from FTP and

SFTP, HTTP, and HTTPS servers. If not specified, Wget will download to the directory the

user is currently in.

**Textbook s. 141:** Wget is a non-interactive tool, which means that the user does not have to be logged in

to the server to download files. Files can download in the background without requiring

a user to be logged in to the system. Wget can recursively download entire websites

(excluding pages listed in the Robots.txt file, unless otherwise defined), while keeping

the original structure of the site and creating a local copy of the website.

Wget has the capacity to pause and resume downloads, whether manually by the user

or automatically due to an unresponsive server, in which case Wget will automatically

resume the download once the server responds.

The W¢et syntax is wget [option] [URL].

Examples of Wget options include:

fe Lists all available options.

Allows downloads in the

background.

-o [path] Overwrites an existing file.

«| Resumes download.

-i [file name] Looks for URLs in a file.

mo Mirrors an entire website.

Curl stands for client URL and is used to transfer data to, or from a server with URL

syntax. Curl supports a variety of protocols, and doesn’t require user interaction. It can

run from a CLI, as well as in a script.

The -o option must be used in the curl command, followed by a file name, to save the

output to a file; otherwise, the requested web page will be download and displayed in

the terminal window: curl -o facebook_login.txt https://www.facebook.com/

**Textbook s. 142:** johnd@debian: ~ x

File Edit View Search Terminal Help

$ curl https ‘www . facebook. com,

<!DOCTYPE html> |

<html lang="he" id="facebook" class="no_js">

<head><meta charset="utf-8" /><meta name="referrer" content="default" id="meta_r

eferrer" /><script>window. cstart=+new Date();</script><script>function envFlush

(a){function b(b){for(var c in a)b[c]=alc] }window. requireLazy?window. requireLazy

(["Env"],b) : (window. Env=window.Env| |{},b(window.Env) )}envFlush({"ajaxpipe token"

"AXhQkPu-zhQIFONj","timeslice heartbeat_config":{"pollIntervalMs":33,"idleGapTh

resholdMs" :60, "ignoredTimesliceNames" :{"requestAnimationFrame":true, "Event liste

nHandler mousemove":true,"Event listenHandler mouseover": true, "Event ListenHandl

er mouseout":true,"Event listenHandler scroll":true},"isHeartbeatEnabled": true,"

isArtilleryon": false}, "shouldLogCounters":true, "timeslice categories”:{"react_re

nder":true,"reflow":true}, "sample continuation stacktraces":true, "dom mutation f

lag":true,"stack trace limit":30,"deferred stack trace rate":1000,"timesliceBuff

erSize":5000,"show invariant decoder": false,"compat_iframe_token":"AQ4chP4 7VXJL

82p", "isCQuick": false}) ;</script><style></style><script> DEV =0;CavalryLogger=

window. CavalryLogger| | function(a){this. lid=a, this .transition=!1, this.metric coll

Curl enables multiple page requests in the same command, using brackets. For

example: https://yoursite.{abc,def,ghi}.com. Or, if you are downloading files from an

FTP server, you can use the following syntax: ftp://ftp. yourserver.com/file[1-50].txt.

Nesting is not supported, but several brackets can be used in the same command:

http://yoursite.com/archive[2000-2019]/vol[1-15]/part{a,b,c}.html

Curl can display a detailed progress meter of the download or upload using the -o

option. The information it displays includes data transferred, transfer speed, and

estimated time.

Curl syntax varies depending on the protocol in use:

Syntax Meaning

-a (uses FTP, SFTP when uploading) Appends to a file instead of overwriting it

--basic (basic HTTP authentication) Downloads in the background

-o [file name] (HTTP, HTTPS, FTP, SFTP) _| Outputs to a file

-C [offset] Resumes download from a given offset

-D [filename] (HTTP, FTP) Dumps headers to a file

-E <certificate[:password]> Tells curl to use a specific certificate file

</details>

<details>
<summary>Pełne notatki źródłowe — slajdy (OCR, slajd po slajdzie)</summary>

**Slides s. 324:** Network Security

Bash Scripting to Counter

Apache Enumeration

**Slides s. 325:** (Di Bash Scripting to Counter Apache Enumeration

@ Enumeration means scanning for directories

and web service pages.

@ The 404 HTTP response code means a page was

not found.

@ The 200 HTTP response code means a successful

HTTP request.

@ Logs are saved in various Apache log files.

Enumeration is a method of discovering

potential attack vectors.

= .

**Slides s. 326:** (Cu Bash Scripting to Counter Apache Enumeration

C) N

@ Weet is a command that downloads

a content from a remote server.

= ® It can download content recursively.

® Curl is a library that has upload and send

capabilities.

@ Flexible interface used as a debugging tool.

Curl supports numerous protocols, such as FTP,

HTTP, SCP, Telnet, LDAP, POP3, SMTP, and others.

Lp

**Slides s. 327:** (Wi Bash Scripting to Counter Apache Enumeration

The username does not exist. toa

(ex O) | Password is incorrect.

ic)

An email was sent to reset the password. 7™

aa

**Slides s. 328:** Bash Scripting to Counter Apache Enumeration

)

© or nan 881 an poranet -q . Dirbuster

CT ~

Work Method © Use GET requests only @ Auto Switch (HEAD and GET)

Number Of Threads l-———_ 10 Threads [_|Go Faster

Select scanning type: list based brute force © Pure Erute Foree

(Geerono] Nikto

charset [Hee Min lent vexteneth [>]

Select starting options: @ Standard start point. § URL Fuzz

[Brute Force Dirs @ Be Recursive Dir to start with

[ipnute Force Files [use Blank Extension File extension [php

Beat

Please complete the test detalls D i rb

</details>
