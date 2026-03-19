## What QR Security Means

QR security means designing QR-based workflows so that a scanned code cannot be easily guessed, copied, reused, or abused to perform unauthorized actions.

## Why It Matters in Mojakey

Mojakey may use QR-based workflows for check-in, check-out, or identity-related actions. Because these actions can affect child safety, attendance accuracy, and operational trust, QR flows must be protected against forgery, replay, and unauthorized use.

## Security Considerations

- QR codes should not be simple static identifiers.
- QR tokens should expire after a limited time.
- Every QR scan should be validated by the backend before the action is allowed.
- Reuse or replay of the same QR token should be blocked where appropriate.
- QR-based actions should be recorded in audit logs.
- Sensitive actions may require additional verification beyond a QR scan alone.

## Risks if QR Flows Are Weak

If QR flows are weak, an attacker or unauthorized user could copy a code, replay an old code, or trigger a sensitive action without proper authorization. In Mojakey, this could lead to invalid attendance events, unauthorized check-out activity, and loss of trust in the platform.
