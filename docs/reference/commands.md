# Command Reference

[← Indeks wiki](../index.md)

To jest indeks poleceń występujących w textbooku, slajdach, labach, projekcie i PadRiseup. Składnia jest zachowana w stylu materiału kursowego.

## System / orientacja

```bash
whoami
pwd
uname
uname -r
env
history
man <command>
<command> --help
whatis <command>
whereis <command>
which <command>
```

## Nawigacja i pliki

```bash
cd /path
cd ..
cd .
cd ~
cd -
ls
ls -l
ls -la
touch file
mkdir dir
rm file
rm -r dir
rm -f file
rmdir dir
cp source destination
mv source destination
cat file
more file
less file
head -n 3 file
tail -n 1 file
```

## Wyszukiwanie / tekst / potoki

```bash
grep pattern file
grep -in Fire /var/log/dpkg.log --color
grep -v root
find / -name '*.sh' 2>/dev/null
locate <name>
sort
cut -f 1 -d ':'
awk '{print $1" "$9}'
sed 's/://g'
uniq -c
command1 | command2
command > file
command >> file
```

## Edytory

```bash
nano file
vim file
gedit file
```

## Użytkownicy / grupy / uprawnienia

```bash
adduser <user>
useradd <user>
deluser <user>
passwd <user>
usermod -aG <group> <user>
groups
id <user>
gpasswd
gpasswd -d <user> <group>
chown user:group file
chmod 640 file
chmod 644 file
chmod 755 file
chmod 777 file
visudo
sudo whoami
sudo su
```

## PATH / shell

```bash
export PATH=/usr/sbin:$PATH
source ~/.bashrc
chmod +x script.sh
./script.sh
```

## APT / pakiety

```bash
apt update
apt upgrade
apt update && apt upgrade
apt install <package>
apt purge <package>
wget <URL>
```

## Sieć

```bash
ping <IP>
ping -c 1 <IP>
traceroute <IP>
ip address
ip route show
ip addr del 10.0.2.15/24 dev enp0s3
ifconfig
route
dhclient
nslookup <name-or-IP>
netstat -tulpn
ss
lsof
lsof -i :80
curl -v http://localhost
nc -nlvp 9001
```

## Usługi / systemd

```bash
systemctl status <service>
systemctl start <service>
systemctl restart <service>
systemctl reboot
systemctl poweroff
service <service> start
/etc/init.d/networking stop
/etc/init.d/networking start
```

## SSH / SCP / SFTP

```bash
apt install openssh-server
ssh user@IP
ssh user@IP -p PORT
scp ./file user@IP:/path
sftp user@IP
```

## FTP / Samba

```bash
apt install vsftpd
systemctl restart vsftpd.service
ftp <IP>
put file
delete file
apt install samba
systemctl restart samba
net use
```

## Apache / Nginx

```bash
apt install apache2
systemctl status apache2
systemctl restart apache2
apt install nginx
curl -v http://localhost
```

## Bash / backup / integrity

```bash
#!/bin/bash
date '+%Y-%m-%d'
date '+%d-%m-%Y'
tar -czvf archive.tar.gz <path>
md5sum file > hashfile
cmp --silent hash1 hash2
sleep 2
```

## Cron

```bash
crontab -e
crontab -l
```

## Host security

```bash
password_pbkdf2 admin
update-grub
apt install cracklib-runtime
apt install libpam-pwquality
vim /etc/pam.d/common-password
vim /etc/pam.d/sshd
sysctl fs.protected_regular=1
```

## Firewall / web hardening

```bash
iptables -L -n
iptables -A INPUT -p tcp --dport 22 --source <trusted_IP> -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
apt install libapache2-mod-security2
a2enmod ssl
a2enmod headers
a2ensite default-ssl
```

## Konfiguracje / ścieżki używane na zajęciach

```text
/etc/ssh/sshd_config
/etc/ssh/ssh_config
/etc/network/interfaces
/etc/resolv.conf
/etc/apt/sources.list
/etc/vsftpd.conf
/etc/samba/
/etc/apache2/
/etc/apache2/conf-available/security.conf
/etc/apache2/sites-available/000-default.conf
/etc/apache2/sites-available/default-ssl.conf
/etc/grub.d/00_header
/etc/pam.d/common-password
/etc/pam.d/sshd
/var/log/
/var/www/html/index.html
```
