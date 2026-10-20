# O aplikacji MZ-Trading

**Nazwa aplikacji w Allegro:** `MZ-Trading`  
**Podmiot korzystający:** MZ Trade s.c.  
**Konto sprzedażowe:** `mztrade`  
**System nadrzędny:** FX NEXUS  
**Publiczna strona informacyjna:** https://github.com/FenixMint/all-trade

## Przeznaczenie

MZ-Trading jest modułem integracji motoryzacyjnej działalności MZ Trade z oficjalnym Allegro REST API. Stanowi część systemu FX NEXUS, który korzysta z wymiennych konektorów usług zewnętrznych.

Zakres przewidziany dla modułu:

1. Odczyt danych produktowych i katalogowych Allegro, wspierający dopasowanie części według MPN, marki, GTIN i danych technicznych.
2. Odczyt oraz zestawianie własnych ofert konta sprzedażowego `mztrade` i ich statusów.
3. Dostęp do danych o kosztach, naliczonych opłatach i ustawieniach sprzedaży, w zakresie uprawnionych zasobów API.
4. **Planowana funkcja:** aktualizacja wybranych własnych ofert (w tym cen) po dopuszczeniu operacji zapisu, weryfikacji zgodności i zatwierdzeniu przez operatora.

Dopasowanie katalogowe nie jest samo w sobie dowodem zgodności danej części z pojazdem ani upoważnieniem do publikowania ogłoszenia. Przed zmianami ofert niezbędna jest kontrola poprawności identyfikacji, legalności i aktualności informacji o produkcie.

## Odbiorcy i dostępność

Moduł jest przeznaczony do działalności wewnętrznej MZ Trade. Nie oferujemy tutaj publicznej usługi logowania do kont Allegro, udostępniania tokenów, hurtowej ekstrakcji danych Allegro ani niezależnej usługi marketplace dla dowolnych podmiotów. Repozytorium publiczne służy celom informacyjnym i identyfikacji ruchu API.

## Stan potwierdzenia

Nazwa aplikacji **MZ-Trading** jest przyjęta przez właściciela. **Rejestrację aplikacji w Allegro Developer Apps zaplanowano dopiero po zakończeniu weryfikacji 2FA** na dotychczasowym koncie sprzedażowym `mztrade`. User-Agent, Client ID/Secret i autoryzacja OAuth nie zostały w tej sesji skonfigurowane ani zweryfikowane. Kontrole będą odbywać się poza repozytorium.

## Powiązania i niezależność

MZ-Trading jest modułem **FX NEXUS**, nie odrębną kopią pełnego programu. Allegro jest dostawcą zewnętrznej usługi API. Nazwa Allegro oraz pozostałe znaki handlowe nie oznaczają sponsorowania, partnerstwa ani certyfikacji tej integracji przez Allegro.

Kontakt: [CONTACT.md](CONTACT.md).
