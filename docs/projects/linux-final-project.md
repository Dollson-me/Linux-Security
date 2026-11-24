# Linux Fundamentals — Final Project

[← Indeks wiki](../index.md)

> **Źródło:** `Linux Project .pdf` — 18 stron. Projekt łączy podstawową administrację Linux z siecią i bezpieczeństwem.

## Struktura projektu

1. **Basic Commands** — nawigacja, listowanie, operacje na plikach/katalogach i podstawowa praca z terminalem.
2. **The Find Command** — tworzenie pliku testowego i wyszukiwanie zasobów w systemie.
3. **User & Group Management** — konta, grupy i członkostwo.
4. **Permissions** — uprawnienia symboliczne/numeryczne, właściciel i grupa.
5. **Alias** — aliasy powłoki i `.bashrc`.
6. **System Update and APT Usage** — repozytoria, `apt update`, instalacja/aktualizacja pakietów.
7. **ifconfig / Address Settings** — konfiguracja i diagnostyka interfejsów/adresów.
8. **Remote Control and Telnet Services** — uruchomienie i obserwacja nieszyfrowanego zdalnego dostępu.
9. **SSH Connection** — uruchomienie SSH i bezpieczny zdalny dostęp.
10. **Apache Webserver** — konfiguracja serwera WWW.
11. **VSFTPD** — FTP; projekt pokazuje, że zwykły FTP ujawnia login i hasło w ruchu i wskazuje SFTP/FTPS jako bezpieczniejsze rozwiązania.
12. **Gzip** — archiwizacja/kompresja.
13. **Questions** — katalogi systemowe, encoding vs hashing vs encryption, SSH, kernel, komunikacja VM, ping, chmod, case sensitivity oraz pojęcia Telnet/SSH/cron/FTP/SFTP/gzip/tar/Bash/Apache.

## Najważniejsze komendy z projektu

```text
cd /  cd ..  cd .  cd ~  cd -
touch  mkdir  ls  cp  mv  rm
find
user/group management commands
chmod / chown
alias / ~/.bashrc
apt update / apt install / apt upgrade
ifconfig / ip
systemctl / service
telnet
ssh / scp
apache2
ftp / vsftpd
gzip / tar
```

## Bezpieczeństwo pokazane w projekcie

- Telnet i zwykły FTP są przykładami protokołów przesyłających dane bez odpowiedniej ochrony; SSH/SFTP zapewniają szyfrowaną alternatywę.
- `sshd_config` pozwala sterować portem, metodami uwierzytelniania i dostępem użytkowników/grup.
- Uprawnienia Linux są rozdzielone między owner/group/others, a zapis numeryczny sumuje `r=4`, `w=2`, `x=1`.
- Projekt łączy wiedzę o usługach, sieci i plikach konfiguracyjnych z diagnostyką ruchu i praktyką administracyjną.

## Powiązane strony

- [CLI](../02-cli/index.md)
- [Users & Permissions](../03-users-permissions/index.md)
- [Networking & System Management](../04-network-system/index.md)
- [Services & Hardening](../05-services-hardening/index.md)
- [SSH & SCP](../05-services-hardening/ssh-scp.md)
- [FTP & vsftpd](../05-services-hardening/ftp.md)
- [Bash](../06-bash/index.md)

<details>
<summary>Pełny tekst warstwy tekstowej projektu</summary>

Linux fundamentals Final Project

Part 1: Basic Commands
cd - change directory
"/" oznacza ścieżkę bezwzględną
.. - katalog nadrzędny
. - aktualny katalog
~ - katalog domowy użytkownika
- - powrót do poprzedniego katalogu
Part 2: The Find Command

Sudo touch /(directory)/test_plik
Part 3: User & Group Management
Part 4: Permissions
Part 5: Alias
Part 6: System Update and Apt Usage
Part 7: Ifcon g and Address Settings
fi
Part 8: Remote Control and Telnet Services




Part 9: SSH Connection
Part 10: Apache Webserver




Part 11: VSFTPD




                            Widać login i hasło ponieważ zwykły
                            protokół FTP nie jest szyfrowany/
                            zamiast tego użyć SFTP lub FPTS
Part 12: Gzip
Part 13: Questions
1:
/etc

Opis: Katalog ‚/etc’ zawiera pliki konfiguracyjne systemu oraz skrypty powłoki używane do uruchamiania i inicjalizacji ustawień systemu.


Szczegóły:


Pliki konfiguracyjne: W katalogu ‚/etc’ znajdują się pliki konfiguracyjne niezbędne do administracji systemem oraz ustawień aplikacji. Przykłady to
‚fstab’ (tablica systemów plików), ‚passwd’ (informacje o kontach użytkowników) oraz ‚network/interfaces’ (konfiguracja sieci).

Skrypty startowe: Zawiera również skrypty, które uruchamiają i zatrzymują usługi systemowe i demony, często znajdujące się w ‚/etc/init.d’ lub ‚/etc/
systemd’.

Informacje o użytkownikach i grupach: Pliki takie jak ‚passwd’, ‚group’ i ‚shadow' zawierają informacje o kontach użytkowników oraz autoryzacji.

Konfiguracja usług systemowych: Katalogi takie jak ‚/etc/ssh’ dla konfiguracji ‚SSH’, ‚/etc/apache2’ dla ‚Apache’, itp.

/mnt

Opis: Katalog ‚/mnt’ jest używany jako punkt montowania dla tymczasowego montowania systemów plików.


Szczegóły:


Tymczasowe montowanie: Administratorzy systemu używają ‚/mnt’ jako punktu montowania, gdy potrzebują ręcznie zamontować system plików, na
przykład dysk USB lub udział sieciowy, do krótkoterminowego dostępu.

Konwencja: Jest to konwencja używania ‚/mnt’ dla tymczasowych punktów montowania, podczas gdy ‚/media’ jest często używane dla automatycznie
montowanych nośników, takich jak CD, DVD i dyski USB.

Przykład użycia: Jeśli chcesz ręcznie zamontować dysk USB, możesz utworzyć podkatalog w ‚/mnt’ (np. ‚/mnt/usb’) i użyć polecenia ‚mount’, aby
zamontować dysk w tym miejscu.

/bin

Opis: Katalog /bin zawiera podstawowe pliki binarne poleceń, które są potrzebne do uruchomienia systemu oraz do pracy w trybie pojedynczego
użytkownika.


Szczegóły:


Podstawowe polecenia: W katalogu ‚/bin’ znajdują się podstawowe polecenia i narzędzia systemowe, które są potrzebne dla wszystkich użytkowników, w
tym podstawowe polecenia manipulacji plikami, takie jak ‚cp’, ‚mv’, ‚rm’ i ‚ls’.

Utrzymanie systemu: Zawiera również podstawowe narzędzia powłoki używane do naprawy systemu, zwłaszcza w trybie odzyskiwania, takie jak ‚bash’,
‚cat’, ‚echo’ i ‚grep'.

Dostęp użytkowników: W przeciwieństwie do ‚/sbin’, który zawiera pliki binarne systemowe przeznaczone głównie dla superużytkownika, pliki binarne w
‚/bin’ są przeznaczone do użytku przez wszystkich użytkowników.

Niezbędne narzędzia systemowe: W katalogu znajdują się również narzędzia takie jak ‚sh’ (powłoka systemowa), ‚mount’, ‚umount’, ‚ps’ (lista procesów),
‚kill’ (zabijanie procesów).


2: Kodowanie (Encoding)
Opis:


Kodowanie to proces konwersji danych z jednego formatu na inny. Głównym celem kodowania jest zapewnienie, że dane mogą być poprawnie odczytane
przez różne systemy. Kodowanie nie jest zaprojektowane do ukrywania danych, ale do umożliwienia ich transportu lub przechowywania.


Kluczowe Punkty:


Cel: Przekształcenie danych w format, który może być prawidłowo odczytany przez różne systemy (np. konwersja danych binarnych na format tekstowy).

Odwracalność: Kodowanie jest procesem odwracalnym. Oryginalne dane można przywrócić poprzez dekodowanie.

Przykłady: Base64, ASCII, Unicode, kodowanie URL.

Zastosowanie: Transmisja danych, przechowywanie danych, interoperacyjność między systemami.

Haszowanie (Hashing)

Opis:


Haszowanie to proces konwersji danych na ciąg znaków o stałej długości, który zazwyczaj wygląda jak losowy ciąg znaków. Ten ciąg nazywa się wartością
haszującą lub kodem haszującym.
Kluczowe Punkty:


Cel: Generowanie unikalnego identyfikatora dla danych (hasza), który reprezentuje dane, ale nie pozwala na odtworzenie oryginalnych danych z hasza.

Nieodwracalność: Haszowanie jest procesem jednokierunkowym. Nie można odtworzyć oryginalnych danych na podstawie wartości hasza.

Algorytmy: MD5, SHA-1, SHA-256, SHA-3.

Zastosowanie: Weryfikacja integralności danych, przechowywanie haseł, podpisy cyfrowe.

Szyfrowanie Symetryczne (Symmetric Encryption)

Opis:


Szyfrowanie symetryczne to metoda szyfrowania, w której ten sam klucz jest używany do szyfrowania i deszyfrowania danych. Klucz ten musi być
zachowany w tajemnicy między stronami.


Kluczowe Punkty:


Jeden Klucz: Używa jednego tajnego klucza zarówno do szyfrowania, jak i deszyfrowania.

Szybkość: Zazwyczaj szybsze niż szyfrowanie asymetryczne.

Bezpieczeństwo: Bezpieczeństwo danych zależy od utrzymania klucza w tajemnicy. Jeśli klucz zostanie skompromitowany, dane mogą zostać
odszyfrowane.

Algorytmy: AES (Advanced Encryption Standard), DES (Data Encryption Standard), 3DES (Triple DES).

Zastosowanie: Bezpieczna transmisja danych, szyfrowanie plików, szyfrowanie dysków.

Szyfrowanie Asymetryczne (Asymmetric Encryption)

Opis:


Szyfrowanie asymetryczne, znane również jako szyfrowanie z kluczem publicznym, używa pary kluczy: klucza publicznego i klucza prywatnego. Klucz
publiczny służy do szyfrowania danych, a klucz prywatny do ich odszyfrowania.


Kluczowe Punkty:


Dwa Klucze: Używa pary kluczy – jednego publicznego i jednego prywatnego. Klucz publiczny może być udostępniany każdemu, ale klucz prywatny musi
być utrzymywany w tajemnicy.

Bezpieczeństwo: Bardziej bezpieczne dla dystrybucji kluczy niż szyfrowanie symetryczne, ponieważ klucz publiczny może być otwarcie udostępniany.

Szybkość: Zazwyczaj wolniejsze niż szyfrowanie symetryczne z powodu bardziej skomplikowanych operacji matematycznych.

Algorytmy: RSA (Rivest-Shamir-Adleman), ECC (Elliptic Curve Cryptography), DSA (Digital Signature Algorithm).

Zastosowanie: Bezpieczna wymiana kluczy, podpisy cyfrowe, bezpieczna komunikacja e-mailowa (np. PGP).


3. SSH (Secure Shell)

Dlaczego trzeba zmieniać plik konfiguracyjny przy włączaniu SSH?


Kiedy włączamy SSH, zazwyczaj musimy dostosować plik konfiguracyjny, aby zapewnić odpowiednie ustawienia bezpieczeństwa i funkcjonalności. Plik
konfiguracyjny /etc/ssh/sshd_config pozwala na dostosowanie różnych opcji, takich jak:


Port: Domyślnie SSH nasłuchuje na porcie 22, ale można to zmienić, aby zwiększyć bezpieczeństwo.

Uwierzytelnianie: Możemy skonfigurować, jakie metody uwierzytelniania są dozwolone, np. klucze publiczne, hasła, czy uwierzytelnianie dwuskładnikowe.

Dostęp użytkowników: Możemy ograniczyć, którzy użytkownicy lub grupy mogą się logować przez SSH.

Inne ustawienia bezpieczeństwa: Takie jak czas trwania sesji, dozwolone protokoły, itp.

Czy znasz inny plik konfiguracyjny i w jakiej usłudze?


Tak, na przykład dla usługi Apache, plik konfiguracyjny to /etc/apache2/apache2.conf lub indywidualne pliki w /etc/apache2/sites-available/ dla
specyficznych wirtualnych hostów. Te pliki konfiguracyjne pozwalają na ustawienie opcji takich jak domyślne katalogi, prawa dostępu, mod_rewrite i wiele
innych.


Jakie jest zastosowanie SSH?
SSH (Secure Shell) jest używany do bezpiecznego zdalnego logowania i wykonywania poleceń na odległych komputerach. Dzięki SSH można zarządzać
serwerami, przenosić pliki za pomocą SCP (Secure Copy) lub SFTP (SSH File Transfer Protocol) oraz tunelować inne protokoły sieciowe w bezpieczny
sposób.


Czy SSH jest szyfrowane?


Tak, SSH jest szyfrowane. Używa kryptografii asymetrycznej do ustanowienia bezpiecznego połączenia i wymiany kluczy, a następnie kryptografii
symetrycznej do szyfrowania sesji komunikacyjnej. To zapewnia, że dane przesyłane między klientem a serwerem są chronione przed podsłuchiwaniem i
modyfikacją.


4. Co to jest jądro (kernel)?

Opis:


Jądro systemu operacyjnego, zwane również kernellem, jest rdzeniem systemu operacyjnego, który zarządza zasobami sprzętowymi i umożliwia
komunikację między sprzętem a oprogramowaniem.


Kluczowe Funkcje:


Zarządzanie Procesami: Kernel kontroluje tworzenie, schedulowanie i zakończenie procesów. Obsługuje również synchronizację i komunikację
międzyprocesową.

Zarządzanie Pamięcią: Zarządza alokacją i zwalnianiem pamięci dla procesów, kontroluje pamięć wirtualną i fizyczną, a także zarządza swapem.

Zarządzanie Systemem Plików: Kernel zarządza operacjami wejścia/wyjścia (I/O) do systemów plików, umożliwiając procesom odczyt i zapis danych.

Obsługa Sprzętu: Kernel zawiera sterowniki, które pozwalają na komunikację z różnymi urządzeniami sprzętowymi, takimi jak dyski twarde, karty sieciowe,
urządzenia peryferyjne.

Bezpieczeństwo i Uprawnienia: Kernel zapewnia mechanizmy ochrony zasobów systemowych, kontrolując dostęp do pamięci, procesów i urządzeń za
pomocą uprawnień i polityk bezpieczeństwa.

Rodzaje Jąder:


Monolityczne: Jądro, które zawiera wszystkie podstawowe funkcje i sterowniki w jednym dużym bloku kodu (np. Linux).

Mikrojądra: Jądro, które zawiera minimalne funkcje, a reszta systemu operacyjnego działa w przestrzeni użytkownika (np. Minix, QNX).

Jądro jest fundamentem, na którym opiera się cały system operacyjny. Jest odpowiedzialne za efektywne i bezpieczne zarządzanie zasobami komputera,
zapewniając stabilność i wydajność systemu.


5. Jak nawiązać połączenie między dwoma maszynami wirtualnymi?

Aby nawiązać połączenie między dwiema maszynami wirtualnymi, należy wykonać następujące kroki:


Sprawdzenie ustawień sieciowych maszyn wirtualnych:


           Otwórz menedżera maszyn wirtualnych (np. VirtualBox, VMware).

           Przejdź do ustawień sieciowych każdej maszyny wirtualnej.

           Upewnij się, że obie maszyny są podłączone do tej samej sieci wirtualnej. Można to zrobić, wybierając opcję sieci "Bridge" (mostek sieciowy)
           lub "Internal Network" (sieć wewnętrzna) w ustawieniach sieciowych każdej maszyny.

Skonfigurowanie adresów IP:


           Jeśli maszyny są podłączone do tej samej sieci wirtualnej, każda z nich powinna mieć unikalny adres IP.

           Możesz skonfigurować adresy IP ręcznie, edytując ustawienia sieciowe w systemie operacyjnym każdej maszyny, lub pozwolić routerowi DHCP
           przydzielić adresy IP automatycznie.

Sprawdzenie łączności:


           Uruchom obie maszyny wirtualne.

           Otwórz terminal na jednej z maszyn.

           Użyj polecenia ping, aby sprawdzić, czy maszyna może osiągnąć drugą maszynę. Na przykład, jeśli adres IP drugiej maszyny to 192.168.1.2,
           wpisz:bash

           Skopiuj kod
           ping 192.168.1.2




           Jeśli ping zwraca odpowiedzi, oznacza to, że maszyny mogą się komunikować.

Konfiguracja firewalli (jeśli jest to konieczne):
           Jeśli maszyny nie mogą się komunikować, sprawdź ustawienia firewalli na obu maszynach i upewnij się, że pozwalają one na ruch sieciowy na
           odpowiednich portach.

Dodatkowe kroki (opcjonalnie):


           Jeśli chcesz nawiązać bezpieczne połączenie (np. SSH), upewnij się, że odpowiednie usługi są zainstalowane i skonfigurowane na obu
           maszynach.

           Na przykład, aby połączyć się przez SSH, upewnij się, że serwer SSH działa na jednej z maszyn, a na drugiej maszynie masz zainstalowanego
           klienta SSH.

Podsumowując, kluczowe jest, aby maszyny były podłączone do tej samej sieci wirtualnej i miały poprawnie skonfigurowane adresy IP.


6. Co to jest ping?

Opis:


Ping to polecenie sieciowe używane do testowania łączności między dwoma urządzeniami w sieci. Jest to podstawowe narzędzie diagnostyczne używane
do sprawdzania, czy urządzenie (np. komputer, serwer) jest osiągalne przez sieć.


Jak działa ping?:


Ping wysyła pakiety ICMP (Internet Control Message Protocol) Echo Request do docelowego urządzenia.

Jeśli docelowe urządzenie jest dostępne i działa poprawnie, odpowiada pakietami ICMP Echo Reply.

Polecenie ping mierzy czas, jaki upłynął od wysłania żądania do otrzymania odpowiedzi (czas podróży w obie strony, RTT - Round Trip Time).

Kluczowe informacje dostarczane przez ping:


Czas odpowiedzi (RTT): Pokazuje, jak długo trwa podróż pakietu do docelowego urządzenia i z powrotem.

Straty pakietów: Pokazuje, ile pakietów zostało wysłanych, a ile z nich otrzymało odpowiedź. Straty mogą wskazywać na problemy w sieci.

Dostępność urządzenia: Informuje, czy docelowe urządzenie jest osiągalne.


Zastosowanie ping:


Diagnostyka sieci: Sprawdzanie, czy urządzenia są dostępne i działają poprawnie.

Pomiar opóźnień: Ocena jakości połączenia sieciowego.

Rozwiązywanie problemów: Identyfikacja problemów z siecią, takich jak przerwy w połączeniu czy opóźnienia.

Ping jest niezwykle przydatnym narzędziem, które pomaga szybko ocenić stan połączeń sieciowych i zidentyfikować potencjalne problemy.7:



7. Co oznaczają trzy liczby przy nadawaniu uprawnień do plików i folderów?

Opis:


W systemach Unix i Linux uprawnienia do plików i folderów są określane za pomocą trzech cyfr. Każda cyfra reprezentuje zestaw uprawnień dla trzech
różnych kategorii użytkowników:


Pierwsza cyfra: Uprawnienia właściciela pliku (user).

Druga cyfra: Uprawnienia grupy, do której należy plik (group).

Trzecia cyfra: Uprawnienia pozostałych użytkowników (others).

Znaczenie poszczególnych cyfr:


Każda cyfra jest sumą trzech możliwych uprawnień:


Read (r): Uprawnienie do odczytu (wartość 4).

Write (w): Uprawnienie do zapisu (wartość 2).

Execute (x): Uprawnienie do wykonania (wartość 1).
Jak to działa?:


Każda cyfra jest sumą wartości uprawnień:


0: brak uprawnień.

1: tylko uprawnienie do wykonania.

2: tylko uprawnienie do zapisu.

3: uprawnienia do zapisu i wykonania (2 + 1).

4: tylko uprawnienie do odczytu.

5: uprawnienia do odczytu i wykonania (4 + 1).

6: uprawnienia do odczytu i zapisu (4 + 2).

7: pełne uprawnienia (odczyt, zapis, wykonanie) (4 + 2 + 1).

Przykład:


chmod 755 plik.txt
7 (rwx): Właściciel ma pełne uprawnienia (odczyt, zapis, wykonanie).

5 (r-x): Grupa ma uprawnienia do odczytu i wykonania, ale nie do zapisu.

5 (r-x): Pozostali użytkownicy mają uprawnienia do odczytu i wykonania, ale nie do zapisu.

Dlaczego zapisujemy je trzy razy (777)?:


Zapisujemy trzy liczby, aby określić różne zestawy uprawnień dla każdej kategorii użytkowników:


Pierwsza cyfra: Uprawnienia właściciela.

Druga cyfra: Uprawnienia grupy.

Trzecia cyfra: Uprawnienia pozostałych użytkowników.

Przykład:



chmod 777 folder
7 (rwx): Właściciel ma pełne uprawnienia.

7 (rwx): Grupa ma pełne uprawnienia.

7 (rwx): Pozostali użytkownicy mają pełne uprawnienia.




8. Czy można utworzyć dwa foldery o tej samej nazwie, jeden małymi, a drugi dużymi literami?

Odpowiedź:


Tak, w systemach plików Linux/Unix można utworzyć dwa foldery o tej samej nazwie, różniące się tylko wielkością liter, ponieważ te systemy są
rozróżniające wielkość liter (case-sensitive).


Przykład:


Możemy utworzyć dwa foldery o nazwach folder i Folder:

mkdir folder
mkdir Folder
folder: mała litera "f".

Folder: wielka litera "F".

Dlaczego tak jest?:


Systemy plików w Unix/Linux traktują wielkie i małe litery jako różne znaki. Oznacza to, że nazwy plików i folderów folder, Folder, FOLDER, i foLDer są
traktowane jako różne.
Różnice w systemach operacyjnych:


Unix/Linux: Rozróżniają wielkość liter (case-sensitive).

Windows: Zwykle nie rozróżniają wielkości liter w systemie plików NTFS (case-insensitive).

Dlatego w systemach Unix/Linux można bez problemu mieć dwa foldery lub pliki o nazwach różniących się tylko wielkością liter, co nie jest możliwe w
systemach operacyjnych Windows bez specjalnych ustawień.


To pozwala na większą elastyczność, ale wymaga także większej uwagi podczas pracy z nazwami plików i folderów, aby unikać nieporozumień i
potencjalnych błędów.



9:
Telnet

Telnet to protokół sieciowy umożliwiający użytkownikowi komunikację zdalną z urządzeniem lub serwerem przez sieć TCP/IP. Telnet zapewnia
dwukierunkową, interaktywną komunikację tekstową przy użyciu wirtualnego połączenia terminalowego. Pomimo swojej przydatności, Telnet jest uważany
za niebezpieczny, ponieważ przesyła dane, w tym hasła, w postaci zwykłego tekstu, co czyni go podatnym na przechwycenie i podsłuchiwanie. Z tego
powodu Telnet został w dużej mierze zastąpiony przez bardziej bezpieczne protokoły, takie jak SSH (Secure Shell).


SSH

SSH (Secure Shell) to kryptograficzny protokół sieciowy zaprojektowany do zapewnienia bezpiecznego dostępu do wiersza poleceń oraz komunikacji
zdalnej z systemami przez niezabezpieczoną sieć. SSH szyfruje wszystkie dane przesyłane między klientem a serwerem, w tym dane logowania i
polecenia, zapewniając poufność i integralność. SSH wspiera również bezpieczny transfer plików, przekierowanie portów oraz różne metody
uwierzytelniania, takie jak uwierzytelnianie oparte na hasłach, kluczach oraz uwierzytelnianie wieloskładnikowe.


Crontab

Crontab (skrót od "cron table") to plik konfiguracyjny i narzędzie wiersza poleceń używane w systemach operacyjnych typu Unix do planowania i
automatyzacji powtarzających się zadań (znanych jako "cron jobs") w określonych odstępach czasu. Użytkownicy mogą definiować zadania do wykonania
o określonych godzinach i datach, co pozwala na automatyzację konserwacji systemu, kopii zapasowych, uruchamiania skryptów i innych cyklicznych
działań. Plik crontab określa harmonogram i polecenia do wykonania.


FTP

FTP (File Transfer Protocol) to standardowy protokół sieciowy używany do przesyłania plików między klientem a serwerem przez sieć TCP/IP. FTP pozwala
użytkownikom na przesyłanie, pobieranie i zarządzanie plikami na zdalnym serwerze. Jednak, podobnie jak Telnet, FTP przesyła dane, w tym dane
uwierzytelniające, w postaci zwykłego tekstu, co czyni go niebezpiecznym. Zalecane są bezpieczne alternatywy, takie jak SFTP (SSH File Transfer
Protocol) i FTPS (FTP Secure) do bezpiecznych transferów plików.


SFTP

SFTP (SSH File Transfer Protocol) to bezpieczny protokół transferu plików działający w ramach protokołu SSH. SFTP zapewnia bezpieczny dostęp do
plików, transfer i zarządzanie nimi, szyfrując zarówno dane, jak i polecenia wymieniane między klientem a serwerem. To szyfrowanie zapewnia poufność i
integralność przesyłanych danych, co sprawia, że SFTP jest preferowaną alternatywą w stosunku do tradycyjnego FTP do bezpiecznych transferów plików.


gzip tar

gzip to narzędzie kompresji, które zmniejsza rozmiar plików przy użyciu algorytmu kompresji GNU zip. tar (skrót od "tape archive") to narzędzie używane
do łączenia wielu plików w jeden plik archiwum, często nazywany tarballem, bez kompresji. Kiedy są używane razem jako gzip tar (często zapisywane jako
tar.gz lub tgz), tworzą skompresowane archiwum, zmniejszając rozmiar tarballa w celu efektywnego przechowywania i transferu. Połączone użycie pozwala
na archiwizację i kompresję plików w jednym kroku.


Bash

Bash (Bourne Again Shell) to interpreter wiersza poleceń i język skryptowy dla systemów operacyjnych typu Unix. Bash jest domyślną powłoką w wielu
dystrybucjach Linuxa i macOS. Zapewnia potężne środowisko do wykonywania poleceń, uruchamiania skryptów i automatyzacji zadań. Skrypty Bash mogą
zawierać zmienne, struktury sterujące i funkcje, co czyni go wszechstronnym narzędziem do administracji systemem i automatyzacji.


Apache

Apache odnosi się do Apache HTTP Server, otwartego i szeroko używanego oprogramowania serwera WWW rozwijanego przez Apache Software
Foundation. Apache dostarcza treści internetowe klientom za pośrednictwem protokołów HTTP i HTTPS oraz wspiera szeroki zakres funkcji, w tym
generowanie dynamicznych treści, uwierzytelnianie, szyfrowanie SSL/TLS, przepisanie adresów URL i równoważenie obciążenia. Modułowa architektura
Apache pozwala na szeroką personalizację i integrację z różnymi językami programowania i bazami danych, co czyni go popularnym wyborem do
hostowania stron internetowych i aplikacji internetowych.


Każde z tych pojęć odgrywa istotną rolę w cyberbezpieczeństwie i administracji systemami, zapewniając różne funkcjonalności i usługi kluczowe dla
utrzymania bezpiecznych i efektywnych środowisk IT.


</details>

<details>
<summary>OCR screenshotów i kolejnych stron projektu</summary>

**PDF s. 1:** Linux fundamentals Final Project

Part 1: Basic Commands

luke@ kali ~

$ sudo su

[sudo] password for luke:

r—( || /home/Luke |

( )- (/home/luke |

Lets

[Desktop Documents Downloads Music Pictures Public Templates Videos

( |-1/hone/luke|

Dg cd'/nome/luke/Desktop/

m )_[/hone/luke/Dezktep|

mkdir foli fol2 fola 56 touch pliki plik? plik

( |-1/home/luke/Desktop |

Lets

jfol1 fol2 fol3 pliki plik2 plik3

in )-[/home/luke/Desktop |

uv plika plita plika fol2/

( |-1/home/luke/Desktop |

Dy ts

|fFol1 fol2 fol3

( )-|/home/luke/Desktop |

Cy cd fol2/

LE |-|/home/luke/Desktop/fol2 |

13

pliki plik2 plik3

A) )-| /home/luke/Desktop/fol2 |

my plik plik2 plik3 /home/luke/Desktop/foli/

( |-|/home/luke/Desktop/fol2 |

Cits

( |-|/home/luke/Desktop/fol2 |

ę )- [Pome /Luke/Desktop

Cy cd fol1/

ct )-|/home/luke/Desktop/fol1 |

ls

pliki plik2 plika

ń )- [/hone/ luke/Desktep/foL1.

zsh: sure you want to delete all 3 files in /hone/luke/Desktop/fol1 [yn]? y

LE )-|/home/luke/Desktop/fol1 |

( )-|/home/luke/Desktop/fol1 |

(te

cS )-|/home/luke/Desktop/fol1 |

home/Luke/Desktop/ fol

( )-|/home/luke/Desktop/fol1 |

Ty cd”.

( |-1/home/luke/Desktop |

Dy ts -a

+ «= foll fol2 fol3

r )-|/hone/tuke/Desktep.

Dy ts -1a

total 20

drwxr-xr-x 5 luke luke 4096 May 13 00:54 .

drwx——— 15 luke luke 4096 May 13 01:20 ..

drwxr-xr-x 2 root root 4096 May 13 00:57 fol2

|) |-1/home/luke/Desktop]

A) |-1/home/luke/Desktop |

id

4 )- [/hone/luka/Dezktep!

Cy u passwd luke

New password:

Retype new password:

passwd: password updated successfully

**PDF s. 2:** cd - change directory

"/" oznacza ścieżkę bezwzględną

.. - katalog nadrzędny

. - aktualny katalog

~ - katalog domowy użytkownika

- - powrót do poprzedniego katalogu

EG |-1/home/luke/Desktop

( )-[~]

EFG

( )-[=]

| pwd

( )-[~]

ea

( |-1/home/luke |

nano ulubiony_os. txt

Cy Lub

( |-1/home/luke |

Cy 1y.

( |-1/home/ Luke |

cat ulubiony_os.txt

G Aubi

Macos

Linux

( |-1/home/luke |

touch „ukryty! .ukryty2 .ukryty3

i

( |-1/home/luke |

. „sudo_as_admin_successful

- Templates

‘bash_Logout „ukryty

„bashrc „ukryty2

bashrc.original -ukryty3

„cache ulubiony_os.txt

Desktop „vboxelient-clipboard-tty7-service.pid

KUŚ „vboxclient-display-svga-x11-tty7-control.pid

Downloads „vboxelient-draganddrop-tty7-control..pid

|face.icon „vboxeLient-hostversion-tty7-control .pid

.gnupg vboxcLient-seamless-tty7-control.pid

„ICEauthority „vboxclient-seamless-tty7-service.pid

Tava ‘vboxclient-vmsvga-session-tty7-control..pid

Mocat Videos

Music „Xauthority

Pictures |xsession-errors

„profile „zshre

Public

jm eo EU

( |-1/home/ Luke |

. „profile

- Public

-bash_logout „sudo_as_admin_successful

|bashre Tonplatez

.bashrc.original ulubiony_os.txt

„config Vboxclient-cLipboard-tty7-service.pid

Desktop /VbokcLient-display-svga-x11-tty7-control.pid

„dmrc „vboxelient-display-svga-x11-tty7-service.pid

Documents „VbokcLient-draganddrop-tty7-control..pid

„face „vbokclient-hostversion-tty7-control .pid

„gnupg „vboxelient-seamless-tty7-service.pid

«java Videos

„local „Xauthority

Music „xsession-errors

Pictures „zshre

a |-1/home/luke |

**PDF s. 3:** Part 2: The Find Command

Sudo touch /(directory)/test_plik

oo a) | Shome/Luke:

p 7 test_plik

media/test_plik

usr/sbin/test_pLik

usr/bin/test_plik

usr/lib/test_plik

usr/test_plik

home/test_plik

run/test_plik

‘var/test_plik

mnt/test_plik

boot/test_plik

tnp/test_plik

etc/test_plik

opt/test_plik

root/test_plik

oot 211 )-[/home/luke

8

00041 )-1/hone/luke

cj 1

root@kali)-[/

p 0-91 [0-0] [0-9

ls: cannot access '[0-9][0-9][0-9]*': No such file or directory

rootS$kali)-[/:

1 1

root®kali)-[/

HE **[0-9]43)'

root @ kali)-I/.

HE **[0-9]43)'

root®kali)-[/

rootSkali)-[/.

ot

root® kali)-[/.

Ls vt "/run/userx" * *.x/[0-9]M5W0.*'"

find: ‘/run/user/10@0/gvfs': Permission denied

root€ kati)-[/

U / '$1 < "4m" {print $2)"

Lost+found

ust

du: cannot access "/proc/145912/fdinfo/4": Io such file or directory

proc

mnt

etc

opt

root6 kali)-1/

f l f bash*

usr/bin/bashbug

usr/Lib/python3/dist_packages/ invoke/conpLet1on/bash.conpletion

‘usr/Lib/1Lvm-14/share/clang/bash-autocomplete.sh

ust/share/nenu/bash

usr/share/Locale/nl/LC_MESSAGES/bash.no

usr/share/Locale/cs/LC_MESSAGES/bash.no

root€ kali) -[/

p 1 +

media/test_plik

usr/sbin/pnuncony

usr/sbin/intelmetool

usr/sbin/ fectest

usr/sbin/cifs.idnap

**PDF s. 4:** Part 3: User & Group Management

0000) -|/home/luke

A mordini

Adding user 'mordini' ...

Adding new group 'mordini' (1001) ...

Adding new user “mordini' (1001) with group “mordini (1001)' ...

Creating home directory '/home/mordini' ...

Copying files from '/etc/skel' ...

New password:

Retype new password:

passwd: password updated successfully

Changing the user information for mordini

Enter the new value, or press ENTER for the default

Full Name []:

Room Number []:

work Phone []:

Home Phone []:

Other []

Is the information correct? [Y/n] y

Adding new user 'mordini' to supplemental / extra groups 'users' ...

Adding user 'mordini' to group ‘users’ ...

root kali /home/luke

it mordziaty

oo )-1/home/luke

p mordziaty

New password:

Retype new password:

passwd: password updated successfully

root kali /home/luke

A passwd

root :x:0:0: root: /root:/usr/bin/zsh

daemon: x:1:1:daemon: /usr/sbin: /usr/sbin/nologin

bin:x:2:2:bin:/bin:/usr/sbin/nologin

sys:x:3:3:sys:/dev:/usr/sbin/nologin

man:x:6:12:man:/var/cache/man: /usr/sbin/nologin

lp:x:7:7:1p:/var/spool/lpd: /usr/sbin/nologin

mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

sucp:x:10:10:uucp:/var/spool/uucp: /usr/sbin/nologin

proxy:x:13:13:proxy:/bin:/usr/sbin/nologin

backup:x:34:34:backup: /var/backups: /usr/sbin/nologin

list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin

irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin

_apt:x:42:65534 :: /nonexistent:/usr/sbin/nologin

nobody :x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin

systemd-network:x:998:998:systemd Network Management: /:/usr/sbin/nolo

mysql:x:100:107:MySQL Server,,,:/nonexistent:/bin/false

tss:x:101:108:TPM software stack,,,:/var/lib/tpm:/bin/false

strongswan:x:102:65534 :: /var/Lib/strongswan: /usr/sbin/nologin

systemd-timesync:x:997:997:systemd Time Synchronization:/:/usr/sbin/n

suidd:x:103:109:: /run/uuidd: /usr/sbin/nologin

redsocks:x:104:110:: /var/run/redsocks:/usr/sbin/nologin

iodine:x:106:65534 :: /run/iodine: /usr/sbin/nologin

messagebus:x:107:112::/nonexistent:/usr/sbin/nologin

miredo:x:108:65534 :: /var/run/miredo: /usr/sbin/nologin

redis:x:109:115::/var/lib/redis:/usr/sbin/nologin

usbmux:x:110:46:usbmux daemon, ,,:/var/lib/usbmux:/usr/sbin/nologin

mosquitto:x:111:117:: /var/lib/mosquitto:/usr/sbin/nologin

tepdunp:x:112:119:: /nonexistent: /usr/sbin/nologin

sshd:x:113:65534 :: /run/sshd: /usr/sbin/nologin

xrdp:x:114:121:: /run/xrdp: /usr/sbin/nologin

_rpc:x:115:65534 :: /run/rpcbind: /usr/sbin/nologin

dnsmasą:x:116:65534:dnsmasq, , , :/var/lib/misc: /usr/sbin/nologin

statd:x:117:65534 :: /var/lib/nfs:/usr/sbin/nologin

avahi:x:118:125:Avahi mDNS daemon, , , :/run/avahi-daemon: /usr/sbin/nolo

stunnel4:x:996:996:stunnel service system account: /var/run/stunnel4

inetsim:x:125:133::/var/lib/inetsim:/usr/sbin/nologin

Lightdm:x:126:134:Light Display Manager:/var/lib/lightdm:/bin/false

geoclue:x:127:135:: /var/lib/geoclue:/usr/sbin/nologin

king-phisher:x:128:136:: /var/lib/king-phisher:/usr/sbin/nologin

polkitd:x:994:994:polkit:/nonexistent:/usr/sbin/nologin

rtkit:x:129:137:Realtimekit,,,:/proc:/usr/sbin/nologin

nm-openvpn:x:131:139:NetworkManager OpenVPN, ,, :/var/Lib/openvpn/chroo

gin

nm-openconnect:x:132:140:NetworkManager OpenConnect plugin, ,,:/var/li

:/usr/sbin/nologin

luke:x:1000:1000:Luke, , ,:/home/luke:/usr/bin/zsh

mordini:x:1001:1001:,,,:/home/mordini:/bin/bash

mordziaty:x:1002:1002 :: /home/mordziaty:/bin/sh

oo |-|/home/luke

4 cd hone,

cd: no such file or directory: home

root kali /home/luke

cj /home

000 010)-1/home

tt

test_plik

**PDF s. 5:** a )-1/home|

su mordini

mordini kali )-[/home

4 mkdir biznes_dir

mkdir: cannot create directory 'biznes_dir': Permission denied

[—(mordini© kali )-[/home

4 sudo mkdir biznes_dir

[sudo] password for mordini

mordini is not in the sudoers file.

mordini kali )-[/home

4 dodajemy mordini do sudoersjj

a )-[/home |

useradd new_mordini 66 usermod sudo new_mordini

M )|-1/home|

ls

luke mordini mordziaty new_mordini test_plik

M )-1/home|

usermod sudo mordini

| )-1/home|

|

Part 4: Permissions

cS )- (| /home/Luke |

— cd Desktop/

LE || /home/luke/Desktop_

ls

fol1 fol2 fol3

m )-1/home/luke/Desktop|

cd fol3/

CS )- (| /home/Luke/Desktop/fol3)

touch filel.txt file2.txt

[EA )- | /home/Luke/Desktop/fol3 |

chmod: missing operand after ‘u+w,go-w’

Try ‘chmod —help' for more information.

CS || /home/Luke/Desktop/fol3 |

—! chmod u+w,go-w .

cS || /home/luke/Desktop/fol3_

ls

total 8

drwxr-xr-x 2 root root 4096 May 13 17:03 .

drwxr-xr-x 5 luke luke 4096 May 13 00:54 ..

-rw-r—r-—- 1 root root © May 13 17:03 filel.txt

-rw-r—r— 1 root root © May 13 17:03 file2.txt

Le )-[ Shome/Luke/Desktop/fol3 |

chmod 777 file1.txt file2.txt

LE )- | /home/Luke/Desktop/fol3 |

—# ls

total 8

drwxr-xr-x 2 root root 4096 May 13 17:03 .

drwxr-xr-x 5 luke luke 4096 May 13 00:54 ..

-rwxrwxrwx 1 root root © May 13 17:03 filei.txt

-rwxrwxrwx 1 root root © May 13 17:03 file2.txt

| )-(/home/luke/Desktop/fol3

chown new_mordini: file1.txt

| )-(/home/luke/Desktop/fol3 |

1s

total 8

drwxr-xr-x 2 root root 4096 May 13 17:03 .

drwxr-xr-x 5 luke luke 4096 May 13 00:54 ..

-rwxrwxrwx 1 new_mordini new_mordini © May 13 17:03 file1.txt

-ruxrwxrwx 1 root root © May 13 17:03 file2.txt

z )-1/home/luke/Desktop/fol3 |

|

**PDF s. 6:** Part 5: Alias

« root @kali: /etc

File Actions Edit View Help

# enable bash completion in interactive shells

# if [ -f /usr/share/bash-completion/bash_completion ]; then

# —. /usr/share/bash-completion/bash_completion

# elif [ -f /etc/bash_completion ]; then

# . /etc/bash_completion

# fi

# if the command-not-found package is installed, use it

‘usr/1ib/command-not-found usr/share/command-not-found/c

d

function command_not_found_handle {

# check because c-n-f could've been removed in the mean

'usr/lib/command-not-found

'usr/Llib/command-not-found $1

/usr/share/command-not-found/command-not-founi

/usr/share/command-not-found/command-not-found

ifconfig

F- root@kali: /etc

File Actions Edit View Help

# /etc/profile: system-wide .profile file for the Bourne shell (sh(1))

# and Bourne compatible shells (bash(1), ksh(1), ash(1), ...)

oo

PATH

ifconfig i |

# The file bash.bashrc already sets the default PS1.

# PS1='Nh:iwi$ *

'etc/bash.bashrc

/etc/bash.bashrc

p

/etc/profile.d

i ‘etc/profile.d/*.sh

L, )-1/home/luke_

su - mordini

(mordini$ kali )-[*

$ nano -/.bashrc

GNU nano 7.2 /home/mordini/.bashrc *

# always display files in long format]

alias ls

six

HISTCONTROL-ignoreboth

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)

HISTSIZE-1000

HISTFILESIZE-2000

**PDF s. 7:** Part 6: System Update and Apt Usage

[A | (fete)

— u apt update

Hit:1 http://http.kali.org/kali kali-rolling InRelease

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

2010 packages can be upgraded. Run ‘apt list —upgradable' to see them.

m (sete!

—ii sudo apt upgrade

Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

Calculating upgrade... Done

The following packages were automatically installed and are no longer ri

cython3 debtags gir1.2-gtksource-3.0 gir1.2-javascriptcoregtk-4.0 gir

gir1.2-webkit2-4.0 gobject-introspection gobject-introspection-bin ka

king-phisher libabsl20220623 libadwaita-1-0 libappstream5 Libarmadilld

libatk-adaptor libblkid-dev libblockdev-crypto2 libblockdev-fs2 libbld

libblockdev-part-err2 libblockdev-part2 libblockdev-swap2 Libblockdev

libblockdev2 libboost-dev libboost1.74-dev libcanberra-gtk-module lib

libcbor0.8 libcurl3-nss libgdal32 libgeos3.11.1 libglib2.0-dev libglil

libgumbo1 libgupnp-igd-1.0-4 libhiredis0.14 libjavascriptcoregtk-4.0-

liblc3-0 libmagickcore-6.q16-6 libmagickcore-6.q16-6-extra libmagickw

libmount-dev libmujs2 libncurses5 libobjc-12-dev libopenblas-dev

libopenblas-pthread-dev Libopenblas® libpcre2-32-0 libpcre2-dev libpc

Libperl5.36 Libpython3-all-dev Libpython3.12 Libpython3.12-dev Librtl

libselinux1-dev libsepol-dev libsoup-gnome2.4-1 libspatialite7 libsteń

libsuperlu5 libtexluajit2 libtinfo5 Libucl1 libutf8proc2 libwebkit2gt

libwebsockets17 libxmlb2 libxsimd-dev libyara9 libzxing2 lua-lpeg nss

perl-modules-5.36 pipewire-alsa pwgen python3-advancedhttpserver pythd

python3-backcall python3-beniget python3-boltons python3-cairo-dev

python3-cryptography37 python3-flask-security python3-future python3-g

python3-geoip2 python3-geojson python3-graphene python3-graphene-sqla}

( )-_ /home/Luke |

nano /etc/apt/sources. list

R z urces-list-repositories/

http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware

[ Additional line for source packages

# deb-src http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware

Cc )- | /home/Luke |

c pt update 66 spt install cmatrix

Hit:1 http://http.kali.org/kali kali-rolling InRelease

Reading package lists... Done

Building dependency tree... Done

Reading state information ... Done

r )- | /home/luke |

— )- (/home/luke |

Ly sudo apt purge cmatrix i te i

Reading package lists... Done

Building dependency tree... Done B

Reading state information... Done

The following packages will be REMOVED: . H :

cmatrix* : u

(0 upgraded, © newly installed, 1 to remove and 52 not upgraded. :

After this operation, 76.8 kB disk space will be freed.

Do you want to continue? [Y/n] Y , |

(Reading database ... 439915 files and directories currently installed.)

Removing cmatrix (2.0-6) ...

Processing triggers for desktop-file-utils (0.27-1) ...

Processing triggers for hicolor-icon-theme (0.17-2) ...

Processing triggers for mailcap (3.70+nmu1) ...

Processing triggers for kali-menu (2023.4.7) ...

**PDF s. 8:** Part 7: Ifconfig and Address Settings

‘oot ka 1)-[/hane/ uke

a

1o: Flags<73<UP, LOOPBACK, RUNNING? mtu 65536

So Sepa

4 ipa

2 BROADCAST MULTICAST, UP, LOWER_UP> mtu 1500 qdisc fq_codel state UP group default glen 1200

Ank/ether_ 08:00:27:ubrcdi3d brd fFeff:feiffethceF

So) | /home/ uke

EMO: FLAGS=4163<UP, BROADCAST RUNNING MULTICAST> MTU 1500

NET 10,0.2:15 NETMASK 255,255.255.0 BROADCAST 10.0.2.255

THET6 FEB0::400:27FF:FELB:CDD PREFTXLEN B4 SCOPETD @20¢LTHK

ETHER 08:00:27:48:CD:0 TXOJEUELEN 1800 (ETHERNET)

RX PACKETS 6200 BYTES 8751493 (8.3 MID)

RX ERRORS. 0 DROPPED 0 OVERRUNS 0 FRAME 0

TX PACKETS 1898 BYTES 122200 (119.3 KTB)

TX ERRORS © DROPPED 0 GVERRUNS © CARRIER @ COLLISIONS @

MET 127.0.0.1. NETHASK 255.0.0.0

INET6 iii PREFIXLEN 128 SCOPEID oxrechost

Sete ets) tometer

0016 ka 1)-[/hana/ uke

So peas

© cat dp.log

0000) Zn /Lake

a

ip.tog

00004 )-1/home/tuke

l cat dp.log

au

**PDF s. 9:** Part 8: Remote Control and Telnet Services

Desktop/

Desktop

U

Part 9: SSH Connection

**PDF s. 10:** ~/dosktop

install openssh-server

Reading package Lists... Done

Building dependency tree... Done

Reading state information... Done

openssh-seryer is already the newest version (1:9.6p1-4).

openssh-server set to nanually installed.

0 upgraded, © newly installed, @ to renove and 58 not upgraded.

-/Desktop

systnctl start ssh

sudo: systmctl: comnand not found

-/Desktop

/home/luke/Desktop

start ssh

> 2

ŚR PuTTY Configuration ? x

PTY Seat Ale x

Category:

EJ Session Basic options for your PUTTY session e

- co Specify the destination you want to connect to ‘Thoth tached eth er:

E- Temini 152168. 1 Get Z

Keyboard Host Name (or IP address) Port OTOZ

Bel [52.168.114] me | earnest

Features Connection type: re 581925 SA Ce STZAV UNOwPOORLEEY2DO WV AUR

Ę]- Window @sSH OsSeral Other: | Telnet v pe mo "km sda TY cc cen

Appearance Ewart canyon czmec at nce, tho adding they tothe ach, ree

Behaviour Load, save or delete a stored session Sones res

raster iho m “Canosa con

Translation Saved Sessions

s Selection

Colours o | [Howie lee | | Comat ree

5) Connection (Default Settings = = ae

Data a

Proxy Save

Rlogin

SUPDUP Close window on exit 5

OAways ONever @ Only onclean ext mm

Ra | He Cr

aan ai BY eases cute) z")

MOORIE RNA ST et At OP By Sw & @ x ©

1 Bic 53 sting tack conn a saa j z.

RE i zona ie JE ~= || FE

B - nee 7 Phueet saa

Boze ow | tema | tte | tra ry 4) Em ki + eh brseeer vent EKES

Saur Sha (SH) sean | A) Baa AE

Ce cre I arte renting i |

RISER REIN Fa aa 5

20104 oo Be we

<

Hosts oa

Groups

Hosts

aqiwie rit yjulij op

afsfaftfafnfifk[!

8 zx cv) b nm &

123 ©Q spacja retum

© g

**PDF s. 11:** Part 10: Apache Webserver

/var/wm/html

index.html

id ‘Apache? Debian Default Page

ma TT

Part 11: VSFTPD

=|=la]

~/Desktop GOFE irae: + tama + ac - 5

ża cy Orgia = Summih e Nawtadui =- a ©

220-SecureBlackbox FIPS server ready par Documents library Aaaa Fold =

REORRZNIE =e A 7 — DL | =| Widaé login i hasło ponieważ zwykły

SESE EG ADS Mo PERI MEME u mauus PFOtOKOt FTP nie jest szyfrowany/

BZ midi mami Ho EMMĘ wu zamiast tego użyć SFTP lub FPTS

**PDF s. 12:** Part 12: Gzip

~/besktop

/ust/Local/share/man/man1/push.1.¢2

/ust/\ab/python3/dist-packages/oyatgraph/exanples /optics/schott_glasses.csv.gz

ast/LD/ jvm/Java~17-open}ok-ando4/nan/nani/Keytool. 1.32

ust /Lab/3vm/Java-17-open) dk-amd64/nan/nani/java. 1.62

/ust/Lib/ jvm java-22 open jak-amdo4/man/man2/jpackage .1.¢z

~/Desktop

/usr/share/info/screen.info-5.gz

gzip: /usr/share/info/screen.info-5: Permission denied

~/Desktop

[sudo] password for luke:

0001 |-1/home/luke/Desktop

“it /usr/share/info/screen.info-5.gz

0001 |-|/home/luke/Desktop

i plik1.txt plik2.txt plik3.txt plik4.txt

00 )-1/home/luke/Desktop

“it pliki.tar pliki.txt plik2.txt plik3.txt plik4.txt

tar: You may not specify more than one '-Acdtrux', '--delete' or '-—-test-label' option

Try ‘tar —help' or ‘tar --usage' for more information.

root® kali /home/luke/Desktop

e pliki.tar plik1.txt plik2.txt plik3.txt plik4.txt

tar: You may not specify more than one '-Acdtrux', '--delete' or '--test-label' option

Try 'tar —help' or 'tar —usage' for more information.

0001 1-1 )-[/home/luke/Desktop

i pliki.tar plik1.txt plik2.txt plik3.txt plik4.txt

plik1.txt

plik2.txt

plik3.txt

plik4.txt

root® kali /home/luke/Desktop

e) pliki.tar

000 )-1/home/luke/Desktop

e) pliki.tar.gz

plik1.txt0000644000000000000000000000000014621247001011320 Oustar rootrootplik2.txt0000644000000000000000000000000

014621247001011321 Qustar rootrootplik3.txt0000644000000000000000000000000014621247001011322 Qustar rootrootplik4

„txt0000644000000000000000000000000014621247001011323 Oustar rootroot

root® kali /home/luke/Desktop

a)

**PDF s. 13:** Part 13: Questions

1:

letc

Opis: Katalog /etc’ zawiera pliki konfiguracyjne systemu oraz skrypty powłoki używane do uruchamiania i inicjalizacji ustawień systemu.

Szczegóły:

Pliki konfiguracyjne: W katalogu „etc znajdują się pliki konfiguracyjne niezbędne do administracji systemem oraz ustawień aplikacji. Przykłady to

fstab’ (tablica systemów plików), „passwd! (informacje o kontach użytkowników) oraz ,network/interfaces’ (konfiguracja sieci).

Skrypty startowe: Zawiera również skrypty, które uruchamiają i zatrzymują usługi systemowe i demony, często znajdujące się w ,/etc/init.d’ lub /etc/

systemd:.

Informacje o użytkownikach i grupach: Pliki takie jak passwd’, group’ i shadow’ zawierają informacje o kontach użytkowników oraz autoryzacji

Konfiguracja usług systemowych: Katalogi takie jak ,/etc/ssh’ dla konfiguracji ,SSH’, ,/etc/apache2’ dla ,Apache’, itp.

Imnt

Opis: Katalog ,/mnt’ jest używany jako punkt montowania dla tymczasowego montowania systemów plików.

Szczegóły:

Tymczasowe montowanie: Administratorzy systemu używają /mnt’ jako punktu montowania, gdy potrzebują ręcznie zamontować system plików, na

przykład dysk USB lub udział sieciowy, do krótkoterminowego dostępu.

Konwencja: Jest to konwencja używania ,/mnt’ dla tymczasowych punktów montowania, podczas gdy ,/media’ jest często używane dla automatycznie

montowanych nośników, takich jak CD, DVD i dyski USB.

Przykład użycia: Jeśli chcesz ręcznie zamontować dysk USB, możesz utworzyć podkatalog w ,/mnt’ (np. ,/mnt/usb’) i użyć polecenia „mount, aby

zamontować dysk w tym miejscu.

Ibin

Opis: Katalog /bin zawiera podstawowe pliki binarne poleceń, które są potrzebne do uruchomienia systemu oraz do pracy w trybie pojedynczego

użytkownika.

Szczegóły:

Podstawowe polecenia: W katalogu ,/bin’ znajdują sie podstawowe polecenia i narzędzia systemowe, które są potrzebne dla wszystkich użytkowników, w

tym podstawowe polecenia manipulacji plikami, takie jak ,cp’, , mv’, ,rm’ i „ls'.

Utrzymanie systemu: Zawiera również podstawowe narzędzia powłoki używane do naprawy systemu, zwłaszcza w trybie odzyskiwania, takie jak ,bash',

„cat, echo’ i grep’.

Dostęp użytkowników: W przeciwieństwie do „/sbin', który zawiera pliki binarne systemowe przeznaczone głównie dla superużytkownika, pliki binarne w

bin’ są przeznaczone do użytku przez wszystkich użytkowników.

Niezbędne narzędzia systemowe: W katalogu znajdują się również narzędzia takie jak ,sh’ (powłoka systemowa), „mount', ,umount, ,ps’ (lista procesów),

kill’ (zabijanie procesów).

2: Kodowanie (Encoding)

Opis:

Kodowanie to proces konwersji danych z jednego formatu na inny. Głównym celem kodowania jest zapewnienie, że dane mogą być poprawnie odczytane

przez różne systemy. Kodowanie nie jest zaprojektowane do ukrywania danych, ale do umożliwienia ich transportu lub przechowywania.

Kluczowe Punkty:

Cel: Przekształcenie danych w format, który może być prawidłowo odczytany przez różne systemy (np. konwersja danych binarnych na format tekstowy).

Odwracalność: Kodowanie jest procesem odwracalnym. Oryginalne dane można przywrócić poprzez dekodowanie.

Przykłady: Base64, ASCII, Unicode, kodowanie URL.

Zastosowanie: Transmisja danych, przechowywanie danych, interoperacyjność między systemami.

Haszowanie (Hashing)

Opis:

Haszowanie to proces konwersji danych na ciąg znaków o stałej długości, który zazwyczaj wygląda jak losowy ciąg znaków. Ten ciąg nazywa się wartością

haszującą lub kodem haszującym.

**PDF s. 14:** Kluczowe Punkty:

Cel: Generowanie unikalnego identyfikatora dla danych (hasza), który reprezentuje dane, ale nie pozwala na odtworzenie oryginalnych danych z hasza.

Nieodwracalność: Haszowanie jest procesem jednokierunkowym. Nie można odtworzyć oryginalnych danych na podstawie wartości hasza.

Algorytmy: MD5, SHA-1, SHA-256, SHA-3.

Zastosowanie: Weryfikacja integralności danych, przechowywanie haseł, podpisy cyfrowe.

Szyfrowanie Symetryczne (Symmetric Encryption)

Opis:

Szyfrowanie symetryczne to metoda szyfrowania, w której ten sam klucz jest używany do szyfrowania i deszyfrowania danych. Klucz ten musi być

zachowany w tajemnicy między stronami.

Kluczowe Punkty:

Jeden Klucz: Używa jednego tajnego klucza zarówno do szyfrowania, jak i deszyfrowania.

Szybkość: Zazwyczaj szybsze niż szyfrowanie asymetryczne.

Bezpieczeństwo: Bezpieczeństwo danych zależy od utrzymania klucza w tajemnicy. Jeśli klucz zostanie skompromitowany, dane mogą zostać

odszyfrowane.

Algorytmy: AES (Advanced Encryption Standard), DES (Data Encryption Standard), 3DES (Triple DES).

Zastosowanie: Bezpieczna transmisja danych, szyfrowanie plików, szyfrowanie dysków.

Szyfrowanie Asymetryczne (Asymmetric Encryption)

Opis:

Szyfrowanie asymetryczne, znane również jako szyfrowanie z kluczem publicznym, używa pary kluczy: klucza publicznego i klucza prywatnego. Klucz

publiczny służy do szyfrowania danych, a klucz prywatny do ich odszyfrowania.

Kluczowe Punkty:

Dwa Klucze: Używa pary kluczy — jednego publicznego i jednego prywatnego. Klucz publiczny może być udostępniany każdemu, ale klucz prywatny musi

być utrzymywany w tajemnicy.

Bezpieczeństwo: Bardziej bezpieczne dla dystrybucji kluczy niż szyfrowanie symetryczne, ponieważ klucz publiczny może być otwarcie udostępniany.

Szybkość: Zazwyczaj wolniejsze niż szyfrowanie symetryczne z powodu bardziej skomplikowanych operacji matematycznych.

Algorytmy: RSA (Rivest-Shamir-Adleman), ECC (Elliptic Curve Cryptography), DSA (Digital Signature Algorithm).

Zastosowanie: Bezpieczna wymiana kluczy, podpisy cyfrowe, bezpieczna komunikacja e-mailowa (np. PGP).

3. SSH (Secure Shell)

Dlaczego trzeba zmieniać plik konfiguracyjny przy włączaniu SSH?

Kiedy włączamy SSH, zazwyczaj musimy dostosować plik konfiguracyjny. aby zapewnić odpowiednie ustawienia bezpieczeństwa i funkcjonalności. Pik

konfiguracyjny /etc/ssh/sshd_config pozwala na dostosowanie różnych opcji, takich jak:

Port: Domyślnie SSH nasłuchuje na porcie 22, ale można to zmienić, aby zwiększyć bezpieczeństwo.

Uwierzytelnianie: Możemy skonfigurować, jakie metody uwierzytelniania są dozwolone, np. klucze publiczne, hasła, czy uwierzytelnianie dwuskładnikowe.

Dostęp użytkowników: Możemy ograniczyć, którzy użytkownicy lub grupy mogą się logować przez SSH.

Inne ustawienia bezpieczeństwa: Takie jak czas trwania sesji, dozwolone protokoły, itp.

Czy znasz inny plik konfiguracyjny i w jakiej usłudze?

Tak, na przykład dla usługi Apache, plik konfiguracyjny to /etclapache2/apache2.conf lub indywidualne pliki w /etcapache2/sites-available/ dla

specyficznych wirtualnych hostów. Te pliki konfiguracyjne pozwalają na ustawienie opcji takich jak domyślne katalogi, prawa dostępu, mod_rewrite i wiele

innych.

Jakie jest zastosowanie SSH?

**PDF s. 15:** SSH (Secure Shell) jest używany do bezpiecznego zdalnego logowania i wykonywania poleceń na odległych komputerach. Dzięki SSH można zarządzać

serwerami, przenosić pliki za pomocą SCP (Secure Copy) lub SFTP (SSH File Transfer Protocol) oraz tunelować inne protokoły sieciowe w bezpieczny

sposób.

Czy SSH jest szyfrowane?

Tak, SSH jest szyfrowane. Używa kryptografii asymetrycznej do ustanowienia bezpiecznego połączenia i wymiany kluczy, a następnie kryptografii

symetrycznej do szyfrowania sesji komunikacyjnej. To zapewnia, że dane przesyłane między klientem a serwerem są chronione przed podsłuchiwaniem i

modyfikacją.

4. Co to jest jądro (kernel)?

Opis:

Jądro systemu operacyjnego, zwane również kernellem, jest rdzeniem systemu operacyjnego, który zarządza zasobami sprzętowymi i umożliwia

komunikację między sprzętem a oprogramowaniem.

Kluczowe Funkcje:

Zarządzanie Procesami: Kernel kontroluje tworzenie, schedulowanie i zakończenie procesów. Obsługuje również synchronizację i komunikację

międzyprocesową,

Zarządzanie Pamięcią: Zarządza alokacją i zwalnianiem pamięci dla procesów, kontroluje pamięć wirtualną i fizyczną, a także zarządza swapem

Zarządzanie Systemem Plików: Kernel zarządza operacjami wejścia/wyjścia (I/O) do systemów plików, umożliwiając procesom odczyt i zapis danych.

Obsługa Sprzętu: Kernel zawiera sterowniki, które pozwalają na komunikację z różnymi urządzeniami sprzętowymi, takimi jak dyski twarde, karty sieciowe,

urządzenia peryferyjne.

Bezpieczeństwo i Uprawnienia: Kernel zapewnia mechanizmy ochrony zasobów systemowych, kontrolując dostęp do pamięci, procesów i urządzeń za

pomocą uprawnień i polityk bezpieczeństwa.

Rodzaje Jąder:

Monolityczne: Jądro, które zawiera wszystkie podstawowe funkcje i sterowniki w jednym dużym bloku kodu (np. Linux).

Mikrojądra: Jądro, które zawiera minimalne funkcje, a reszta systemu operacyjnego działa w przestrzeni użytkownika (np. Minix, QNX).

Jądro jest fundamentem, na którym opiera się cały system operacyjny. Jest odpowiedzialne za efektywne i bezpieczne zarządzanie zasobami komputera,

zapewniając stabilność i wydajność systemu.

5. Jak nawiązać połączenie między dwoma maszynami wirtualnymi?

Aby nawiązać połączenie między dwiema maszynami wirtualnymi, należy wykonać następujące kroki:

Sprawdzenie ustawień sieciowych maszyn wirtualnych:

Otwórz menedżera maszyn wirtualnych (np. VirtualBox, VMware).

Przejdź do ustawień sieciowych każdej maszyny wirtualnej.

Upewnij się, że obie maszyny są podłączone do tej samej sieci wirtualnej. Można to zrobić, wybierając opcję sieci "Bridge" (mostek sieciowy)

lub "Internal Network" (sieć wewnętrzna) w ustawieniach sieciowych każdej maszyny.

Skonfigurowanie adresów IP:

Jeśli maszyny są podłączone do tej samej sieci wirtualnej, każda z nich powinna mieć unikalny adres IP.

Możesz skonfigurować adresy IP ręcznie, edytując ustawienia sieciowe w systemie operacyjnym każdej maszyny, lub pozwolić routerowi DHCP

przydzielić adresy IP automatycznie.

Sprawdzenie łączności:

Uruchom obie maszyny wirtualne.

Otwórz terminal na jednej z maszyn.

Użyj polecenia ping, aby sprawdzić, czy maszyna może osiągnąć drugą maszynę. Na przykład, jeśli adres IP drugiej maszyny to 192.168.1.2,

wpisz:bash

Skopiuj kod

ping 192.168.1.2

Jeśli ping zwraca odpowiedzi, oznacza to, że maszyny mogą się komunikować.

Konfiguracja firewalli (jeśli jest to konieczne):

**PDF s. 16:** Jeśli maszyny nie mogą się komunikować, sprawdż ustawienia firewalli na obu maszynach i upewnij się, że pozwalają one na ruch sieciowy na

odpowiednich portach.

Dodatkowe kroki (opcjonalnie):

Jeśli chcesz nawiązać bezpieczne połączenie (np. SSH), upewnij się, że odpowiednie usługi są zainstalowane i skonfigurowane na obu

maszynach.

Na przykład, aby połączyć się przez SSH, upewnij się, że serwer SSH działa na jednej z maszyn, a na drugiej maszynie masz zainstalowanego

klienta SSH

Podsumowując, kluczowe jest, aby maszyny były podłączone do tej samej sieci wirtualnej i miały poprawnie skonfigurowane adresy IP.

6. Co to jest ping?

Opis:

Ping to polecenie sieciowe używane do testowania łączności między dwoma urządzeniami w sieci. Jest to podstawowe narzędzie diagnostyczne używane

do sprawdzania, czy urządzenie (np. komputer, serwer) jest osiągalne przez sieć.

Jak działa ping?:

Ping wysyła pakiety ICMP (Internet Control Message Protocol) Echo Request do docelowego urządzenia.

Jeśli docelowe urządzenie jest dostępne i działa poprawnie, odpowiada pakietami ICMP Echo Reply.

Polecenie ping mierzy czas, jaki upłynął od wysłania żądania do otrzymania odpowiedzi (czas podróży w obie strony, RTT - Round Trip Time).

Kluczowe informacje dostarczane przez ping:

Czas odpowiedzi (RTT): Pokazuje, jak długo trwa podróż pakietu do docelowego urządzenia i z powrotem.

Straty pakietów: Pokazuje, ile pakietów zostało wysłanych, a ile z nich otrzymało odpowiedź. Straty mogą wskazywać na problemy w sieci.

Dostępność urządzenia: Informuje, czy docelowe urządzenie jest osiągalne.

Zastosowanie ping:

Diagnostyka sieci: Sprawdzanie, czy urządzenia są dostępne i działają poprawnie.

Pomiar opóźnień: Ocena jakości połączenia sieciowego.

Rozwiązywanie problemów: Identyfikacja problemów z siecią, takich jak przerwy w połączeniu czy opóźnienia.

Ping jest niezwykle przydatnym narzędziem, które pomaga szybko ocenić stan połączeń sieciowych i zidentyfikować potencjalne problemy.7:

7. Co oznaczają trzy liczby przy nadawaniu uprawnień do plików i folderów?

Opis:

W systemach Unix i Linux uprawnienia do plików i folderów są określane za pomocą trzech cyfr. Każda cyfra reprezentuje zestaw uprawnień dla trzech

różnych kategorii użytkowników:

Pierwsza cyfra: Uprawnienia właściciela pliku (user).

Druga cyfra: Uprawnienia grupy, do której należy plik (group).

Trzecia cyfra: Uprawnienia pozostałych użytkowników (others).

Znaczenie poszczególnych cyfr:

Każda cyfra jest sumą trzech możliwych uprawnień:

Read (r): Uprawnienie do odczytu (wartość 4).

Write (w): Uprawnienie do zapisu (wartość 2).

Execute (x): Uprawnienie do wykonania (wartość 1)

**PDF s. 17:** Jak to dziata?:

Każda cyfra jest sumą wartości uprawnień

0: brak uprawnień.

1: tylko uprawnienie do wykonania.

2: tylko uprawnienie do zapisu.

3: uprawnienia do zapisu i wykonania (2 + 1).

4: tylko uprawnienie do odczytu.

5: uprawnienia do odczytu i wykonania (4 + 1).

6: uprawnienia do odczytu i zapisu (4 + 2).

7: pełne uprawnienia (odczyt, zapis, wykonanie) (4 + 2 + 1).

Przykład:

chmod 755 plik.txt

7 (rwx): Właściciel ma pełne uprawnienia (odczyt, zapis, wykonanie).

5 (r-x): Grupa ma uprawnienia do odczytu i wykonania, ale nie do zapisu.

5 (r-x): Pozostali użytkownicy mają uprawnienia do odczytu i wykonania, ale nie do zapisu.

Dlaczego zapisujemy je trzy razy (777)?:

Zapisujemy trzy liczby, aby określić różne zestawy uprawnień dla każdej kategorii użytkowników:

Pierwsza cyfra: Uprawnienia właściciela.

Druga cyfra: Uprawnienia grupy.

Trzecia cyfra: Uprawnienia pozostałych użytkowników.

Przykład:

chmod 777 folder

7 (rw): Właściciel ma pełne uprawnienia.

7 (rwx): Grupa ma pełne uprawnienia.

7 (rwx): Pozostali użytkownicy mają pełne uprawnienia.

8. Czy można utworzyć dwa foldery o tej samej nazwie, jeden małymi, a drugi dużymi literami?

Odpowiedź:

Tak, w systemach plików Linux/Unix można utworzyć dwa foldery o tej samej nazwie, różniące się tylko wielkością liter, ponieważ te systemy są

rozróżniające wielkość liter (case-sensitive).

Przykład:

Możemy utworzyć dwa foldery o nazwach folder i Folder.

mkdir folder

mkdir Folder

folder: mała litera "f.

Folder: wielka litera "F".

Dlaczego tak jest?:

Systemy plików w Unix/Linux traktują wielkie i małe litery jako różne znaki. Oznacza to, że nazwy plików i folderów folder, Folder, FOLDER, i foLDer są

traktowane jako różne.

**PDF s. 18:** Różnice w systemach operacyjnych:

Unix/Linux: Rozróżniają wielkość liter (case-sensitive).

Windows: Zwykle nie rozróżniają wielkości liter w systemie plików NTFS (case-insensitive).

Dlatego w systemach Unix/Linux można bez problemu mieć dwa foldery lub pliki o nazwach różniących się tylko wielkością liter, co nie jest możliwe w

systemach operacyjnych Windows bez specjalnych ustawień

To pozwala na większą elastyczność, ale wymaga także większej uwagi podczas pracy z nazwami plików i folderów, aby unikać nieporozumień i

potencjalnych błędów.

9:

Telnet

Telnet to protokół sieciowy umożliwiający użytkownikowi komunikację zdalną z urządzeniem lub serwerem przez sieć TCPIIP. Telnet zapewnia

dwukierunkową, interaktywną komunikację tekstową przy użyciu wirtualnego połączenia terminalowego. Pomimo swojej przydatności, Telnet jest uważany

za niebezpieczny, ponieważ przesyła dane, w tym hasła, w postaci zwykłego tekstu, co czyni go podatnym na przechwycenie i podsłuchiwanie. Z tego

powodu Telnet został w dużej mierze zastąpiony przez bardziej bezpieczne protokoły, takie jak SSH (Secure Shell).

SSH

SSH (Secure Shell) to kryptograficzny protokół sieciowy zaprojektowany do zapewnienia bezpiecznego dostępu do wiersza poleceń oraz komunikacji

zdalnej z systemami przez niezabezpieczoną sieć. SSH szyfruje wszystkie dane przesyłane między klientem a serwerem, w tym dane logowania i

polecenia, zapewniając poufność i integralność. SSH wspiera również bezpieczny transfer plików, przekierowanie portów oraz różne metody

uwierzytelniania, takie jak uwierzytelnianie oparte na hasłach, kluczach oraz uwierzytelnianie wieloskładnikowe.

Crontab

Crontab (skrót od "cron table") to plik konfiguracyjny i narzędzie wiersza poleceń używane w systemach operacyjnych typu Unix do planowania i

automatyzacji powtarzających się zadań (znanych jako "cron jobs") w określonych odstępach czasu. Użytkownicy mogą definiować zadania do wykonania

© określonych godzinach i datach, co pozwala na automatyzację konserwacji systemu, kopii zapasowych, uruchamiania skryptów i innych cyklicznych

działań. Plik crontab określa harmonogram i polecenia do wykonania.

FTP

FTP (File Transfer Protocol) to standardowy protokół sieciowy używany do przesyłania plików między klientem a serwerem przez sieć TCP/IP. FTP pozwala

użytkownikom na przesyłanie, pobieranie i zarządzanie plikami na zdalnym serwerze. Jednak, podobnie jak Telnet, FTP przesyła dane, w tym dane

uwierzytelniające, w postaci zwykłego tekstu, co czyni go niebezpiecznym. Zalecane są bezpieczne alternatywy, takie jak SFTP (SSH File Transfer

Protocol) i FTPS (FTP Secure) do bezpiecznych transferów plików.

SFTP

SFTP (SSH File Transfer Protocol) to bezpieczny protokół transferu plików działający w ramach protokołu SSH. SFTP zapewnia bezpieczny dostęp do

plików, transfer i zarządzanie nimi, szyfrując zarówno dane, jak i polecenia wymieniane między klientem a serwerem. To szyfrowanie zapewnia poufność i

integralność przesyłanych danych, co sprawia, że SFTP jest preferowaną alternatywą w stosunku do tradycyjnego FTP do bezpiecznych transferów plików.

gzip tar

gzip to narzędzie kompresji, które zmniejsza rozmiar plików przy użyciu algorytmu kompresji GNU zip. tar (skrót od "tape archive") to narzędzie używane

do łączenia wielu plików w jeden plik archiwum, często nazywany tarballem, bez kompresji. Kiedy są używane razem jako gzip tar (często zapisywane jako

tar.gz lub tgz), tworzą skompresowane archiwum, zmniejszając rozmiar tarballa w celu efektywnego przechowywania i transferu. Połączone użycie pozwala

na archiwizację i kompresję plików w jednym kroku.

Bash

Bash (Bourne Again Shell) to interpreter wiersza poleceń i język skryptowy dla systemów operacyjnych typu Unix. Bash jest domyślną powłoką w wielu

dystrybucjach Linuxa i macOS. Zapewnia potężne środowisko do wykonywania poleceń, uruchamiania skryptów i automatyzacji zadań. Skrypty Bash mogą

zawierać zmienne, struktury sterujące i funkcje, co czyni go wszechstronnym narzędziem do administracji systemem i automatyzacji.

Apache

Apache odnosi się do Apache HTTP Server, otwartego i szeroko używanego oprogramowania serwera WWW rozwijanego przez Apache Software

Foundation. Apache dostarcza treści internetowe klientom za pośrednictwem protokołów HTTP i HTTPS oraz wspiera szeroki zakres funkcji, w tym

generowanie dynamicznych treści, uwierzytelnianie, szyfrowanie SSL/TLS, przepisanie adresów URL i równoważenie obciążenia. Modułowa architektura

Apache pozwala na szeroką personalizację i integrację z różnymi językami programowania i bazami danych, co czyni go popularnym wyborem do

hostowania stron internetowych i aplikacji internetowych.

Każde z tych pojęć odgrywa istotną rolę w cyberbezpieczeństwie i administracji systemami, zapewniając różne funkcjonalności i usługi kluczowe dla

utrzymania bezpiecznych i efektywnych środowisk IT.

</details>
