# Przypadki użycia

## UC-01 — Zarezerwuj wizytę

| Pole | Opis |
|---|---|
| Aktor główny | Pacjent |
| Cel | Zarezerwowanie wizyty u wybranego specjalisty. |
| Warunki wstępne | Pacjent ma dostęp do systemu rezerwacji. |
| Warunki końcowe | Wizyta ma status `Potwierdzona` albo termin zostaje zwolniony. |

### Główny scenariusz

1. Pacjent wybiera specjalizację lub specjalistę.
2. System prezentuje dostępne terminy.
3. Pacjent wybiera termin.
4. System tymczasowo rezerwuje termin.
5. System sprawdza, czy wymagana jest przedpłata.
6. Jeśli przedpłata nie jest wymagana, system potwierdza wizytę.
7. Jeśli przedpłata jest wymagana, system przekierowuje do płatności.
8. Po pozytywnej autoryzacji system potwierdza wizytę.
9. System wysyła wiadomość z potwierdzeniem.

### Scenariusze alternatywne

- A1: płatność nie powiodła się — system zwalnia termin i pokazuje błąd.
- A2: termin został zajęty — system prosi o wybór innego terminu.
- A3: pacjent przerywa proces — system zwalnia tymczasowo zablokowany termin.

## UC-02 — Anuluj wizytę

Pacjent lub personel anuluje wizytę zgodnie z regułami anulowania. System aktualizuje status i wysyła powiadomienie.

## UC-03 — Zarządzaj harmonogramem

Administrator lub recepcja aktualizuje dostępność specjalistów i blokady terminów.
