# Requirements

## Business requirements

| ID | Requirement |
|---|---|
| BRQ-01 | The patient can search available slots online. |
| BRQ-02 | The system holds the slot during the booking process. |
| BRQ-03 | The system supports prepayment for services that require it. |
| BRQ-04 | The patient receives confirmation after a successful booking. |
| BRQ-05 | Reception staff can manage appointments and exceptions. |

## Functional requirements

| ID | Requirement |
|---|---|
| FR-01 | The system displays available slots by doctor, service and date. |
| FR-02 | The system temporarily reserves a slot during booking finalization. |
| FR-03 | The system checks whether the selected service requires prepayment. |
| FR-04 | The system sends payment authorization to the payment gateway. |
| FR-05 | The system confirms the appointment after successful completion of the process. |
| FR-06 | The system releases the slot after failed payment or timeout. |
| FR-07 | The system sends an SMS/e-mail notification. |

## Non-functional requirements

| ID | Requirement |
|---|---|
| NFR-01 | Available slot search response time should not exceed 2 seconds. |
| NFR-02 | Patient data must be processed according to the data minimization principle. |
| NFR-03 | Booking operations must prevent double booking of a slot. |
| NFR-04 | Critical operations should be recorded in audit logs. |
