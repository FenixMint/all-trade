# Integracja MZ-Trading z Allegro REST API

## Tożsamość

| Element | Wartość |
| --- | --- |
| Aplikacja | `MZ-Trading` (nazwa wskazana przez OWNER jako zarejestrowana w Allegro) |
| Publiczna strona informacyjna | https://github.com/FenixMint/all-trade |
| Konto sprzedawcy | `mztrade` |
| System nadrzędny | FX NEXUS |
| Repozytorium | Informacyjne, bez produkcyjnego kodu i danych firmowych |
| Status uwierzytelnienia | Niepotwierdzony na podstawie publicznego repozytorium |

## Założenia modułu

**Matcher i dane katalogowe:** wspomaganie identyfikacji części przez markę, numery producenta (MPN), GTIN, kategorię i inne zgodne z REST API atrybuty. Katalog Allegro jest jednym ze źródeł; wyszukanie produktu nie jest niezależną certyfikacją prawidłowości oferty.

**Sprzedaż:** odczyt i porównywanie ofert własnego konta, ich cen, statusów, dostępności i szczegółów, pod warunkiem właściwych uprawnień. Umożliwia to weryfikację bieżącego stanu przed przygotowaniem zmiany.

**Ustawienia i koszty:** dostęp do udostępnionych danych opłat oraz ustawień dostawy dla potrzeb wewnętrznej analizy kosztów. Szacowane opłaty nie muszą być równe finalnym opłatom transakcyjnym.

**Przyszłe zarządzanie ofertami:** edycja wskazanych ofert po zatwierdzeniu przez operatora, przy sprawdzeniu tożsamości konta, identyfikatora oferty i szczegółowego zakresu zmian.

## Sposób komunikacji

- Tylko dokumentowane zasoby HTTPS Allegro REST API, poprawny `Accept`, `Authorization` i identyfikujący nagłówek `User-Agent`.
- Do publicznego katalogu wyłącznie dopuszczony przez konkretny zasób typ autoryzacji, np. `client_credentials`.
- Do danych własnego konta sprzedawcy token uzyskany w ramach OAuth z autoryzacją użytkownika, np. `Device flow`, jeśli jest zgodny z faktycznie zarejestrowanym typem aplikacji.
- `GET /me` w celu zweryfikowania, że token należy do właściwego konta, a nie tylko że jest ważny.
- Bezpieczne ponawianie jedynie dozwolonych odczytów i respektowanie błędów oraz limitów platformy. HTTP `429` to sygnał do ograniczenia intensywności zapytań.
- Odrębne testy środowiska Sandbox; poświadczeń produkcyjnych nie wykorzystuje się w środowisku testowym.

## Przykłady zasobów (orientacyjne, zawsze sprawdzać bieżącą dokumentację)

| Cel | Zasób | Operacja |
| --- | --- | --- |
| Tożsamość sprzedawcy | `/me` | GET |
| Katalog produktów | `/sale/products` | GET |
| Lista własnych ofert | `/sale/offers` | GET |
| Szczegóły oferty | `/sale/product-offers/{offerId}` | GET |
| Aktualizacja określonych pól oferty (przyszłość) | `/sale/product-offers/{offerId}` | PATCH |

**Ważne:** PATCH może również zmienić status publikacji, nie tylko cenę. Implementacja edycji cen musi ograniczać wysyłane pola i blokować zmianę statusu poza osobnym zatwierdzonym procesem. Przy odpowiedzi `202 Accepted` trzeba zweryfikować wynik wskazanym przez Allegro zasobem operacji.

## Dostęp i uprawnienia

Zobacz [SCOPES.md](SCOPES.md), [USER-AGENT.md](USER-AGENT.md), [SECURITY.md](../SECURITY.md) oraz [źródła](SOURCES.md).

## Aktualny etap

To repozytorium dokumentuje **zamierzone funkcje** modułu. Fakt rejestracji nazwy aplikacji został przekazany przez właściciela; nie oznacza to, że przeprowadzono produkcyjne uwierzytelnienie sprzedawcy, aktywowano zapisy, przetestowano wymaganą ochronę sekretów lub zweryfikowano działanie obecnego konektora.
