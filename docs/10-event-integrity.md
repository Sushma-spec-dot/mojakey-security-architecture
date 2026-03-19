## What Event Integrity Means

Event integrity means making sure important system events are accurate, trustworthy, and protected from unauthorized change. In Mojakey, this includes actions such as check-in, check-out, enrollment updates, and billing-related events. The system should be designed so these records cannot be easily duplicated, altered, replayed, or created by an unauthorized user.

## Why It Matters in Mojakey

Mojakey handles child attendance, enrollment actions, and payment-related workflows. If these events are incorrect or tampered with, the platform could produce billing disputes, inaccurate attendance history, operational confusion, or even safety-related issues around child pickup and tracking.

## Integrity Protections

- Prevent duplicate check-in or check-out events.
- Prevent unauthorized users from creating or changing attendance events.
- Validate the actor, time, and context of each sensitive action.
- Protect enrollment and billing-related records from tampering.
- Record sensitive event changes in audit logs for later review.

## Risks if Integrity Is Weak

If event integrity is weak, the platform may allow duplicate attendance events, unauthorized check-outs, altered billing records, or inaccurate operational history. This can reduce trust in the system and make disputes or investigations much harder to resolve.
