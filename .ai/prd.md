# Dokument wymagań produktu (PRD) - Meal Composer

## 1. Przegląd produktu
Meal Composer to aplikacja umożliwiająca modyfikację ulubionych przepisów w oparciu o aktualnie posiadane składniki, preferencje żywieniowe oraz dostępne urządzenia kuchenne. System wykorzystuje AI (za pośrednictwem Openrouter) do generowania kandydatów na przepisy oraz interaktywną recenzję, aby użytkownik mógł zaakceptować, odrzucić lub iterować przepisy.

## 2. Problem użytkownika
Użytkownicy (początkujący i średniozaawansowani kucharze domowi) mają trudności z dostosowaniem swoich receptur do dostępnych składników, zachowując przy tym pożądany smak i strukturę potrawy. Chcą prostego narzędzia, które podpowie im gotowe rozwiązania i pozwoli szybko eksperymentować.

## 3. Wymagania funkcjonalne
- bezpieczna rejestracja i logowanie użytkownika
- profil użytkownika z preferencjami żywieniowymi (alergie, diety roślinne, eliminacyjne, keto, indywidualne upodobania) i listą sprzętu kuchennego (podstawowe + dodatkowe urządzenia)
- wprowadzanie dostępnych składników w formie wolnego tekstu
- integracja z AI (Openrouter) do generowania nieograniczonej liczby kandydatów na przepisy
- interaktywny interfejs recenzji kandydatów: akceptacja (zapis do bazy), odrzucenie, iteracja z uwagami oraz możliwość przywrócenia ostatniego zaakceptowanego przepisu
- wyświetlanie przypomnienia o uzupełnieniu profilu przy próbie generowania, gdy profil jest niepełny
- przeglądanie i filtrowanie zapisanych przepisów po słowach kluczowych
- zbieranie i zapisywanie w bazie danych wszystkich zdarzeń analitycznych (profil, generowanie, iteracje, akceptacje)
- zbieranie kosztów AI per użytkownik
- zgodność z RODO oraz standardami OWASP Top Ten 2025

## 4. Granice produktu
zakres MVP:
- CRUD dla zaakceptowanych przepisów tekstowych
- generowanie i recenzja kandydatów na przepisy
- ręczne wprowadzanie składników (wolny tekst)
- profil użytkownika i lista przepisów
- przypomnienia o uzupełnieniu profilu
- podstawowe monitorowanie zdarzeń i kosztów AI

poza zakresem MVP:
- import przepisów z URL
- rozbudowane multimedia (zdjęcia, wideo)
- udostępnianie przepisów i funkcje społecznościowe
- rozbudowana współpraca między użytkownikami

## 5. Historyjki użytkowników

### US-001: Rejestracja konta
Opis: użytkownik tworzy konto, podając email i hasło.
Kryteria akceptacji:
- formularz rejestracji przyjmuje email i hasło
- konto zostaje utworzone przy poprawnych danych
- użytkownik jest zalogowany po rejestracji
- przy błędnych danych wyświetlany jest komunikat o błędzie

### US-002: Logowanie
Opis: użytkownik loguje się do istniejącego konta.
Kryteria akceptacji:
- formularz logowania przyjmuje email i hasło
- poprawne dane przekierowują do pulpitu użytkownika
- przy niepoprawnych danych wyświetlany jest komunikat o błędzie

### US-003: Uzupełnienie profilu
Opis: użytkownik dodaje preferencje żywieniowe i sprzęt kuchenny.
Kryteria akceptacji:
- użytkownik może zaznaczyć kategorie diet i wpisać indywidualne upodobania
- użytkownik może wpisać dodatkowy sprzęt kuchenny
- dane są zapisane i widoczne w profilu

### US-004: Edycja profilu
Opis: użytkownik modyfikuje istniejące preferencje i sprzęt.
Kryteria akceptacji:
- użytkownik może edytować i zapisać zmiany w profilu
- zmiany są natychmiast widoczne

### US-005: Przeglądanie zapisanych przepisów
Opis: użytkownik przegląda bibliotekę zaakceptowanych przepisów.
Kryteria akceptacji:
- lista przepisów pozwala na filtrowanie po słowach kluczowych
- kliknięcie przepisu pokazuje szczegóły
- użytkownik może edytować lub usunąć przepis

### US-006: Dodawanie nowego przepisu
Opis: użytkownik na głównym ekranie może zainicjować dodanie nowego przepisu.
Kryteria akceptacji:
- użytkownik ma musi wprowadzić treść przepisu w pole tekstowe
- użytkownik może wypełnić też opcjonalnie pole tesktowe uwag odnośnie składników, np. brak jakiegoś składnika lub wymuszenie użycia innego
- kliknięcie przycisku generowania wysyła zapytanie do Openrouter
- system wyświetla co najmniej jednego kandydata w czasie do 10s
- wyświetlana jest animacja lub komunikat ładowania

### US-007: Tworzenie alternatywnej wersji zapisanego przepisu
Opis: użytkownik na ekranie zapisanego przepisu może zainicjować dodanie nowego przepisu na podsatwie aktualnie otwartego.
Kryteria akceptacji:
- działa tak samo jako US-006, z tym, że pole przepisu jest ju wstępnie wypełnione treścią aktualnie otwartego przepisu

### US-008: Akceptacja przepisu
Opis: użytkownik akceptuje kandydata i zapisuje go.
Kryteria akceptacji:
- kliknięcie akceptacji zapisuje przepis w bazie danych
- użytkownik widzi potwierdzenie zapisu
- przepis jest widoczny w bibliotece przepisów

### US-009: Odrzucenie przepisu
Opis: użytkownik odrzuca kandydata na przepis.
Kryteria akceptacji:
- kliknięcie odrzucenia usuwa kandydata z widoku
- użytkownik może wygenerować kolejnego kandydata

### US-010: Iteracja przepisu
Opis: użytkownik prosi o zmianę kandydata, podając uwagi.
Kryteria akceptacji:
- użytkownik może wpisać notatki zmian i wysłać iterację
- system zwraca zmodyfikowanego kandydata

### US-011: Anulowanie iteracji
Opis: użytkownik przywraca ostatnio zaakceptowany przepis.
Kryteria akceptacji:
- kliknięcie przywrócenia cofniętych zmian
- system wyświetla poprzedni zapisany przepis

### US-012: Przypomnienie o uzupełnieniu profilu
Opis: system wyświetla przypomnienie, gdy profil jest niepełny.
Kryteria akceptacji:
- przy próbie generowania niepełny profil wyświetla komunikat
- użytkownik może zamknąć komunikat lub przejść do profilu

### US-013: Obsługa błędów AI
Opis: system reaguje na błędy komunikacji z AI.
Kryteria akceptacji:
- w przypadku błędu wyświetlana jest informacja o problemie
- użytkownik może ponowić próbę generowania

### US-014: Zarządzanie ustawieniami prywatności
Opis: użytkownik wyraża zgodę na przetwarzanie danych zgodnie z RODO.
Kryteria akceptacji:
- przed rejestracją wyświetlana jest polityka prywatności
- użytkownik zaznacza zgodę, która jest zapisana

### US-015: Wylogowanie
Opis: użytkownik kończy sesję i wylogowuje się.
Kryteria akceptacji:
- kliknięcie wylogowania usuwa sesję i przekierowuje do ekranu logowania

### US-016: Resetowanie hasła
Opis: użytkownik może zresetować hasło, otrzymując email z linkiem resetującym.
Kryteria akceptacji:
- użytkownik może zainicjować reset hasła, podając swój email
- system wysyła wiadomość email z linkiem resetującym hasło (w środowisku testowym symulacja)
- link umożliwia ustawienie nowego hasła
- po zmianie hasła użytkownik może zalogować się nowym hasłem
- w przypadku nieprawidłowego tokena lub błędu wysyłki wyświetlany jest komunikat o błędzie

### US-017: Obsługa błędów sieci/API
Opis: system reaguje na błędy sieciowe i błędy backendu.
Kryteria akceptacji:
- przy timeoutcie lub braku połączenia wyświetlany jest komunikat o problemie z połączeniem
- użytkownik może ponowić operację (generowanie, pobieranie przepisów, zapis)
- błąd jest logowany w systemie analitycznym

### US-018: Zgoda na pliki cookie i analitykę
Opis: użytkownik wyraża zgodę na korzystanie z plików cookie i analitykę.
Kryteria akceptacji:
- przy pierwszym wejściu wyświetlany jest baner zgody na pliki cookie
- użytkownik może zaakceptować lub odrzucić cookies
- wybór jest zapisywany i respektowany przy kolejnych wizytach

## 6. Metryki sukcesu
- 90% użytkowników kończy z kompletnym profilem (monitorowane przez zdarzenia profilu)
- 75% użytkowników generuje co najmniej jedną zaakceptowaną propozycję tygodniowo
- 90% sesji generowania kończy się akceptacją lub iteracją
- zbieranie i analiza kosztów AI per użytkownik
