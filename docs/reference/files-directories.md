# Files & Directories Reference

[← Indeks wiki](../index.md)

| Path | Znaczenie w materiale |
|---|---|
| `/` | korzeń całego drzewa systemu plików |
| `/root` | katalog domowy superusera |
| `/boot` | pliki związane z uruchamianiem systemu / kernel / GRUB |
| `/etc` | globalne pliki konfiguracyjne systemu i usług |
| `/home` | katalogi domowe zwykłych użytkowników |
| `/mnt` | ręczne/tymczasowe punkty montowania |
| `/media` | typowe automatyczne montowanie nośników wymiennych |
| `/bin` | podstawowe binaria dostępne użytkownikom |
| `/sbin` | narzędzia systemowe/administracyjne |
| `/usr` | programy, biblioteki i dane użytkowe; m.in. `/usr/bin`, `/usr/sbin` |
| `/lib` | biblioteki |
| `/dev` | pliki urządzeń |
| `/tmp` | dane tymczasowe |
| `/var` | dane zmienne, logi, dane usług |
| `/var/log` | logi systemowe/usług |
| `/var/www` | dane serwera WWW w typowej konfiguracji Apache |
| `/proc` | wirtualne informacje o procesach/systemie |
| `/sys` | informacje/interfejs do kernela i urządzeń |

## Pliki konfiguracyjne używane w kursie

- `/etc/passwd` — konta użytkowników.
- `/etc/shadow` — chronione dane haseł.
- `/etc/group` — grupy.
- `/etc/network/interfaces` — konfiguracja sieci.
- `/etc/resolv.conf` — resolver/DNS.
- `/etc/apt/sources.list` — źródła APT.
- `/etc/ssh/sshd_config` — konfiguracja serwera SSH.
- `/etc/ssh/ssh_config` — konfiguracja klienta SSH.
- `/etc/vsftpd.conf` — vsftpd.
- `/etc/samba/` — Samba.
- `/etc/apache2/` — Apache.
- `/etc/grub.d/00_header` — element konfiguracji GRUB używany w labie.
- `/etc/pam.d/` — polityki PAM.
- `~/.bashrc` — konfiguracja powłoki użytkownika / aliasy.
