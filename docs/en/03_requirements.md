# Requirements

## Business Requirements

| ID | Requirement |
|---|---|
| BRQ-01 | The system should allow the patient to book an appointment online independently. |
| BRQ-02 | The system should reduce the number of manual confirmations handled by the reception desk. |
| BRQ-03 | The system should require online prepayment before appointment confirmation. |
| BRQ-04 | The system should provide a clear and unambiguous status for every appointment. |

## Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | The patient can search for a specialist by specialization. |
| FR-02 | The patient can view available appointment slots for a selected specialist. |
| FR-03 | The system temporarily holds the selected appointment slot during the booking process. |
| FR-04 | The system creates a temporary slot reservation before the payment process starts. |
| FR-05 | The system redirects the patient to the payment gateway to complete the online prepayment. |
| FR-06 | The system confirms the appointment after successful payment authorization. |
| FR-07 | The system sends an appointment confirmation message. |
| FR-08 | The patient can cancel an appointment according to business rules. |
| FR-09 | The patient can change the appointment slot according to slot availability. |
| FR-10 | The administrator can manage system users. |
| FR-11 | The receptionist or administrator can manage doctors’ schedules. |

## Non-functional Requirements

| ID | Requirement |
|---|---|
| NFR-01 | The appointment booking process should be possible to complete in less than 3 minutes. |
| NFR-02 | The system should be available at least 99.5% of the time per month. |
| NFR-03 | Patient data should be protected according to privacy and security requirements. |
| NFR-04 | The interface should be responsive and available on mobile devices. |
