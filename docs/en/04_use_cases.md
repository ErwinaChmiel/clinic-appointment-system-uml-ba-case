# Use Cases

## UC-01 — Book Appointment

| Field | Description |
|---|---|
| Primary actor | Patient |
| Goal | Book an appointment with a selected specialist. |
| Preconditions | The patient has access to the booking system. |
| Postconditions | The appointment has the status “Confirmed” or the appointment slot is released. |

### Main scenario

1. The patient selects a specialization or specialist.
2. The system displays available appointment slots.
3. The patient selects an appointment slot.
4. The system temporarily reserves the selected slot.
5. The system redirects the patient to online payment.
6. The patient completes the payment.
7. After successful payment authorization, the system confirms the appointment.
8. The system sends an appointment confirmation message.

### Alternative scenarios

- A1: Payment fails — the system releases the selected slot and displays a payment error.
- A2: The selected slot is no longer available — the system asks the patient to choose another slot.
- A3: The patient abandons the process — the system releases the temporarily reserved slot after the reservation timeout.

---

## UC-02 — Cancel Appointment

| Field | Description |
|---|---|
| Primary actor | Patient or staff |
| Goal | Cancel a scheduled appointment. |
| Preconditions | The appointment exists in the system and can be cancelled according to business rules. |
| Postconditions | The appointment has the status “Cancelled” and the patient receives a notification. |

### Main scenario

1. The patient or staff member selects an appointment to cancel.
2. The system checks whether cancellation is allowed according to business rules.
3. The system changes the appointment status to “Cancelled”.
4. The system releases the appointment slot in the schedule.
5. The system sends an appointment cancellation notification.

### Alternative scenarios

- A1: The appointment cannot be cancelled — the system informs the user that cancellation is not allowed.
- A2: The appointment does not exist or has already been cancelled — the system displays an appropriate message.

---

## UC-03 — Manage Schedule

| Field | Description |
|---|---|
| Primary actor | Administrator or receptionist |
| Goal | Update doctors’ availability and appointment slot blocks. |
| Preconditions | The user has the required permissions to manage schedules. |
| Postconditions | The doctor’s schedule is updated. |

### Main scenario

1. The administrator or receptionist selects a doctor.
2. The system displays the doctor’s current schedule.
3. The user adds, changes or blocks available appointment slots.
4. The system saves the schedule changes.
5. Updated slots become visible in the appointment booking process.

### Alternative scenarios

- A1: The selected slot conflicts with an existing appointment — the system blocks the update and displays a message.
- A2: The user does not have the required permissions — the system denies access to schedule editing.
