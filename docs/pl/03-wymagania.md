# Wymagania

## Wymagania biznesowe

| ID | Wymaganie |
|---|---|
| BRQ-01 | Pacjent może samodzielnie wyszukać dostępne terminy. |
| BRQ-02 | System blokuje termin podczas procesu rezerwacji. |
| BRQ-03 | System obsługuje przedpłatę dla usług, które jej wymagają. |
| BRQ-04 | Pacjent otrzymuje potwierdzenie po skutecznej rezerwacji. |
| BRQ-05 | Recepcja może zarządzać wizytami i wyjątkami. |

## Wymagania funkcjonalne

| ID | Wymaganie |
|---|---|
| FR-01 | System prezentuje dostępne terminy według lekarza, usługi i daty. |
| FR-02 | System tymczasowo rezerwuje termin na czas finalizacji procesu. |
| FR-03 | System sprawdza, czy dana usługa wymaga przedpłaty. |
| FR-04 | System przekazuje płatność do bramki płatności. |
| FR-05 | System potwierdza wizytę po pozytywnym zakończeniu procesu. |
| FR-06 | System zwalnia termin po nieudanej płatności lub przekroczeniu czasu. |
| FR-07 | System wysyła powiadomienie SMS/e-mail. |

## Wymagania niefunkcjonalne

| ID | Wymaganie |
|---|---|
| NFR-01 | Czas odpowiedzi listy terminów nie powinien przekraczać 2 sekund. |
| NFR-02 | Dane pacjenta muszą być przetwarzane zgodnie z zasadą minimalizacji. |
| NFR-03 | Operacje rezerwacji muszą zapobiegać podwójnej rezerwacji terminu. |
| NFR-04 | System powinien rejestrować zdarzenia krytyczne w logach audytowych. |
