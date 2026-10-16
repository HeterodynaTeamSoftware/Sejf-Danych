# Sejf Danych PQ

**Sejf Danych PQ** to desktopowe narzędzie dla Windows do tworzenia szyfrowanych sejfów na pliki i zarządzania nimi lokalnie.

Aktualna wersja: **02.001.0055**

Program pracuje na własnym formacie sejfu `HSV2` i łączy klasyczne szyfrowanie danych z mechanizmami post-quantum dostępnymi przez `liboqs`.

## Najważniejsze funkcje

- tworzenie szyfrowanych sejfów z plików,
- dodawanie i usuwanie plików z kontenera,
- odszyfrowywanie zawartości do wybranego folderu,
- AES-256-GCM do szyfrowania danych,
- PBKDF2-SHA256 z konfigurowalnymi profilami bezpieczeństwa,
- obsługa hasła i pliku-klucza,
- generowanie mocnych keyfile,
- backup i odtwarzanie keyfile,
- backup i odtwarzanie kontenera,
- kontrola integralności i hash nagłówka,
- audyt sejfu przed otwarciem,
- audyt payloadu,
- testowe odszyfrowanie przed właściwą operacją,
- self-test kontenera,
- eksport i import paczek `.pqvault`,
- migracja starszych wersji sejfu,
- plan recovery i raporty audytowe,
- obsługa ML-KEM i ML-DSA przez `liboqs`,
- tworzenie i obsługa par kluczy podpisu post-quantum.

## Kryptografia

W obecnym buildzie wykorzystywane są m.in.:

- **AES-256-GCM**,
- **PBKDF2-SHA256**,
- **SHA-256**,
- **ML-KEM**,
- **ML-DSA**,
- `liboqs` / `oqs.dll`.

Program potrafi pracować z hasłem, keyfile albo kombinacją obu metod, zależnie od wybranego trybu sejfu.

## Wymagania

- Windows 10 lub Windows 11,
- architektura x64.

Build znajdujący się w repo jest self-contained dla .NET 8. Biblioteki `oqs.dll`, `liboqs.dll` lub zgodny build `liboqs-9.dll` muszą być dostępne obok aplikacji albo w `PATH`.

## Uruchomienie

Przejdź do:

```text
dist/windows-x64/
```

i uruchom:

```text
SejfDanychPQ.exe
```

## Struktura repo

```text
dist/windows-x64/   gotowy build Windows x64
README.md           opis projektu
LICENSE             GNU GPL v3
```

## Ważne

To repo zostało przygotowane z przekazanej paczki programu. Przekazana paczka zawierała **gotowy build**, a nie komplet oryginalnych plików źródłowych `.cs` / `.xaml`.

Nie publikuję sztucznie odtworzonego kodu jako „oryginalnego źródła”. Gdy źródła projektu będą dostępne, można je dodać do repo jako właściwy kod źródłowy.

## Autor

**Heterodyna Team Software**  
https://heterodynateamsoftware.pl

## Licencja

**GPL-3.0-only**

---

## English

**Sejf Danych PQ** is a Windows desktop application for creating and managing encrypted local file vaults.

Current version: **02.001.0055**

Main features include AES-256-GCM encryption, password and keyfile modes, vault backup and recovery, integrity checks, audit reports, `.pqvault` import/export and post-quantum mechanisms based on ML-KEM / ML-DSA through `liboqs`.

### Requirements

- Windows 10 / 11
- x64

### License

**GPL-3.0-only**
