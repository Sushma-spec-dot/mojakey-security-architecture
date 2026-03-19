## System Overview

Mojakey is a family-focused platform that allows parents or guardians to create an account, manage family and child profiles, enroll one or more children into after-school programs, and handle related payments in one place.

The platform may support multiple institutions and multiple activities, such as chess, soccer, and table tennis. A single family account may manage one child or multiple children across different programs.

During account creation, the platform verifies ownership of the email address through an email verification flow. For higher-trust workflows, the system may also support identity verification using a government-issued ID, such as a driver’s license or state ID. These controls help reduce fraudulent account creation and improve trust in enrollment, attendance, and child pickup workflows.

## Main Components

- Family web or mobile application
- Authentication and account verification service
- Parent and child profile management service
- Enrollment and program management service
- Payment and billing service
- Identity verification service
- Backend API and application logic
- Database and secure storage
- Audit logging service
- Institution admin portal

## Basic Request Flow

1. A parent uses the Mojakey family app to create an account or sign in.
2. The authentication service verifies the user through login credentials and email verification.
3. If required for higher-trust workflows, the user completes identity verification through a secure verification process.
4. The parent uses the app to create or manage child profiles, enroll in programs, and make payments.
5. The family app sends requests to the backend API.
6. The backend validates the user session, role, and tenant context before allowing access to the requested action.
7. The appropriate service processes the request, such as profile management, enrollment, attendance, QR validation, or billing.
8. The system stores approved changes in the database.
9. Important actions such as login, enrollment, payment updates, check-in, and check-out are recorded in the audit logging service.
10. The result is returned to the family app or institution admin portal.

## Security Relevance

This architecture handles sensitive parent and child data, enrollment actions, attendance records, and payment-related events. Because these workflows affect child safety, privacy, and billing accuracy, the system must enforce strong authentication, role-based access control, tenant isolation, secure verification, and audit logging.

The architecture should be designed so that only authorized users can perform sensitive actions, institutions cannot access each other’s data, and important events can be traced later during disputes or security investigations.

## Key Enforcement Points

- Authentication: users must sign in through a secure login flow.
- Email verification: parent or guardian email ownership must be confirmed during account creation.
- Identity verification: higher-trust actions may require verified identity through approved verification workflows.
- RBAC: parents, staff, coaches, and admins should only access actions allowed by their role.
- Tenant isolation: each institution must be restricted to its own data, users, and operational records.
- QR validation: QR-based actions must be validated by the backend and protected against reuse or forgery.
- Audit logging: sensitive actions must be recorded for traceability and investigation.
- Event integrity: attendance, enrollment, and billing-related events must be protected from tampering or duplication.
