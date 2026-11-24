# LNX-08-L4 — SSL Encryption

[← Wszystkie laboratoria](index.md)

> **Źródło:** Linux Security Zadania - odpowiedzi.pdf, strony PDF 513–529.

## Cel, misja i środowisko

- G Lab Objective Learn about SSL and how it can be used to encrypt HTTP communication to and froma web server. bs Lab Mission
- bs Lab Mission Generate an SSL certificate for the Apache web server, and configure Apache to use SSL. ea . © Lab Duration
- © Lab Duration 20-25 minutes tC) Requirements e Working knowledge of the SSH and Apache services
- tC) Requirements e Working knowledge of the SSH and Apache services oo | Resources
- | Resources e¢ Environment & Tools o VirtualBox = Debian

## Zadania / etapy

1. Lab Task 1: Generate an SSL Key and Configure Apache to use HTTPS Communication Use the openssl! and apache2 commands to configure encrypted connections to the web server.
2. Lab Task 1: Generate an SSL Key and Configure Apache to use HTTPS Communication Use the openssl and apache2 commands to configure encrypted connections to the web server.

## Komendy występujące w labie

```text
nano /etc/apache2/conf-available/ssl.conf.
Redirect "/" https://Debian/.
a2enmod ssl && a2enmod headers.
a2ensite default-ssl.
openssl req -x5@9 -nodes -days 365 -newkey rsa:2048 -keyout /etc/
ff
nano /etc/apache2/sites-available/default-ssl.conf
Redirect "/" "https://Debian/™
systemctl restart apache2
J
systemctl reload apache2
apache2ctl configtest
apt install wireshark.
```

## Powiązana teoria

- [Ssl Tls](../08-network-security/ssl-tls.md)

<details>
<summary>Pełne notatki źródłowe z kolejnych stron (pomocniczy OCR)</summary>

**PDF s. 513:** Linux Security

Lab Assignment Network Security

LNX-08-L4

o at SSL Encryption

Oln

ES

All Rights Reserved.

**PDF s. 514:** Linux Security

Lab Assignment Network Security

LNX-08-L4

o at SSL Encryption

Oln

ES

All Rights Reserved.

**PDF s. 515:** G Lab Objective

Learn about SSL and how it can be used to encrypt HTTP communication to and froma

web server.

bs Lab Mission

Generate an SSL certificate for the Apache web server, and configure Apache to use SSL.

ea .

© Lab Duration

20-25 minutes

tC) Requirements

e Working knowledge of the SSH and Apache services

oo

| Resources

e¢ Environment & Tools

o VirtualBox

= Debian

o Openssl

o Apache

**PDF s. 516:** Lab Task 1: Generate an SSL Key and Configure Apache to

use HTTPS Communication

Use the openssl! and apache2 commands to configure encrypted connections to the

web server.

1 Loginto the Debian VM and switch to the root user by running su -.

Use the following openss! command to generate a self-signed key:

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout

/etc/ssl/private/apache-selfsigned.key -out

/etc/ssl/certs/apache_selfsigned.crt.

Make sure to fill in the prompts correctly. The most important line requests the

Common Name (server FQDN or YOUR name). You need to enter Debian as the

domain.

Note: you should fill in the details that suit you, and the common name should be

localhost.

2. Tocause Apache to use SSL, use Nano to create a new file under

/etc/apache2/conf-available/ named ssl.conf. Use the following command:

nano /etc/apache2/conf-available/ssl.conf.

3 Paste the following SSL configuration in the file:

SSLCipherSuite EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH

SSLProtocol All -SSLv2 -SSLv3 -TLSv1 -TLSv1.1

SSLHonorCipherOrder On

# Disable preloading HSTS for now. You can use the commented out header line

that includes

# the "preload" directive if you understand the implications.

# Header always set Strict-Transport-Security

"maxage=63072000;includeSubDomains; #preload"

Header always set X-Frame-Options DENY

Header always set X-Content-Type-Options nosniff

# Requires Apache >= 2.4

SSLCompression off

SSLUseStapling on

**PDF s. 517:** SSLStaplingCache "shmcb:logs/stapling-cache(150000)"

# Requires Apache >= 2.4.11

SSLSessionTickets Off

4 Using Nano, open the file /etc/apache2/sites-available/default-ssl.conf, and run

the following:

5 Add the following line below webmaster@localhost: ServerName Debian.

6 Change the path of the line SSLCertificateKeyFile to

/etc/ssl/private/apache-selfsigned.key, and change the path of the line

SSLCertificateFile to /etc/ssl/certs/apache_selfsigned.crt.

These lines redirect the certificate and the key so that Apache will know where

they are.

7 Tell the server to redirect HTTP to the server to use HTTPS instead by editing the

following file with Nano:

/etc/apache2/sites-available/000-default.conf.

In the file, in VirtualHost configuration blocks, add a redirect instruction that

sends all traffic to the SSL version of the site by adding the following line:

Redirect "/" https://Debian/.

Note: https://Debian can be used because we are the only users that access that

website and its localhost. We would work with FQDN or the external domain

name for other users.

8 Use the following command to activate SSL and the headers:

a2enmod ssl && a2enmod headers.

9 Use the following command to enable default-ss/:

a2ensite default-ssl.

10 Use the following command to execute the configuration file:

a2enconf ssl.

11. Check your configuration with the command apache2ctl configtest (Syntax OK

means the command is correct).

Restart the Apache service with systemctl restart apache2.

**PDF s. 518:** 12 Test the encryption. From your Debian machine, open the browser and type

https://Debian.

Note: Because we created a certificate that was not signed by one of the

browser's trusted certificate authorities (CA), you will see the following warning:

Click Advanced and then click Accept the Risk and Continue.

You should see a lock icon in the URL.

**PDF s. 519:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS4

o at SSL Encryption

oln

ES

All Rights Reserved.

**PDF s. 520:** Linux Security

Lab Assignment Network Security

& Solution

LNX-08-LS4

o at SSL Encryption

oln

ES

All Rights Reserved.

**PDF s. 521:** Note: Solutions for the instructor are shown inside the green box.

G Lab Objective

Learn about SSL and how it can be used to encrypt HTTP communication to and froma

web server.

2 Lab Mission

Generate an SSL certificate for the Apache web server, and configure Apache to use SSL.

of :

@ Lab Duration

20-25 minutes

fe Requirements

e Working knowledge of the SSH and Apache services

Lt

| Resources

e Environment & Tools

o VirtualBox

=" Debian

o Openssl

o Apache

**PDF s. 522:** Lab Task 1: Generate an SSL Key and Configure Apache to

use HTTPS Communication

Use the openssl and apache2 commands to configure encrypted connections to the

web server.

1 Login to the Debian VM and switch to the root user by running su -.

Use the following openss! command to generate a self-signed key:

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout

/etc/ssl/private/apache-selfsigned.key -out

/etc/ssl/certs/apache_selfsigned.crt.

root@debian:~# openssl req -x5@9 -nodes -days 365 -newkey rsa:2048 -keyout /etc/

ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache selfsigned.crt

Generating a RSA private key

Make sure to fill in the prompts correctly. The most important line requests the

Common Name (server FQDN or YOUR name). You need to enter Debian as the

domain.

writing new private key to '/etc/ssl/private/apache-selfsigned.key’

into your certificate request.

What you are about to enter is what is called a Distinguished Name or a DN

There are quite a few fields but you can leave some blank

For some fields there will be a default value,

If you enter ', the field will be left blank

Fauntry Name (2 letter code) [AU]:US

State or Province Name (full name) [Some-State]:Florida-State

Locality Name (eg, city) []:Miami

Organization Name (eg, company) [Internet Widgits Pty Ltd]:Party-Time Ltd

Organizational Unit Name (eg, section) []:IT

Common Name (e.g. server FQDN or YOUR name) []:Debian

Email Address []:example@example.com

root@debian:/home/debian# ff

Note: you should fill in the details that suit you, and the common name should be

localhost.

**PDF s. 523:** 2. Tocause Apache to use SSL, use Nano to create a new file under

/etc/apache2/conf-available/ named ssl.conf. Use the following command:

nano /etc/apache2/conf-available/ssl.conf.

3 Paste the following SSL configuration in the file:

SSLCipherSuite EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH

SSLProtocol All -SSLv2 -SSLv3 -TLSv1 -TLSv1.1

SSLHonorCipherOrder On

# Disable preloading HSTS for now. You can use the commented out header line

that includes

# the "preload" directive if you understand the implications.

# Header always set Strict-Transport-Security

"maxage=63072000;includeSubDomains; #preload"

Header always set X-Frame-Options DENY

Header always set X-Content-Type-Options nosniff

# Requires Apache >= 2.4

SSLCompression off

SSLUseStapling on

SSLStaplingCache "shmcb:logs/stapling-cache(150000)"

# Requires Apache >= 2.4.11

SSLSessionTickets Off

Hstcir herSuite EECDH+AESGCM: EDH+AESGCM: AES256+EECDH: AES256+EDH

SSLProtocol ALL SSLv2 -SSLv3 -TLSv1 -TLSv1.1

5SLHonorCipherOrder On

Header always set X-Frame-Options DENY

Header always set X-Content-Type-Options nosniff

SSLCompression off

5SLUseStapling on

SSLStaplingCache “shmcb:logs/stapling-cache(150000)

SSLSessionTickets off

**PDF s. 524:** 4 Using Nano, open the file /etc/apache2/sites-available/default-ssl.conf, and run

the following:

root@debian:~# nano /etc/apache2/sites-available/default-ssl.conf

5 Add the following line below webmaster@localhost: ServerName Debian.

GNU nano 3.2 /etc/apache2/sites-available/default-ssl.conf Modified

<IfModule mod ssl.c>

<VirtualHost default :443>

ServerAdmin webmaster@localhost

DocumentRoot /var/www/htmL

6 Change the path of the line SSLCertificateKeyFile to

/etc/ssl/private/apache-selfsigned.key, and change the path of the line

SSLCertificateFile to /etc/ssl/certs/apache_selfsigned.crt.

GNU nano 3.2 /etc/apache2/sites-available/default-ssl.conf Modified

SSLEngine on

ssLCertificateFile /etc/ssl/certs/apache selfsigned.crt

ssLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key

These lines redirect the certificate and the key so that Apache will know where

they are.

**PDF s. 525:** 7 Tell the server to redirect HTTP to the server to use HTTPS instead by editing the

following file with Nano:

/etc/apache2/sites-available/000-default.conf.

In the file, in VirtualHost configuration blocks, add a redirect instruction that

sends all traffic to the SSL version of the site by adding the following line:

Redirect "/" https://Debian/.

GNU nano 3.2 fetc/apache2/sites-available/000-default.conf Modified

<VirtualHost *:80>

ServerAdmin webmaster@locaLlhost

DocumentRoot /var/www/htmL

Redirect "/" "https://Debian/™

Note: https://Debian can be used because we are the only users that access that

website and its localhost. We would work with FQDN or the external domain

name for other users.

**PDF s. 526:** 8 Use the following command to activate SSL and the headers:

a2enmod ssl && a2enmod headers.

Considering dependency setenvif for ssl:

Module setenvif already enabled

Considering dependency mime for ssl

Module mime already enabled

Considering dependency socache shmcb for ssl:

Enabling module socache shmcb

Enabling module ssl

See /usr/share/doc/apache2/README .Debian.gz on how to configure SSL and create self

-signed certificates

To activate the new configuration, you need to run

systemctl restart apache2

Enabling module headers

To activate the new configuration, you need to run:

systemctl restart apache2

root@debian:~# J

9 Use the following command to enable default-ss/:

a2ensite default-ssl.

Enabling site default-ssl

To activate the new configuration, you need to run

systemctl reload apache2

root@debian:~#

10 Use the following command to execute the configuration file:

a2enconf ssl.

rootadebian:=# azencont 331]

Enabling cont ssl.

To activate the new configuration, you need to run

systemctl reload apache2

root@debian:~#

11. Check your configuration with the command apache2ctl configtest (Syntax OK

means the command is correct).

Restart the Apache service with systemctl restart apache2.

root@debian:~# apache2ctl configtest

AHOO558: apache2: Could not reliably determine the server's fully qualified domain nam}

e, using 127.0.1.1. Set the 'ServerName' directive globally to suppress this message

root@debian:~# ff

root@debian:~# systemctl reload apache2

root@debian:~#

**PDF s. 527:** 12 Test the encryption. From your Debian machine, open the browser and type

https://Debian.

Note: Because we created a certificate that was not signed by one of the

browser's trusted certificate authorities (CA), you will see the following warning:

ET

Warning: Potential Security Risk Ahead

Firefox detected a potential security threat and did not continue to localhost. if you visit this

site, attackers could try to steal information like your passwords, emails, or credit card details.

Learn more

Report errors like this to help Mozilla identify and block malicious sites

Click Advanced and then click Accept the Risk and Continue.

**PDF s. 528:** Learn more...

locathostuses an invalid security certificate.

The certificate is not trusted because itis self-signed.

Error code: MOZILLA_PKIX_ERROR_SELF_SIGNED_CERT

View Certificate

Reporterrors like this to help Mozilla identify and block malicious sites

You should see a lock icon in the URL.

Apache2 Debian Default Ps: x | ++

€ Cc a @ & https://debian

( ) Apache2 Debian —

depian

It work:

**PDF s. 529:** If students want to surf to the website using their host machine (not Debian), do not

forget in the host file to add the IP address in the domain (Debian) configured in the

certificate.

If you have spare time, install Wireshark using the following command:

apt install wireshark.

Open Wireshark on the Debian machine, and start to listen to incoming traffic.

Open the browser on your host computer, and, after you change the host file to

recognize the Debian machine, surf to http://Debian.

The website will redirect you to https://Debian, and in Wireshark you can show

students that traffic between the machines is encrypted.

Activities Wireshark ~ Mon 21:33 env a O-

Wireshark - Follow TCP Stream (tcp.stream eq 0)- enpOs3 x

Ele TE iecaqeeeeen jrqccici=9 ue es x Glog Modes =

4@) iow

¥IO(. plana Wi ep SOU e pelea treme Beton. | +

g |..-0..-{W!..jZ.{..n.@.Cp..%u4-"{..... |

No. PG Ue anes Si eee vole (hone VOL ea (cee te OL. WM) ied lems = She Info ——_*

Ge Neh ice se cl oa UWecele ce Waals ‘AgGI

HO secs ctG: Niece. 2h aeWe , LOE Oe een iene 3

j |H;0. art |

| 8M..B. 443

‘ Hone sancnd LER nod and aac soit sled let naean aca he es ,

» fRietiea|s| LEB voce eeekeres eles eee ere ha nec ike. UUs cnjaerg nnd eem see ace 0

> Ethem@ |\.....2.]6.0....1...m.j".(.6 had (08:00

b REM teMma| erect ngechn Ooo Ws Giese atere cuca

» Trang] | “OQwS=8....B.r..'it.......seWING.....Do.Mi.sE Gee UNG | Len: ©

b:f QE cP CU. ceca | einer eee

BeBe OPV Aire Za AEM See esas nae hae e Ot auWe ceealeamlabGtain.

i Bo3o-4-H01-N1-€-R. -kg.-c.-x.. } ;

q | 2.-E1..".Vi.. sd... os. .E( MYi2 00 vues uses sPO*U. 728s tive }

@ B.NqL.,.i.\...5!:v...%...@}.k.

q =

2. 2client pkts, 2 server pkts, 3 turns.

Entire conversation (2,102 bytes) + | Showand save dataas ASCII ~ | Stream |O [>

Find: | Find Next |

()Help Filter Out This Stream Print Save as... Back Close |

OF y Pfile: Default

</details>
