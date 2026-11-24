# Class Notes — PadRiseup

[← Indeks wiki](../index.md)

> Materiał techniczny z `PadRiseup.pdf`, uporządkowany jako notatki z zajęć. Dane osobiste/logistyczne niezwiązane z wiedzą techniczną (np. prywatny numer telefonu) nie są publikowane w wersji repo.

1.10.2023

Ch1 & Ch2 - Intro to Linux & CLI Fundamentals

https://github.com/torvalds/linux

 #Do pobrania (linki z maila):

http://debian.uz/debian-cd/10.3.0/amd64/iso-cd/debian-10.3.0-amd64-netinst.iso

https://ubuntu.com/download/desktop

Przykładowe distro Linux red teamingowe:

https://www.kali.org/

https://blackarch.org/

https://www.parrotsec.org/

distro które powpstało z myślą zapewnienia zwiększonej anonimowości:

https://www.whonix.org/

https://tails.boum.org/
wyłączenie maszyny ex cli:

Systemctl poweroff

aktualizacja

apt update

instalacja guest additions:

chmod +x VBoxLinuxAdditions.run

sh ./VBoxLinuxAdditions.run

polska wersja dla debiana - jako ciekawostka:

https://itbiznes.pl/oprogramowanie/nowy-polski-gnome/

https://wiki.ubuntu.com/PolonizacjaUbuntu

oh my zsh https://ohmyz.sh/

linux manual pages - help https://linux.die.net/man/

znaki zachęty:



root
$ zwykły user

 #Podstawowe komendy Linuxa:

https://www.astrouw.edu.pl/~jskowron/pracownia/komendy/

https://pixelozaa.wordpress.com/podstawowe-komendy-linuxa/

apt install htop

debian sources list https://wiki.debian.org/SourcesList

apt update

apt install Linux-headers-$(uname-r)

cat /etc/ssh/ssh_config

vim tutorials

https://www.openvim.com/
https://www.freecodecamp.org/news/vim-beginners-guide/

https://danielmiessler.com/p/vim/

apt install gedit

grep sed awk

https://www.linode.com/docs/guides/differences-between-grep-sed-awk/

https://arstechnica.com/gadgets/2021/08/linux-bsd-command-line-101-using-awk-sed-and-
grep-in-the-terminal/

praca domowa - zapoznać się , zrobić kilka
poziomów https://overthewire.org/wargames/bandit/




14.10.2023

find / -name *.sh 2>/dev/null

grep -in Fire /var/log/dpkg.log --color

cat /etc/passwd | head -n3 | tail -n 1

cat /etc/passwd | cut -f 1 -d ':' > users

more /var/log/dpkg.log

less /var/log/dpkg.log

cat local_users.txt | sort > sorted_local_users.txt

cat sorted_local_users.txt | grep -v root

export PATH=/usr/sbin:$PATH

cp /etc/shadow

vim /etc/quality/pwquality.conf

for i in {5..7}; do deluser tempuser$i;done

chown root:adm /var/log/boot.log

usermod -aG adm piotr

export PATH=/usr/sbin:$PATH

usermod -aG adm piotr
chmod 640 /var/log/boot.log

chmod 644 /var/log/boot.log

chown root:root /var/log/boot.log

gpasswd

gpasswd

gpasswd -d piotr adm

ls -la /usr/bin/passwd

env

/home/[nazwa uzytkownika]/.bashrc

visudo

apt purge sudo

apt install sudo

sudo whoami

usermod -a -G sudo piotr

groups

export PATH=/usr/sbin:$PATH

sudo su

apt install firefox

sudo cat /etc/shadow

/etc/init.d/networking stop

/etc/init.d/networking start

sudo ip addr del 10.0.2.15/24 dev enp0s3

sudo apt install net-tools

sudo apt update

sudo apt upgrade
15.10.2023

deb https://http.kali.org/kali kali-rolling main non-free contrib

wget https://archive.kali.org/archive-key.asc

sudo apt-key add archive-key.asc

sudo rm kali.list

sudo apt update

sudo apt install apache2

systemctl status apache2

sudo vim ports.conf

sudo systemctl restart apache2

sudo apt install nginx

sudo netstat -tulpn

sudo apt install openssh-server

sudo netstat -tulpn

echo "testowy plik" > plikzubuntu.txt

scp ./plikzubuntu.txt [username]@[ip debiana]:/home/[user]/Desktop

sudo apt install samba

systemctl restart samba

net use

net use \192.168.1.68\tempuser /d

sudo apt install vsftpd

/etc/vsftpd.conf

systemctl restart vsftpd.service

ftp 192.168.1.68

put pliktubuntu.txt

delete plikzubuntu.txt
fail2ban

systemctl restart sshd

ssh Piotr@192.168.1.68 -p 4843

/etc/vsftpd.conf

listen_port=201

apt update && apt upgrade

import socket

socket.setdefaulttimeout(4)

target = input("Enter the IP address of the target: ")

while True:

  try:

     sock = socket.socket()

     port = input("Enter port to scan: ")

     try:

        val = int(port)
print(val)

     except:

         print("You have to choose number or exit")

         continue

     finally:

         if "exit" in port:

            break

     sock.connect((target, int(port)))

     ret = (sock.recv(16000).decode()).replace("\n","")

     print("For port: {} Service is: {}".format(port, ret))

     sock.close()

  except:
     print("Port {} is closed".format(port))

ping -c 1 192.168.1.69 | grep "bytes from" |cut -f 4 -d " " | sed 's/://g'

chmod +x ping_sweep.sh

./ping_sweep.sh

date '+%Y-%m-%d'

date '+%d-%m-%Y'

{ date '+%Y-%m-%d' }

chmod +x backup.sh

 1 #!/bin/bash

 2

 3 # To jest skrypt backupujacy katalog /home/piotr/Desktop do katalogu /tmp

 4 #Co chcemy backupowac

 5 backup_path="/home/piotr/Desktop"

 6

 7

 8 # Gdzie chcemy zapisac backup

 9 dest_path="/tmp"

10

11

12 # pozyskanie aktualnej daty

13 data=$(date '+%d-%m-%Y')

14

15 # tworzenie nazwy pliku z backupem

16 filename=${data}_backup

17

18 echo "Rozpoczynamy proces backupu"
 19 sleep 3

 20

 21 tar -czvf dest ath/filename $backup_path
                  p




 22

 23 echo "Zakonczono tworzenie backupu"

chmod +x backup.sh

#!/bin/bash


file=/var/www/html/index.html

hashpath=/tmp/wwwhash

temppath=/tmp/temphash



Stworz hash tymczasowy pliku index.html
echo "Tworze hash z pliku index.html"

md5sum $file > $temppath

sleep 2



Sprawdz czy dwa hashe temppath oraz hashpath
sa takie same?
echo "Porownuje ze soba oryginalny hash z nowostworzonym"

sleep 2

status="$(cmp --silent $hashpath $temppath; echo $?)"

if $status -ne 0; then

       echo "Hashe sie nie zgadzaja!"

else

       echo "Hashe sie zgadzaja!"

fi
28.10.2023

00_header

/etc/grub.d/00_header

set superusers="admin"

password_pbkdf2 admin

sudo update-grub

sudo apt install cracklib-runtime

sudo apt install libpam-pwquality

sudo apt update

sudo vim /etc/pam.d/common-password

echo "piotr" > /etc/ssh/sshd.allow

vim /etc./pam.d./sshd

vim /etc/pam.d/sshd

systemctl start ssh

sudo systemctl restart ssh

crontab -e

#!/bin/bash

me=$(whoami)

echo "It works as $me" > /tmp/crontabout.txt

crontab -e

crontab -l

nc -nlvp 9001

sudo sysctl fs.protected_regular=1

pfsense https://www.pfsense.org/

sudo iptables -L -n
sudo iptables -A INPUT -p tcp --dport 22 --source 192.168.1.69 -j ACCEPT

https://ln5.sync.com/dl/6590efdb0/5cqptub9-t7apvd3u-6987ncj3-
kc8gzasq/view/default/14531647630007?sync_id=11201546540007

cat logs | awk '{print $1" " $9}' | grep 404 | cut -d " " -f 1 | uniq -c > ips

cat ips | cut -d " " -f 1

curl -v http://localhost

sudo vim /etc/apache2/conf-available/security.conf

http://localhost/fdsafasdfas

sudo apt install libapache2-mod-security2

/etc/init.d/apache2 force-reload

mv modsecurity.conf-recommended modsecurity.conf

https://github.com/SpiderLabs/owasp-modsecurity-crs

https://github.com/coreruleset/coreruleset

sudo mv modsecurity-crs/ modsecurity-crs_bak

sudo apt install git

git clone https://github.com/SpiderLabs/owasp-modsecurity-crs

sudo mv owasp-modsecurity-crs/ modsecurity-crs

sudo mv crs-setup.conf.example crs-setup.conf

cd /etc/apache2/mods-enabled

sudo vim security2.conf

IncludeOptional /usr/share/modsecurity-crs/*.conf

IncludeOptional /usr/share/modsurity-crs/rules/*.conf

IncludeOptional /usr/share/modsecurity-crs/rules/*.conf

sudo vim /etc/apache2/sites-available/default-ssl.conf

SSLCertificateFile          /etc/ssl/certs/apache_selfsigned.crt

SSLCertificateKeyFile /etc/ssl/private/apache_selfsigned.key

sudo vim /etc/apache2/sites-available/000-default.conf
Redirect "/" "https://Debian/"

sudo a2enmod ssl

sudo a2enmod headers

sudo a2ensite default-ssl

https://github.com/rebootuser/LinEnum
