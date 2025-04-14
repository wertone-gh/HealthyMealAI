# Dokument wymagań produktu (PRD) - HealthyMeal

## 1. Przegląd produktu

HealthyMeal to webowa aplikacja umożliwiająca użytkownikom dostosowywanie przepisów kulinarnych znalezionych w internecie do ich indywidualnych potrzeb żywieniowych. Aplikacja wykorzystuje sztuczną inteligencję do automatycznej modyfikacji przepisów zgodnie z preferencjami użytkownika, takimi jak nietolerancje pokarmowe, alergie czy ograniczenia dietetyczne.

Główne cechy produktu:
- Prosta rejestracja i logowanie przez OAuth (Facebook, Apple, Microsoft)
- Zapisywanie preferencji żywieniowych w profilu użytkownika
- Wyszukiwanie przepisów dostępnych w internecie
- Automatyczna modyfikacja przepisów przez AI (ChatGPT) zgodnie z preferencjami użytkownika
- Zapisywanie, przeglądanie i usuwanie przepisów
- Wyszukiwanie zapisanych przepisów
- System oceny przepisów (LIKE/DISLIKE)

MVP zostanie zrealizowany w ciągu 6 tygodni jako aplikacja webowa.

## 2. Problem użytkownika

Dostosowywanie dostępnych w sieci przepisów kulinarnych do osobistych potrzeb i wymagań żywieniowych jest problematyczne dla wielu osób. Użytkownicy z różnymi ograniczeniami dietetycznymi, alergiami czy nietolerancjami często muszą samodzielnie modyfikować znalezione przepisy, co wymaga specjalistycznej wiedzy i doświadczenia kulinarnego.

HealthyMeal rozwiązuje ten problem poprzez:
- Automatyzację procesu modyfikacji przepisów z wykorzystaniem AI
- Zapisywanie preferencji żywieniowych w jednym miejscu
- Dostosowywanie przepisów do indywidualnych wymagań bez konieczności manualnych zmian
- Zapewnienie informacji o wartościach odżywczych dostosowanych przepisów

Grupa docelowa obejmuje każdego, kto chce zadbać o swoje zdrowie i zdrowo się odżywiać, ze szczególnym uwzględnieniem osób z ograniczeniami dietetycznymi.

## 3. Wymagania funkcjonalne

### 3.1. System kont użytkowników
- Rejestracja i logowanie przez OAuth (Facebook, Apple, Microsoft)
- Zbieranie podstawowych danych: email, imię, wiek, płeć
- Brak weryfikacji adresu email w MVP
- Możliwość edycji danych profilu

### 3.2. Profil użytkownika
- Zapisywanie preferencji żywieniowych jako pola tekstowe
- Kategorie preferencji: nietolerancje, alergie i ograniczenia dietetyczne
- Edycja wprowadzonych preferencji
- Konieczność wypełnienia preferencji dla dostosowania przepisów

### 3.3. Wyszukiwanie i pobieranie przepisów
- Wyszukiwanie przepisów za pomocą integracji z wyszukiwarką Google
- Automatyczne pobieranie znalezionych przepisów
- Wyświetlanie informacji o źródle przepisu i autorze

### 3.4. Modyfikacja przepisów
- Automatyczna adaptacja przepisów przez AI zgodnie z preferencjami użytkownika
- Informacja w przypadku braku możliwości dostosowania przepisu
- Wyświetlanie wartości odżywczych z oryginalnego przepisu oraz po modyfikacji
- Disclaimer o konieczności konsultacji z dietetykiem

### 3.5. Zarządzanie przepisami
- Zapisywanie przepisów (limit 1000 na użytkownika)
- Przeglądanie zapisanych przepisów jako płaska lista
- Sortowanie przepisów (najnowsze, alfabetycznie)
- Usuwanie zapisanych przepisów
- Wyszukiwanie przepisów po nazwie potrawy oraz składnikach

### 3.6. System oceny przepisów
- Prosty mechanizm LIKE/DISLIKE pod przepisami
- Brak dodatkowych pól na komentarze w MVP

## 4. Granice produktu

Poniższe funkcje NIE są częścią MVP:

- Import przepisów z adresu URL
- Bogata obsługa multimediów (np. zdjęć przepisów)
- Udostępnianie przepisów dla innych użytkowników
- Funkcje społecznościowe
- Mechanizm odzyskiwania hasła
- System kategoryzacji i tagowania przepisów
- Weryfikacja adresu email przy rejestracji
- Limit zapytań do API OpenAI dla użytkownika
- Mechanizm "fallback" w przypadku awarii integracji z AI
- Strategia promocji aplikacji
- Możliwość dodawania własnych przepisów
- Porównanie oryginalnego przepisu ze zmodyfikowanym
- Przeglądanie historii modyfikowanych przepisów

## 5. Historyjki użytkowników

### US-001: Rejestracja użytkownika
**Tytuł:** Rejestracja konta użytkownika przez OAuth
**Opis:** Jako nowy użytkownik, chcę zarejestrować się w aplikacji za pomocą istniejącego konta (Facebook, Apple, Microsoft), aby szybko uzyskać dostęp do funkcji aplikacji.
**Kryteria akceptacji:**
- Użytkownik może wybrać jedną z opcji logowania: Facebook, Apple, Microsoft
- Aplikacja pobiera podstawowe dane: email, imię
- Użytkownik zostaje przekierowany do strony głównej po udanej rejestracji
- Użytkownik otrzymuje powiadomienie o udanej rejestracji
- System tworzy nowy profil użytkownika z pustymi preferencjami żywieniowymi

### US-002: Logowanie użytkownika
**Tytuł:** Logowanie do aplikacji przez OAuth
**Opis:** Jako zarejestrowany użytkownik, chcę zalogować się do aplikacji za pomocą mojego konta OAuth, aby uzyskać dostęp do moich zapisanych przepisów i preferencji.
**Kryteria akceptacji:**
- Użytkownik może wybrać jedną z opcji logowania: Facebook, Apple, Microsoft
- System weryfikuje tożsamość użytkownika przez wybranego dostawcę OAuth
- Po udanej weryfikacji użytkownik zostaje przekierowany do strony głównej
- System przywraca sesję użytkownika z jego preferencjami i zapisanymi przepisami

### US-003: Wypełnianie profilu preferencji żywieniowych
**Tytuł:** Wprowadzanie preferencji żywieniowych
**Opis:** Jako użytkownik, chcę wprowadzić moje preferencje żywieniowe, aby otrzymywać przepisy dostosowane do moich potrzeb.
**Kryteria akceptacji:**
- Użytkownik może dodać dowolną liczbę wpisów tekstowych dla nietolerancji
- Użytkownik może dodać dowolną liczbę wpisów tekstowych dla alergii
- Użytkownik może dodać dowolną liczbę wpisów tekstowych dla ograniczeń dietetycznych
- System zapisuje wprowadzone preferencje w profilu użytkownika
- Użytkownik może edytować i usuwać wprowadzone preferencje

### US-004: Edycja profilu
**Tytuł:** Aktualizacja danych profilowych
**Opis:** Jako użytkownik, chcę mieć możliwość edycji moich danych osobowych i preferencji żywieniowych, aby utrzymać je aktualne.
**Kryteria akceptacji:**
- Użytkownik może edytować dane: imię, wiek, płeć
- Użytkownik może dodawać, edytować i usuwać preferencje żywieniowe
- System zapisuje zaktualizowane dane
- Użytkownik otrzymuje potwierdzenie udanej aktualizacji

### US-005: Wyszukiwanie przepisów online
**Tytuł:** Wyszukiwanie przepisów w internecie
**Opis:** Jako użytkownik, chcę wyszukać przepisy w internecie, aby znaleźć interesujące mnie potrawy.
**Kryteria akceptacji:**
- Użytkownik może wprowadzić frazy wyszukiwania
- System prezentuje listę wyników wyszukiwania z internetu
- Dla każdego wyniku wyświetlane są podstawowe informacje o przepisie
- Wyniki zawierają odnośnik do oryginalnego źródła przepisu

### US-006: Adaptacja przepisu przez AI
**Tytuł:** Dostosowanie przepisu do preferencji żywieniowych
**Opis:** Jako użytkownik, chcę aby system automatycznie dostosował wybrany przepis do moich preferencji żywieniowych, aby uniknąć samodzielnych modyfikacji.
**Kryteria akceptacji:**
- System analizuje preferencje użytkownika i oryginalny przepis
- System modyfikuje przepis zgodnie z preferencjami użytkownika
- Zmodyfikowany przepis zawiera wszystkie niezbędne informacje (składniki, kroki, czas, wartości odżywcze)
- System wyświetla informację, jeśli przepis nie może być dostosowany
- Zmodyfikowany przepis zawiera disclaimer o konsultacji z dietetykiem

### US-007: Zapisywanie przepisu
**Tytuł:** Zapisanie przepisu w kolekcji użytkownika
**Opis:** Jako użytkownik, chcę zapisać przepis, aby mieć do niego dostęp w przyszłości.
**Kryteria akceptacji:**
- Użytkownik może zapisać przepis za pomocą jednego kliknięcia
- System dodaje przepis do kolekcji użytkownika
- System informuje o udanym zapisaniu przepisu
- System weryfikuje, czy nie przekroczono limitu 1000 przepisów
- Zapisane przepisy zawierają informację o źródle

### US-008: Przeglądanie zapisanych przepisów
**Tytuł:** Wyświetlanie kolekcji zapisanych przepisów
**Opis:** Jako użytkownik, chcę przeglądać moje zapisane przepisy, aby znaleźć interesujący mnie przepis.
**Kryteria akceptacji:**
- System wyświetla płaską listę wszystkich zapisanych przepisów
- Użytkownik może sortować listę (najnowsze, alfabetycznie)
- Dla każdego przepisu wyświetlane są podstawowe informacje (nazwa, główne składniki)
- Użytkownik może wejść w szczegóły dowolnego przepisu

### US-009: Wyszukiwanie w zapisanych przepisach
**Tytuł:** Wyszukiwanie wśród zapisanych przepisów
**Opis:** Jako użytkownik, chcę przeszukiwać moje zapisane przepisy po nazwie potrawy i składnikach, aby szybko znaleźć interesujący mnie przepis.
**Kryteria akceptacji:**
- Użytkownik może wprowadzić tekst wyszukiwania
- System przeszukuje zapisane przepisy po nazwie potrawy
- System przeszukuje zapisane przepisy po składnikach
- System wyświetla pasujące wyniki
- System informuje, gdy nie znaleziono pasujących przepisów

### US-010: Usuwanie przepisu
**Tytuł:** Usunięcie przepisu z kolekcji
**Opis:** Jako użytkownik, chcę móc usunąć przepis z mojej kolekcji, aby zarządzać moimi zapisanymi przepisami.
**Kryteria akceptacji:**
- Użytkownik może usunąć przepis za pomocą jednego kliknięcia
- System wyświetla prośbę o potwierdzenie usunięcia
- Po potwierdzeniu przepis jest usuwany z kolekcji użytkownika
- System informuje o udanym usunięciu przepisu

### US-011: Ocenianie przepisu
**Tytuł:** Ocena przepisu przez LIKE/DISLIKE
**Opis:** Jako użytkownik, chcę wyrazić swoją opinię o przepisie, aby zapamiętać które przepisy mi odpowiadają.
**Kryteria akceptacji:**
- Użytkownik może kliknąć przycisk LIKE dla przepisu
- Użytkownik może kliknąć przycisk DISLIKE dla przepisu
- System zapisuje ocenę użytkownika
- Użytkownik może zmienić swoją ocenę
- System wyświetla aktualną ocenę użytkownika

### US-012: Wyświetlanie szczegółów przepisu
**Tytuł:** Przeglądanie szczegółów przepisu
**Opis:** Jako użytkownik, chcę zobaczyć wszystkie szczegóły przepisu, aby móc go przygotować.
**Kryteria akceptacji:**
- System wyświetla pełną nazwę przepisu
- System wyświetla listę składników z ilościami
- System wyświetla kroki przygotowania
- System wyświetla czas przygotowania
- System wyświetla wartości odżywcze jako listę punktową
- System wyświetla informację o źródle przepisu i autorze
- System wyświetla disclaimer o konsultacji z dietetykiem

## 6. Metryki sukcesu

### 6.1. Kluczowe wskaźniki wydajności (KPI)
- 90% użytkowników posiada wypełnioną sekcję preferencji żywieniowych w swoim profilu
- 75% użytkowników generuje jeden lub więcej przepisów w tygodniu

### 6.2. Metody zbierania danych
- System LIKE/DISLIKE jako podstawowe źródło feedbacku