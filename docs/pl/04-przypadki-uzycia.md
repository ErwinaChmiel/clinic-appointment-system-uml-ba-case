# Przypadki użycia

## UC-01: Rezerwacja wizyty

| Pole | Opis |
|---|---|
| Aktor główny | Pacjent |
| Cel | Zarezerwowanie wizyty medycznej online |
| Warunek początkowy | Pacjent wybrał usługę i widzi dostępne terminy |
| Warunek końcowy | Wizyta jest potwierdzona lub termin zostaje zwolniony |

### Scenariusz główny

1. Pacjent wybiera termin.
2. System tymczasowo rezerwuje termin.
3. System sprawdza, czy wymagana jest przedpłata.
4. Jeżeli przedpłata nie jest wymagana, system potwierdza wizytę.
5. Jeżeli przedpłata jest wymagana, system przekierowuje proces do bramki płatności.
6. Po skutecznej płatności system potwierdza wizytę.
7. System wysyła potwierdzenie do pacjenta.

### Scenariusze alternatywne

| ID | Sytuacja | Reakcja systemu |
|---|---|---|
| A1 | Płatność nie powiodła się | System zwalnia termin i pokazuje błąd |
| A2 | Termin został zajęty | System prosi o wybór innego terminu |
| A3 | Pacjent przekroczył czas rezerwacji | System zwalnia termin |
