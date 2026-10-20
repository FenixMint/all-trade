# Zasady korzystania — MZ-Trading

## Przeznaczenie

MZ-Trading jest wewnętrznym modułem FX NEXUS dla MZ Trade, którego zadaniem jest obsługa własnego konta Allegro oraz wspomaganie identyfikacji części motoryzacyjnych przy użyciu autoryzowanego REST API.

Moduł nie jest ogólnodostępną usługą logowania do Allegro i nie pełni roli zamiennego dostawcy autoryzacji. Dostęp użytkowników do funkcji operacyjnych określa właściciel środowiska.

## Zasady korzystania z API

- Korzystanie wyłącznie z oficjalnych, udostępnionych i dozwolonych endpointów oraz dozwolonych typów autoryzacji.
- Przestrzeganie regulaminu Allegro, praw osób trzecich i praw do treści produktowych; bez nieautoryzowanego scrapingu.
- Prawidłowa identyfikacja ruchu przy użyciu nagłówka `User-Agent`.
- Ograniczanie zakresów OAuth do potrzebnych operacji i kontrola właściwego konta sprzedawcy.
- Poszanowanie limitów częstotliwości i reakcji API, w tym 401, 403 i 429.
- Przed zatwierdzeniem zmian ofert — prawidłowa tożsamość produktu, odpowiednia informacja o bezpieczeństwie produktu, legalne materiały i zweryfikowane fakty.
- Żadna funkcja nie daje automatycznego prawa do kopiowania danych innych sprzedawców lub dalszego ich rozpowszechniania.

## Operacje sprzedażowe

Dostęp aplikacji do scope'a umożliwiającego modyfikowanie ofert nie jest równoznaczny z prawem do masowej aktualizacji bez kontroli. Wprowadzanie zmian powinno być ograniczone do określonego konta, dokładnych identyfikatorów ofert i zatwierdzonego zakresu. Operacje niepotwierdzone pozostają w stanie wymagającym wyjaśnienia.

## Stan i odpowiedzialność

To repozytorium opisuje zasady i docelowe funkcje integracji. Nie dowodzi samo w sobie certyfikacji przez Allegro, udanego wdrożenia, przeprowadzonej autoryzacji użytkownika ani przejścia testów bezpieczeństwa.

Regulamin: https://developer.allegro.pl/rules. Dokument bezpieczeństwa: [SECURITY.md](../SECURITY.md).
