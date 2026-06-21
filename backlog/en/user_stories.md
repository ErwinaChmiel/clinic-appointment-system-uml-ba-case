# Backlog — user stories

## Epic: Appointment booking

| ID | User story | Priority |
|---|---|---|
| US-01 | As a patient, I want to search for a specialist so that I can find the right service. | Must |
| US-02 | As a patient, I want to view available slots so that I can choose a convenient appointment time. | Must |
| US-03 | As a patient, I want to pay the required prepayment so that I can confirm the appointment. | Must |
| US-04 | As a patient, I want to receive a confirmation so that I know the appointment has been booked. | Must |
| US-05 | As reception staff, I want to manage the schedule so that availability stays up to date. | Should |

## Acceptance criteria — US-03

- Given the service requires prepayment, when the patient selects a slot, then the system redirects the patient to payment.
- Given payment is successful, when the system receives confirmation, then the appointment status becomes `Confirmed`.
- Given payment fails, when the system receives rejection, then the slot is released.
