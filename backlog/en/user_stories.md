# Backlog — User Stories

## Epic: Appointment Booking

| ID | User story | Priority |
|---|---|---|
| US-01 | As a patient, I want to search for a doctor so that I can find the right medical service. | Must |
| US-02 | As a patient, I want to view available appointment slots so that I can choose a convenient appointment time. | Must |
| US-03 | As a patient, I want to pay the required online prepayment so that I can confirm my appointment. | Must |
| US-04 | As a patient, I want to receive an appointment confirmation so that I can be sure my appointment has been booked. | Must |
| US-05 | As a receptionist, I want to manage doctors’ schedules so that appointment availability remains up to date. | Should |
| US-06 | As a patient, I want to cancel an appointment so that the slot can be released if I cannot attend. | Should |
| US-07 | As a patient, I want to change my appointment slot so that I can adjust the booking to my availability. | Should |
| US-08 | As an administrator, I want to manage users so that user data and permissions remain up to date. | Could |

## Acceptance Criteria — US-03

```gherkin
Scenario: Redirect to payment after selecting an appointment slot
Given the patient has selected an available appointment slot
When the patient confirms the selected slot
Then the system creates a temporary slot reservation
And the appointment receives the status "Pending payment"
And the system redirects the patient to online payment

Scenario: Successful payment
Given the patient has been redirected to online payment
When the payment is completed successfully
Then the system changes the appointment status to "Confirmed"
And the system sends an appointment confirmation to the patient

Scenario: Failed payment
Given the patient has been redirected to online payment
When the payment is declined
Then the system releases the temporarily reserved slot
And the system displays a payment error message to the patient
