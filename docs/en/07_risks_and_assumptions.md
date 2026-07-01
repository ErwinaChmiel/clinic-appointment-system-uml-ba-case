# Risks and Assumptions

## Risks

| ID | Risk | Mitigation |
|---|---|---|
| R-01 | Payment gateway unavailability may block the appointment booking process. | Display an error message, release the appointment slot and allow the patient to retry the payment process. |
| R-02 | An outdated specialist schedule may lead to incorrect bookings. | Use centralized availability management and validate the slot before creating a temporary reservation. |
| R-03 | The patient may abandon the payment process. | Temporarily hold the appointment slot and automatically release it after the payment session expires. |
| R-04 | An e-mail or SMS notification may not be delivered. | Track the notification delivery status and allow the notification to be resent. |

## Assumptions

- The payment provider exposes an API for transaction authorization.
- Each appointment booking requires online prepayment before appointment confirmation.
- The medical facility maintains an up-to-date list of specialists and services.
- Specialists’ schedules are maintained in the system as a single source of truth.
- Notifications are sent by e-mail or SMS.
- A temporary appointment slot reservation expires automatically if the payment is not completed within the defined time.
