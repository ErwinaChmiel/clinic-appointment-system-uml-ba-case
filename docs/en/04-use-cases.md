# Use cases

## UC-01: Book appointment

| Field | Description |
|---|---|
| Primary actor | Patient |
| Goal | Book a medical appointment online |
| Precondition | The patient selected a service and can see available slots |
| Postcondition | The appointment is confirmed or the slot is released |

### Main scenario

1. The patient selects a slot.
2. The system temporarily reserves the slot.
3. The system checks whether prepayment is required.
4. If prepayment is not required, the system confirms the appointment.
5. If prepayment is required, the system starts payment authorization.
6. After successful payment, the system confirms the appointment.
7. The system sends confirmation to the patient.

### Alternative scenarios

| ID | Situation | System response |
|---|---|---|
| A1 | Payment fails | The system releases the slot and shows an error |
| A2 | Slot is no longer available | The system asks the patient to select another slot |
| A3 | Reservation timeout is reached | The system releases the slot |
