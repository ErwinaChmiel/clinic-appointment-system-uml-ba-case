# Ryzyka i założenia

## Ryzyka

| ID | Ryzyko | Wpływ | Mitygacja |
|---|---|---|---|
| RSK-01 | Niedostępność bramki płatności | Brak możliwości potwierdzenia usług z przedpłatą | Mechanizm ponowienia i czytelny komunikat błędu |
| RSK-02 | Podwójna rezerwacja terminu | Konflikt w grafiku | Blokada transakcyjna terminu |
| RSK-03 | Nieaktualna dostępność lekarza | Błędne terminy dla pacjenta | Synchronizacja grafiku i walidacja przed potwierdzeniem |
| RSK-04 | Niedostarczenie SMS/e-mail | Pacjent nie otrzyma potwierdzenia | Kolejka ponowień i log zdarzeń |

## Założenia

- Pacjent ma dostęp do Internetu i adresu e-mail lub telefonu.
- Placówka posiada zdefiniowane usługi i grafiki lekarzy.
- Bramka płatności zwraca jednoznaczny status transakcji.
- Powiadomienia są wysyłane przez zewnętrznego dostawcę.
