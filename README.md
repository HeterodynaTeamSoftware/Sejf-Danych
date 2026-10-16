# Sejf Danych PQ

**Sejf Danych PQ** to program dla Windows do tworzenia i obsługi szyfrowanych sejfów na pliki.

Projekt łączy klasyczne szyfrowanie danych z mechanizmami kryptografii post-quantum. Program działa lokalnie — sejf, klucze i pliki pozostają na komputerze użytkownika.

**Aktualna wersja: 02.001.0055**

---

## Co potrafi

Sejf Danych pozwala m.in. na:

- tworzenie nowych szyfrowanych sejfów,
- dodawanie plików do istniejącego sejfu,
- usuwanie plików z sejfu,
- odszyfrowywanie zawartości do wybranego katalogu,
- pracę z hasłem,
- pracę z plikiem-kluczem,
- łączenie hasła i keyfile,
- generowanie plików-kluczy,
- tworzenie kopii zapasowych keyfile,
- odtwarzanie keyfile z kopii,
- tworzenie kopii kontenera,
- odtwarzanie kontenera,
- kontrolę integralności sejfu,
- testowe odszyfrowanie przed właściwą operacją,
- audyt kontenera,
- audyt zaszyfrowanego payloadu,
- self-test sejfu,
- migrację starszych wersji kontenera,
- eksport i import paczek `.pqvault`,
- przygotowanie informacji potrzebnych do recovery.

---

## Kryptografia

Program wykorzystuje m.in.:

- **AES-256-GCM** do szyfrowania danych,
- **PBKDF2-SHA256** do wyprowadzania kluczy z hasła,
- **SHA-256** do kontroli integralności,
- **ML-KEM**,
- **ML-DSA**,
- bibliotekę **liboqs** do obsługi mechanizmów post-quantum.

W zależności od wybranego trybu sejf może korzystać z:

- samego hasła,
- samego pliku-klucza,
- hasła i pliku-klucza jednocześnie.

---

## Keyfile

Program obsługuje pliki-klucze jako dodatkowy element ochrony sejfu.

Można:

- wygenerować nowy keyfile,
- wykorzystać go podczas tworzenia sejfu,
- wykonać jego kopię zapasową,
- odtworzyć go z przygotowanego backupu.

Jeżeli dany sejf wymaga keyfile, jego utrata może uniemożliwić odszyfrowanie danych. Warto przechowywać kopię klucza w innym bezpiecznym miejscu.

---

## Audyt i kontrola integralności

Sejf Danych posiada funkcje pomagające sprawdzić stan kontenera przed rozpoczęciem właściwego odszyfrowania.

Dostępne są m.in.:

- sprawdzanie struktury kontenera,
- weryfikacja integralności nagłówka,
- kontrola zaszyfrowanego payloadu,
- test odszyfrowania,
- self-test,
- raporty audytowe,
- informacje przydatne przy recovery.

---

## Backup i odzyskiwanie

Program pozwala przygotować kopie zapasowe najważniejszych elementów sejfu.

Dotyczy to m.in.:

- kontenera,
- pliku-klucza,
- danych potrzebnych podczas odzyskiwania.

Backup powinien być przechowywany oddzielnie od głównego sejfu.

---

## Format `.pqvault`

Sejf Danych obsługuje paczki:

```text
.pqvault
```

Mogą być używane do eksportowania i importowania danych związanych z sejfem.

---

## Wymagania

- Windows 10 lub Windows 11
- architektura x64

Program jest wydany jako **self-contained dla .NET 8**, dlatego nie wymaga osobnej instalacji środowiska .NET.

Wymagane biblioteki kryptograficzne są dołączone do paczki programu.

---

## Uruchomienie

Przejdź do katalogu:

```text
dist/windows-x64/
```

i uruchom:

```text
SejfDanychPQ.exe
```

Nie trzeba instalować dodatkowych bibliotek ani dodawać ich ręcznie do `PATH`, jeżeli program uruchamiany jest z kompletnej paczki.

---

## Struktura repozytorium

```text
Sejf-Danych/
├── dist/
│   └── windows-x64/
│       ├── SejfDanychPQ.exe
│       ├── SejfDanych.PQ.App.dll
│       ├── SejfDanych.PQ.App.deps.json
│       ├── SejfDanych.PQ.App.runtimeconfig.json
│       ├── oqs.dll
│       ├── liboqs.dll
│       ├── liboqs-9.dll
│       └── ...
├── README.md
├── LICENSE
└── .gitignore
```

---

## Bezpieczeństwo

Sejf Danych jest narzędziem do ochrony lokalnych plików, ale bezpieczeństwo całego rozwiązania zależy również od sposobu korzystania z programu.

Warto pamiętać o kilku podstawowych zasadach:

- używaj długiego i unikalnego hasła,
- wykonuj kopie zapasowe kontenera,
- wykonuj kopie zapasowe keyfile,
- nie przechowuj jedynej kopii keyfile razem z sejfem,
- nie usuwaj oryginalnych danych, dopóki nie sprawdzisz, że backup można poprawnie otworzyć,
- chroń komputer przed malware i nieautoryzowanym dostępem.

---

## Wersja

```text
02.001.0055
```

---

## Autor

**Heterodyna Team Software**

https://heterodynateamsoftware.pl

---

## Licencja

Projekt jest udostępniany na licencji:

**GNU General Public License v3.0 only**

SPDX:

```text
GPL-3.0-only
```

Pełny tekst licencji znajduje się w pliku:

```text
LICENSE
```

---

# English

## Sejf Danych PQ

**Sejf Danych PQ** is a Windows application for creating and managing encrypted file vaults.

It combines conventional data encryption with post-quantum cryptographic mechanisms.

**Current version: 02.001.0055**

---

## Main features

- creating encrypted file vaults,
- adding files to existing vaults,
- removing files from vaults,
- extracting decrypted files,
- password protection,
- keyfile support,
- password and keyfile mode,
- keyfile generation,
- keyfile backup and recovery,
- vault backup and restore,
- integrity verification,
- test decryption,
- vault audit,
- payload audit,
- self-test,
- migration of older vault formats,
- `.pqvault` import and export,
- recovery-related tools.

---

## Cryptography

The application uses:

- **AES-256-GCM**
- **PBKDF2-SHA256**
- **SHA-256**
- **ML-KEM**
- **ML-DSA**
- **liboqs**

Depending on the selected mode, a vault can use:

- a password,
- a keyfile,
- a password and keyfile together.

---

## Requirements

- Windows 10 or Windows 11
- x64 architecture

The application is distributed as a **self-contained .NET 8 build**, so a separate .NET installation is not required.

Required cryptographic libraries are included with the application package.

---

## Running

Open:

```text
dist/windows-x64/
```

and run:

```text
SejfDanychPQ.exe
```

No additional libraries need to be installed or added manually to `PATH` when using the complete application package.

---

## Author

**Heterodyna Team Software**

https://heterodynateamsoftware.pl

---

## License

**GNU General Public License v3.0 only**

SPDX:

```text
GPL-3.0-only
```

The full license text is available in:

```text
LICENSE
```
