# Risks and assumptions

## Risks

| ID | Risk | Impact | Mitigation |
|---|---|---|---|
| RSK-01 | Payment gateway unavailable | Services requiring prepayment cannot be confirmed | Retry mechanism and clear error message |
| RSK-02 | Double booking of a slot | Schedule conflict | Transactional slot lock |
| RSK-03 | Outdated doctor availability | Incorrect slots displayed to patients | Schedule synchronization and validation before confirmation |
| RSK-04 | SMS/e-mail not delivered | Patient may not receive confirmation | Retry queue and event log |

## Assumptions

- The patient has internet access and an e-mail address or phone number.
- The clinic has defined services and doctor schedules.
- The payment gateway returns a clear transaction status.
- Notifications are sent through an external provider.
