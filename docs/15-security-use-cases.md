## Parent Account Creation

**Goal**  
Allow a parent or guardian to create a family account securely.

**Actors**  
Parent or guardian, authentication service, backend API

**Security Checks**  
- The user must provide required account information.
- Email ownership must be verified through an email verification flow.
- The system should validate the registration request before the account becomes active.
- Higher-trust workflows may later require identity verification.

**Result**  
A verified family account is created and can be used to manage child profiles, enrollments, and related actions.

## Child Enrollment

**Goal**  
Allow a parent or guardian to enroll one or more children into an institution program.

**Actors**  
Parent or guardian, family app, backend API, enrollment service

**Security Checks**  
- The user must be authenticated before starting enrollment.
- The system must confirm that the parent or guardian is acting within the correct family account.
- Enrollment actions must be tied to the correct institution and tenant context.
- Sensitive enrollment changes should be recorded in audit logs.

**Result**  
The selected child is enrolled in the correct program, and the enrollment action is stored as a trusted system event.

## Staff Check-In

**Goal**  
Allow authorized institution staff to check a student into the correct program safely and accurately.

**Actors**  
Institution staff, admin portal, backend API, attendance service

**Security Checks**  
- The staff member must be authenticated.
- The system must verify that the staff member has permission to perform check-in actions.
- The action must be limited to the correct institution and program context.
- The attendance event should be recorded in audit logs.

**Result**  
A valid check-in event is created for the correct student, program, and institution.

## QR-Based Check-Out

**Goal**  
Allow a child check-out or related workflow to be completed through a secure QR-based process.

**Actors**  
Parent or guardian, staff member, QR validation service, backend API

**Security Checks**  
- The QR token must be validated by the backend.
- The token should be time-bound and protected against replay or reuse.
- The system must verify that the action is being performed by an authorized user.
- The check-out action should be recorded in audit logs.

**Result**  
A trusted check-out event is created only if the QR workflow passes validation and authorization checks.

## Attendance Dispute Review

**Goal**  
Allow an institution administrator or authorized reviewer to investigate a disputed attendance event.

**Actors**  
Institution administrator, backend API, audit logging service, attendance records

**Security Checks**  
- The reviewer must be authenticated and authorized for dispute review.
- Access must remain limited to the correct institution and tenant context.
- The system should provide trusted event history, timestamps, and actor details from audit logs.
- Any corrective action should also be recorded in audit logs.

**Result**  
The disputed attendance event can be reviewed using reliable system records, and any approved correction is traceable.

## Admin Role Change

**Goal**  
Allow an authorized administrator to change a user’s role in a controlled way.

**Actors**  
Institution administrator or platform super admin, backend API, role management service

**Security Checks**  
- The administrator must be authenticated and authorized to manage roles.
- Role changes must be limited to the correct tenant scope unless platform-level authority is required.
- High-privilege role assignments should be tightly restricted.
- Every role or permission change must be recorded in audit logs.

**Result**  
The user’s role is updated in a controlled and traceable manner without granting unauthorized access.
