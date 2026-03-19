## Current Assumptions

- Mojakey is a multi-tenant platform used by multiple institutions.
- A family account may manage one or more children.
- Parents or guardians use the family app to manage profiles, enrollments, and payments.
- Institution staff and administrators use a separate operational interface.
- Some workflows may use QR-based verification for check-in, check-out, or related actions.
- Higher-trust workflows may require identity verification in addition to email verification.
- Attendance and billing-related actions are important security and integrity events.

  # Open Questions

When should identity verification be required?

Which actions need step-up verification beyond normal login?

Should QR be used for check-in, check-out, or both?

How long should audit logs be retained?

What billing events must be immutable?

Which roles can override attendance or enrollment actions?
