# Identyfikacja MZ-Trading w User-Agent

Oficjalne Allegro wymaga niestandardowego nagłówka `User-Agent` umożliwiającego identyfikację aplikacji i kontakt z jej właścicielem.

## Nazwa i informacyjny adres URL

- **Nazwa wybrana przez OWNER; rejestracja w Developer Apps jeszcze planowana:** `MZ-Trading`
- **Strona informacyjna:** https://github.com/FenixMint/all-trade
- **Wersja:** rzeczywista wersja uruchomionego modułu FX NEXUS; status wydania produkcyjnego pozostaje do potwierdzenia.

## Wzór

```text
MZ-Trading/<RZECZYWISTA_WERSJA> (+https://github.com/FenixMint/all-trade)
```

Przykład formatu (**wyłącznie przykład, nie stwierdzenie wdrożonej wersji**):

```text
MZ-Trading/1.0.0 (+https://github.com/FenixMint/all-trade)
```

Nie zmieniać części `MZ-Trading` na nazwę repozytorium `all-trade`, nazwę wcześniejszego `MZ-Parts-Matcher` ani ogólną nazwę systemu `FX-NEXUS`. W razie odmiennej pisowni w faktycznym panelu aplikacji pierwszeństwo ma rzeczywista nazwa rejestracyjna potwierdzona przez OWNER w Developer Apps.

Nagłówek należy wysyłać przy **każdym żądaniu HTTP** do Allegro API, wraz z żądaniami OAuth. Nie należy stosować domyślnego identyfikatora biblioteki HTTP.

## Walidacja przed uruchomieniem

1. Zweryfikować faktyczną nazwę aplikacji w [Allegro Developer Apps](https://apps.developer.allegro.pl/).
2. Potwierdzić rzeczywistą wersję zainstalowanego kodu.
3. Sprawdzić publiczny adres repozytorium oraz czy zawiera aktualny opis i kontakt.
4. Wprowadzić pełny identyfikator do [oficjalnego walidatora User-Agent](https://apps.developer.allegro.pl/user-agent).
5. Wykonać kontrolowany test wysyłania tego samego nagłówka na wszystkich ścieżkach, także OAuth, i zweryfikować brak domyślnych fallbacków.

**Status: WSTRZYMANE DO ZAKOŃCZENIA 2FA I REJESTRACJI APLIKACJI.** Nie ustalono produkcyjnego numeru wersji i nie uruchomiono walidatora. Ten plik jest dokumentacją przyszłego etapu, a nie potwierdzeniem dostępu API.

Oficjalny opis formatu: [Allegro FAQ](https://developer.allegro.pl/faq) i [Informacje podstawowe](https://developer.allegro.pl/tutorials/informacje-podstawowe-b21569boAI1).
