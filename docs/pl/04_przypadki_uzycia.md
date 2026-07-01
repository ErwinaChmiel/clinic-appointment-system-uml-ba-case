## UC-01 — Zarezerwuj wizytę

| Pole | Opis |
|---|---|
| Aktor główny | Pacjent |
| Cel | Zarezerwowanie wizyty u wybranego specjalisty. |
| Warunki wstępne | Pacjent ma dostęp do systemu rezerwacji. |
| Warunki końcowe | Wizyta ma status Potwierdzona albo termin zostaje zwolniony. |

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

## UC-02 — Anuluj wizytę

Pacjent lub personel anuluje wizytę zgodnie z regułami anulowania. System aktualizuje status i wysyła powiadomienie.

## UC-03 — Zarządzaj harmonogramem

Administrator lub recepcja aktualizuje dostępność lekarzy i blokady terminów.
