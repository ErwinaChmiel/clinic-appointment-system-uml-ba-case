# Przypadki użycia

## UC-01 — Zarezerwuj wizytę

| Pole | Opis |
|---|---|
| Aktor główny | Pacjent |
| Cel | Zarezerwowanie wizyty u wybranego specjalisty. |
| Warunki wstępne | Pacjent ma dostęp do systemu rezerwacji. |
| Warunki końcowe | Wizyta ma status „Potwierdzona” albo termin zostaje zwolniony. |

### Główny scenariusz

1. Pacjent wybiera specjalizację lub specjalistę.
2. System prezentuje dostępne terminy.
3. Pacjent wybiera termin.
4. System tymczasowo rezerwuje termin.
5. System przekierowuje pacjenta do płatności online.
6. Pacjent dokonuje płatności.
7. Po pozytywnej autoryzacji płatności system potwierdza wizytę.
8. System wysyła wiadomość z potwierdzeniem.

### Scenariusze alternatywne

- A1: Płatność nie powiodła się — system zwalnia termin i pokazuje błąd płatności.
- A2: Termin został zajęty — system prosi o wybór innego terminu.
- A3: Pacjent przerywa proces — system zwalnia tymczasowo zablokowany termin po upływie czasu rezerwacji.

---

## UC-02 — Anuluj wizytę

| Pole | Opis |
|---|---|
| Aktor główny | Pacjent lub personel |
| Cel | Anulowanie zaplanowanej wizyty. |
| Warunki wstępne | Wizyta istnieje w systemie i może zostać anulowana zgodnie z regułami biznesowymi. |
| Warunki końcowe | Wizyta ma status „Anulowana”, a pacjent otrzymuje powiadomienie. |

### Główny scenariusz

1. Pacjent lub personel wybiera wizytę do anulowania.
2. System sprawdza, czy anulowanie jest zgodne z regułami biznesowymi.
3. System zmienia status wizyty na „Anulowana”.
4. System zwalnia termin w harmonogramie.
5. System wysyła powiadomienie o anulowaniu wizyty.

### Scenariusze alternatywne

- A1: Wizyta nie może zostać anulowana — system informuje użytkownika o braku możliwości anulowania.
- A2: Wizyta nie istnieje lub została już anulowana — system pokazuje odpowiedni komunikat.

---

## UC-03 — Zarządzaj harmonogramem

| Pole | Opis |
|---|---|
| Aktor główny | Administrator lub pracownik recepcji |
| Cel | Aktualizacja dostępności lekarzy i blokad terminów. |
| Warunki wstępne | Użytkownik ma odpowiednie uprawnienia do zarządzania harmonogramem. |
| Warunki końcowe | Harmonogram lekarza zostaje zaktualizowany. |

### Główny scenariusz

1. Administrator lub pracownik recepcji wybiera lekarza.
2. System wyświetla aktualny harmonogram lekarza.
3. Użytkownik dodaje, zmienia lub blokuje dostępne terminy.
4. System zapisuje zmiany w harmonogramie.
5. Zaktualizowane terminy są widoczne w procesie rezerwacji wizyty.

### Scenariusze alternatywne

- A1: Wybrany termin koliduje z istniejącą wizytą — system blokuje zapis i pokazuje komunikat.
- A2: Użytkownik nie ma wymaganych uprawnień — system odmawia dostępu do edycji harmonogramu.
