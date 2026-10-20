# Bezpieczeństwo — MZ-Trading

MZ-Trading stanowi moduł komunikujący się z Allegro REST API. Ten dokument przedstawia **wymagania projektowe i zasady odpowiedzialnego korzystania**, a nie niezależnie potwierdzony audyt bezpieczeństwa wdrożenia.

## Oficjalna autoryzacja

- Do uwierzytelniania i autoryzacji wykorzystywane są dozwolone standardowe mechanizmy **OAuth 2.0** Allegro.
- Dostęp aplikacyjny do dozwolonych danych publicznych oraz dostęp do danych konta sprzedawcy są rozdzielane zgodnie z dokumentacją zasobu i typem tokena.
- Moduł nie powinien zbierać ani przechowywać hasła, kodów 2FA czy sesji przeglądarkowej Allegro.
- Przyznane uprawnienia (OAuth scopes) powinny odpowiadać rzeczywistym potrzebom. Odczyt danych sprzedawcy nie jest zgodą na modyfikowanie ofert.
- Token użytkownika ma być używany tylko w powiązaniu z właściwym kontem, środowiskiem i zakresem uprawnień.

## Klucze i tokeny

- **Client Secret, access_token, refresh_token, kody autoryzacyjne oraz logi z danymi wrażliwymi nigdy nie trafiają do publicznego repozytorium**, zgłoszeń ani plików przykładowych.
- Poświadczenia muszą być ograniczone do upoważnionego środowiska wykonawczego, z ochroną plików/sekretów i bez ich ujawniania w logach.
- Odświeżanie tokena powinno uwzględniać rotację, ograniczenie współbieżności i bezpieczny zapis.
- Tokeny środowisk testowych i produkcyjnych muszą być rozdzielone.

## Zmiany ofert i ograniczanie błędów

Operacje zmieniające stan oferty, cenę, dostępność lub publikację są traktowane jako działania podwyższonego ryzyka. Przed ich uruchomieniem potrzebne są: jawna zgoda upoważnionego operatora, weryfikacja dokładnego konta i identyfikatora oferty, kontrola żądanej zmiany, ślad audytu i potwierdzenie wyniku w API. Przy niepewnym wyniku operacji nie należy jej automatycznie powtarzać.

**Status:** dokumentacja nie potwierdza, że wszystkie opisane powyżej mechanizmy są już zaimplementowane i przetestowane. Do czasu spełnienia bramek bezpieczeństwa operacje modyfikujące oferty pozostają wyłączone.

## Zasady integracji

Korzystanie wyłącznie z dozwolonych zasobów REST API, poszanowanie warunków Allegro, poprawne identyfikowanie żądań własnym User-Agent, respektowanie ograniczeń prędkości i odpowiedzi 429. Zabronione jest pozyskiwanie danych metodą obchodzenia API lub publikowanie danych, do których aplikacja nie ma praw.

## Zgłaszanie problemów bezpieczeństwa

Zobacz [CONTACT.md](CONTACT.md). Nie zamieszczaj informacji o podatnościach ani tokenów w publicznych Issues. W razie podejrzenia wycieku operator powinien odizolować dostęp i przeprowadzić odpowiednią procedurę odwołania/rotacji poświadczeń.

Źródła: [Oficjalne wymagania Allegro](docs/SOURCES.md).
