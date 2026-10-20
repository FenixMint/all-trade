# Uprawnienia OAuth — MZ-Trading

Uprawnienia aplikacji powinny być ograniczone zarówno w **panelu Allegro Developer Apps**, jak i w zakresie żądanym przy uzyskaniu tokena. Użytkownik `mztrade` musi zaakceptować dostęp. Rzeczywiste aktualnie skonfigurowane scope'y nie są potwierdzone przez publiczne repozytorium.

## Rozpoczęcie od uprawnień odczytu

| Scope | Uzasadnienie |
| --- | --- |
| `allegro:api:profile:read` | Weryfikacja tożsamości autoryzowanego konta |
| `allegro:api:sale:offers:read` | Katalog produktu, lista i szczegóły ofert, podgląd prognozy opłat |
| `allegro:api:sale:settings:read` | Ustawienia sprzedaży, dostępne cenniki i opcje dostawy |
| `allegro:api:billing:read` | Dane o opłatach i rozliczeniach konta |

Powyższe zakresy są **proponowaną początkową konfiguracją do zatwierdzenia przez operatora**, a nie potwierdzeniem faktycznego aktywowania danego scope'a.

## Uprawnienia przyszłe, niewłączone w ramach samej dokumentacji

- `allegro:api:sale:offers:write` — szerokie uprawnienie do tworzenia, edycji, publikacji i kończenia ofert. Może zostać użyte wyłącznie po dodatkowych testach i świadomym dopuszczeniu przez operatora do konkretnych operacji.
- `allegro:api:orders:read` — tylko w razie zatwierdzonej potrzeby analizy zamówień i odpowiednio określonych zasad przetwarzania danych. Na początku nie jest wymagane do katalogowego Matchera i samych własnych ofert.

Nie wnioskujemy z góry o scope'ach dotyczących płatności, wiadomości, zmian ustawień konta, kampanii czy logistyki, jeśli moduł faktycznie nie wykonuje tych operacji.

## Rozdział tokenów

- Token aplikacyjny `client_credentials` służy tylko do zasobów dopuszczających ten rodzaj uwierzytelniania.
- OAuth użytkownika (np. Device Flow) służy do zasobów prywatnych sprzedawcy.
- Token przyznany dla określonego konta, środowiska i scopes nie upoważnia do innego konta ani nie zastępuje wewnętrznej zgody na konkretne operacje.

## Zasada minimalizacji dostępu

Dodanie scope'a w panelu nie jest automatyczną zgodą MZ Trade na wykonywanie zmian. Nowe możliwości włącza się dopiero w wersji programu z poprawnie zaimplementowaną kontrolą dostępu, walidacją celu i rejestrem czynności.

Oficjalna lista uprawnień: [Allegro — OAuth, scopes](https://developer.allegro.pl/tutorials/uwierzytelnianie-i-autoryzacja-zlq9e75GdIR).
