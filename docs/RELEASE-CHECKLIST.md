# MZ-Trading — warunki gotowości integracji produkcyjnej

Ten plik jest **listą kontrolną**, nie certyfikatem zgodności. Nie zaznaczać elementu jako ukończony bez dowodu z odpowiedniego środowiska.

## Identyfikacja i kontakt

- [x] Publiczne repozytorium informacyjne `FenixMint/all-trade` jest dostępne.
- [x] Jednoznaczny opis nazwy `MZ-Trading`, systemu FX NEXUS, działalności i konta `mztrade`.
- [x] Udokumentowano zasady kontaktu przez GitHub bez przekazywania poufnych informacji.
- [ ] Potwierdzono monitorowany, bezpośredni adres kontaktowy administratora integracji i uzupełniono `CONTACT.md`.
- [ ] Zweryfikowano w panelu Allegro dokładną nazwę `MZ-Trading`, faktycznie zarejestrowany typ aplikacji i przyznane scopes.
- [ ] Ustalono rzeczywisty numer wersji aplikacji z uruchomionego kodu.
- [ ] Sprawdzono pełny `User-Agent` oficjalnym walidatorem Allegro i potwierdzono jego użycie na wszystkich żądaniach.

## Bezpieczeństwo i OAuth

- [ ] Potwierdzono uprawnienie właściciela aplikacji oraz włączenie 2FA dla konta Allegro.
- [ ] Wdrożono ochronę poświadczeń i bezpieczne odświeżanie tokenów oraz testy braku wycieku przez logi.
- [ ] Sprawdzono minimalne scopes i akceptację autoryzacji dla konta `mztrade`.
- [ ] Potwierdzono w API rzeczywistą tożsamość sprzedawcy, np. przez `GET /me`.
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

Właściciel przekazał, że aplikacja `MZ-Trading` jest już zarejestrowana. Tego faktu **nie sprawdzono niezależnie w prywatnym panelu Allegro**. Samo zapisanie dokumentacji w repozytorium nie przeprowadza autoryzacji OAuth, testów ani zmian w ofertach. Niezaznaczone punkty pozostają wymaganiami lub czynnościami do weryfikacji.
