# Ryzyka i założenia

## Ryzyka

| ID | Ryzyko | Mitygacja |
|---|---|---|
| R-01 | Niedostępność bramki płatności może blokować proces rezerwacji wizyt. | Komunikat błędu, zwolnienie terminu i możliwość ponowienia procesu płatności. |
| R-02 | Nieaktualny harmonogram specjalisty może prowadzić do błędnych rezerwacji. | Centralne zarządzanie dostępnością i walidacja terminu przed utworzeniem tymczasowej rezerwacji. |
| R-03 | Pacjent może porzucić proces płatności. | Czasowa blokada terminu i automatyczne zwolnienie po wygaśnięciu sesji płatności. |
| R-04 | Powiadomienie e-mail lub SMS może nie zostać dostarczone. | Rejestrowanie statusu wysyłki powiadomienia oraz możliwość ponowienia wysyłki. |

## Założenia

- Dostawca płatności udostępnia API do autoryzacji transakcji.
- Każda rezerwacja wizyty wymaga przedpłaty online przed potwierdzeniem wizyty.
- Placówka posiada aktualną listę specjalistów i usług.
- Harmonogramy specjalistów są utrzymywane w systemie jako jedno źródło prawdy.
- Powiadomienia są wysyłane przez e-mail lub SMS.
- Tymczasowa rezerwacja terminu wygasa automatycznie, jeśli płatność nie zostanie zakończona w określonym czasie.
