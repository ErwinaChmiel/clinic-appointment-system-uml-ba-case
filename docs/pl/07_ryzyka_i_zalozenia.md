# Ryzyka i założenia

## Ryzyka

| ID | Ryzyko | Mitygacja |
|---|---|---|
| R-01 | Niedostępność bramki płatności może blokować rezerwacje wymagające przedpłaty. | Komunikat błędu, zwolnienie terminu i możliwość ponowienia procesu. |
| R-02 | Nieaktualny harmonogram specjalisty może prowadzić do błędnych rezerwacji. | Centralne zarządzanie dostępnością i walidacja przed potwierdzeniem. |
| R-03 | Pacjent może porzucić proces płatności. | Czasowa blokada terminu i automatyczne zwolnienie po wygaśnięciu sesji. |

## Założenia

- Dostawca płatności udostępnia API do autoryzacji transakcji.
- Placówka posiada aktualną listę specjalistów i usług.
- Powiadomienia są wysyłane przez e-mail lub SMS.
