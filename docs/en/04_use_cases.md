# Use cases

## UC-01 — Book appointment

| Field | Description |
|---|---|
| Primary actor | Patient |
| Goal | Book an appointment with a selected specialist. |
| Preconditions | The patient has access to the booking system. |
| Postconditions | The appointment is `Confirmed` or the slot is released. |

### Main scenario

1. The patient selects a specialization or specialist.
2. The system displays available slots.
3. The patient selects a slot.
4. The system temporarily reserves the slot.
5. The system checks whether prepayment is required.
6. If prepayment is not required, the system confirms the appointment.
7. If prepayment is required, the system redirects to payment.
8. After successful authorization, the system confirms the appointment.
9. The system sends a confirmation message.

### Alternative scenarios

- A1: payment fails — the system releases the slot and shows an error.
- A2: the slot is no longer available — the system asks the patient to choose another slot.
- A3: the patient abandons the process — the system releases the temporarily locked slot.

## UC-02 — Cancel appointment

The patient or staff member cancels an appointment according to cancellation rules. The system updates the status and sends a notification.

## UC-03 — Manage schedule

The administrator or reception staff updates specialist availability and slot blocks.
