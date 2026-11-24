# Linux Hardening Checklist — z materiału kursowego

[← Indeks wiki](../index.md)

- [ ] Aktualizuj repozytoria i pakiety (`apt update`, `apt upgrade`).
- [ ] Instaluj tylko potrzebne usługi i sprawdzaj porty nasłuchujące (`ss`, `netstat`, `lsof`).
- [ ] Ogranicz używanie root; używaj sudo/least privilege.
- [ ] Wymuszaj silne hasła przez PAM/pwquality i kontroluj historię/reuse.
- [ ] Audytuj użytkowników, grupy, sudoers i `/etc/shadow`.
- [ ] Ustaw poprawne ownership i permissions; unikaj `777` bez potrzeby.
- [ ] Audytuj SUID/SGID i skrypty uruchamiane z wysokimi uprawnieniami.
- [ ] Używaj bezpiecznego PATH i bezwzględnych ścieżek w skryptach uprzywilejowanych.
- [ ] Zabezpiecz GRUB i rozważ pełne szyfrowanie LUKS.
- [ ] Stosuj PAM, SELinux/AppArmor tam, gdzie są dostępne.
- [ ] Dla SSH ogranicz dostęp, preferuj klucze, ogranicz root/login i minimalizuj banner.
- [ ] Nie używaj Telnet/FTP do poufnych danych; preferuj SSH/SFTP/FTPS.
- [ ] Zabezpiecz Samba/FTP i wyłącz niepotrzebne możliwości.
- [ ] Stosuj firewall (iptables/firewalld), najlepiej allow-list dla usług administracyjnych.
- [ ] Używaj Fail2Ban do reakcji na powtarzające się nieudane próby.
- [ ] Monitoruj logi i agreguj wskaźniki (np. liczne 404 z jednego IP).
- [ ] Zabezpiecz Apache: ogranicz metody, ukryj wersje/banner, TLS, ModSecurity/OWASP CRS.
- [ ] Używaj monitoringu integralności dla krytycznych plików.
- [ ] Zabezpiecz cron: zaufane skrypty, właściwe ownership/permissions, absolutne ścieżki.
- [ ] Kontroluj montowanie nośników zewnętrznych.
