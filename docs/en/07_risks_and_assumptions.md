# Risks and assumptions

## Risks

| ID | Risk | Mitigation |
|---|---|---|
| R-01 | Payment gateway unavailability may block bookings requiring prepayment. | Show error message, release the slot and allow retry. |
| R-02 | Outdated specialist schedule may cause invalid bookings. | Central schedule management and validation before confirmation. |
| R-03 | The patient may abandon the payment process. | Temporary slot lock and automatic release after session expiry. |

## Assumptions

- The payment provider exposes an API for transaction authorization.
- The clinic has an up-to-date list of specialists and services.
- Notifications are sent via e-mail or SMS.
