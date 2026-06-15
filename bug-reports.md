# Zgłoszenia błędów i obserwacje — Osobisty Organizer

Dokument zawiera zgłoszenia błędów oraz obserwacje wykryte podczas analizy i testowania aplikacji **Osobisty Organizer — Todo App**.

---

## BUG_01 — Niezalogowany użytkownik ma dostęp do formularza dodawania zadania

**Priorytet:** wysoki  
**Środowisko:** Google Chrome, macOS, MacBook  
**Obszar:** Dodawanie zadania / autoryzacja

### Kroki do odtworzenia

1. Upewnić się, że użytkownik nie jest zalogowany.
2. Przejść bezpośrednio do strony dodawania zadania.
3. Wpisać treść zadania.
4. Kliknąć przycisk „Dodaj”.

### Rezultat aktualny

Niezalogowany użytkownik może otworzyć formularz dodawania zadania. Dopiero po kliknięciu przycisku „Dodaj” aplikacja wyświetla alert „Musisz być zalogowana”.

### Rezultat oczekiwany

Niezalogowany użytkownik nie powinien mieć dostępu do formularza dodawania zadania. Aplikacja powinna przekierować użytkownika do strony logowania przed wyświetleniem formularza.

### Dane testowe

Treść zadania: Test  
Kategoria: Dom  
Termin: pusty

### Propozycja poprawy

Dodać sprawdzenie statusu zalogowania przy wejściu na stronę dodawania zadania i przekierowywać niezalogowanego użytkownika do `/login`.

---

## BUG_02 — Możliwość dodania zadania z terminem w przeszłości

**Priorytet:** średni  
**Środowisko:** Google Chrome, macOS, MacBook  
**Obszar:** Termin zadania / dodawanie zadania

### Kroki do odtworzenia

1. Zalogować się do aplikacji.
2. Przejść do formularza dodawania zadania.
3. Wpisać treść zadania.
4. Wybrać kategorię.
5. Ustawić termin wykonania na datę wcześniejszą niż aktualna.
6. Kliknąć przycisk „Dodaj”.
7. Przejść do listy zadań.

### Rezultat aktualny

Aplikacja pozwala dodać zadanie z terminem w przeszłości. Zadanie zostaje zapisane i jest widoczne na liście zadań.

### Rezultat oczekiwany

Aplikacja nie powinna pozwalać na dodanie zadania z terminem w przeszłości albo powinna wyraźnie oznaczać takie zadanie jako zaległe.

### Dane testowe

Treść zadania: Kupić zanętę  
Kategoria: Hobby  
Termin: 2026-01-10

### Propozycja poprawy

Dodać ograniczenie minimalnej daty w polu wyboru terminu, np. ustawić minimalną datę na aktualny dzień, albo dodać oznaczenie zadań po terminie jako „zaległe”.

---

## OBS_01 — Rejestracja kolejnego użytkownika nadpisuje poprzednie konto

**Typ:** sugestia ulepszenia  
**Priorytet:** średni  
**Obszar:** Rejestracja / localStorage

### Opis

Aplikacja zapisuje dane użytkownika w `localStorage` pod jednym kluczem `user`. Rejestracja kolejnego użytkownika powoduje nadpisanie wcześniej zapisanego konta.

### Rezultat aktualny

Po zarejestrowaniu kolejnego użytkownika poprzednie konto nie jest już dostępne.

### Rezultat oczekiwany

Aplikacja mogłaby obsługiwać wielu użytkowników albo informować, że obsługiwane jest tylko jedno konto lokalne.

### Propozycja

Zapisywać użytkowników jako tablicę obiektów w `localStorage` albo dodać komunikat informujący o ograniczeniu aplikacji do jednego konta lokalnego.

---

## OBS_02 — Brak potwierdzenia przed usunięciem zadania

**Typ:** sugestia UX  
**Priorytet:** niski/średni  
**Obszar:** Usuwanie zadania

### Opis

Zadanie jest usuwane od razu po kliknięciu przycisku usunięcia, bez dodatkowego potwierdzenia.

### Rezultat aktualny

Użytkownik może przypadkowo usunąć zadanie bez możliwości potwierdzenia decyzji.

### Rezultat oczekiwany

Aplikacja mogłaby wyświetlać komunikat potwierdzający usunięcie zadania.

### Propozycja

Dodać okno potwierdzenia, np. „Czy na pewno chcesz usunąć to zadanie?”.

---

## OBS_03 — Minimalne wymagania dotyczące hasła są bardzo niskie

**Typ:** sugestia bezpieczeństwa / UX  
**Priorytet:** niski/średni  
**Obszar:** Rejestracja

### Opis

Aplikacja wymaga hasła o długości minimum 4 znaków, ale nie sprawdza jego złożoności.

### Rezultat aktualny

Użytkownik może utworzyć konto z bardzo prostym hasłem.

### Rezultat oczekiwany

Aplikacja mogłaby wymagać dłuższego hasła lub informować użytkownika o zaleceniach dotyczących bezpieczeństwa.

### Propozycja

Zwiększyć minimalną długość hasła, np. do 8 znaków, albo dodać informację o zalecanych wymaganiach dotyczących hasła.