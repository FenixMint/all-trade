# Informacje o danych — MZ-Trading

## Zakres i przeznaczenie

MZ-Trading to moduł przeznaczony do wewnętrznej obsługi działalności sprzedażowej MZ Trade przez oficjalne Allegro REST API. Zakres przetwarzanych danych zależy od funkcji faktycznie wdrożonych i uprawnień nadanych aplikacji.

Możliwe rodzaje danych obejmują:

- dane katalogowe części, np. kategoria, producent, nazwa, MPN i GTIN,
- dane identyfikacyjne firmowego konta sprzedawcy potrzebne do weryfikacji autoryzacji,
- dane własnych ofert, np. identyfikator oferty, cena, status, asortyment, ilość, parametry,
- dane o opłatach i cennikach w zakresie dostępnym w autoryzowanych zasobach,
- minimalne zdarzenia diagnostyczne związane z komunikacją API.

**Dane kupujących, zamówień i wiadomości nie są automatycznie częścią początkowego zakresu.** Każde rozszerzenie wymaga decyzji, odpowiednich uprawnień oraz oceny zasad przetwarzania danych osobowych.

## Źródło i zakres uprawnienia

Dane z Allegro mają pochodzić wyłącznie z zasobów API udostępnionych dla konkretnego celu, tokena i konta. Aplikacja nie nabywa przez sam dostęp do API praw do swobodnej redystrybucji danych, zdjęć, opisów czy analiz dotyczących innych sprzedawców.

## Bezpieczeństwo i okres przechowywania

Dostęp do danych powinien być ograniczony do uprawnionych osób i procesów; poświadczenia nie powinny pojawiać się w dokumentacji, logach ani publicznych repozytoriach. Okres przechowywania i środki bezpieczeństwa powinny być ustalone osobno dla poszczególnych kategorii danych na podstawie rzeczywistego wdrożenia, potrzeb biznesowych i obowiązków prawnych — ten publiczny dokument nie deklaruje niezweryfikowanego okresu retencji.

Repozytorium `FenixMint/all-trade` nie służy do zbierania danych osobowych kupujących, tokenów API, rachunków, cenników wewnętrznych ani historii ofert.

## Zgłoszenia dotyczące danych

Informacje o kanale kontaktu: [CONTACT.md](../CONTACT.md). Szczegółów lub danych wrażliwych nie należy publikować w GitHub Issues.
