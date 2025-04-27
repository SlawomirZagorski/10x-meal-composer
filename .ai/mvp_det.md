<conversation_summary>
<decisions>
1. Preferencje żywieniowe obejmują alergie, diety roślinne, diety eliminacyjne, diety specjalne (np. keto) oraz indywidualne upodobania.
2. Lista dostępnych składników jest wprowadzana jako wolny tekst przez użytkownika.
3. Wyposażenie kuchni domyślnie zawiera sprzęt podstawowy; dodatkowe urządzenia (frytkownica powietrzna, Ninja Creami, maszyna do chleba) są opcjonalne, liczba sztuk nieistotna.
4. AI (przez Openrouter) generuje kandydatów na przepisy; użytkownik może zaakceptować (zapis), odrzucić lub poprosić o iterację z uwagami.
5. Iteracje przepisów są nieograniczone; użytkownik może w każdej chwili anulować zmiany i powrócić do poprzednio zaakceptowanego przepisu.
6. Onboarding pozwala pominąć uzupełnienie profilu, ale przy każdym generowaniu przepisu, gdy profil jest niepełny, wyświetlane jest przypomnienie o uzupełnieniu.
7. Kluczowymi personami są początkujący i średniozaawansowani kucharze domowi.
8. “1 przepis w tygodniu” to co najmniej jedna zaakceptowana propozycja w danym tygodniu kalendarzowym, mierzone przez zdarzenia akceptacji.
9. Wymagania prawne i bezpieczeństwa: RODO oraz OWASP Top Ten 2025 i Mobile Top 10.
10. Budżet AI w MVP nie jest limitowany; system jedynie zbiera koszty per użytkownik.
11. Analityka: wszystkie zdarzenia (profil, generowanie, iteracje, akceptacje) są zapisywane w bazie danych; raportowanie odbywa się zewnętrznie.
12. Termin realizacji MVP: 2 tygodnie przy pracy jednej osoby poza etatem.
</decisions>
<matched_recommendations>
1. Opracować szczegółowe persony i scenariusze użytkownika.
2. Przygotować mapę ścieżek użytkownika dla flow: rejestracja → profil → lista przepisów → generowanie przepisu → iteracja/akceptacja/odrzucenie → zapis.
3. Stworzyć makiety interfejsów: ekran listy przepisów, ekran profilu, kreator przepisu (wolny tekst składników), panel recenzji i iteracji (z możliwością anulowania zmian).
4. Zdefiniować schemat danych dla preferencji, wolnotekstowych składników, sprzętu, kandydatów na przepisy i zaakceptowanych przepisów.
5. Zaplanować techniczne wymagania integracji AI przez Openrouter (format danych, SLA, monitorowanie).
6. Uruchomić zapisywanie zdarzeń analitycznych w bazie danych i zdefiniować metryki do raportowania (koszt per użytkownik, profil, generowanie, akceptacje).
7. Zidentyfikować i ocenić ryzyka (jakość AI, adopcja, prywatność, zgodność z RODO) oraz opracować plany mitigacji.
8. Ustalić harmonogram iteracyjny z kamieniami milowymi i czasem na testy użyteczności.
9. Zaangażować interesariuszy: UX, AI, bezpieczeństwo, prawny.
</matched_recommendations>
<prd_planning_summary>
1. Główne wymagania funkcjonalne produktu
* Rejestracja i profil z preferencjami żywieniowymi (alergie, diety, upodobania) i sprzętem kuchennym.
* Możliwość przeglądania zapisanych przepisów na liście przepisów oraz filtracja po słowach kluczowych
* Wprowadzanie składników w wolnym tekście.
* Moduł AI (Openrouter) generujący nieograniczoną liczbę iteracji kandydatów na przepisy.
* Interfejs recenzji: akceptacja, odrzucenie, iteracja z uwagami i możliwość anulowania zmian do ostatniego zaakceptowanego przepisu.
* Zapis zaakceptowanych przepisów do bazy danych.
* Przypomnienie o uzupełnieniu profilu przy niepełnym profilu.
* Zbieranie kosztów AI per użytkownik.
* Zgodność z RODO oraz standardami OWASP Top Ten 2025 i Mobile Top 10.
* Zapis wszystkich zdarzeń analitycznych w bazie danych.
1. Kluczowe historie użytkownika i ścieżki
2. Nowy użytkownik rejestruje się, pomija lub uzupełnia profil, następnie dodaje składniki w wolnym tekście.
3. Użytkownik generuje kandydatów na przepisy; przegląda i może akceptować, odrzucać lub iterować bez limitu, z opcją anulowania do poprzedniego stanu.
4. Po akceptacji przepis jest zapisywany; użytkownik przegląda bibliotekę zapisanych przepisów.
5. Przy każdej próbie generowania system przypomina o niepełnym profilu.
6. Kryteria sukcesu i pomiar
* 90% użytkowników z wypełnionym profilem (zdarzenia uzupełnienia profilu).
* 75% użytkowników generuje co najmniej jedną zaakceptowaną propozycję tygodniowo (zdarzenia akceptacji).
* 90% sesji generowania kończy się akceptacją lub iteracją (stosunek akceptacji i iteracji do wszystkich wygenerowanych kandydatów).
* Monitorowanie kosztów AI per użytkownik.
1. Nierozwiązane kwestie lub dalsze wyjaśnienia
Brak – wszystkie kluczowe obszary zostały doprecyzowane.
</prd_planning_summary>
<unresolved_issues>
Brak nierozwiązanych kwestii.
</unresolved_issues>
</conversation_summary>
