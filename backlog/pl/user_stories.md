# Backlog — user stories

## Epic: Rezerwacja wizyty

| ID | User story | Priorytet |
|---|---|---|
| US-01 | Jako pacjent chcę wyszukać lekarza, aby znaleźć właściwą usługę. | Must |
| US-02 | Jako pacjent chcę zobaczyć dostępne terminy, aby wybrać dogodny czas wizyty. | Must |
| US-03 | Jako pacjent chcę opłacić wymaganą przedpłatę, aby potwierdzić wizytę. | Must |
| US-04 | Jako pacjent chcę otrzymać potwierdzenie, aby mieć pewność, że wizyta została zarezerwowana. | Must |
| US-05 | Jako recepcja chcę zarządzać harmonogramem, aby utrzymywać aktualną dostępność. | Should |

## Acceptance criteria — US-03

- Given usługa wymaga przedpłaty, when pacjent wybiera termin, then system kieruje do płatności.
- Given płatność zakończyła się sukcesem, when system otrzyma potwierdzenie, then wizyta otrzymuje status `Potwierdzona`.
- Given płatność nie powiodła się, when system otrzyma odmowę, then termin zostaje zwolniony.
