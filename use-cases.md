# Przypadki użycia — Osobisty Organizer

Dokument opisuje główne przypadki użycia aplikacji **Osobisty Organizer — Todo App** z perspektywy użytkownika.

---

## UC_01 — Rejestracja użytkownika

**Aktor:** niezalogowany użytkownik

**Opis:**  
Przypadek użycia umożliwia utworzenie konta użytkownika w aplikacji na podstawie imienia, adresu e-mail i hasła.

**Warunki wstępne:**  
Użytkownik nie jest zalogowany w aplikacji.

**Scenariusz podstawowy:**

1. Użytkownik otwiera aplikację.
2. Użytkownik przechodzi do formularza rejestracji.
3. Użytkownik wprowadza imię, adres e-mail i hasło.
4. Użytkownik zatwierdza formularz.
5. Aplikacja sprawdza poprawność wprowadzonych danych.
6. Aplikacja zapisuje dane użytkownika lokalnie.
7. Aplikacja przekierowuje użytkownika do strony logowania.

**Scenariusze alternatywne:**

**A1. Brak imienia:**  
Aplikacja wyświetla komunikat „Wpisz imię”.

**A2. Brak adresu e-mail:**  
Aplikacja wyświetla komunikat „Wpisz email”.

**A3. Hasło krótsze niż 4 znaki:**  
Aplikacja wyświetla komunikat „Hasło jest za krótkie”.

**A4. Niepoprawny format adresu e-mail:**  
Formularz blokuje wysłanie danych.

**Warunki końcowe:**  
Konto użytkownika zostaje utworzone, a użytkownik może przejść do logowania.

---

## UC_02 — Logowanie użytkownika

**Aktor:** zarejestrowany użytkownik

**Opis:**  
Przypadek użycia umożliwia zalogowanie użytkownika do aplikacji na podstawie danych zapisanych lokalnie w przeglądarce.

**Warunki wstępne:**  
Użytkownik posiada konto utworzone w aplikacji.

**Scenariusz podstawowy:**

1. Użytkownik otwiera formularz logowania.
2. Użytkownik wprowadza adres e-mail i hasło.
3. Użytkownik zatwierdza formularz.
4. Aplikacja weryfikuje dane logowania.
5. Aplikacja loguje użytkownika.
6. Aplikacja wyświetla stronę główną.

**Scenariusze alternatywne:**

**A1. Brak zapisanego konta:**  
Aplikacja wyświetla komunikat „Brak konta”.

**A2. Niepoprawne dane logowania:**  
Aplikacja wyświetla komunikat „Niepoprawne dane”.

**Warunki końcowe:**  
Użytkownik zostaje zalogowany do aplikacji i ma dostęp do jej funkcji.

---

## UC_03 — Dodanie zadania

**Aktor:** zalogowany użytkownik

**Opis:**  
Przypadek użycia umożliwia dodanie nowego zadania do osobistej listy zadań użytkownika.

**Warunki wstępne:**  
Użytkownik jest zalogowany w aplikacji.

**Scenariusz podstawowy:**

1. Użytkownik przechodzi do formularza dodawania zadania.
2. Użytkownik wprowadza treść zadania.
3. Użytkownik wybiera kategorię zadania.
4. Użytkownik opcjonalnie ustawia termin wykonania zadania.
5. Użytkownik klika przycisk „Dodaj”.
6. Aplikacja zapisuje zadanie.
7. Aplikacja wyświetla komunikat „Zadanie zostało dodane.”.

**Scenariusze alternatywne:**

**A1. Brak treści zadania:**  
Aplikacja nie dodaje zadania i wyświetla komunikat „Wpisz treść zadania.”.

**A2. Brak ustawionego terminu:**  
Aplikacja dodaje zadanie bez daty wykonania.

**A3. Brak zmiany kategorii:**  
Aplikacja dodaje zadanie z domyślną kategorią „Dom”.

**Warunki końcowe:**  
Nowe zadanie zostaje dodane do listy zadań użytkownika.

---

## UC_04 — Filtrowanie zadań

**Aktor:** zalogowany użytkownik

**Opis:**  
Przypadek użycia umożliwia wyświetlenie zadań należących do wybranej kategorii.

**Warunki wstępne:**  
Użytkownik jest zalogowany i znajduje się na liście zadań.

**Scenariusz podstawowy:**

1. Użytkownik przechodzi do listy zadań.
2. Użytkownik wybiera kategorię z filtra.
3. Aplikacja filtruje zadania według wybranej kategorii.
4. Aplikacja wyświetla zadania pasujące do wybranej kategorii.

**Warunki końcowe:**  
Użytkownik widzi zadania należące do wybranej kategorii.

---

## UC_05 — Oznaczenie zadania jako wykonane

**Aktor:** zalogowany użytkownik

**Opis:**  
Przypadek użycia umożliwia zmianę statusu zadania na wykonane.

**Warunki wstępne:**  
Użytkownik jest zalogowany i ma co najmniej jedno zadanie na liście.

**Scenariusz podstawowy:**

1. Użytkownik przechodzi do listy zadań.
2. Użytkownik wybiera zadanie.
3. Użytkownik oznacza zadanie jako wykonane.
4. Aplikacja aktualizuje status zadania.

**Warunki końcowe:**  
Zadanie zostaje oznaczone jako wykonane.

---

## UC_06 — Usunięcie zadania

**Aktor:** zalogowany użytkownik

**Opis:**  
Przypadek użycia umożliwia usunięcie zadania z listy zadań użytkownika.

**Warunki wstępne:**  
Użytkownik jest zalogowany i ma co najmniej jedno zadanie na liście.

**Scenariusz podstawowy:**

1. Użytkownik przechodzi do listy zadań.
2. Użytkownik wybiera zadanie do usunięcia.
3. Użytkownik klika opcję usunięcia zadania.
4. Aplikacja usuwa zadanie z listy.

**Warunki końcowe:**  
Zadanie nie jest już widoczne na liście zadań użytkownika.