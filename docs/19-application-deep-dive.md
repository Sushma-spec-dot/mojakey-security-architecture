## Request Handling Flow

- A parent, guardian, staff member, coach, or administrator interacts with the Mojakey client application or admin portal.
- The client sends the request to the backend API.
- The backend validates the session and confirms the user identity and role context.
- The backend checks tenant scope and request permissions before routing the action.
- The appropriate service processes the request, such as profile management, enrollment, attendance, QR validation, or billing.
- Approved changes are written to storage and important actions are recorded in audit logs.
- The result is returned to the requesting client.

  ## Authentication and Session Handling

- Protected workflows require the user to authenticate before accessing the platform.
- Account creation should include email verification to confirm parent or guardian ownership of the account.
- Higher-trust workflows may require additional identity verification.
- The backend should validate the active session before allowing sensitive actions.
- Session handling should reduce the risk of unauthorized reuse or misuse of authenticated access.

  ## Authorization and Tenant Checks

- The backend must evaluate the user’s role before allowing protected actions.
- Access should be limited by both role and tenant context.
- Parents or guardians should only access their own family and child records.
- Institution staff and administrators should only access records within their own institution scope.
- Platform-level actions should be more tightly restricted than normal tenant actions.

  ## Service Responsibilities

- The profile management service handles parent, guardian, and child profile workflows.
- The enrollment service handles institution program enrollment and related updates.
- The attendance service handles check-in and check-out workflows.
- The QR validation service verifies QR-based actions before sensitive workflows are completed.
- The billing service handles payment-related workflows and billing-impacting events.
- The audit logging service records important administrative and operational actions for later review.

## Write-Path Controls

- Sensitive writes must be allowed only after authentication, authorization, and tenant checks succeed.
- Attendance, enrollment, and billing-related changes should be validated before being committed.
- The system should reduce the risk of duplicate, replayed, or unauthorized event creation.
- Important state changes should be recorded in audit logs.
- High-risk writes should remain traceable to actor, time, and tenant context.
