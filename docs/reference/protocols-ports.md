# Protocols & Ports

[← Indeks wiki](../index.md)

| Protokół/usługa | Port / transport podany w materiale | Uwagi |
|---|---:|---|
| SSH | 22 | szyfrowany zdalny dostęp; SCP i SFTP wykorzystują SSH |
| SCP | 22 | transfer plików przez SSH |
| SFTP | 22 | bezpieczny transfer w kanale SSH |
| FTP control | 21 | nieszyfrowany kanał sterujący |
| FTP data | 20 | kanał danych wg textbooka |
| SMB over NetBIOS | 139 | starszy wariant SMB |
| SMB over TCP | 445 | nowszy bezpośredni wariant TCP |
| HTTP | 80 | Apache domyślnie w materiale |
| HTTPS | 443 | HTTP chroniony TLS |
| Telnet | standardowa usługa zdalnego terminala | materiał projektowy podkreśla brak szyfrowania |

## Bezpieczeństwo

- FTP i Telnet są traktowane jako przykłady protokołów niechroniących odpowiednio danych uwierzytelniających.
- SSH/SCP/SFTP chronią sesję szyfrowaniem.
- HTTPS wymaga konfiguracji certyfikatu/klucza po stronie serwera.
- SMB/Samba wymaga kontroli uprawnień i ekspozycji udziałów.
