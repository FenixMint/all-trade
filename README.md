# MZ-Trading

**Moduł integracji Allegro REST API dla systemu FX NEXUS — MZ Trade**

[O aplikacji](ABOUT.md) · [Integracja](docs/INTEGRATION.md) · [Zakresy OAuth](docs/SCOPES.md) · [User-Agent](docs/USER-AGENT.md) · [Bezpieczeństwo](SECURITY.md) · [Kontakt](CONTACT.md) · [Kontrola gotowości](docs/RELEASE-CHECKLIST.md) · [Źródła Allegro](docs/SOURCES.md)

## Identyfikacja

| Pole | Wartość |
| --- | --- |
| **Nazwa aplikacji Allegro** | **MZ-Trading** |
| **Repozytorium informacyjne** | [FenixMint/all-trade](https://github.com/FenixMint/all-trade) |
| **System nadrzędny** | FX NEXUS |
| **Podmiot korzystający** | MZ Trade s.c. |
| **Konto sprzedawcy Allegro** | `mztrade` |
| **Cel integracji** | Wewnętrzna obsługa sprzedaży części motoryzacyjnych poprzez oficjalne Allegro REST API |
| **Dystrybucja** | Narzędzie do użytku wewnętrznego; to repozytorium jest publicznym opisem integracji, a nie instalatorem |
| **Rejestracja aplikacji** | Nazwa `MZ-Trading` zgłoszona przez właściciela jako już zarejestrowana w Allegro; konfiguracja API i autoryzacja produkcyjna **niezależnie wymagają weryfikacji** |

**MZ-Trading** jest modułem większej platformy **FX NEXUS**. Repozytorium stanowi publiczny punkt informacyjny do identyfikacji aplikacji korzystającej z Allegro REST API oraz kontaktu z jej administratorem. Nie jest to osobny system sprzedażowy, publiczna aplikacja internetowa ani repozytorium produkcyjnego kodu FX NEXUS.

## Zastosowania

- **Katalog produktów i Matcher:** wyszukiwanie i weryfikacja części motoryzacyjnych według marki, numerów producenta (MPN), GTIN, kategorii i innych dostępnych danych katalogowych. Wynik dopasowania jest poddawany kontroli przed wykorzystaniem w ofercie.
- **Własne oferty Allegro:** odczyt ofert i ich parametrów, statusu, dostępności oraz cen konta `mztrade`.
- **Koszty sprzedaży:** analiza dostępnych w API informacji o opłatach, prowizjach i ustawieniach dostawy.
- **Planowane operacje edycji:** po odrębnej autoryzacji i weryfikacji zabezpieczeń — kontrolowane aktualizacje konkretnych ofert, w tym cen. Sam opis celu nie oznacza włączenia operacji zapisu.

Zakres faktycznie uruchomionych funkcji i zgód może być węższy niż docelowe możliwości; szczegóły: [funkcje i stan integracji](docs/INTEGRATION.md) oraz [zakresy OAuth](docs/SCOPES.md).

## Identyfikacja żądań API (User-Agent)

Docelowy wzór:

```text
MZ-Trading/<wersja-faktycznie-uruchomionego-programu> (+https://github.com/FenixMint/all-trade)
```

Wdrożona wersja musi odpowiadać rzeczywistemu wydaniu oprogramowania; przykładowego numeru nie należy przedstawiać jako produkcyjnego. Nazwa `MZ-Trading` ma odpowiadać dokładnej nazwie aplikacji w Allegro Developer Apps. Przed użyciem identyfikator powinien przejść [oficjalny walidator Allegro](https://apps.developer.allegro.pl/user-agent). Zapytania OAuth oraz REST API muszą być poprawnie identyfikowane.

## Ochrona danych i bezpieczeństwo

Wykorzystujemy wyłącznie udostępnione i dozwolone zasoby oficjalnego REST API. Dostęp do danych sprzedawcy wymaga uprawnień OAuth; login, hasło i kody 2FA nie są elementami konfiguracji przekazywanej aplikacji. Klucze i tokeny nie mogą znajdować się w tym repozytorium.

Zasady i ograniczenia: [SECURITY.md](SECURITY.md), [Informacje o danych](docs/DATA.md), [Zasady korzystania](docs/USAGE.md).

## Kontakt i problemy techniczne

- Publiczne zgłoszenia **bez danych poufnych**: [GitHub Issues](https://github.com/FenixMint/all-trade/issues).
- [Informacje o kontakcie i zgłoszeniach bezpieczeństwa](CONTACT.md).

> Repozytorium jest dokumentacją informacyjną niezależnej integracji MZ Trade. **Nie jest oficjalnym produktem Allegro ani potwierdzeniem certyfikacji lub aprobaty Allegro.** Wszystkie nazwy i znaki towarowe należą do ich uprawnionych właścicieli.

---

*EN: MZ-Trading is MZ Trade's internal Allegro REST API integration module within FX NEXUS, providing automotive product-catalog matching and seller-account offer management. This public repository documents its identity, intended functionality, security principles and support contact; it does not expose production software or credentials.*
