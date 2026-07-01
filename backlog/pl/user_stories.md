# Backlog — user stories

## Epic: Rezerwacja wizyty

| ID | User story | Priorytet |
|---|---|---|
| US-01 | Jako pacjent chcę wyszukać lekarza, aby znaleźć właściwą usługę. | Must |
| US-02 | Jako pacjent chcę zobaczyć dostępne terminy, aby wybrać dogodny czas wizyty. | Must |
| US-03 | Jako pacjent chcę opłacić wymaganą przedpłatę online, aby potwierdzić wizytę. | Must |
| US-04 | Jako pacjent chcę otrzymać potwierdzenie, aby mieć pewność, że wizyta została zarezerwowana. | Must |
| US-05 | Jako pracownik recepcji chcę zarządzać harmonogramem lekarzy, aby utrzymywać aktualną dostępność terminów. | Should |
| US-06 | Jako pacjent chcę anulować wizytę, aby zwolnić termin, jeśli nie mogę pojawić się na wizycie. | Should |
| US-07 | Jako pacjent chcę zmienić termin wizyty, aby dostosować rezerwację do mojej dostępności. | Should |
| US-08 | Jako administrator chcę zarządzać użytkownikami, aby utrzymywać aktualne dane i uprawnienia w systemie. | Could |

## Acceptance criteria — US-03

```gherkin
Scenario: Przekierowanie do płatności dla wizyty wymagającej przedpłaty
Given wybrana usługa wymaga przedpłaty
When pacjent potwierdzi wybór terminu
Then system tworzy tymczasową rezerwację terminu
And system przekierowuje pacjenta do płatności online

Scenario: Udana płatność
Given pacjent został przekierowany do płatności online
When płatność zakończy się sukcesem
Then system zmienia status wizyty na "Potwierdzona"
And system wysyła potwierdzenie wizyty do pacjenta

Scenario: Nieudana płatność
Given pacjent został przekierowany do płatności online
When płatność zostanie odrzucona
Then system zwalnia tymczasowo zablokowany termin
And system wyświetla pacjentowi informację o błędzie płatności


