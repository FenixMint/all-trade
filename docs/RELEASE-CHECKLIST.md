# MZ-Trading — warunki gotowości integracji produkcyjnej

Ten plik jest **listą kontrolną**, nie certyfikatem zgodności. Nie zaznaczać elementu jako ukończony bez dowodu z odpowiedniego środowiska.

## Identyfikacja i kontakt

- [x] Publiczne repozytorium informacyjne `FenixMint/all-trade` jest dostępne.
- [x] Jednoznaczny opis nazwy `MZ-Trading`, systemu FX NEXUS, działalności i konta `mztrade`.
- [x] Udokumentowano zasady kontaktu przez GitHub bez przekazywania poufnych informacji.
- [x] Właściciel wskazał publiczny kontakt techniczny `maciej@mztrade.com.pl`; uzupełniono `CONTACT.md`.
- [ ] Zweryfikowano odbiór wiadomości przez ten adres.
- [x] Właściciel ukończył 2FA na koncie Allegro `mztrade` przed rejestracją nowej aplikacji.
- [x] Właściciel potwierdził rejestrację aplikacji `MZ-Trading` jako Device na koncie `mztrade`.
- [ ] Właściwy zakres uprawnień do przyszłego WRITE i reautoryzacja tokenu — do osobnej weryfikacji.
- [ ] Ustalono rzeczywisty numer wersji aplikacji z uruchomionego kodu.
- [ ] Sprawdzono pełny `User-Agent` oficjalnym walidatorem Allegro i potwierdzono jego użycie na wszystkich żądaniach.

## Bezpieczeństwo i OAuth

- [x] Właściciel potwierdził 2FA na koncie `mztrade` i zarejestrowanie aplikacji na tym koncie.
- [ ] Wdrożono ochronę poświadczeń i bezpieczne odświeżanie tokenów oraz testy braku wycieku przez logi.
- [x] Ukończono OAuth z zakresami odczytu konta i ofert, potwierdzone testem operatora 22.10.2026. Nie weryfikuje to WRITE.
- [x] Test operatora z 22.10.2026 potwierdził poprawność `GET /me` i `GET /sale/offers`.
- [ ] Odrębnie przetestowano właściwy typ tokena dla katalogu i prywatnych ofert.
- [ ] Rozdzielono Sandbox i produkcję; wykonano udane testy niewprowadzające zmian.

## Bezpieczna eksploatacja

- [ ] Zweryfikowano niską intensywność zapytań, limity, odpowiedzi `429`, `401`, `403` i procedurę odświeżania tokenów.
- [ ] Działanie Matchera na nowej aplikacji porównano z wcześniejszym, przed wycofaniem starej integracji.
- [ ] Dopuszczono zapis tylko po odrębnym upoważnieniu; bezpiecznik WRITE przetestowany także na błędnych identyfikatorach ofert.
- [ ] Przeprowadzono osobny pilot ograniczonej zmiany jednej oferty, potwierdzając wynik i zachowując audyt — wyłącznie po upoważnieniu operatora.
- [ ] Zweryfikowano poprawność treści ofert, GPSR, praw do zdjęć i danych katalogowych przed ich publikacją lub modyfikacją.
- [ ] Wycofano stary `MZ-Parts-Matcher` **dopiero po** potwierdzonym przejęciu jego funkcji przez nową aplikację i osobnej decyzji właściciela.

## Stan znany z dokumentowania

**Stan 2026-10-22:** właściciel potwierdził rejestrację MZ-Trading na koncie `mztrade` oraz skuteczny odczyt danych konta/ofert przez OAuth w instalacji FX NEXUS. Nie wykonano tu niezależnej oceny bezpieczeństwa ani żadnej aktualizacji cen. Do dopuszczenia operacji zapisu wymagane są odrębne testy, weryfikacja odpowiednich uprawnień i kontrolowany pilot. Niezaznaczone punkty pozostają do wykonania.
